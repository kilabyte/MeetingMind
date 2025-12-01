# MeetingMind - Issue Tracking & Documentation

> **Note**: This repository is for **issue tracking, documentation, and community support** only. The main codebase is maintained in a private repository.

[![Mac App Store](https://img.shields.io/badge/Download-Mac%20App%20Store-blue.svg)](https://apps.apple.com/app/meeting-mind/id6751551175)
[![Website](https://img.shields.io/badge/Website-meetingmind.kilabyte.io-orange.svg)](https://meetingmind.kilabyte.io)

## About MeetingMind

MeetingMind is a macOS menu bar application that automatically detects and records online meetings with AI-powered features. Built with Swift/SwiftUI for macOS 15.0+.

## Features

### Recording & Detection

- **Multi-Platform Meeting Detection**: Automatically detects Zoom, Teams, Google Meet, and Webex meetings with smart platform filtering and priority ordering
- **Smart Recording**: Record system audio, microphone, or both with automatic meeting title extraction from detected platforms
- **Live Transcription**: Real-time transcription during recording using WhisperKit or Parakeet on-device models
- **Drag-and-Drop Processing**: Drop audio files (M4A, WAV, MP3, AIFF, CAF, AAC) onto the menu bar icon for instant transcription

### AI-Powered Features

- **AI Summaries**: Generate meeting summaries using local AI (Ollama) or cloud providers (OpenRouter)
- **AI Chat Interface**: Interactive chat with full meeting context, document analysis, and historical meeting search
- **Enhanced Speaker Identification**: AI systematically tracks speakers with voice patterns and contextual attribution
- **Custom Vocabulary**: Add domain-specific terms, acronyms, and specialized vocabulary for improved transcription accuracy

### Real-time Insights

- **Live Insight Detection**: AI-powered detection of key moments during meetings as they happen
- **Built-in Categories**: Automatically detect commitments, tasks, questions, decisions, and urgent items
- **Custom Insight Categories**: Create your own categories with custom icons, colors, and detection criteria
- **Auto-Answer Questions**: In listener mode (system audio only), automatically generate suggested answers for questions from meeting participants
- **Sensitivity Control**: Adjust detection sensitivity from low to high based on your meeting style

### Export Integrations

- **Obsidian Integration**: Automatically export meeting notes to your Obsidian vault with rule-based folder routing
- **Notion Integration**: Export meeting notes directly to Notion pages via API with folder/database selection
- **Export Rules**: Create pattern-matching rules to route different meeting types to specific destinations (e.g., "Weekly Standup*" → Meetings/Standups)
- **Markdown with Frontmatter**: Exported notes include YAML frontmatter with tags, date, duration, and meeting metadata

### Organization & History

- **History Manager**: Full-featured window for browsing, searching, sorting, and managing all past recordings
- **Tag Management**: Create custom tags with colors and icons to organize recordings by project, client, or topic
- **Tag Filtering**: Filter recordings by tag in the History Manager for quick access
- **Search & Sort**: Search recordings by title and sort by date, title, or duration
- **Batch Operations**: Delete, reprocess, or export multiple recordings at once

### Calendar Integration

- **Clickable Meeting Links**: Join meetings instantly from the menu bar - calendar events display meeting links that open directly in your browser or meeting app
- **Visual Hover Feedback**: Meeting links highlight on hover for easy identification
- **Event Display**: See upcoming meetings in your menu bar with one-click join

### Privacy & Security

- **Privacy-First**: All recordings and data stored locally on your Mac
- **Local AI Processing**: WhisperKit and Parakeet models run entirely on-device - no cloud required
- **Optional Cloud AI**: OpenRouter and other cloud services are opt-in and user-controlled
- **Full Sandbox Compliance**: Mac App Store approved with security-scoped bookmarks for file access

### Additional Features

- **Launch on Login**: Automatically start MeetingMind when you log into macOS
- **Processing Status**: Real-time processing indicator with queue management
- **Multiple Storage Locations**: Save recordings to iCloud Drive, Dropbox, OneDrive, or any folder
- **Audio Format Support**: Works with M4A, WAV, MP3, AIFF, CAF, and AAC files
- **Manual Import**: Import existing audio files for transcription and processing

## Download

**[Download on the Mac App Store](https://apps.apple.com/app/meeting-mind/id6751551175)**

- **Free tier**: 45 minutes of recording per day
- **Premium tier**: Unlimited recording + Real-time Insights

## Purpose of This Repository

This GitHub repository serves as the **public-facing hub** for MeetingMind:

- 🐛 **Issue Tracking**: Report bugs, request features, and discuss improvements
- 📖 **Documentation**: User guides, API documentation, and technical references
- 💬 **Community Support**: Get help from maintainers and other users

The main codebase is developed and maintained in a private repository for security and intellectual property reasons.

## How to Contribute

### Bug Reports

Found a bug? Please [create an issue](https://github.com/kilabyte/meetingmind/issues/new?template=bug_report.md) with:

- Detailed description of the problem
- Steps to reproduce
- Expected vs actual behavior
- macOS version and MeetingMind version
- Relevant logs (if applicable)

### Feature Requests

Have an idea? Please [create an issue](https://github.com/kilabyte/meetingmind/issues/new?template=feature_request.md) with:

- Clear description of the feature
- Use case and benefits
- Any relevant examples or mockups

See [CONTRIBUTING.md](CONTRIBUTING.md) for detailed guidelines.

## Support

- **Issues**: [GitHub Issues](https://github.com/kilabyte/meetingmind/issues)
- **Support Form**: [Website Support](https://meetingmind.kilabyte.io/support.html)
- **Website**: [meetingmind.kilabyte.io](https://meetingmind.kilabyte.io)

## System Requirements

- **macOS**: 15.0 (Sequoia) or later
- **Permissions**: Microphone, Screen Recording (for system audio), Calendar (optional)
- **Disk Space**: ~100MB for app + WhisperKit/Parakeet models

## Privacy

MeetingMind is privacy-first:

- All recordings and data stored locally on your Mac
- Local AI processing with WhisperKit or Parakeet (no cloud required)
- Optional cloud AI services (OpenRouter) - user controlled
- Full macOS App Sandbox compliance

See our [Privacy Policy](https://meetingmind.kilabyte.io/privacy.html) for details.

## License

Copyright © 2025 Kilabyte IO. All rights reserved.

This repository contains documentation and issue tracking for a proprietary application. The documentation is provided for informational purposes. The application binary is distributed through the Mac App Store.

---

**[Download MeetingMind](https://apps.apple.com/app/meeting-mind/id6751551175)** | **[Visit Website](https://meetingmind.kilabyte.io)** | **[Report Issue](https://github.com/kilabyte/meetingmind/issues/new)**
