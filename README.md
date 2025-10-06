# Neovim — The Config

Welcome to a small, opinionated, and slightly cheeky Neovim config. Drop this into `~/.config/nvim` (or point Neovim there) and enjoy a comfy editing experience with:
- Treesitter highlighting
- Telescope-powered file search
- Harpoon for quick-project navigation
- LSP + completion for a tasty dev UX
- A chill Nord color theme with optional transparency

Quick start
1. Clone this repo into your Neovim config folder:
   git clone (https://github.com/WambuiGrace/neovim-configs.git) ~/.config/nvim
2. Open Neovim. The included bootstrap will try to install `lazy.nvim` automatically:
   - See [`config.lazy-config`](lua/config/lazy-config.lua) for the bootstrap logic.
3. Let Lazy install plugins, then restart Neovim.

What’s in this config
- Entry point: [init.lua](init.lua) — loads the modules:
  - [`config.options`](lua/config/options.lua)
  - [`config.keybinds`](lua/config/keybinds.lua)
  - [`config.lazy-config`](lua/config/lazy-config.lua)

Plugins (notable)
- Colors / UI:
  - [lua/plugins/colors.lua](lua/plugins/colors.lua) — Nord theme and lualine. Notable helper: [`enable_transparency`](lua/plugins/colors.lua).
- Fuzzy finder:
  - [lua/plugins/telescope.lua](lua/plugins/telescope.lua) — Telescope bindings (leader+ff, leader+fg, leader+fb, leader+fh).
- Harpoon:
  - [lua/plugins/harpoon.lua](lua/plugins/harpoon.lua) — Harpoon integration with a Telescope helper: [`toggle_telescope`](lua/plugins/harpoon.lua).
- Treesitter:
  - [lua/plugins/treesitter.lua](lua/plugins/treesitter.lua)
- LSP & completion:
  - [lua/plugins/lsp.lua](lua/plugins/lsp.lua) — LSP, mason, cmp, luasnip and related config.
- Misc one-liners:
  - [lua/plugins/oneliners.lua](lua/plugins/oneliners.lua)

Keybindings (highlights)
- Leader (space) + cd → file explorer (configured in [lua/config/keybinds.lua](lua/config/keybinds.lua))
- Leader + ff / fg / fb / fh → Telescope find files / live grep / buffers / help
  (see [lua/plugins/telescope.lua](lua/plugins/telescope.lua))
- Leader + a → Harpoon add
- Ctrl-e → Harpoon quick menu
- Ctrl-p / Ctrl-n → Harpoon prev / next
  (see [lua/plugins/harpoon.lua](lua/plugins/harpoon.lua))
- LSP helpers (hover, goto definition, rename, format, etc.) are attached when an LSP starts — see [lua/plugins/lsp.lua](lua/plugins/lsp.lua)

Files in the workspace
- [init.lua](init.lua)
- [lua/config/options.lua](lua/config/options.lua)
- [lua/config/keybinds.lua](lua/config/keybinds.lua)
- [lua/config/lazy-config.lua](lua/config/lazy-config.lua)
- [lua/plugins/colors.lua](lua/plugins/colors.lua)
- [lua/plugins/harpoon.lua](lua/plugins/harpoon.lua)
- [lua/plugins/lsp.lua](lua/plugins/lsp.lua)
- [lua/plugins/oneliners.lua](lua/plugins/oneliners.lua)
- [lua/plugins/telescope.lua](lua/plugins/telescope.lua)
- [lua/plugins/treesitter.lua](lua/plugins/treesitter.lua)

Tweaks & tips
- Toggle transparency by calling the helper in [lua/plugins/colors.lua](lua/plugins/colors.lua): [`enable_transparency`](lua/plugins/colors.lua).
- Harpoon’s Telescope integration lives in [lua/plugins/harpoon.lua](lua/plugins/harpoon.lua): [`toggle_telescope`](lua/plugins/harpoon.lua).
- To add more plugins, drop files into `lua/plugins/` (each file should return a plugin spec) and they will be picked up by the lazy setup (see [`config.lazy-config`](lua/config/lazy-config.lua)).

Have fun, hack safely, and may your edits always be fast and reversible.