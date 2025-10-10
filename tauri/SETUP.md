# Setup Guide for Astragalomancy

This guide will help you set up the development environment for the Astragalomancy desktop application.

## Table of Contents
1. [System Requirements](#system-requirements)
2. [Installing Prerequisites](#installing-prerequisites)
3. [Project Setup](#project-setup)
4. [Verification](#verification)
5. [Next Steps](#next-steps)

## System Requirements

### Minimum Requirements
- **OS**: Windows 10/11, macOS 10.13+, or Linux (Ubuntu 20.04+, Fedora 36+)
- **RAM**: 4 GB (8 GB recommended)
- **Disk Space**: 2 GB for development tools, 500 MB for project
- **Internet**: Required for downloading dependencies

### Recommended Requirements
- **OS**: Windows 11, macOS 12+, or Ubuntu 22.04+
- **RAM**: 8 GB or more
- **Disk Space**: 5 GB or more
- **CPU**: Multi-core processor for faster builds

## Installing Prerequisites

### Step 1: Install Rust

Rust is required for building the Tauri backend.

#### Windows
1. Download Rust installer from: https://rustup.rs/
2. Run `rustup-init.exe`
3. Follow the installation prompts
4. Restart your terminal/command prompt
5. Verify installation:
   ```bash
   rustc --version
   cargo --version
   ```

#### macOS
1. Open Terminal
2. Run:
   ```bash
   curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
   ```
3. Follow the installation prompts
4. Restart your terminal
5. Verify installation:
   ```bash
   rustc --version
   cargo --version
   ```

#### Linux
1. Open Terminal
2. Run:
   ```bash
   curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
   ```
3. Follow the installation prompts
4. Restart your terminal
5. Verify installation:
   ```bash
   rustc --version
   cargo --version
   ```

### Step 2: Install Node.js

Node.js is required for managing frontend dependencies and running build scripts.

#### Windows
1. Download Node.js LTS from: https://nodejs.org/
2. Run the installer
3. Follow the installation wizard
4. Restart your terminal
5. Verify installation:
   ```bash
   node --version
   npm --version
   ```

#### macOS
**Option 1: Official Installer**
1. Download Node.js LTS from: https://nodejs.org/
2. Run the .pkg installer
3. Follow the installation wizard
4. Verify installation:
   ```bash
   node --version
   npm --version
   ```

**Option 2: Homebrew**
```bash
brew install node
node --version
npm --version
```

#### Linux
**Ubuntu/Debian:**
```bash
curl -fsSL https://deb.nodesource.com/setup_lts.x | sudo -E bash -
sudo apt-get install -y nodejs
node --version
npm --version
```

**Fedora:**
```bash
sudo dnf install nodejs
node --version
npm --version
```

### Step 3: Install Platform-Specific Dependencies

#### Windows
1. **Visual Studio C++ Build Tools**
   - Download from: https://visualstudio.microsoft.com/downloads/
   - Install "Desktop development with C++" workload
   - Or use the direct link: https://aka.ms/vs/17/release/vs_BuildTools.exe

2. **WebView2** (usually pre-installed on Windows 10/11)
   - If needed, download from: https://developer.microsoft.com/en-us/microsoft-edge/webview2/

#### macOS
Install Xcode Command Line Tools:
```bash
xcode-select --install
```

#### Linux (Ubuntu/Debian)
```bash
sudo apt update
sudo apt install -y \
  libwebkit2gtk-4.1-dev \
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
sudo dnf install -y \
  webkit2gtk4.1-devel \
  openssl-devel \
  curl \
  wget \
  file \
  libappindicator-gtk3-devel \
  librsvg2-devel
```

## Project Setup

### Step 1: Navigate to Project Directory

```bash
cd C:\Users\Dan Neiderhiser\Desktop\astragalomancy
```

Or on macOS/Linux:
```bash
cd ~/Desktop/astragalomancy
```

### Step 2: Install Node.js Dependencies

```bash
npm install
```

This will install:
- `@tauri-apps/cli` - Tauri command-line interface

**Expected Output:**
```
added 1 package, and audited 2 packages in 3s
found 0 vulnerabilities
```

### Step 3: Verify Project Structure

Ensure the following directories and files exist:

```
astragalomancy/
├── src/                          # Frontend files
│   ├── index.html               # Main HTML file
│   ├── help.html                # Help documentation
│   ├── favicon.ico              # Favicon
│   ├── *.png                    # 56 divination images
│   └── help_files/              # Help documentation assets
├── src-tauri/                   # Tauri backend
│   ├── src/
│   │   ├── main.rs             # Rust main file
│   │   └── lib.rs              # Rust library file
│   ├── capabilities/
│   │   └── default.json        # Permissions
│   ├── Cargo.toml              # Rust dependencies
│   ├── tauri.conf.json         # Tauri configuration
│   └── build.rs                # Build script
├── package.json                 # Node.js configuration
├── quick-dev.bat               # Quick development script
├── quick-build.bat             # Quick build script
└── README.md                    # Project documentation
```

## Verification

### Test Development Build

Run the development server to verify everything is set up correctly:

```bash
npm run dev
```

Or use the quick script:
```bash
quick-dev.bat
```

**Expected Behavior:**
1. Terminal shows compilation progress
2. Application window opens
3. Astragalomancy interface is displayed
4. You can enter a question and cast bones

**If the application opens successfully, your setup is complete!**

### Common Setup Issues

#### Issue: "cargo not found"
**Solution:** Rust is not installed or not in PATH
- Reinstall Rust from https://rustup.rs/
- Restart your terminal
- Verify with `cargo --version`

#### Issue: "node not found"
**Solution:** Node.js is not installed or not in PATH
- Reinstall Node.js from https://nodejs.org/
- Restart your terminal
- Verify with `node --version`

#### Issue: "failed to run custom build command"
**Solution:** Platform-specific dependencies missing
- **Windows:** Install Visual Studio C++ Build Tools
- **macOS:** Run `xcode-select --install`
- **Linux:** Install webkit2gtk and other dependencies (see Step 3)

#### Issue: "WebView2 not found" (Windows)
**Solution:** Install WebView2 Runtime
- Download from: https://developer.microsoft.com/en-us/microsoft-edge/webview2/
- Install and restart

#### Issue: Build takes very long (first time)
**Solution:** This is normal
- First build compiles all Rust dependencies (10-30 minutes)
- Subsequent builds are much faster (1-5 minutes)
- Be patient and let it complete

## Next Steps

After successful setup:

1. **Read the Documentation:**
   - `README.md` - Project overview and features
   - `BUILD_INSTRUCTIONS.md` - Detailed build instructions
   - `PROJECT_SUMMARY.md` - Technical details

2. **Start Development:**
   ```bash
   npm run dev
   ```

3. **Make Changes:**
   - Edit files in `src/` for frontend changes
   - Edit files in `src-tauri/src/` for backend changes
   - Changes auto-reload in development mode

4. **Build for Production:**
   ```bash
   npm run build
   ```

5. **Test the Application:**
   - Try casting bones with different questions
   - Test dark mode toggle
   - Review help documentation
   - Verify all images load correctly

## Development Workflow

### Typical Development Session

1. **Start Development Server:**
   ```bash
   npm run dev
   ```

2. **Make Changes:**
   - Edit HTML/CSS/JavaScript in `src/`
   - Changes auto-reload in the application

3. **Test Changes:**
   - Verify functionality in the application window
   - Check console for errors

4. **Stop Development Server:**
   - Press `Ctrl+C` in the terminal

### Building for Distribution

1. **Build the Application:**
   ```bash
   npm run build
   ```

2. **Find Installers:**
   - Windows: `src-tauri/target/release/bundle/msi/` or `nsis/`
   - macOS: `src-tauri/target/release/bundle/dmg/`
   - Linux: `src-tauri/target/release/bundle/deb/` or `rpm/`

3. **Test the Installer:**
   - Install on a clean system if possible
   - Verify all features work

## IDE Setup (Optional)

### Visual Studio Code
Recommended extensions:
- **rust-analyzer** - Rust language support
- **Tauri** - Tauri development tools
- **ESLint** - JavaScript linting
- **Prettier** - Code formatting

### Other IDEs
- **IntelliJ IDEA** - With Rust plugin
- **Sublime Text** - With Rust Enhanced
- **Vim/Neovim** - With rust.vim

## Getting Help

If you encounter issues:

1. **Check Documentation:**
   - Review `BUILD_INSTRUCTIONS.md`
   - Check `README.md`

2. **Common Issues:**
   - See troubleshooting sections above
   - Check Tauri documentation: https://tauri.app/

3. **Community Support:**
   - Tauri Discord: https://discord.com/invite/tauri
   - Tauri GitHub: https://github.com/tauri-apps/tauri

4. **Project Support:**
   - Contact Radius.Center
   - Check project repository

## Summary

You should now have:
- ✅ Rust installed and verified
- ✅ Node.js installed and verified
- ✅ Platform-specific dependencies installed
- ✅ Project dependencies installed
- ✅ Development server running successfully

**You're ready to develop and build Astragalomancy!**
