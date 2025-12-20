# MeetingMind

<p align="center">
  <img src="icon_256.png" width="128" height="128" alt="MeetingMind Icon">
</p>

<p align="center">
  <a href="https://apps.apple.com/app/meeting-mind/id6751551175"><img src="https://img.shields.io/badge/download-Mac%20App%20Store-blue?style=flat" alt="Download on Mac App Store"/></a>
  <img src="https://img.shields.io/badge/platform-macOS-lightgrey?style=flat" alt="Platform"/>
  <img src="https://img.shields.io/badge/requires-macOS%2015%2B-orange?style=flat" alt="Requirements"/>
  <a href="https://meetingmind-website.web.app"><img src="https://img.shields.io/badge/Website-meetingmind-green?style=flat" alt="Website"/></a>
</p>

MeetingMind is a menu bar app for macOS that automatically records your online meetings and creates AI-powered transcripts and summaries. It detects when you join a call and starts recording in the background. When the meeting ends, it transcribes the audio and generates a summary with action items.

Everything runs locally on your Mac for privacy. Your recordings and transcripts stay on your computer unless you choose to use cloud AI services.

> **Recording Disclaimer**: Always notify all meeting participants before recording. Many jurisdictions require consent from all parties before recording a conversation. You are responsible for complying with all applicable laws.

> This repository is for issue tracking and community support. The main codebase is maintained in a private repository.

## Download

**[Download from the Mac App Store](https://apps.apple.com/app/meeting-mind/id6751551175)**

The free version includes core features with a 45 minute daily recording limit. The one-time purchase unlocks all features and removes the recording limit.

## Features

- Automatically detects when you join an online meeting and starts recording.
- Records both your microphone and system audio so you capture both sides of the conversation.
- Shows live transcription while you're recording.
- Generates meeting summaries with key points and action items when the meeting ends.
- Automatically identifies and labels different speakers in the transcript.
- Detects commitments, decisions, questions, and urgent items in real-time during meetings.
- Generates instant AI answers when questions come up in the meeting.
- Lets you create custom insight categories for your specific needs like risks, blockers, or compliance mentions.
- Names files automatically based on your calendar events, with customizable filename formats.
- Handles overlapping calendar events by letting you pick which meeting to associate with the recording.
- Prompts you to name the recording when you stop, which is useful for ad-hoc meetings.
- Exports transcripts to Obsidian vaults or Notion databases with smart routing rules based on meeting names.
- Lets you tag recordings with custom colors and icons for easy filtering.
- Includes a History Manager where you can search, rename, and reprocess old recordings.
- Lets you drag and drop external audio files onto the menu bar icon to transcribe them.
- Supports custom vocabulary so the AI understands your company-specific terms and acronyms.
- Works with local AI using Ollama, or cloud providers like OpenRouter, OpenAI, and Anthropic.
- Uses Parakeet for transcription which is 10-100x faster than traditional Whisper models.
- Stores everything locally on your Mac unless you choose to use cloud services.
- Keeps your API keys secure in the macOS Keychain.
- Includes usage statistics showing how many meetings you've recorded and time saved.
- Launches automatically when you log in if you enable it in settings.

## Requirements

- macOS 15.0 (Sequoia) or later
- Apple Silicon or Intel Mac
- Microphone permission required
- Screen Recording permission required (for system audio)
- 8GB RAM minimum, 16GB recommended

## Setting Up Local AI

MeetingMind can use Ollama for local AI processing. This keeps everything on your Mac and works offline.

1. Download and install Ollama from [ollama.com](https://ollama.com)
2. Open Ollama and download a model like `gemma3:12b`
3. Go to Ollama settings and increase the context length to at least 32000. Without this, your meeting summaries will be blank because Ollama's default context is too small for meeting transcripts.
4. Open MeetingMind settings, go to AI Services, and select your model.

## Using Cloud AI

If you want access to more powerful models, MeetingMind also supports OpenRouter. This sends your transcripts to cloud AI services for processing, but gives you access to hundreds of models from OpenAI, Anthropic, Google, and others for higher quality summaries.

Sign up at [openrouter.ai](https://openrouter.ai), get an API key, and add it in MeetingMind settings under AI Services.

## Reporting Issues

If you run into a bug or have a feature request, please submit an issue:

1. Go to the [Issues page](https://github.com/kilabyte/meetingmind/issues)
2. Click "New Issue"
3. Choose "Bug Report" or "Feature Request"
4. Fill out the template with as much detail as possible
5. For bugs, include your macOS version, what you were doing when the issue occurred, and any error messages you saw

We read every issue and appreciate the feedback.

## FAQs

**Why isn't my meeting being detected?**

Make sure the meeting window is open and visible. MeetingMind looks for specific window titles to detect meetings. If auto-detection isn't working, you can always start recording manually from the menu bar.

**Where are my recordings saved?**

By default, recordings go to your Desktop in a "MeetingMind Recordings" folder. You can change this in Settings. Transcripts are saved separately in a "MeetingMind Transcripts" folder.

**Do I need an internet connection?**

Not if you're using local AI with Ollama. The app works completely offline. You only need internet if you configure cloud AI providers.

**My AI summaries aren't generating**

Make sure you have an AI service configured and running. If using Ollama, check that it's running and that you have a model installed. Also make sure the context length is set to at least 32000 in Ollama settings.

## Privacy

MeetingMind is designed with privacy in mind. All processing happens locally on your Mac by default. Your recordings, transcripts, and meeting content are stored only on your computer. If you choose to use cloud AI services, only the audio/text needed for processing is sent to those services.

See our [Privacy Policy](https://meetingmind-website.web.app/privacy.html) for full details.

## Support

- [Contact Form](https://meetingmind-website.web.app/support.html) for questions and help
- [Website](https://meetingmind-website.web.app) for more information

## License

Copyright 2025 Kilabyte IO. All rights reserved.

This repository contains documentation and issue tracking for a proprietary application. The application is distributed through the Mac App Store.
