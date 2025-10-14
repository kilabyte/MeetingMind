# MeetingMind - Issue Tracking & Documentation

> **Note**: This repository is for **issue tracking, documentation, and community support** only. The main codebase is maintained in a private GitLab repository.

[![Mac App Store](https://img.shields.io/badge/Download-Mac%20App%20Store-blue.svg)](https://apps.apple.com/app/meeting-mind/id6751551175)
[![Website](https://img.shields.io/badge/Website-meetingmind--website.web.app-orange.svg)](https://meetingmind-website.web.app)
[![Version](https://img.shields.io/badge/Version-1.3.3-green.svg)](#)

## About MeetingMind

MeetingMind is a macOS menu bar application that automatically detects and records online meetings (Zoom, Microsoft Teams, Google Meet, Webex) with AI-powered features. Built with Swift/SwiftUI for macOS 15.0+.

### Key Features

- **Automatic Meeting Detection**: Detects Zoom, Teams, Google Meet, and Webex meetings automatically
- **Smart Recording**: Records system audio, microphone, or both with live transcription
- **AI-Powered Processing**: Local WhisperKit transcription + AI summaries (Ollama or OpenRouter)
- **Calendar Integration**: Extracts meeting titles from your calendar automatically
- **AI Chat Interface**: Interactive chat with meeting context and document analysis
- **Privacy-First**: All data stored locally, optional cloud AI services
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
- 📝 **Public Roadmap**: See what's coming next

The main codebase is developed and maintained in a private GitLab repository for security and intellectual property reasons.

## Roadmap

### Version 1.4.0 (Q4 2025) - Enhanced AI & Integrations
- **Advanced AI Features**
  - Multi-language transcription support (Spanish, French, German, Japanese)
  - Custom AI prompt templates with variables
  - Speaker diarization improvements (better speaker identification)
  - Sentiment analysis in meeting summaries

- **Integration Enhancements**
  - Export to Notion, Obsidian, and other note-taking apps
  - Slack/Teams direct message integration for action items
  - CRM integration (Salesforce, HubSpot) for sales meetings
  - Google Drive/Dropbox direct upload

### Version 1.5.0 (Q3 2025) - Collaboration & Teams
- **Team Features**
  - Shared meeting transcripts with team members
  - Team workspaces for organized collaboration
  - Role-based permissions (viewer, editor, admin)
  - Comment threads on transcripts

- **Advanced Search**
  - Full-text search across all meetings
  - Semantic search with AI-powered relevance
  - Filter by date range, participants, keywords
  - Export search results

### Version 2.0.0 (Q4 2025) - Enterprise & Analytics
- **Enterprise Features**
  - SSO integration (SAML, OAuth)
  - Admin dashboard for team management
  - Usage analytics and compliance reporting
  - Custom retention policies

- **Meeting Analytics**
  - Talk time analysis per participant
  - Meeting effectiveness scores
  - Action item tracking and completion rates
  - Trend analysis across meetings

### Future Considerations (2026+)
- Video recording alongside audio
- Real-time collaborative transcription editing
- iOS/iPadOS companion app
- Integration with project management tools (Jira, Asana, Monday.com)
- Custom vocabulary for industry-specific terminology
- Meeting templates and agenda tracking
- Automated meeting minutes generation
- Browser extension for web-based meeting platforms

**Vote on Features**: Have a feature request? [Create an issue](https://github.com/kilabyte/meetingmind/issues/new?template=feature_request.md) and let us know what you'd like to see!

## Repository Structure

```
├── README.md                 # This file
├── CONTRIBUTING.md          # How to contribute
├── docs/                    # Documentation
│   ├── user-guide/         # End-user documentation
│   ├── technical/          # Technical architecture
│   ├── troubleshooting/    # Common issues and solutions
│   └── api/                # API documentation
└── .github/
    └── ISSUE_TEMPLATE/     # Issue templates
```

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

## Documentation

Comprehensive documentation is available in the [docs/](docs/) directory and on the [Wiki](https://github.com/kilabyte/meetingmind/wiki):

- **[User Guide](docs/user-guide/)**: Getting started, features, and workflows
- **[Technical Documentation](docs/technical/)**: Architecture, design patterns, and implementation details
- **[Troubleshooting](docs/troubleshooting/)**: Common issues and solutions
- **[API Reference](docs/api/)**: Integration and extension points

## Support

- **Issues**: [GitHub Issues](https://github.com/kilabyte/meetingmind/issues)
- **Support Form**: [Website Support](https://meetingmind-website.web.app/support.html)
- **Website**: [meetingmind-website.web.app](https://meetingmind-website.web.app)

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

See our [Privacy Policy](https://meetingmind-website.web.app/privacy.html) for details.

## Technology Stack

- **Language**: Swift 5.9+
- **UI Framework**: SwiftUI
- **Audio**: ScreenCaptureKit, AVFoundation
- **Speech Recognition**: Apple Speech Framework
- **Local Transcription**: Forked WhisperKit
- **Cloud AI**: Ollama (local), OpenRouter (cloud)
- **Calendar**: EventKit
- **Distribution**: Mac App Store

## Recent Updates

### Version 1.3.3 (Current)
- MetricKit integration for system diagnostics
- OpenRouter API key verification
- What's New feature system
- Enhanced AI prompt system
- User-configurable AI model parameters
- Meeting time limits extended (60 min/day free tier)

### Version 1.3.2
- Settings corruption detection & recovery
- Production UI cleanup (dev-only settings hidden)
- StoreKit pricing enhancements
- CI/CD Mac App Store integration
- Comprehensive test suite improvements

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

**[Download MeetingMind](https://apps.apple.com/app/meeting-mind/id6751551175)** | **[Visit Website](https://meetingmind-website.web.app)** | **[Report Issue](https://github.com/kilabyte/meetingmind/issues/new)**
