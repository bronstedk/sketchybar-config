# SketchyBar Setup with SbarLua

This repository contains my SketchyBar configuration using [SbarLua](https://github.com/FelixKratz/SbarLua).

## Requirements

* [Homebrew](https://brew.sh/) installed
* [SketchyBar](https://felixkratz.github.io/SketchyBar/)
* [SbarLua](https://github.com/FelixKratz/SbarLua)
* SF Pro font (via Homebrew)
* SketchyBar App Font (via Homebrew)

## Installation

1. **Install dependencies**:

   ```sh
   brew tap FelixKratz/formulae
   brew install sketchybar
   brew install --cask sf-symbols
   brew install --cask sf-pro
   brew install sketchybar-app-font
   ```

2. **Install SbarLua** (required for the `.so` file SketchyBar uses):

   ```sh
   git clone https://github.com/FelixKratz/SbarLua.git /tmp/SbarLua \
   && cd /tmp/SbarLua/ \
   && make install \
   && rm -rf /tmp/SbarLua/
   ```

   The shared object (`.so`) files are installed under:

   ```lua
   package.cpath = package.cpath .. ";/Users/" .. os.getenv("USER") .. "/.local/share/sketchybar_lua/?.so"
   ```

3. **Clone this repository** into your SketchyBar config directory:

   ```sh
   git clone https://github.com/bronstedk/sketchybar-config.git ~/.config/sketchybar
   ```

4. **Make sure `sketchybarrc` is executable**:

   ```sh
   chmod +x ~/.config/sketchybar/sketchybarrc
   ```

## Usage

Start SketchyBar with your configuration:

```sh
sketchybar --config ~/.config/sketchybar/sketchybarrc
```

## Uninstall

To remove the setup:

1. Remove the config:

   ```sh
   rm -rf ~/.config/sketchybar
   ```

2. Uninstall SbarLua:

   ```sh
   rm -rf ~/.local/share/sketchybar_lua
   ```

3. Uninstall fonts and SketchyBar:

   ```sh
   brew uninstall sketchybar
   brew uninstall --cask sf-symbols
   brew uninstall --cask sf-pro
   brew uninstall sketchybar-app-font
   ```

## Notes

* Fonts **SF Pro** and **SketchyBar App Font** are required for proper icons and symbols.
* `sketchybarrc` controls how SketchyBar loads and runs.
* Lua modules are loaded through SbarLua’s shared object (`.so`).
* Custom scripts can be placed in `~/.config/sketchybar`.

