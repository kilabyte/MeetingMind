# MeetingMind - Issue Tracking & Documentation

> **Note**: This repository is for **issue tracking, documentation, and community support** only. The main codebase is maintained in a private repository.

[![Mac App Store](https://img.shields.io/badge/Download-Mac%20App%20Store-blue.svg)](https://apps.apple.com/app/meeting-mind/id6751551175)
[![Website](https://img.shields.io/badge/Website-meetingmind.kilabyte.io-orange.svg)](https://meetingmind.kilabyte.io)
[![Version](https://img.shields.io/badge/Version-1.3.5-green.svg)](#)

## About MeetingMind

MeetingMind is a macOS menu bar application that automatically detects and records online meetings (Zoom, Microsoft Teams, Google Meet, Webex) with AI-powered features. Built with Swift/SwiftUI for macOS 15.0+.

### Key Features

- **Automatic Meeting Detection**: Detects Zoom, Teams, Google Meet, and Webex meetings automatically
- **Smart Recording**: Records system audio, microphone, or both with live transcription
- **AI-Powered Processing**: Local WhisperKit transcription + AI summaries (Ollama, OpenRouter, or Apple Intelligence)
- **Drag-and-Drop Processing**: Drop audio files (M4A, WAV, MP3, AIFF, CAF, AAC) onto menu bar icon for instant transcription
- **Launch on Login**: Automatically start MeetingMind when you log into macOS
- **Enhanced Speaker Identification**: AI systematically tracks speakers with voice patterns and contextual attribution
- **Custom Vocabulary**: Add domain-specific terms, acronyms, and specialized vocabulary for improved accuracy
- **Calendar Integration**: Extracts meeting titles from your calendar automatically
- **AI Chat Interface**: Interactive chat with meeting context and document analysis
- **Privacy-First**: All data stored locally, optional cloud AI services, Apple Intelligence on-device processing
- **Mac App Store Available**: Full sandboxing support with security-scoped bookmarks

## Download

**[Download on the Mac App Store](https://apps.apple.com/app/meeting-mind/id6751551175)**

Free tier: 60 minutes of recording per day
Premium tier: Unlimited recording

## Purpose of This Repository

This GitHub repository serves as the **public-facing hub** for MeetingMind:

- 🐛 **Issue Tracking**: Report bugs, request features, and discuss improvements
- 📖 **Documentation**: User guides, API documentation, and technical references
- 💬 **Community Support**: Get help from maintainers and other users

The main codebase is developed and maintained in a private repository for security and intellectual property reasons.

## How to Report Issues

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
- **Disk Space**: ~500MB for app + WhisperKit models
- **Supported Meeting Platforms**: Zoom, Microsoft Teams, Google Meet, Webex

## Privacy

MeetingMind is privacy-first:

- All recordings stored locally on your Mac
- Local AI processing with WhisperKit (no cloud required)
- Optional cloud AI services (Ollama, OpenRouter) - user controlled
- No telemetry or analytics in the app
- Full macOS App Sandbox compliance

See our [Privacy Policy](https://meetingmind.kilabyte.io/privacy.html) for details.

## Technology Stack

- **Language**: Swift 5.9+
- **UI Framework**: SwiftUI
- **Audio**: ScreenCaptureKit, AVFoundation
- **Speech Recognition**: Apple Speech Framework
- **Local Transcription**: WhisperKit (custom models supported)
- **AI Services**: Ollama (local), OpenRouter (cloud), Apple Intelligence (on-device, macOS 26+)
- **Calendar**: EventKit
- **Distribution**: Mac App Store

## Recent Updates

### Version 1.3.5 (Current - October 2025)
- **Drag-and-Drop Audio Processing**: Drop audio files onto menu bar for instant transcription
- **Launch on Login**: Automatic app startup when logging into macOS
- **Apple Intelligence Integration**: Native on-device AI processing (macOS 26+) as automatic fallback
- **Enhanced Speaker Identification**: Systematic speaker tracking with voice patterns and contextual attribution
- **Custom Vocabulary System**: Add domain-specific terms for improved transcription accuracy
- **Custom WhisperKit Models**: Integrate HuggingFace models with real-time validation
- **Configurable Markdown Output**: Toggle transcript inclusion to save disk space

### Version 1.3.4 (October 2025)
- OpenAI-compatible AI architecture with dynamic model discovery
- Platform-agnostic tutorial language for cleaner UI
- Calendar integration improvements (15-minute meeting window)
- Bug reporting feature in Settings > About
- Enhanced purchase messaging

### Version 1.3.3 (October 2025)
- Multi-platform meeting detection (Teams, Google Meet, Webex added)
- Free tier extended to 60 minutes per day (from 30 minutes)
- What's New feature system
- Fixed QoS priority inversions in audio system

See [Release Notes](https://github.com/kilabyte/meetingmind/releases) for complete changelog.

## Contributing

We welcome contributions! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines on:

- Reporting issues
- Suggesting features
- Contributing documentation
- Code contributions (limited to public components)

## License

Copyright © 2025 Kilabyte IO. All rights reserved.

This repository contains documentation and issue tracking for a proprietary application. The documentation is provided for informational purposes. The application binary is distributed through the Mac App Store.

---

**[Download MeetingMind](https://apps.apple.com/app/meeting-mind/id6751551175)** | **[Visit Website](https://meetingmind.kilabyte.io)** | **[Report Issue](https://github.com/kilabyte/meetingmind/issues/new)**
