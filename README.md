# Tmux Config

My personal tmux configuration, tuned for efficiency and left-hand ergonomics.

## Quick Start

```bash
git clone https://github.com/<your-username>/dotfiles.git
cp dotfiles/tmux.conf ~/.tmux.conf
tmux source ~/.tmux.conf
```

Or symlink it:

```bash
ln -sf $(pwd)/tmux.conf ~/.tmux.conf
tmux source ~/.tmux.conf
```

## Keybindings

All shortcuts use the modified prefix key **Ctrl+a** (default is Ctrl+b).

| Shortcut | Action |
|---|---|
| `C-a + -` | Split window vertically |
| `C-a + \|` | Split window horizontally |
| `C-a + j` | Move to left pane |
| `C-a + k` | Move to bottom pane |
| `C-a + i` | Move to top pane |
| `C-a + l` | Move to right pane |
| `C-a + r` | Rename current window |
| `C-a + R` | Rename current session |

## Configuration Breakdown

### Prefix Key

Changed from `C-b` to `C-a` to reduce left pinky strain.

### Pane & Window Indexing

Both start from `1` instead of `0` — more intuitive for daily use.

### Mouse & Clipboard

- **mouse on**: Click to switch panes, drag to resize
- **set-clipboard on**: Proper clipboard integration
- **history-limit 50000**: Keep 50k scrollback lines

### Pane Splitting

`-` for vertical split (top/bottom), `|` for horizontal split (left/right) — matches the visual layout.

### Plugins

Managed by **[tpm](https://github.com/tmux-plugins/tpm)**:

- **[tmux-resurrect](https://github.com/tmux-plugins/tmux-resurrect)** — persist and restore sessions, windows, panes, and working directories.

#### Installing plugins

```bash
# Install tpm first
git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm

# Then in tmux, press:
# C-a + I   → install all plugins
```

#### Restoring a session

```
# Save:   C-a + Ctrl-s
# Restore: C-a + Ctrl-r   (after restarting tmux)
```
