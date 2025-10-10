# START HERE - Astragalomancy Quick Start Guide

Welcome to the Astragalomancy project! This guide will get you up and running quickly.

## What is Astragalomancy?

Astragalomancy is a desktop application that brings the ancient Greek practice of knuckle bone divination to your computer. Cast 5 virtual sheep knuckle bones and receive divine guidance through 56 traditional interpretations.

## Quick Start (For Users)

### If You Just Want to Use the App

1. **Download the installer** for your platform:
   - Windows: Download the `.msi` or `.exe` installer
   - macOS: Download the `.dmg` file
   - Linux: Download the `.deb` or `.rpm` package

2. **Install the application**:
   - Windows: Double-click the installer and follow prompts
   - macOS: Open the DMG and drag to Applications
   - Linux: Use your package manager or double-click the package

3. **Run Astragalomancy**:
   - Find it in your applications menu
   - Enter your question
   - Click "Toss" to cast the bones
   - Receive your divine interpretation

## Quick Start (For Developers)

### Prerequisites Check

Before you begin, verify you have:
- [ ] Rust installed (`rustc --version`)
- [ ] Node.js installed (`node --version`)
- [ ] Platform-specific tools (see below)

**Don't have these?** → See [SETUP.md](SETUP.md) for detailed installation instructions.

### Platform-Specific Requirements

**Windows:**
- Visual Studio C++ Build Tools
- WebView2 (usually pre-installed)

**macOS:**
- Xcode Command Line Tools

**Linux:**
- webkit2gtk and development libraries

### 5-Minute Setup

1. **Open terminal in project directory:**
   ```bash
   cd astragalomancy
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Run the application:**
   ```bash
   npm run dev
   ```
   
   Or use the quick script:
   ```bash
   quick-dev.bat
   ```

4. **The application window will open!**
   - Try entering a question
   - Click "Toss" to test the divination
   - Toggle dark mode
   - Click "?" for help

**That's it! You're running Astragalomancy in development mode.**

## What's Next?

### For Users

- **Learn the System**: Click the "?" button in the app for comprehensive help
- **Understand Results**: Each cast shows a deity, image, and interpretation
- **Dark Mode**: Toggle the switch in the top-right for dark theme
- **Ask Questions**: The oracle responds to any question you pose

### For Developers

Choose your path:

#### Just Want to Build?
→ See [BUILD_INSTRUCTIONS.md](BUILD_INSTRUCTIONS.md)

#### Need to Set Up Environment?
→ See [SETUP.md](SETUP.md)

#### Want Technical Details?
→ See [PROJECT_SUMMARY.md](PROJECT_SUMMARY.md)

#### Need a Checklist?
→ See [CHECKLIST.md](CHECKLIST.md)

#### Want to Understand Structure?
→ See [DIRECTORY_STRUCTURE.md](DIRECTORY_STRUCTURE.md)

## Common First Steps

### Making Your First Change

1. **Edit the frontend:**
   - Open `src/index.html` in your editor
   - Make a change (e.g., modify a color in the `<style>` section)
   - Save the file
   - The app will automatically reload with your changes!

2. **Test your change:**
   - Verify it looks correct in the application window
   - Try different features to ensure nothing broke

### Building Your First Installer

1. **Build the application:**
   ```bash
   npm run build
   ```
   
   Or use the quick script:
   ```bash
   quick-build.bat
   ```

2. **Find your installer:**
   - Windows: `src-tauri/target/release/bundle/msi/` or `nsis/`
   - macOS: `src-tauri/target/release/bundle/dmg/`
   - Linux: `src-tauri/target/release/bundle/deb/` or `rpm/`

3. **Test the installer:**
   - Install it on your system
   - Run the installed application
   - Verify all features work

## Project Structure Overview

```
astragalomancy/
├── src/                    # Frontend files (HTML, CSS, JS, images)
├── src-tauri/             # Backend files (Rust, Tauri config)
├── package.json           # Node.js configuration
├── quick-dev.bat          # Quick development script
├── quick-build.bat        # Quick build script
└── *.md                   # Documentation files
```

**Key Files:**
- `src/index.html` - Main application interface
- `src-tauri/tauri.conf.json` - Application configuration
- `src-tauri/src/main.rs` - Rust backend entry point

## Development Workflow

### Typical Session

1. **Start development server:**
   ```bash
   npm run dev
   ```

2. **Make changes to files in `src/`**

3. **Changes auto-reload in the application**

4. **Test your changes**

5. **Stop server with Ctrl+C**

### Before Committing

- [ ] Test the application works
- [ ] Verify all features function correctly
- [ ] Check for console errors
- [ ] Test dark mode toggle
- [ ] Verify help documentation loads

## Troubleshooting

### Application Won't Start

**Error: "cargo not found"**
- Install Rust: https://rustup.rs/
- Restart terminal

**Error: "node not found"**
- Install Node.js: https://nodejs.org/
- Restart terminal

**Error: Build fails**
- Check you have platform-specific dependencies
- See [SETUP.md](SETUP.md) for details

### First Build Takes Forever

**This is normal!**
- First build: 10-30 minutes (compiling Rust dependencies)
- Subsequent builds: 1-5 minutes
- Development mode: Much faster

### Images Don't Load

- Verify all PNG files are in `src/` directory
- Check file names match exactly (case-sensitive)
- Ensure `help_files/` directory is present

## Getting Help

### Documentation

1. **README.md** - Overview and features
2. **SETUP.md** - Environment setup
3. **BUILD_INSTRUCTIONS.md** - Building the app
4. **PROJECT_SUMMARY.md** - Technical details
5. **This file** - Quick start guide

### Community

- **Tauri Documentation**: https://tauri.app/
- **Tauri Discord**: https://discord.com/invite/tauri
- **Rust Documentation**: https://doc.rust-lang.org/

### Project Support

- Contact: Radius.Center
- Check documentation files
- Review code comments

## Key Commands Reference

### Development
```bash
npm install          # Install dependencies
npm run dev         # Start development server
quick-dev.bat       # Quick development start (Windows)
```

### Building
```bash
npm run build           # Build for current platform
npm run build:windows   # Build for Windows
npm run build:macos     # Build for macOS
npm run build:linux     # Build for Linux
quick-build.bat         # Quick build (Windows)
```

### Maintenance
```bash
cargo clean         # Clean Rust build (in src-tauri/)
npm install         # Reinstall dependencies
rustup update       # Update Rust
```

## Important Notes

### Icons
⚠️ **The project needs icons created!**
- Required in `src-tauri/icons/`
- See [BUILD_INSTRUCTIONS.md](BUILD_INSTRUCTIONS.md) for details
- Can use favicon.ico as a starting point

### First Build
⏱️ **Be patient with the first build!**
- Takes 10-30 minutes to compile Rust dependencies
- Subsequent builds are much faster
- This is normal for Rust/Tauri projects

### Development Mode
🔄 **Hot reload is enabled in dev mode**
- Changes to HTML/CSS/JS auto-reload
- No need to restart the server
- Very fast iteration cycle

## Success Checklist

You're ready to develop when:
- [ ] `npm run dev` opens the application
- [ ] You can enter a question and cast bones
- [ ] Results display with images and text
- [ ] Dark mode toggle works
- [ ] Help button opens documentation
- [ ] Changes to `src/index.html` auto-reload

## Next Steps

Now that you're set up:

1. **Explore the code** in `src/index.html`
2. **Try making a small change** and see it reload
3. **Read the help documentation** in the app
4. **Build an installer** with `npm run build`
5. **Review other documentation** for deeper understanding

## Welcome Aboard!

You're now ready to work with Astragalomancy! Whether you're using it for divination or developing new features, we hope you enjoy this ancient practice brought to modern technology.

**Happy divining! 🎲**

---

**Need more help?** Check the other documentation files or contact Radius.Center.
