<p align="center">
  <img src="assets/logo-text.svg" alt="Astryx" width="280" height="66" />
</p>

## Ghostty theme — for all the people who love to code in deep dark spaces.

The [Ghostty](https://ghostty.org) port of [Astryx for Zed](https://github.com/BrankoSlavkov/astryx), using the same terminal palette.

----------

## Install

1. Download the theme into Ghostty's themes folder:

   ```sh
   mkdir -p ~/.config/ghostty/themes
   curl -fsSL https://raw.githubusercontent.com/BrankoSlavkov/astryx-ghostty/main/themes/Astryx \
     -o ~/.config/ghostty/themes/Astryx
   ```

2. Add this line to your Ghostty config (`~/.config/ghostty/config.ghostty`; on macOS it may instead live at `~/Library/Application Support/com.mitchellh.ghostty/config.ghostty`). The theme file itself must stay in `~/.config/ghostty/themes`, even when your config is in Application Support:

   ```
   theme = Astryx
   ```

3. Reload the config (<kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>,</kbd> on macOS, <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>,</kbd> on Linux) or restart Ghostty.

Check the setup with `ghostty +validate-config`.

## Palette

| | Normal | Bright |
| --- | --- | --- |
| Black | `#0b0c0f` | `#6c6f93` |
| Red | `#e95678` | `#ec6a88` |
| Green | `#29d398` | `#00ffb3` |
| Yellow | `#fab795` | `#fbc3a7` |
| Blue | `#26bbd9` | `#3fc4de` |
| Magenta | `#ee64ac` | `#f075b5` |
| Cyan | `#59e1e3` | `#6be4e6` |
| White | `#d5d8da` | `#ffffff` |

Background `#0b0c0f`, foreground `#d5d8da`, cursor `#4ad0f5`, selection `#1f5287`.

## Credits

Astryx is inspired by [Celestial](https://github.com/apvarun/celestial-theme) (Horizon-derived).

## License

[MIT](LICENSE)
