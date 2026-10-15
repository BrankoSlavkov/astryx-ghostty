# Astryx for Ghostty: agent notes

Theme name `Astryx`. Theme file `themes/Astryx` (no extension; the name is case-sensitive).

## Configure Astryx for a user

1. **Install the theme file** at `$XDG_CONFIG_HOME/ghostty/themes/Astryx` (default `~/.config/ghostty/themes/Astryx`). Copy it from this repo, or download it:
   `curl -fsSL https://raw.githubusercontent.com/BrankoSlavkov/astryx-ghostty/main/themes/Astryx -o ~/.config/ghostty/themes/Astryx`
   Ghostty looks up theme names only in that folder and in its bundled themes. It does **not** look next to a config in `~/Library/Application Support/com.mitchellh.ghostty/` (tested on Ghostty 1.3.1).
2. **Find the config file.** Candidates:
   - `~/.config/ghostty/config.ghostty`
   - `~/.config/ghostty/config`
   - on macOS, `~/Library/Application Support/com.mitchellh.ghostty/config.ghostty` or `config` next to it

   Edit whichever exists. Ghostty loads all of them, so check that none of the others sets a different `theme`. If none exists, create `~/.config/ghostty/config.ghostty`.
3. **Set `theme = Astryx`.** Replace an existing `theme =` line rather than adding a second one, and leave other lines alone. To follow the system light/dark mode, use `theme = light:<other theme>,dark:Astryx`. In that form, `+validate-config` resolves only the light theme, so a typo in the dark name passes validation. Check that the file exists yourself.
4. **Verify.** Run `ghostty +validate-config`; no output means OK. Then run `ghostty +show-config | grep -E '^(theme|background) ='`, which should print `theme = Astryx` and `background = #0b0c0f`. On macOS the binary is `/Applications/Ghostty.app/Contents/MacOS/ghostty` if `ghostty` isn't on `PATH`.
5. **Reload.** An agent can't trigger this. Tell the user to press Cmd+Shift+, on macOS or Ctrl+Shift+, on Linux, or to restart Ghostty. Open windows keep the old colours until then.

Undo: remove the `theme = Astryx` line and delete `~/.config/ghostty/themes/Astryx`.

## Maintaining

- The palette comes from the Zed theme (`themes/astryx.json` in https://github.com/BrankoSlavkov/astryx). Change it there first, then mirror it here:
  - `palette` 0–7 come from `terminal.ansi.<colour>`, and 8–15 from `terminal.ansi.bright_<colour>`.
  - `background` and `foreground` come from `terminal.background` and `terminal.foreground`.
  - `cursor-color` comes from `players[0].cursor`.
- Ghostty colours have no alpha channel. Blend Zed's alpha colours over the background `#0b0c0f`. For example, `selection-background` is Zed's `#3399ff7f` blended, which gives `#1f5287`.
- After editing, validate the file directly: write a temp config containing `theme = /absolute/path/to/themes/Astryx`, then run `ghostty +validate-config --config-file=<temp config>`. Unknown keys fail validation, so stick to standard theme keys.
- Keep the README's palette table and install steps in sync with the theme file.
