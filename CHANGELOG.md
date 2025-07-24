# Changelog

## [1.0.0] - 2025-07-23
### Added
- Full OTA update system with manifest and checksum verification
- Captive portal setup mode with Wi-Fi + ZIP/lat/lon input
- Multi-phase weather display loop (non-blocking)
- Fallback to observation/hourly if forecast fails
- Error handling for invalid ZIPs or out-of-US lat/lon

### Improved
- iOS captive portal flow and browser compatibility
- Graceful config error recovery without wiping config

### Fixed
- Settings page Save button contrast issues across platforms
- Checksum verification bug during finalize step
