# MeetingMind - Issue Tracking & Documentation

> **Note**: This repository is for **issue tracking, documentation, and community support** only. The main codebase is maintained in a private repository.

[![Mac App Store](https://img.shields.io/badge/Download-Mac%20App%20Store-blue.svg)](https://apps.apple.com/app/meeting-mind/id6751551175)
[![Website](https://img.shields.io/badge/Website-meetingmind.kilabyte.io-orange.svg)](https://meetingmind.kilabyte.io)

## About MeetingMind

MeetingMind is a macOS menu bar application that automatically detects and records online meetings with AI-powered features. Built with Swift/SwiftUI for macOS 15.0+.

### Key Features

- **Calendar Integration with Clickable Links**: Join meetings instantly from menu bar - calendar events display meeting links that open directly in your browser or meeting app with visual hover feedback
- **Multi-Platform Meeting Detection**: Automatically detects Zoom, Teams, Google Meet, and Webex meetings with smart platform filtering
- **Smart Recording**: Records system audio, microphone, or both with live transcription and automatic meeting title extraction
- **AI-Powered Processing**: Local WhisperKit/Parakeet transcription + AI summaries (Ollama, OpenRouter, or Apple Intelligence)
- **Drag-and-Drop Processing**: Drop audio files (M4A, WAV, MP3, AIFF, CAF, AAC) onto menu bar icon for instant transcription
- **AI Chat Interface**: Interactive chat with meeting context, document analysis, and historical meeting search
- **Enhanced Speaker Identification**: AI systematically tracks speakers with voice patterns and contextual attribution
- **Custom Vocabulary**: Add domain-specific terms, acronyms, and specialized vocabulary for improved transcription accuracy
- **Privacy-First**: All data stored locally, optional cloud AI services, on-device Apple Intelligence processing
- **Launch on Login**: Automatically start MeetingMind when you log into macOS
- **Mac App Store Available**: Full sandboxing support with security-scoped bookmarks for cloud storage

## Download

**[Download on the Mac App Store](https://apps.apple.com/app/meeting-mind/id6751551175)**

- **Free tier**: 60 minutes of recording per day
- **Premium tier**: Unlimited recording

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
