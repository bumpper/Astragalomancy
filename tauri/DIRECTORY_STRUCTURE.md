# Astragalomancy Directory Structure

This document provides a detailed overview of the project's directory structure and file organization.

## Root Directory

```
astragalomancy/
├── src/                          # Frontend source files
├── src-tauri/                    # Tauri backend files
├── node_modules/                 # Node.js dependencies (generated)
├── package.json                  # Node.js configuration
├── package-lock.json            # Dependency lock file (generated)
├── .gitignore                   # Git ignore rules
├── quick-dev.bat                # Quick development script
├── quick-build.bat              # Quick build script
├── README.md                     # User documentation
├── BUILD_INSTRUCTIONS.md         # Build guide
├── SETUP.md                      # Setup guide
├── PROJECT_SUMMARY.md            # Technical overview
├── START_HERE.md                 # Quick start guide
├── CHECKLIST.md                  # Development checklist
├── DIRECTORY_STRUCTURE.md        # This file
└── BUILD_STATUS.md               # Build status tracking
```

## Source Directory (`src/`)

Contains all frontend files that make up the user interface.

```
src/
├── index.html                    # Main application interface
├── help.html                     # Help documentation page
├── favicon.ico                   # Application favicon
│
├── 01-11111-Olympian-Zeus.png
├── 02-11113-Athena-Who-Judges.png
├── 03-11114-The-Fates.png
├── 04-33111-The-Eagle-of-Zeus.png
├── 05-61111-The-Great-Spirit.png
├── 06-11143-Tyche-Opportune-Chance.png
├── 07-33311-Nike-Goddess-of-Victory.png
├── 08-11144-Artemis-of-Bravrona.png
├── 09-11136-Dionysus-Bassareus.png
├── 10-11334-Zeus-the-King.png
├── 11-11164-Hermes-of-the-Games.png
├── 12-11344-The-Melodious-Muse.png
├── 13-33331-Themis.png
├── 14-13334-Triton.png
├── 15-61133-Hermes-the-Guide.png
├── 16-44411-The-Benevolent-Spirit.png
├── 17-13344-Zeus-the-Savior.png
├── 18-11166-Zeus-Ammon.png
├── 19-33333-Benevolent-Fortune.png
├── 20-43611-Zeus-the-Guardian-of-Travelers.png
├── 21-63331-Hercules.png
├── 22-64411-Cybele.png
├── 23-13444-Prometheus.png
├── 24-33334-The-Fertile-Earth.png
├── 25-33344-Nereus.png
├── 26-13346-Artemis-of-the-Fields.png
├── 27-11366-Fruit-bearing-Demeter.png
├── 28-14444-Zephyrus.png
├── 29-66411-Adrasteia-She-Who-None-Can-Escape.png
├── 30-16443-Zeus-the-Thunderer.png
├── 31-44433-The-Supplicant-Deity.png
├── 32-63333-Benevolent-Time.png
├── 33-66133-Good-Hope.png
├── 34-44461-Zeus-the-Creator.png
├── 35-34444-Hermes-Who-Presides-Over-Gain.png
├── 36-63334-Victory-Trimumphant.png
├── 37-66611-The-Victorious-Sun.png
├── 38-44444-The-Heavenly-Fates.png
├── 39-43661-Nemesis.png
├── 40-63344-Zeus-The-Guardian-of-the-Dead.png
├── 41-66441-Demeter.png
├── 42-44463-The-Shining-Sun.png
├── 43-33366-Good-Fortune-Who-Delivers-Us-from-Pain.png
├── 44-16663-The-Renowned-Fates.png
├── 45-64444-Poseidon.png
├── 46-66433-Raging-Ares.png
├── 47-16664-Athena.png
├── 48-66443-Euphrosyne.png
├── 49-66633-Pythian-Apollo.png
├── 50-44466-Cronus-Who-Devours-His-Children.png
├── 51-46663-The-Shining-Month.png
├── 52-66661-The-Mother-of-the-gods.png
├── 53-66644-Zeus-of-the-Underworld.png
├── 54-66663-Celestial-Aphrodite.png
├── 55-66664-Damage.png
├── 56-66666-Hermes-of-the-Square.png
│
└── help_files/                   # Help documentation assets
    ├── colorschememapping.xml
    ├── filelist.xml
    ├── themedata.thmx
    ├── image001.png
    ├── image002.png
    ├── image003.gif
    ├── image004.png
    ├── image005.gif
    ├── image006.png
    ├── image007.gif
    ├── image008.gif
    ├── image009.png
    ├── image010.gif
    ├── image011.gif
    ├── image012.gif
    ├── image013.gif
    ├── image014.gif
    ├── image015.gif
    ├── image016.gif
    ├── image017.gif
    ├── image018.gif
    ├── image019.gif
    ├── image020.gif
    ├── image021.gif
    ├── image022.gif
    ├── image023.gif
    ├── image024.gif
    ├── image025.gif
    ├── image026.gif
    ├── image027.png
    ├── image028.gif
    ├── image029.gif
    ├── image030.gif
    ├── image031.gif
    ├── image032.gif
    ├── image033.gif
    ├── image034.gif
    ├── image035.gif
    ├── image036.gif
    ├── image037.gif
    ├── image038.gif
    ├── image039.gif
    ├── image040.gif
    ├── image041.gif
    ├── image042.gif
    ├── image043.gif
    ├── image044.gif
    ├── image045.gif
    ├── image046.gif
    ├── image047.gif
    ├── image048.gif
    ├── image049.gif
    ├── image050.gif
    ├── image051.gif
    ├── image052.gif
    ├── image053.gif
    ├── image054.gif
    ├── image055.gif
    ├── image056.gif
    ├── image057.gif
    ├── image058.gif
    ├── image059.gif
    ├── image060.gif
    └── image061.gif
```

### File Descriptions

#### `index.html`
- Main application interface
- Contains HTML structure, CSS styles, and JavaScript logic
- Self-contained single-page application
- Includes dark mode toggle and divination system

#### `help.html`
- Comprehensive help documentation
- Explains the divination system
- Provides usage instructions
- Includes historical context

#### `favicon.ico`
- Browser/application icon
- Displayed in window title bar
- Used as fallback icon

#### Divination Images (56 PNG files)
- Format: `##-#####-Name.png`
- First number: Result number (01-56)
- Five digits: Bone combination (e.g., 11111, 33344)
- Name: Associated deity or concept
- Used to display divination results

#### `help_files/`
- Supporting files for help documentation
- Images and formatting files
- Generated from Word document

## Tauri Directory (`src-tauri/`)

Contains all backend files for the Tauri application.

```
src-tauri/
├── src/                          # Rust source code
│   ├── main.rs                  # Application entry point
│   └── lib.rs                   # Library code
│
├── capabilities/                 # Permission configuration
│   └── default.json             # Default permissions
│
├── icons/                        # Application icons (to be created)
│   ├── 32x32.png               # Small icon
│   ├── 128x128.png             # Medium icon
│   ├── 128x128@2x.png          # Retina icon
│   ├── icon.icns               # macOS icon bundle
│   └── icon.ico                # Windows icon
│
├── target/                       # Build output (generated)
│   ├── debug/                   # Debug builds
│   └── release/                 # Release builds
│       └── bundle/              # Installers
│           ├── msi/            # Windows MSI
│           ├── nsis/           # Windows NSIS
│           ├── deb/            # Linux DEB
│           ├── rpm/            # Linux RPM
│           ├── dmg/            # macOS DMG
│           └── macos/          # macOS APP
│
├── gen/                          # Generated files (generated)
├── Cargo.toml                    # Rust dependencies
├── Cargo.lock                    # Dependency lock file (generated)
├── tauri.conf.json              # Tauri configuration
├── build.rs                      # Build script
└── .gitignore                   # Rust build artifacts
```

### File Descriptions

#### `src/main.rs`
- Rust application entry point
- Initializes Tauri application
- Configures plugins and features
- Minimal boilerplate code

#### `src/lib.rs`
- Rust library code
- Currently minimal
- Can be extended with custom commands

#### `capabilities/default.json`
- Permission configuration
- Defines what the application can access
- Currently allows core features and shell commands

#### `icons/` (To Be Created)
- Application icons for all platforms
- Required for building installers
- Multiple sizes and formats needed

#### `Cargo.toml`
- Rust package configuration
- Lists dependencies (Tauri, serde, etc.)
- Defines build optimizations
- Specifies package metadata

#### `tauri.conf.json`
- Main Tauri configuration
- Window settings (size, title, etc.)
- Bundle configuration (targets, icons)
- Security settings
- Build commands

#### `build.rs`
- Rust build script
- Runs before compilation
- Generates necessary code
- Minimal implementation

## Generated Directories

These directories are created during development and building:

### `node_modules/`
- Node.js dependencies
- Created by `npm install`
- Contains @tauri-apps/cli
- Ignored by git

### `src-tauri/target/`
- Rust build output
- Debug builds during development
- Release builds for distribution
- Contains compiled binaries and installers
- Ignored by git

### `src-tauri/gen/`
- Generated Tauri code
- Created during build process
- Ignored by git

## Documentation Files

### User Documentation
- **README.md**: Overview, features, installation, usage
- **Help.html**: In-app help system

### Developer Documentation
- **BUILD_INSTRUCTIONS.md**: Detailed build process
- **SETUP.md**: Environment setup guide
- **PROJECT_SUMMARY.md**: Technical overview
- **START_HERE.md**: Quick start guide
- **CHECKLIST.md**: Development checklist
- **DIRECTORY_STRUCTURE.md**: This file
- **BUILD_STATUS.md**: Build tracking

## Build Scripts

### `quick-dev.bat`
- Windows batch script
- Installs dependencies
- Starts development server
- Opens application window

### `quick-build.bat`
- Windows batch script
- Installs dependencies
- Builds production version
- Creates installers

## Configuration Files

### `package.json`
- Node.js project configuration
- Scripts for dev, build, etc.
- Dependencies (@tauri-apps/cli)
- Project metadata

### `.gitignore`
- Git ignore rules
- Excludes node_modules
- Excludes build artifacts
- Excludes generated files

## File Naming Conventions

### Divination Images
Format: `##-#####-Name.png`
- `##`: Two-digit result number (01-56)
- `#####`: Five-digit bone combination
- `Name`: Deity or concept name (kebab-case)
- Extension: `.png`

Example: `01-11111-Olympian-Zeus.png`

### Help Files
Format: `image###.ext`
- `image`: Prefix
- `###`: Three-digit number (001-061)
- `.ext`: File extension (.png or .gif)

Example: `image001.png`

### Documentation Files
- All caps with underscores: `BUILD_INSTRUCTIONS.md`
- Or title case: `README.md`
- Markdown format: `.md`

## File Sizes

### Typical Sizes
- **index.html**: ~50 KB (with embedded CSS/JS)
- **help.html**: ~100 KB (with embedded content)
- **Divination PNGs**: ~50-200 KB each
- **Help images**: ~5-50 KB each
- **favicon.ico**: ~15 KB
- **Total src/**: ~10-15 MB

### Build Outputs
- **Debug binary**: ~50-100 MB
- **Release binary**: ~5-10 MB
- **MSI installer**: ~5-8 MB
- **NSIS installer**: ~5-8 MB
- **DMG**: ~5-8 MB
- **DEB**: ~5-8 MB

## Path References

### In HTML Files
- Relative paths from `src/` directory
- Images: `./01-11111-Olympian-Zeus.png`
- Help files: `./help_files/image001.png`
- Help page: `./help.html`

### In Tauri Config
- Relative to project root
- Frontend: `../src`
- Icons: `icons/32x32.png`

### In Build Output
- Absolute paths in `src-tauri/target/`
- Platform-specific bundle directories

## Important Notes

### Case Sensitivity
- File names are case-sensitive on Linux/macOS
- Use exact case in all references
- Windows is case-insensitive but preserves case

### Path Separators
- Use forward slashes `/` in HTML/CSS/JS
- Use backslashes `\` in Windows batch files
- Tauri handles path conversion automatically

### Asset Loading
- All assets served through Tauri's asset protocol
- No external URLs required
- Fully offline capable

## Summary

The project follows a clean, organized structure:
- **Frontend** (`src/`): All user-facing files
- **Backend** (`src-tauri/`): Rust/Tauri configuration
- **Documentation**: Comprehensive guides
- **Scripts**: Quick development and build tools

This structure makes it easy to:
- Find and edit files
- Understand the project layout
- Build and distribute the application
- Maintain and extend functionality
