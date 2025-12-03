# Fallout3Terminal (fork)

This repository is a fork of the original project by fohtla: https://github.com/fohtla/Fallout3Terminal

Overview

- A retro-styled terminal interface inspired by Fallout's RobCo terminals, implemented as a Bash script.
- Lets you view, create, edit and delete "journal entries" stored under the `entries/` directory.
- Includes sound effects (.wav) and a typewriter-style display using `pv`.

Key features

- Browse entries and nested folders from `entries/`.
- Create and edit entries (the script opens `nano` for interactive editing by default).
- Delete entries with confirmation.
- Run small executable "holotape" games stored in `holotapes/`.

Dependencies (example for Debian/Ubuntu)

```bash
sudo apt update
sudo apt install -y bash pv sox fzf nano findutils sed procps
# 'play' comes from sox; 'pv' for typewriter effect; 'fzf' for interactive menus
```

Optional

- `cool-retro-term` can be used to show the interface in a retro window (optional).

Installation

```bash
git clone https://github.com/fohtla/Fallout3Terminal
cd Fallout3Terminal
chmod +x terminalscript
```

Run

```bash
# Run directly in your terminal
./terminalscript

# Or inside cool-retro-term (if installed)
cool-retro-term --fullscreen --noclose -e bash "$PWD/terminalscript"
```

Editing entries

- The script launches `nano` for entry creation and editing so you can navigate with the arrow keys.
- In `nano`: use the arrow keys to move between lines. Save & exit with `Ctrl+X`, then `Y` (if prompted) and `Enter`.
- Note: the original project also supports a non-interactive mode using `cat > file` which finishes on `Ctrl+D` (this overwrites the file).

Repository layout

- `terminalscript` — main Bash script.
- `entries/` — directory containing text entries; nested folders are supported.
- `greeterheader.txt`, `ui_*.wav` — UI and audio assets.
- `holotapes/` — place executables here to show them in the "Load Holotape" menu.

Customization

- To change the editor, edit the `terminalscript` and replace occurrences of `nano` with your preferred editor or command.
- To use Ctrl+D saving behavior, replace `nano "path"` calls with `cat >"path"` (user types content and presses `Ctrl+D` to finish). Be aware `cat` will overwrite existing files.

Fork note

- This is a fork of `fohtla/Fallout3Terminal`. See the project's Git history for specific local changes made in this fork.

License

- See `LICENSE.md` in this repository.

Contributing

- Feel free to open an issue or a pull request with improvements or bug fixes.

Enjoy the retro terminal!
