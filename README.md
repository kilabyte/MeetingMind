# Meeting Mind

<p align="center">
  <img src="icon_256.png" width="128" height="128" alt="Meeting Mind icon">
</p>

<p align="center">
  <a href="https://apps.apple.com/app/id6751551175"><img src="https://img.shields.io/badge/Mac%20App%20Store-Download-blue?style=flat" alt="Download on the Mac App Store"/></a>
  <img src="https://img.shields.io/badge/macOS-26%2B-orange?style=flat" alt="Requires macOS 26 or later"/>
  <img src="https://img.shields.io/badge/MCP-local%20server-6f42c1?style=flat" alt="Local MCP server"/>
  <a href="https://meetingmind.kilabyte.io"><img src="https://img.shields.io/badge/website-meetingmind.kilabyte.io-green?style=flat" alt="Website"/></a>
</p>

**Private AI meeting notes for Mac. No bot joins the call.**

Meeting Mind is a Mac menu bar app that records your Zoom, Microsoft Teams, Google Meet and Webex calls straight
from your Mac, transcribes them on your Mac, and writes a Markdown summary with decisions and action items. It also
ships a **local MCP server**, so Claude, Cursor and other MCP clients on the same Mac can read the meeting you're in.

> This repository holds documentation and the public issue tracker. Meeting Mind is a closed-source app distributed
> through the Mac App Store; its source code lives in a private repository.

- **Download:** [Mac App Store](https://apps.apple.com/app/id6751551175)
- **Website:** [meetingmind.kilabyte.io](https://meetingmind.kilabyte.io)
- **Bugs and feature requests:** [Issues](https://github.com/kilabyte/meetingmind/issues)

> **Recording disclosure:** Always tell everyone in a meeting before you record it. You are responsible for getting
> consent and following the recording laws that apply to you and the other participants.

---

## Contents

- [Why Meeting Mind](#why-meeting-mind)
- [Free vs Unlimited](#free-vs-unlimited)
- [MCP server](#mcp-server)
  - [Turn it on](#1-turn-it-on)
  - [Connect a client (Streamable HTTP)](#2a-connect-a-client-streamable-http)
  - [Connect a client (stdio)](#2b-connect-a-client-stdio)
  - [Tools](#tools)
  - [Security model](#security-model)
  - [Troubleshooting](#mcp-troubleshooting)
- [Features](#features)
- [Requirements](#requirements)
- [Choosing your AI](#choosing-your-ai)
- [FAQ](#faq)
- [Reporting issues](#reporting-issues)
- [Privacy](#privacy)
- [License](#license)

---

## Why Meeting Mind

- **No bot joins the call.** Meeting Mind records your microphone and your Mac's system audio. Nothing joins the
  meeting, nobody sees a "notetaker has joined" message, and there's no virtual audio driver to install.
- **Your audio stays on your Mac.** Transcription runs on your Mac. Recordings are saved to a folder you choose and
  are never uploaded.
- **You choose the AI.** Summaries and chat use a local model through Ollama or LM Studio, so the whole meeting can
  stay offline, or your own OpenAI, Anthropic or OpenRouter API key if you prefer a cloud model.
- **Your meetings, in any AI.** The built-in MCP server lets MCP clients on the same Mac read the live transcript,
  the meeting in progress and your Meeting Mind AI chat. It only listens on 127.0.0.1 and needs a token.
- **No subscription.** Free for 2 hours of recording a day. Unlimited is a one-time in-app purchase.

## Free vs Unlimited

| | Free | Unlimited (one-time in-app purchase) |
|---|:---:|:---:|
| Recording time | 2 hours a day | No daily limit |
| Live on-device transcription | ✓ | ✓ |
| AI summaries (decisions, action items) | ✓ | ✓ |
| AI chat during the call | ✓ | ✓ |
| **MCP server for your AI tools** | ✓ | ✓ |
| Automatic Zoom, Teams and Google Meet detection | ✓ | ✓ |
| History, and chat with past meetings | | ✓ |
| Meeting titles from your calendar, plus Webex and other calendar meeting links | | ✓ |
| Auto-export to Obsidian or Notion (rules by meeting title) | | ✓ |
| Live insights (commitments, urgent tasks, open questions, decisions) | | ✓ |
| Family Sharing | | ✓ |

Unlimited is not a subscription. See the Mac App Store for the price in your region.

---

## MCP server

Meeting Mind includes a [Model Context Protocol](https://modelcontextprotocol.io) server that runs **inside the
Meeting Mind app on your Mac**. There's nothing to install from npm, PyPI or Docker: if Meeting Mind is installed
and running, the server is there. It's included on the free tier.

What it gives an MCP client: the **live** meeting. That's the recording status (elapsed time, meeting name,
participant names), the live transcript exactly as shown in Meeting Mind's AI chat window, and the questions and
replies in that chat. Past meetings are not exposed over MCP. All four tools are read-only.

### 1. Turn it on

1. Install [Meeting Mind](https://apps.apple.com/app/id6751551175) and open it (it lives in the menu bar).
2. Open **Settings > MCP**.
3. Turn on **Enable MCP server**. The server is off by default.
4. Pick a **Transport**: **Streamable HTTP** or **stdio**.
5. Optional: change the **Port** (default `47821`, any port from 1024 to 65535).
6. Click **Copy mcp.json** and paste it into your MCP client's config.

Settings > MCP also lets you show, copy or **regenerate the token**. After regenerating, HTTP clients need the new
token in their config.

### 2a. Connect a client (Streamable HTTP)

The app listens on `http://127.0.0.1:<port>/mcp` and requires the token as a Bearer header. This is the snippet
Settings > MCP generates (with your real port and token filled in):

```json
{
  "mcpServers": {
    "meetingmind": {
      "url": "http://127.0.0.1:47821/mcp",
      "headers": {
        "Authorization": "Bearer <token from Settings > MCP>"
      }
    }
  }
}
```

### 2b. Connect a client (stdio)

For clients that only launch local commands, the client starts the Meeting Mind binary with `--mcp-stdio`. That
process doesn't record anything: it forwards each message to the running Meeting Mind app over 127.0.0.1, and it
picks up the port and token from Meeting Mind itself, so **no token goes in your client config**.

```json
{
  "mcpServers": {
    "meetingmind": {
      "command": "<path shown in Settings > MCP>",
      "args": ["--mcp-stdio"]
    }
  }
}
```

Copy the exact `command` path from Settings > MCP. For the Mac App Store install it is normally
`/Applications/MeetingMind.app/Contents/MacOS/MeetingMind`.
<!-- TODO(Dave): confirm the path above matches what Settings > MCP shows on a fresh App Store install. -->

The Meeting Mind app must be running with the MCP server turned on. If it isn't, the stdio bridge answers with
"MeetingMind MCP server is off. Turn it on in Settings > MCP."

<!-- TODO(Dave): list the clients you've actually tested end to end (e.g. Claude Desktop, Claude Code, Cursor,
VS Code, Cline) and add the config-file location for each. The app's own hint text says "Paste this into Cursor,
Claude, or another MCP client on this Mac." Until confirmed, keep the wording generic. -->

### Tools

All tools are read-only (`readOnlyHint: true`, `destructiveHint: false`, `idempotentHint: true`,
`openWorldHint: false`).

| Tool | What it returns | Arguments |
|---|---|---|
| `meetingmind_get_app_info` | The running Meeting Mind version, build number and bundle identifier. | none |
| `meetingmind_get_recording_status` | Whether a meeting is recording, whether it's paused, the elapsed time, the meeting name and the participant names. | none |
| `meetingmind_get_live_transcript` | The live transcript shown in the AI chat window, verbatim, including speaker tags. | none |
| `meetingmind_get_chat_history` | The questions and replies in the AI chat window, in order, verbatim, each with a role, text and timestamp. | `limit` (optional, integer 1–500): return only the most recent messages |

Server details: name `MeetingMind`; MCP protocol versions `2025-06-18`, `2025-03-26` and `2024-11-05`. Tools only, with
no resources or prompts.

**Example prompts once connected**

- "What have we decided so far in this meeting?"
- "Who's on this call, and how long has it been running?"
- "Draft a follow-up email from the live transcript."
- "What did I ask Meeting Mind's chat earlier in this call?"

### Security model

- **Loopback only.** The listener only accepts connections over the Mac's loopback interface, so other machines on
  your network can't reach it. Requests must be addressed to `127.0.0.1`, `localhost` or `[::1]` (other Host headers
  are refused), and web pages from any other origin are rejected, which blocks DNS-rebinding tricks.
- **Token required.** Every HTTP request must send `Authorization: Bearer <token>`. The token is a random 256-bit
  value generated on your Mac and checked in constant time. Regenerate it any time in Settings > MCP.
- **Read-only.** No tool can start, stop, delete or change anything.
- **Off by default.** Nothing listens until you turn on the MCP server.
- **Your MCP client decides where the data goes.** Meeting Mind only hands the transcript to the client you
  connect. If that client sends it to a cloud model, that's governed by the client's settings, not Meeting Mind's.

### MCP troubleshooting

- **"Unauthorized":** the token in your client config doesn't match. Copy it again from Settings > MCP (it changes
  if you regenerate it).
- **Connection refused:** Meeting Mind isn't running, the MCP server is off, or the port in your config differs from
  the one in Settings > MCP.
- **Empty transcript:** start a recording with live transcription on. The tool returns the same text as the
  transcript panel in the AI chat window.
- **Port already in use:** pick another port in Settings > MCP and copy the new mcp.json.

---

## Features

- No bot in the call: records your mic and your Mac's system audio, no virtual audio driver.
- Starts on its own for Zoom, Microsoft Teams and Google Meet. You can also start a recording yourself for any other
  call app. (Webex and other meeting links in your calendar are picked up with **Unlimited**.)
- Live transcript as you talk, with your name and the other person's.
- Custom vocabulary: add names and terms, plus how they're often misheard, and Meeting Mind keeps the right spelling.
- AI chat about the meeting in progress; add documents or screenshots for context.
- A Markdown note when the call ends: summary, decisions, action items and, if you want, the full transcript, with
  frontmatter and a speaker-labeled transcript.
- Reprocess a meeting with a different prompt or model.
- Drop any audio file (a podcast, lecture or interview) on the menu bar icon to transcribe and summarize it.
- Tag recordings.
- Local MCP server for your AI tools (free).
- **Unlimited:** History and search across past meetings, chat with past meetings, recordings named after the
  meeting in your calendar, live insights during the call, and auto-export to Obsidian or Notion with rules based on
  the meeting title.

## Requirements

- macOS 26 or later.
- Apple Silicon or Intel Mac.
  <!-- TODO(Dave): the 1.5.4 binary is universal (arm64 + x86_64). Confirm which transcription models Intel Macs
  get and whether any features are Apple Silicon only. -->
- Permissions: **Microphone** and **System Audio Recording**. **Accessibility** is recommended for automatic meeting
  detection. **Calendar** is optional (meeting titles, Unlimited). Meeting Mind never uses Screen Recording.
  <!-- TODO(Dave): add a RAM recommendation if you still want one; the old README said 8 GB minimum / 16 GB
  recommended, which I couldn't verify for 1.5.4. -->

## Choosing your AI

Transcription always runs on your Mac. For summaries and chat, pick one in **Settings > AI Services**:

**Local (fully offline)**

1. Install [Ollama](https://ollama.com) or [LM Studio](https://lmstudio.ai) and download a model.
2. Set the model's context length to at least 32,000 tokens. Meeting transcripts are long, and a smaller context can
   leave summaries blank. Meeting Mind checks the context length and warns you if it's too small.
3. In Meeting Mind, open Settings > AI Services and select the model.

**Cloud (your own key)**

Add your OpenAI, Anthropic or OpenRouter API key in Settings > AI Services. Your transcript is then sent to that
provider for summaries and chat; transcription itself still runs on your Mac. API keys are kept in the macOS Keychain.

## FAQ

**Does anything join my call?**
No. Meeting Mind records audio on your Mac. Other participants won't see a bot, so tell them you're recording.

**Why isn't my meeting being detected?**
Make sure the meeting window is open and that Accessibility access is granted. You can always start a recording
from the menu bar.

**Where are my recordings saved?**
By default in a "MeetingMind Recordings" folder on your Desktop, with transcripts and notes in "MeetingMind
Transcripts". You can change both in Settings.

**Do I need an internet connection?**
Not with a local model through Ollama or LM Studio. You only need internet for a cloud AI provider.

**Can MCP clients read my past meetings?**
No. The MCP server exposes the meeting in progress and the current AI chat only.

**Is the MCP server a paid feature?**
No, it's included on the free tier.

**Is Meeting Mind open source?**
No. This repository contains documentation and the issue tracker; the app is distributed through the Mac App Store.

## Reporting issues

1. Search the [existing issues](https://github.com/kilabyte/meetingmind/issues) first.
2. Click **New issue** and choose **Bug report**, **Feature request** or **Question**.
3. For bugs, include your macOS version, your Meeting Mind version (Settings > About), the meeting app you were
   using, what you did, and any error message.
4. For MCP problems, also include your MCP client and its version, the transport (Streamable HTTP or stdio), and
   the error the client shows. **Never paste your MCP token.**

## Privacy

Meeting Mind is built to keep meetings on your Mac. Audio is recorded and transcribed locally, and recordings and
notes are saved to folders you choose. Meeting content only leaves your Mac if you choose a cloud AI provider, export
to Notion, or connect an MCP client that sends data elsewhere.

Full details: [Privacy Policy](https://meetingmind.kilabyte.io/privacy) ·
[Terms of Service](https://meetingmind.kilabyte.io/terms) · [Support](https://meetingmind.kilabyte.io/support)

## License

Copyright © 2025–2026 Kilabyte IO. All rights reserved.

This repository contains documentation and issue tracking for a proprietary application. See [LICENSE](LICENSE).
