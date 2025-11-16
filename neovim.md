# Neovim Configuration

A modern Neovim setup built with Lua and lazy.nvim plugin manager, inspired by [kickstart.nvim](https://github.com/hendrikmi/neovim-kickstart-config). This configuration provides a complete IDE-like experience with LSP support, autocompletion, fuzzy finding, file exploration, and more.

## 📁 Project Structure

```
.config/nvim/
├── init.lua                    # Main entry point
├── lazy-lock.json              # Plugin version lock file
└── lua/
    ├── core/
    │   ├── options.lua         # Editor settings and options
    │   └── keymaps.lua         # General keybindings
    └── plugins/
        ├── alpha.lua           # Dashboard/start screen
        ├── autocompletion.lua  # Completion engine (nvim-cmp)
        ├── autoformatting.lua  # Auto-formatting setup
        ├── bufferline.lua      # Buffer/tab line
        ├── colortheme.lua      # Color scheme
        ├── comments.lua        # Smart commenting
        ├── extras.lua          # Additional utilities
        ├── gitsigns.lua        # Git integration
        ├── harpoon.lua         # Quick file navigation
        ├── lsp.lua             # LSP configuration
        ├── lualine.lua         # Status line
        ├── neotree.lua         # File explorer
        ├── tabindent.lua       # Tab/indent guides
        ├── telescope.lua       # Fuzzy finder
        └── treesitter.lua      # Syntax highlighting
```

## ✨ Features

- **Plugin Management**: lazy.nvim for fast and efficient plugin loading
- **LSP Support**: Full Language Server Protocol integration with Mason
- **Autocompletion**: Intelligent code completion with nvim-cmp and LuaSnip
- **File Explorer**: Neo-tree for browsing and managing files
- **Fuzzy Finding**: Telescope for searching files, text, and more
- **Syntax Highlighting**: Tree-sitter for advanced syntax highlighting
- **Git Integration**: Gitsigns for inline git status
- **Quick Navigation**: Harpoon for lightning-fast file switching
- **Status Line**: Lualine for a beautiful status bar
- **Buffer Management**: Bufferline for easy buffer navigation
- **Auto-formatting**: Automatic code formatting on save

## 🚀 Installation

### Prerequisites

- Neovim >= 0.9.0
- Git
- A [Nerd Font](https://www.nerdfonts.com/) (optional, for icons)
- ripgrep (for Telescope live grep)
- Node.js and npm (for some LSP servers)
- `make` (for Telescope fzf-native)

### Steps

1. **Backup existing config** (if any):
```bash
mv ~/.config/nvim ~/.config/nvim.backup
mv ~/.local/share/nvim ~/.local/share/nvim.backup
```

2. **Clone this repository**:
```bash
git clone https://github.com/TheAK12/My-Setup.git
cp -r My-Setup/.config/nvim ~/.config/
```

3. **Launch Neovim**:
```bash
nvim
```

On first launch, lazy.nvim will automatically:
- Clone itself
- Install all plugins
- Set up LSP servers via Mason

4. **Wait for installation to complete**, then restart Neovim.

## ⌨️ Keymaps

### General

| Mode | Keymap | Description |
|------|--------|-------------|
| `n` | `<Space>` | Leader key |
| `n` | `<C-s>` | Save file |
| `n` | `<leader>sn` | Save without formatting |
| `n` | `<C-q>` | Quit file |
| `n` | `x` | Delete character (no copy) |

### Navigation

| Mode | Keymap | Description |
|------|--------|-------------|
| `n` | `<C-d>` | Scroll down and center |
| `n` | `<C-u>` | Scroll up and center |
| `n` | `n` | Next search result (centered) |
| `n` | `N` | Previous search result (centered) |
| `n` | `<C-k>` | Move to window above |
| `n` | `<C-j>` | Move to window below |
| `n` | `<C-h>` | Move to window left |
| `n` | `<C-l>` | Move to window right |

### Window Management

| Mode | Keymap | Description |
|------|--------|-------------|
| `n` | `<leader>v` | Split window vertically |
| `n` | `<leader>h` | Split window horizontally |
| `n` | `<leader>se` | Make splits equal size |
| `n` | `<leader>xs` | Close current split |
| `n` | `<Up>` | Resize window up |
| `n` | `<Down>` | Resize window down |
| `n` | `<Left>` | Resize window left |
| `n` | `<Right>` | Resize window right |

### Buffer Management

| Mode | Keymap | Description |
|------|--------|-------------|
| `n` | `<Tab>` | Next buffer |
| `n` | `<S-Tab>` | Previous buffer |
| `n` | `<leader>x` | Close buffer |
| `n` | `<leader>b` | New buffer |

### Tab Management

| Mode | Keymap | Description |
|------|--------|-------------|
| `n` | `<leader>to` | Open new tab |
| `n` | `<leader>tx` | Close current tab |
| `n` | `<leader>tn` | Next tab |
| `n` | `<leader>tp` | Previous tab |

### Visual Mode

| Mode | Keymap | Description |
|------|--------|-------------|
| `v` | `<` | Indent left (stay in visual) |
| `v` | `>` | Indent right (stay in visual) |
| `v` | `p` | Paste without overwriting register |

### Diagnostics

| Mode | Keymap | Description |
|------|--------|-------------|
| `n` | `[d` | Previous diagnostic |
| `n` | `]d` | Next diagnostic |
| `n` | `<leader>d` | Open diagnostic float |
| `n` | `<leader>q` | Open diagnostics list |

### Telescope (Fuzzy Finder)

| Mode | Keymap | Description |
|------|--------|-------------|
| `n` | `<leader>sf` | Search files |
| `n` | `<leader>sg` | Search by grep |
| `n` | `<leader>sw` | Search current word |
| `n` | `<leader>sd` | Search diagnostics |
| `n` | `<leader>sr` | Resume last search |
| `n` | `<leader>sh` | Search help |
| `n` | `<leader>sk` | Search keymaps |
| `n` | `<leader>ss` | Search select telescope |
| `n` | `<leader>s.` | Search recent files |
| `n` | `<leader><leader>` | Find buffers |
| `n` | `<leader>/` | Fuzzy search in current buffer |
| `n` | `<leader>s/` | Search in open files |

#### Telescope Navigation (Insert Mode)

| Mode | Keymap | Description |
|------|--------|-------------|
| `i` | `<C-k>` | Previous result |
| `i` | `<C-j>` | Next result |
| `i` | `<C-l>` | Open selected file |

### Neo-tree (File Explorer)

| Mode | Keymap | Description |
|------|--------|-------------|
| `n` | `<leader>e` | Toggle file explorer |
| `n` | `\\` | Reveal current file in tree |
| `n` | `<leader>ngs` | Git status window |

#### Inside Neo-tree

| Keymap | Description |
|--------|-------------|
| `<CR>` / `l` | Open file/folder |
| `<Space>` | Toggle node |
| `<Esc>` | Close window |
| `a` | Add file |
| `A` | Add directory |
| `d` | Delete |
| `r` | Rename |
| `y` | Copy to clipboard |
| `x` | Cut to clipboard |
| `p` | Paste from clipboard |
| `c` | Copy file |
| `m` | Move file |
| `q` | Close window |
| `R` | Refresh |
| `?` | Show help |
| `H` | Toggle hidden files |
| `/` | Fuzzy finder |
| `[g` | Previous git modified |
| `]g` | Next git modified |
| `S` | Open split |
| `s` | Open vsplit |
| `t` | Open in new tab |
| `w` | Open with window picker |

### LSP (Language Server)

| Mode | Keymap | Description |
|------|--------|-------------|
| `n` | `gd` | Go to definition |
| `n` | `gr` | Go to references |
| `n` | `gI` | Go to implementation |
| `n` | `gD` | Go to declaration |
| `n` | `<leader>D` | Type definition |
| `n` | `<leader>ds` | Document symbols |
| `n` | `<leader>ws` | Workspace symbols |
| `n` | `<leader>rn` | Rename symbol |
| `n` | `<leader>ca` | Code action |
| `n` | `<leader>th` | Toggle inlay hints |

### Autocompletion (Insert Mode)

| Keymap | Description |
|--------|-------------|
| `<C-n>` | Next completion item |
| `<C-p>` | Previous completion item |
| `<C-y>` | Accept completion |
| `<C-Space>` | Trigger completion |
| `<C-b>` | Scroll docs backward |
| `<C-f>` | Scroll docs forward |
| `<C-l>` | Jump to next snippet placeholder |
| `<C-h>` | Jump to previous snippet placeholder |
| `<Tab>` | Next item / expand snippet |
| `<S-Tab>` | Previous item |

### Harpoon (Quick Navigation)

| Mode | Keymap | Description |
|------|--------|-------------|
| `n` | `<leader>a` | Add file to harpoon |
| `n` | `<C-e>` | Open harpoon menu (Telescope) |
| `n` | `<C-z>` | Jump to file 1 |
| `n` | `<C-x>` | Jump to file 2 |
| `n` | `<C-c>` | Jump to file 3 |
| `n` | `<C-v>` | Jump to file 4 |
| `n` | `<C-S-P>` | Previous harpoon file |
| `n` | `<C-S-N>` | Next harpoon file |

### Misc

| Mode | Keymap | Description |
|------|--------|-------------|
| `n` | `<leader>lw` | Toggle line wrapping |

## 🔧 Configuration Details

### Editor Options

Key settings in `lua/core/options.lua`:

- **Line numbers**: Relative line numbers enabled
- **Clipboard**: System clipboard integration (`unnamedplus`)
- **Indentation**: 4 spaces, smart indent, auto-indent
- **Scroll**: 4 lines offset, 8 columns side offset
- **Search**: Smart case-insensitive search
- **Splits**: Open below and right
- **Swap files**: Disabled
- **Sign column**: Always visible

### Plugins

#### Core Plugins

1. **lazy.nvim** - Plugin manager
2. **nvim-lspconfig** - LSP configuration
3. **mason.nvim** - LSP/DAP/linter/formatter installer
4. **nvim-cmp** - Completion engine
5. **telescope.nvim** - Fuzzy finder
6. **nvim-treesitter** - Syntax highlighting
7. **neo-tree.nvim** - File explorer

#### UI Plugins

1. **lualine.nvim** - Status line
2. **bufferline.nvim** - Buffer line
3. **alpha-nvim** - Start screen
4. **nvim-web-devicons** - Icons

#### Utility Plugins

1. **harpoon** - Quick file navigation
2. **gitsigns.nvim** - Git integration
3. **Comment.nvim** - Smart commenting
4. **conform.nvim** - Auto-formatting
5. **friendly-snippets** - Snippet collection

### LSP Servers

Pre-configured LSP servers (auto-installed via Mason):

- **TypeScript/JavaScript**: `ts_ls`
- **Python**: `pylsp`, `ruff`
- **Lua**: `lua_ls`
- **Web**: `html`, `cssls`, `tailwindcss`
- **DevOps**: `dockerls`, `terraformls`, `yamlls`
- **Data**: `sqlls`, `jsonls`

### Formatters

- **Lua**: `stylua`

## 🎨 Customization

### Adding New Plugins

1. Create a new file in `lua/plugins/`, e.g., `lua/plugins/myplugin.lua`
2. Define the plugin spec:

```lua
return {
  'author/plugin-name',
  config = function()
    -- Plugin configuration here
  end,
}
```

3. Add to `init.lua`:

```lua
require('lazy').setup {
  -- ... other plugins
  require 'plugins.myplugin',
}
```

lazy.nvim will automatically install it on next startup.

### Changing Theme

Edit `lua/plugins/colortheme.lua` to use your preferred color scheme.

### Adding LSP Servers

1. Open `lua/plugins/lsp.lua`
2. Add your server to the `servers` table:

```lua
local servers = {
  -- ... existing servers
  your_server = {},
}
```

3. Restart Neovim - Mason will auto-install it

### Custom Keymaps

Add custom keybindings in `lua/core/keymaps.lua`:

```lua
vim.keymap.set('n', '<leader>custom', '<cmd>YourCommand<CR>', { desc = 'Description' })
```

## 📚 Learning Resources

- **Neovim Docs**: `:help` or visit [neovim.io](https://neovim.io/doc/)
- **lazy.nvim**: [GitHub](https://github.com/folke/lazy.nvim)
- **LSP Guide**: `:help lsp`
- **Telescope**: `:help telescope`
- **Treesitter**: `:help treesitter`

## 🐛 Troubleshooting

### Plugins not loading

```vim
:Lazy sync
```

### LSP not working

```vim
:Mason
```

Check if language servers are installed. Install manually if needed.

### Treesitter errors

```vim
:TSUpdate
```

### Clear cache and reinstall

```bash
rm -rf ~/.local/share/nvim
rm -rf ~/.local/state/nvim
nvim
```

## 🙏 Credits

- **Waybar Config**: [mehraharsh019/omarchy_custom_config](https://github.com/mehraharsh019/omarchy_custom_config/tree/main/.config/waybar)
- **Neovim Config Inspiration**: [hendrikmi/neovim-kickstart-config](https://github.com/hendrikmi/neovim-kickstart-config)
- **kickstart.nvim**: The original minimal Neovim configuration

## 📝 License

This configuration is provided as-is for personal use. Feel free to fork and modify to your needs.

## 🔗 Links

- **Repository**: [TheAK12/My-Setup](https://github.com/TheAK12/My-Setup)
- **Issues**: [Report bugs or request features](https://github.com/TheAK12/My-Setup/issues)

---

**Note**: This is a work in progress. Many enhancements will be added in the future.
