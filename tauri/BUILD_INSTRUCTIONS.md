# Build Instructions for Astragalomancy

This document provides detailed instructions for building the Astragalomancy desktop application.

## Quick Start

### For Development
```bash
# Run the quick development script
quick-dev.bat

# Or manually:
npm install
npm run dev
```

### For Production Build
```bash
# Run the quick build script
quick-build.bat

# Or manually:
npm install
npm run build
```

## Prerequisites

### Required Software

1. **Rust** (latest stable)
   - Install from: https://rustup.rs/
   - Verify: `rustc --version`
   - Should show version 1.70.0 or higher

2. **Node.js** (v16 or later)
   - Install from: https://nodejs.org/
   - Verify: `node --version` and `npm --version`
   - Recommended: v18.x or v20.x LTS

3. **Cargo** (comes with Rust)
   - Verify: `cargo --version`

### Platform-Specific Requirements

#### Windows
- **Visual Studio C++ Build Tools**
  - Download: https://visualstudio.microsoft.com/downloads/
  - Install "Desktop development with C++" workload
  - Or install via: https://aka.ms/vs/17/release/vs_BuildTools.exe

- **WebView2**
  - Usually pre-installed on Windows 10/11
  - If needed: https://developer.microsoft.com/en-us/microsoft-edge/webview2/

#### macOS
- **Xcode Command Line Tools**
  ```bash
  xcode-select --install
  ```

#### Linux (Debian/Ubuntu)
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

#### Linux (Fedora/RHEL)
```bash
sudo dnf install webkit2gtk4.1-devel \
  openssl-devel \
  curl \
  wget \
  file \
  libappindicator-gtk3-devel \
  librsvg2-devel
```

## Build Process

### Step 1: Install Dependencies

Navigate to the project directory and install Node.js dependencies:

```bash
cd astragalomancy
npm install
```

This will install:
- `@tauri-apps/cli` - Tauri command-line interface

### Step 2: Development Build

For development with hot-reload:

```bash
npm run dev
```

This will:
1. Start the Tauri development server
2. Open the application window
3. Enable hot-reload for frontend changes
4. Show console output for debugging

**Development Features:**
- Hot-reload for HTML/CSS/JS changes
- Debug console available
- Faster build times
- Source maps enabled

### Step 3: Production Build

For production-ready installers:

```bash
npm run build
```

This will:
1. Compile the Rust backend in release mode
2. Optimize the frontend assets
3. Create platform-specific installers
4. Generate bundles in `src-tauri/target/release/bundle/`

**Build Output Locations:**

**Windows:**
- MSI Installer: `src-tauri/target/release/bundle/msi/`
- NSIS Installer: `src-tauri/target/release/bundle/nsis/`
- Executable: `src-tauri/target/release/astragalomancy.exe`

**macOS:**
- DMG: `src-tauri/target/release/bundle/dmg/`
- App Bundle: `src-tauri/target/release/bundle/macos/`

**Linux:**
- DEB Package: `src-tauri/target/release/bundle/deb/`
- RPM Package: `src-tauri/target/release/bundle/rpm/`
- AppImage: `src-tauri/target/release/bundle/appimage/`

### Step 4: Platform-Specific Builds

#### Windows Build
```bash
npm run build:windows
```
Creates MSI and NSIS installers for Windows.

#### macOS Build
```bash
npm run build:macos
```
Creates DMG and .app bundle for macOS.

#### Linux Build
```bash
npm run build:linux
```
Creates DEB and RPM packages for Linux.

## Build Configuration

### Tauri Configuration
The build is configured in `src-tauri/tauri.conf.json`:

- **Product Name**: Astragalomancy
- **Version**: 1.0.0
- **Identifier**: center.radius.astragalomancy
- **Window Size**: 1000x800 (resizable, min 600x500)

### Cargo Configuration
Rust dependencies are defined in `src-tauri/Cargo.toml`:

- **Tauri**: 2.0 with protocol-asset feature
- **Tauri Plugin Shell**: 2.0
- **Serde**: 1.x for serialization

### Release Optimizations
The release build includes:
- Panic abort for smaller binary size
- Link-time optimization (LTO)
- Size optimization (`opt-level = "s"`)
- Symbol stripping for reduced size

## Icon Requirements

The application requires icons in `src-tauri/icons/`:

- `32x32.png` - Small icon
- `128x128.png` - Medium icon
- `128x128@2x.png` - Retina display icon
- `icon.icns` - macOS icon bundle
- `icon.ico` - Windows icon

**Creating Icons:**
1. Start with a high-resolution PNG (512x512 or larger)
2. Use online tools like:
   - https://www.icoconverter.com/
   - https://cloudconvert.com/
3. Or use command-line tools:
   - ImageMagick: `convert icon.png -resize 32x32 32x32.png`
   - For .icns: Use `iconutil` on macOS
   - For .ico: Use ImageMagick or online converters

## Troubleshooting

### Common Build Errors

#### Error: "cargo not found"
**Solution:** Install Rust from https://rustup.rs/

#### Error: "failed to run custom build command for tauri-build"
**Solution:** 
1. Update Rust: `rustup update`
2. Clear cache: `cd src-tauri && cargo clean`
3. Rebuild: `npm run build`

#### Error: "WebView2 not found" (Windows)
**Solution:** Install WebView2 Runtime from Microsoft

#### Error: "gtk not found" (Linux)
**Solution:** Install webkit2gtk development packages (see prerequisites)

#### Error: Icon-related errors
**Solution:** 
1. Ensure all required icon files exist in `src-tauri/icons/`
2. Verify icon files are valid PNG/ICO/ICNS format
3. Check file permissions

### Build Performance

**Slow First Build:**
- First build compiles all Rust dependencies (10-30 minutes)
- Subsequent builds are much faster (1-5 minutes)
- Use `npm run dev` for faster iteration during development

**Reducing Build Time:**
- Use `npm run dev` for development
- Only run `npm run build` for final releases
- Consider using `cargo build --release` directly for testing

### Clean Build

If you encounter persistent issues:

```bash
# Clean Node modules
rm -rf node_modules
npm install

# Clean Rust build
cd src-tauri
cargo clean
cd ..

# Rebuild
npm run build
```

## Build Verification

After building, verify the application:

1. **Check Build Output:**
   - Verify installers exist in `src-tauri/target/release/bundle/`
   - Check file sizes are reasonable (typically 5-15 MB)

2. **Test Installation:**
   - Install the application using the generated installer
   - Verify it launches correctly
   - Test all features (bone casting, dark mode, help)

3. **Test on Clean System:**
   - If possible, test on a system without development tools
   - Verify all dependencies are bundled correctly

## Distribution

### Windows
- Distribute the MSI or NSIS installer
- Users can install without admin rights (per-user install)
- No additional dependencies required

### macOS
- Distribute the DMG file
- Users drag the app to Applications folder
- May need to allow in Security & Privacy settings

### Linux
- Distribute DEB for Debian/Ubuntu
- Distribute RPM for Fedora/RHEL
- Or distribute AppImage for universal compatibility

## Continuous Integration

For automated builds, consider:

1. **GitHub Actions:**
   - Build on push/PR
   - Create releases automatically
   - Test on multiple platforms

2. **Build Matrix:**
   - Windows (latest)
   - macOS (latest)
   - Ubuntu (latest)

## Version Management

To update the version:

1. Update `version` in `package.json`
2. Update `version` in `src-tauri/Cargo.toml`
3. Update `version` in `src-tauri/tauri.conf.json`
4. Rebuild the application

## Support

For build issues:
- Check Tauri documentation: https://tauri.app/
- Review Tauri GitHub issues: https://github.com/tauri-apps/tauri/issues
- Contact Radius.Center for project-specific help
