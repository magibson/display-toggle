# Display Toggle 🖥️

A free, open-source Mac menu bar app to disconnect and reconnect your external display — without unplugging the cable.

![macOS](https://img.shields.io/badge/macOS-13%2B-blue) ![License](https://img.shields.io/badge/license-MIT-green) ![Swift](https://img.shields.io/badge/Swift-5.9-orange)

<!-- TODO: Add GIF demo here -->
<!-- ![Demo](demo.gif) -->

## Why?

Sometimes you want to use just your MacBook screen without unplugging your monitor. Maybe you're:

- 🎮 Gaming and don't want the extra display
- 🎬 Watching something fullscreen on your laptop
- 💻 Moving to the couch but still docked
- 🔋 Saving battery by turning off the external

BetterDisplay Pro charges **$22** for this feature. Display Toggle does it for **free**.

## Install

### Option 1: Download the App

1. Go to [Releases](https://github.com/mattgibson/display-toggle/releases)
2. Download `DisplayToggle.zip`
3. Unzip and drag to Applications
4. Right-click → Open (first time only, to bypass Gatekeeper)

### Option 2: Build from Source

**Prerequisites:** [displayplacer](https://github.com/jakehilborn/displayplacer)

```bash
brew install displayplacer
```

**Build & run:**

```bash
cd DisplayToggleApp
swift build -c release
cp .build/release/DisplayToggle /usr/local/bin/
```

Or just run directly:

```bash
swift run
```

### Option 3: Shell Script (No Build Required)

If you just want the functionality without the menu bar app:

```bash
# Make it executable
chmod +x display-toggle.sh

# Toggle your external display
./display-toggle.sh

# Or use specific commands
./display-toggle.sh off    # Disconnect external
./display-toggle.sh on     # Reconnect external
./display-toggle.sh list   # Show connected displays
```

## How It Works

Display Toggle uses [displayplacer](https://github.com/jakehilborn/displayplacer) under the hood to enable/disable your external display. It saves your display configuration so when you reconnect, everything goes back exactly where it was — resolution, position, arrangement, all of it.

**Menu bar app:**
- Click the monitor icon in your menu bar
- Green dot = external display active
- Orange dot = external display disconnected
- One click to toggle

**What it saves:**
- Display arrangement
- Resolution settings
- Position configuration
- Which display was disconnected

## Requirements

- macOS 13 (Ventura) or later
- [displayplacer](https://github.com/jakehilborn/displayplacer) (`brew install displayplacer`)
- An external display

## FAQ

**Will this work with multiple external monitors?**
Currently it toggles the first external display it finds. Multi-monitor support is planned.

**Is this safe?**
Yes. It's the same as unplugging your monitor and plugging it back in — just without getting up.

**Why not just use BetterDisplay?**
BetterDisplay is great software with tons of features. If you just need display toggling though, this does that one thing for free.

## Contributing

PRs welcome! This is a simple app — if you see something that could be better, go for it.

## License

MIT — do whatever you want with it.

## Credits

- [displayplacer](https://github.com/jakehilborn/displayplacer) by Jake Hilborn — the real hero
- Built by [Matt Gibson](https://github.com/mattgibson)
