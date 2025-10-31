# Privately v0.1 - Initial Release

## What is Privately?

Privately is a local-first, encrypted journaling application with on-device AI analysis. All your journal entries are stored locally on your Mac with military-grade encryption, and AI-powered insights run entirely on your device - no cloud services, no data sharing, complete privacy.

## Key Features

### Local-First & Encrypted Storage
- **SQLCipher Encryption**: All journal entries encrypted at rest with AES-256
- **Keychain Integration**: Encryption keys stored securely in macOS Keychain
- **Zero Cloud Dependencies**: Everything runs on your device - your data never leaves your Mac

### AI-Powered Insights (On-Device)
- **Qwen3 1.7B Model**: Advanced AI analysis running entirely on your device
- **Two-Pass Analysis**: Premium quality insights with enhanced creativity
- **Automatic Summaries**: Get 5-bullet summaries of your journal entries
- **Idea Extraction**: Discover 5 actionable ideas and questions to explore
- **State of Mind**: Neutral, non-judgmental emotional tone analysis
- **No Internet Required**: AI runs 100% offline with model included in the app

### Reliable Data Protection
- **Automatic Backups**: Daily automatic backups with 30-day retention
- **Catastrophic Recovery**: Auto-restore from backups if database corruption occurs
- **Multi-Retry WAL Recovery**: Handles transient SQLite errors gracefully
- **Pre-Migration Backups**: Automatic backups before any schema changes

### Modern UI
- **Clean Interface**: Distraction-free writing experience
- **Intelligent Autosave**: Never lose your work
- **Floating AI Panel**: Analysis results displayed in elegant, readable format

## What's New in v0.1

- Initial release of Privately journaling app
- Complete local-first architecture with SQLCipher encryption
- On-device AI analysis with Qwen3 1.7B model (bundled with app)
- Automatic backup system with corruption recovery
- Production-ready database reliability with multi-retry WAL recovery
- Full macOS code signing and notarization
- Universal binary support (Apple Silicon + Intel)

## System Requirements

- **macOS**: 11.0 (Big Sur) or later
- **RAM**: 8GB minimum (16GB recommended for optimal AI performance)
- **Storage**: ~1.4GB for app with bundled AI model
- **Architecture**:
  - Apple Silicon (M1/M2/M3/M4 Macs): Use `Privately-Apple-Silicon.dmg`
  - Intel Macs (pre-2020): Use `Privately-Intel.dmg`

## Installation

1. Download the appropriate DMG for your Mac:
   - **Apple Silicon**: `Privately-Apple-Silicon.dmg` (M1/M2/M3/M4 Macs)
   - **Intel**: `Privately-Intel.dmg` (Intel-based Macs)

2. Open the DMG file
3. Drag `Privately.app` to your Applications folder
4. Launch Privately from Applications
5. On first launch:
   - The app will create encryption keys in your Keychain
   - Qwen3 AI model is bundled and ready to use (~1.1GB included)

## Known Limitations

- **macOS Only**: Windows and Linux support planned for future releases
- **No Cloud Sync**: Cloud backup/sync planned for future releases
- **No Mobile App**: React Native mobile app in development

## Technical Details

### Security
- **Encryption**: AES-256 via SQLCipher
- **Key Derivation**: Scrypt KDF
- **Key Storage**: macOS Keychain (never stored in files)
- **Code Signing**: Developer ID Application signed and notarized by Apple

### AI Model
- **Model**: Qwen3 1.7B (GGUF Q4_K_M quantization)
- **Size**: ~1.1GB
- **Inference**: LLaMA.cpp via node-llama-cpp
- **Performance**: 10-15s analysis time on typical hardware
- **Privacy**: 100% on-device, zero network calls

### Database
- **Engine**: SQLite 3.x with SQLCipher extension
- **Encryption**: Per-install 32-byte encryption key
- **Backups**: Automatic with 5-backup, 30-day retention
- **Recovery**: Multi-tier recovery (WAL retry + backup restoration)

## Troubleshooting

### App Won't Launch
- Make sure you're running macOS 11.0 or later
- Check that you downloaded the correct architecture (Apple Silicon vs Intel)
- Try right-clicking and selecting "Open" if Gatekeeper shows a warning

### AI Analysis Slow
- First analysis loads the bundled AI model (~1.1GB) into memory - subsequent analyses are faster
- Ensure you have at least 8GB RAM available
- Close other memory-intensive applications

### Database Errors
- The app includes automatic backup and recovery
- If you see database errors, check `~/Library/Logs/journaling-app-electron/main.log`
- Backups are stored in your app data directory

## Support & Feedback

- **Email**: support@privately.to (coming soon)
- **Documentation**: https://docs.privately.to (coming soon)

## Privacy Promise

Privately is built on three core principles:

1. **Local-First**: Your data lives on your device, not our servers
2. **Encrypted**: All data encrypted at rest with keys only you control
3. **Private**: Zero telemetry, zero tracking, zero data collection

We cannot read your journals because we never have access to them.

## What's Next?

Planned for future releases:
- **v0.2**: Local Speech Input & Transcription
- **v0.3**: React Native mobile app (iOS + Android)
- **v0.4**: Optional encrypted cloud sync
- **v0.5**: React Native mobile app (iOS + Android)
- **v1.0**: Embeddings (Past Journals) & Semantic Search (Reminders)
- **v1.5**: Self-Guided Work

---

**Built with**: Electron, React, Tamagui, SQLCipher, node-llama-cpp, Qwen3 1.7B

**License**: AGPLv3 (core app) - Full source code coming soon

---

Thank you for being an early adopter of Privately. Your privacy is our mission.