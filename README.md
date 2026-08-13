

<div align="center">
<img src="media/AnchorLogo.png" width="160" height="160" style="display: block; margin: 0 auto"/>
<h1>Anchor</h1>
<p>Remote device location and control via SMS</p>

</div>

---

A privacy-focused Android application that enables you to locate and control your lost or stolen device remotely via SMS commands. No internet required, no servers involved - just direct SMS communication between your devices.

## Purpose

Anchor provides comprehensive remote control of your Android device through secure SMS commands, helping you recover lost or stolen devices:

- **Device Location**: Get precise GPS coordinates with Google Maps link
- **Remote Ring**: Make your device ring at maximum volume, even when silenced
- **Device Status**: Check battery level, charging status, and screen state
- **Call Back**: Make your device call you immediately
- **Sound Control**: Remotely change device sound mode (Normal/Vibrate/Silent)
- **Service Check**: Verify the tracking service is active

### Use Cases
- Locate lost device using GPS coordinates
- Ring device to find it nearby
- Get device status when lost
- Make device call you back
- Control device remotely when stolen
- Track device location for recovery

The app operates completely offline using SMS, providing:
- **No Internet Required**: Works via cellular SMS
- **No Data Collection**: All operations are local
- **Privacy-First**: No servers, no tracking, no analytics
- **Secure**: Password protection and phone whitelist

## Features

- **7 SMS Commands**: Complete remote control of your device
- **Password Protected**: All commands require authentication
- **Phone Whitelist**: Restrict control to trusted contacts only
- **Custom Prefix**: Personalize your command trigger word
- **Privacy-Focused**: No internet permissions, all operations are local
- **Modern Material Design 3 Interface**: Clean, intuitive UI built with Jetpack Compose

## Configuration

### SMS Commands
The app supports 7 remote control commands:

**Device Location:**
- `locate` - Get GPS coordinates and Google Maps link

**Device Control:**
- `ring` - Play loud alarm at maximum volume
- `info` - Get battery level, charging status, screen state
- `callme` - Make device call you back immediately
- `sound [mode]` - Change sound mode (normal/vibrate/silent)

**Service Management:**
- `ping` - Check if Anchor service is running
- `help` - Get list of all available commands

### Command Configuration
1. Open the app and navigate to **Command Settings**
2. Set your **Command Prefix** (default: `PIN`)
3. Create a strong **Command Password**
4. Save the configuration

### Whitelist Setup (Recommended)
1. Navigate to **Phone Whitelist**
2. Enable whitelist protection
3. Add trusted phone numbers:
   - Import from contacts, or
   - Add manually
4. Only whitelisted numbers can control your device


## Requirements

- Android 8.0 (Oreo, API 26) or higher
- Active SIM card with SMS capability
- GPS/Location services
- Phone call capability

## Installation
<div align="center">

[<img src="media/get_it_github.png" alt="Get it on GitHub" height="80" align="center">](https://github.com/aunchagaonkar/anchor/releases)
[<img src="https://raw.githubusercontent.com/ImranR98/Obtainium/main/assets/graphics/badge_obtainium.png" alt="Get it on Obtainium" height="55" align="center">](https://apps.obtainium.imranr.dev/redirect?r=obtainium://add/https://github.com/aunchagaonkar/Anchor/)
</div>

1. Download the latest APK from the Releases page
2. Install on your Android device
3. Open the app and grant required permissions:
   - SMS (Read & Send)
   - Location (Precise & Background)
   - Phone (Make Calls)
   - Contacts (Import trusted numbers)
   - Display Over Other Apps
4. Configure your command prefix and password
5. Set up phone number whitelist for security
6. Test with a ping command from trusted number

## Project Structure

```
app/
├── src/main/java/com/supernova/anchor/
│   ├── MainActivity.kt                     # Main entry point
│   ├── SettingsActivity.kt                 # App settings
│   ├── PermissionsActivity.kt              # Permission management
│   ├── CommandSettingsActivity.kt          # Command configuration
│   ├── WhitelistActivity.kt                # Phone whitelist management
│   ├── AboutActivity.kt                    # App information
│   ├── receiver/
│   │   └── SmsReceiver.kt                  # SMS command receiver
│   ├── service/
│   │   └── OverlayDisplayService.kt        # Alert display service
│   └── utils/
│       ├── SmsCommandProcessor.kt          # Command processing logic
│       ├── LocationUtils.kt                # GPS location services
│       ├── WhitelistManager.kt             # Whitelist management
│       ├── PermissionManager.kt            # Permission handling
│       ├── AppSettings.kt                  # Settings storage
│       └── RingtonePlayer.kt               # Ring command handler
├── src/main/res/                           # Resources (layouts, strings, etc.)
└── build.gradle.kts                        # App build configuration

.github/workflows/                          # CI/CD pipelines
├── build.yml                               # Continuous Integration
└── release.yml                             # Release automation

gradle/
├── libs.versions.toml                      # Version catalog
└── wrapper/                                # Gradle wrapper

build.gradle.kts                            # Root build configuration
settings.gradle.kts                         # Project settings
```

## Building from Source

```bash
# Clone the repository
git clone https://github.com/aunchagaonkar/anchor.git
cd anchor

# Build debug APK
./gradlew assembleDebug

# Build release APK
./gradlew assembleRelease
```

## Security & Privacy

### What We DON'T Do
- No internet access
- No data collection
- No analytics or tracking
- No third-party services
- No background data sync
- No user accounts

### What We DO
- SMS-only communication
- Password protection
- Phone number whitelist
- Local data storage only
- Open source code
- Transparent operations

### Security Best Practices
1. Use a strong, unique password (12+ characters)
2. Enable phone whitelist protection
3. Only add trusted contacts to whitelist
4. Regularly review whitelist entries
5. Keep the app updated
6. Never share your command password

## TODO
- [x] SMS command processing
- [x] GPS location tracking
- [x] Remote device ring
- [x] Call back feature
- [x] Sound mode control
- [x] Password protection
- [x] Phone whitelist
- [ ] Rate limiting for commands
- [ ] Geofencing alerts
- [ ] Multi-language support

## Contributing

Contributions are welcome! Please follow these guidelines:

### Getting Started
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/feature-name`)
3. Make your changes following the project's code style
4. Test your changes thoroughly
5. Commit your changes (`git commit -m 'Add feature-name'`)
6. Push to the branch (`git push origin feature/feature-name`)
7. Open a Pull Request

### Code Style
- Follow Kotlin coding conventions
- Use meaningful variable and function names
- Add documentation for public APIs
- Maintain clean architecture principles
- Follow Material Design guidelines for UI changes

### Testing
- Test on multiple Android versions (8.0+)
- Verify all SMS commands work correctly
- Test permission flows
- Validate security features
- Test on different devices/manufacturers

### Reporting Issues
- Use the GitHub issue tracker
- Provide detailed reproduction steps
- Include device information and Android version
- Attach relevant logs when possible

## LICENSE

This project is licensed under the GNU General Public License v3.0. See the [LICENSE](LICENSE) file for details.

## Dependencies and Credits

### Core Dependencies
- **Jetpack Compose**: Modern UI framework
- **Material Design 3**: UI components and theming
- **Play Services Location**: GPS location services
- **Kotlin Coroutines**: Asynchronous operations
- **AndroidX Libraries**: Core Android components

### Permissions Used
- **SMS**: Receive and send command messages
- **Location**: Determine device position
- **Phone**: Make callback calls
- **Display Over Other Apps**: Show alerts

Special thanks to the Android development community and the maintainers of the open-source libraries used in this project.

## Disclaimer

**Important:** This app is designed to help you locate and control YOUR OWN device if it's lost or stolen. It is NOT intended for:
- Surveillance or tracking others
- Covert monitoring
- Unauthorized access to devices

Using this app to track others without their knowledge may be illegal in your jurisdiction. Always comply with local laws and respect privacy rights.

**Legal:**
- Use only on devices you own or have permission to track
- Comply with local privacy and surveillance laws
- Disable before selling/transferring device

---

<div align="center">

**Made with ❤️ from Ameya**

⭐ Star this repo if you find it useful!

[Report Bug](https://github.com/aunchagaonkar/anchor/issues) • [Request Feature](https://github.com/aunchagaonkar/anchor/issues) • [Contribute](CONTRIBUTING.md)

</div>
