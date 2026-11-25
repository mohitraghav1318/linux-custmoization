# linux-customization

My Linux desktop customization files.

## Ghostty + pywal ("Frosted Night")

Glass-style Ghostty terminal whose colors follow the wallpaper.

| File | Goes to |
|------|---------|
| `ghostty/config.ghostty` | `~/.config/ghostty/config.ghostty` |
| `wal/templates/ghostty-colors` | `~/.config/wal/templates/ghostty-colors` |

### Setup

```sh
sudo apt install -y pipx
pipx install pywal16
mkdir -p ~/.config/ghostty ~/.config/wal/templates
cp ghostty/config.ghostty ~/.config/ghostty/
cp wal/templates/ghostty-colors ~/.config/wal/templates/
wal -i /path/to/wallpaper.png
```

Reload Ghostty with `Ctrl + Shift + ,`. Re-run `wal -i <image>` whenever the wallpaper changes.

### Notes

- Ghostty loads `~/.cache/wal/ghostty-colors` through `config-file`, so colors persist across restarts.
- `background-blur` only has an effect when the compositor supports it (KDE Plasma, or GNOME 51+ with `ext-background-effect-v1`). On stock GNOME 50 the window is just transparent unless an extension like Blur my Shell is used.
- Font: JetBrainsMono Nerd Font (falls back to the default if missing).
