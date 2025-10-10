# Astragalomancy - Ancient Dice Divination with Knuckle Bones

A desktop application for practicing ancient astragalomancy divination by casting 5 sheep knuckle bones. Built with Tauri for cross-platform support.

## Features

- **Ancient Greek Divination**: Practice the time-honored tradition of astragalomancy
- **56 Traditional Interpretations**: Receive divine guidance through authentic ancient interpretations
- **Interactive Bone Casting**: Ask your question and cast the virtual knuckle bones
- **Dark Mode**: Toggle between light and dark themes for comfortable viewing
- **Help Documentation**: Comprehensive guide to understanding the divination system
- **Cross-platform**: Works on Windows, macOS, and Linux

## About Astragalomancy

Astragalomancy is an ancient form of divination using knuckle bones (astragali) from sheep. This practice dates back to ancient Greece and was used to seek guidance from the gods. The application simulates casting 5 knuckle bones, each landing on one of four sides (valued 1, 3, 4, or 6), producing 56 possible combinations, each with its own divine interpretation.

## Prerequisites

Before building the application, ensure you have the following installed:

1. **Rust** (latest stable version)
   - Download from: https://rustup.rs/
   - Verify installation: `rustc --version`

2. **Node.js** (v16 or later recommended)
   - Download from: https://nodejs.org/
   - Verify installation: `node --version`

3. **Platform-specific dependencies:**

   ### Windows
   - Microsoft Visual Studio C++ Build Tools
   - WebView2 (usually pre-installed on Windows 10/11)

   ### macOS
   - Xcode Command Line Tools: `xcode-select --install`

   ### Linux (Debian/Ubuntu)
   ```bash
   sudo apt update
   sudo apt install libwebkit2gtk-4.1-dev \
     build-essential \
     curl \
     wget \
     file \
     libxdo-dev \
     libssl-dev \
     libayatana-appindicator3-dev \
     librsvg2-dev
   ```

   ### Linux (Fedora/RHEL)
   ```bash
   sudo dnf install webkit2gtk4.1-devel \
     openssl-devel \
     curl \
     wget \
     file \
     libappindicator-gtk3-devel \
     librsvg2-devel
   ```

## Installation

1. Navigate to the project directory:
   ```bash
   cd astragalomancy
   ```

2. Install Node.js dependencies:
   ```bash
   npm install
   ```

## Development

To run the application in development mode:

```bash
npm run dev
```

Or use the quick development script:
```bash
quick-dev.bat
```

This will start the Tauri development server and open the application window.

## Building Installers

### Build for Current Platform

To build the application for your current platform:

```bash
npm run build
```

Or use the quick build script:
```bash
quick-build.bat
```

The installers will be created in `src-tauri/target/release/bundle/`

### Platform-Specific Builds

**Windows (.exe, .msi):**
```bash
npm run build:windows
```
Output: `src-tauri/target/release/bundle/msi/` and `src-tauri/target/release/bundle/nsis/`

**macOS (.dmg, .app):**
```bash
npm run build:macos
```
Output: `src-tauri/target/release/bundle/dmg/` and `src-tauri/target/release/bundle/macos/`

**Linux (.deb, .rpm):**
```bash
npm run build:linux
```
Output: `src-tauri/target/release/bundle/deb/` and `src-tauri/target/release/bundle/rpm/`

## Usage

### Casting the Bones

1. Enter your question in the text field
2. Click the "Toss" button to cast the virtual knuckle bones
3. Receive your divine interpretation with:
   - The deity or concept associated with your cast
   - An image representing the result
   - The total value and combination of the bones
   - The traditional interpretation text

### Features

- **Dark Mode Toggle**: Switch between light and dark themes using the toggle in the top-right corner
- **Help Documentation**: Click the "?" button to access comprehensive help and learn about the divination system
- **Reset**: Clear your question and result to start a new divination

## Installation Paths

The application will be installed to the following default directories:

- **Windows**: `C:\Program Files\Astragalomancy\` or `%LOCALAPPDATA%\Programs\Astragalomancy\`
- **macOS**: `/Applications/Astragalomancy.app`
- **Linux**: `/usr/bin/astragalomancy` (binary) and `/usr/share/applications/` (desktop entry)

## Troubleshooting

### Icon Issues
If you encounter icon-related errors during build, you'll need to create icon files in `src-tauri/icons/`:
- `32x32.png`
- `128x128.png`
- `128x128@2x.png`
- `icon.icns` (macOS)
- `icon.ico` (Windows)

You can use online tools or image editors to create these from the favicon.ico or any PNG image.

### Build Errors
1. Make sure all dependencies are installed
2. Clear the build cache: `cargo clean` in the `src-tauri` directory
3. Update Rust: `rustup update`
4. Update dependencies: `cargo update` in the `src-tauri` directory

### Display Issues
If images don't display correctly:
1. Ensure all PNG files are in the `src/` directory
2. Check that the `help_files/` directory is properly copied
3. Verify file paths in the HTML are correct

## Technologies Used

- **Tauri 2.0**: Cross-platform desktop framework
- **HTML5/CSS3/JavaScript**: Frontend technologies
- **Rust**: Backend system integration

## Historical Context

Astragalomancy was practiced in ancient Greece and Rome, where knuckle bones (astragali) from sheep or goats were used for divination. Each bone has four distinct sides with different values (1, 3, 4, and 6), and the combination of five bones produces 56 possible outcomes. Each outcome was associated with a deity or concept and carried a specific interpretation.

This application preserves these ancient interpretations, allowing modern users to experience this historical divination practice.

## License

MIT License - Copyright © 2025 Radius.Center

## Support

For issues and questions, please visit the project repository or contact Radius.Center.
