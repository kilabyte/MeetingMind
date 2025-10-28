# MeetingMind - Issue Tracking & Documentation

> **Note**: This repository is for **issue tracking, documentation, and community support** only. The main codebase is maintained in a private repository.

[![Mac App Store](https://img.shields.io/badge/Download-Mac%20App%20Store-blue.svg)](https://apps.apple.com/app/meeting-mind/id6751551175)
[![Website](https://img.shields.io/badge/Website-meetingmind.kilabyte.io-orange.svg)](https://meetingmind.kilabyte.io)
[![Version](https://img.shields.io/badge/Version-1.3.7-green.svg)](#)

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

Free tier: 60 minutes of recording per day
Premium tier: Unlimited recording

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


## Recent Updates

### Version 1.3.7 (Current - October 2025)
- **Clickable meeting links in menu bar**: Calendar meetings now open directly in your browser or meeting app with visual hover feedback
- **Multi-platform meeting detection**: Calendar integration supports Microsoft Teams, Google Meet, and Webex beyond Zoom
- **User-controlled calendar filtering**: Toggle to show all events or only meetings with platform links (Zoom, Teams, Google Meet, Webex)
- **Enhanced security**: URL scheme validation protects against malicious calendar event links
- **Simplified OpenRouter settings**: Cleaner API key input with improved visual consistency
- **Improved default AI model**: Changed from gpt-4.1-nano to gpt-4.1 for better quality responses
- Improved calendar selection visibility with dynamic height (automatically expands for 10+ calendars)
- Contextual help text changes based on toggle state with appropriate visual icons

### Version 1.3.6 (October 2025)
- **History Manager Window**: Browse and manage historical recordings with search, sort, and AI chat integration
- **Recording Reprocessing**: Regenerate markdown summaries from existing audio files
- **Parakeet ASR Engine**: Alternative post-processing engine 10-100x faster than Whisper
- **Content-agnostic AI prompts**: Process any audio content (meetings, podcasts, lectures, interviews)
- **MetricKit Analytics**: Anonymous usage analytics with opt-out privacy model
- Centralized error alert system with actual error messages
- Thread safety enhancements for buffer pooling and audio processing

### Version 1.3.5 (October 2025)
- Drop audio files onto menu bar for instant transcription
- Automatic app startup when logging into macOS
- Native on-device AI processing (macOS 26+) as automatic fallback
- Systematic speaker tracking with voice patterns and contextual attribution
- Add domain-specific terms for improved transcription accuracy
- Integrate HuggingFace models with real-time validation
- Toggle transcript inclusion to save disk space


## License

Copyright © 2025 Kilabyte IO. All rights reserved.

This repository contains documentation and issue tracking for a proprietary application. The documentation is provided for informational purposes. The application binary is distributed through the Mac App Store.

---

**[Download MeetingMind](https://apps.apple.com/app/meeting-mind/id6751551175)** | **[Visit Website](https://meetingmind.kilabyte.io)** | **[Report Issue](https://github.com/kilabyte/meetingmind/issues/new)**
