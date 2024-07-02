# Introductions
I made this repository to study how to use Neovim.

# Neovim
- Vim is a text editor tool that supports advanced functions through lots of plugins.
- The shortcut keys are the same as Vim, but can be customized through key mappings.

## Nvim Start
### Install Neovim
[Home-Neovim](https://neovim.io/)

```
# Open tutorial
:help nvim

# Open Neovim
nvim
```

## Plugin Manager
- vim-plugin
- lazy.nvim
- etc.

## Folder Tree
- Windows
    - AppData/Local/nvim/
        - config/
        - plugins/
        - utils/
- Linux
    - ~/.configs/nvim/
        - config/
        - plugins/
        - utils/
- Mac

## Major Plugins
- `indent-blankline`
    - [Indent guides for Neovim](https://github.com/lukas-reineke/indent-blankline.nvim)

- `autopairs`
    - [Autopairs for Neovim](https://github.com/windwp/nvim-autopairs)

- `comment`
    - [Comment for Neovim](https://github.com/numToStr/Comment.nvim)
    - Normal mode
        - gcc: Toggles current line comment
        - {count} gcc: Toggles given the number of lines comment
        - gcb: Toggle current block comment
    - Visual mode
        - gc: Toggle current line comment
        - gb: Toggle current block comment

- `markdown`
    - [Markdown Viewer for Neovim](https://github.com/MeanderingProgrammer/markdown.nvim?tab=readme-ov-file#setup)

- `obsidian`
    - [Obsidian plugin for Neovim](https://github.com/epwalsh/obsidian.nvim)
    - Before you start this plugin, please set the default vaults for obsidian.
        - In my case, I made `~/vaults/obsi/` for default directory.

- `lualine`
    - [Statusline plugin for Neovim](https://github.com/nvim-lualine/lualine.nvim)

- `neo-tree`
    - [Manage the file system with tree structures for Neovim](https://github.com/nvim-neo-tree/neo-tree.nvim)
    - Basically, it can handle three sources. One is a "file system", another is a "buffers", which is a list of recently used files, and the other is a "git status". 
    - The "file system" gives you the same functionality as Windows Explorer.
    - The "buffers" allows you to view and move recently used and opened files at a glance.
        - If you want to move quickly between buffers, I recommend setting keymp ":bp\<CR>" and ":bn\<CR>" to something.
        - In my case, I set both to  "\<C-left>" and "\<C-right>" respectively.
    - The "git-status" provides the convenience of performing  "git add/git commit/git push/git rever/ etc."
        - If you need basit git functionality, you don't need to install any other plugins for neovim.

- `telescope`
    - [Find, Filter, Preview, Pick for Neovim](https://github.com/nvim-telescope/telescope.nvim)
    - To use telescope well, you should have a program called [`ripgrep`](https://github.com/BurntSushi/ripgrep?tab=readme-ov-file#installation)
    - Major functions
        - Find Files
        - Find strings (Live grep)
        - Find words under cursor (Find word)
        - Find buffers (buffers)
        - Find helper (Help) 
    - Support Quickfix
        - You don't need to memorize all positions you found.
        - You can select a list of position in "Live grep" using "Tab"
        - If you choose, "+" mark will be annotated in front of selected list.
        - `<Ctl-q>`: Add all itmes to Quickfixlist
        - `<Alt-q>`: Add selected items to Quickfixlist

- `treesitter`
    - [Provide the syntax highlight for Neovim](https://github.com/nvim-treesitter/nvim-treesitter)

- `noice`
    - [Provide messages,cmdline and the popupmenu for Neovim](https://github.com/folke/noice.nvim)
    - "Noice" is good plugin but I prefer not to use it. So I remvoed it.

- `git-stuff`
    - [Git wrapper for Neovim](https://github.com/tpope/vim-fugitive)
    - [Provide straightforward interface for Git in Neovim](https://github.com/kdheepak/lazygit.nvim)

- `LSP Zero`:   
    - [Collection of LSP packages with lazy](https://github.com/VonHeikemen/lsp-zero.nvim/blob/v3.x/doc/md/guides/lazy-loading-with-lazy-nvim.md)
> `lsp-zero` is the collection of LSP packages, which is analyzing your code to tell you what to do.
> The collections are as follows:
>    - Neovim - LSPconfig (nvim-lspconfig): Bridges Neovim with LSPconfig  
>    - Mason - LSPconfig (mason-lspconfig): Bridges Mason with LSPconfig
>    - Mason (mason): LSP pacakge manager for Neovim 
>       - Language Server Protocol (LSP):
>           - `lua-language-server`
>           - `markdown-oxide`
>           - `pyright`
>           - `ruff`
>           - `fortls`
>       - Debug Adapter Protocol (DAP): 
>           - `debugpy`
>       - Linter: Check the code and provide hints on how to correct the detected problems. 
>       - Formatter: Provide uniform coding style
>           - `stylua`
>           - `fprettify`
>    - Luasnip

- `cmp`
    - [Auto CoMPletion plugin for Neovim](https://github.com/hrsh7th/nvim-cmp)

- `none-ls`
    - [Inject Diagnostics/Code actions/Formatting/Hover/Completion to lsp](https://github.com/nvimtools/none-ls.nvim)
    - `Lua`
        - `stylua`
    - `Python` 
        - Linter like `mypy` or formatter like black needs to be set up to use`lsp.buf.*`. This repository provides this setups. 
    - `Fortran`
        - `findent`
        - `fprettify`

- `dap`
    - [Debug Adapter Protocol](https://github.com/mfussenegger/nvim-dap)
    - This repository provides python debbuger.

## Tips
- Broken fonts and icons
    - Make sure you have **"Nerd Fonts"**
    You can install just clicking `*.ttf` file.
    But I recommend installing as a tff **for all users**. [(Nerd Fonts)](https://www.nerdfonts.com/)
- LSP 
    - LSP like pyright are available through npm. On Windows, you can do this by installing the Node.js program. This can be installed via the following link
    [Download Node.js](https://nodejs.org/en/download/prebuilt-installer). You can install it through the Package Manager like windget, fnm, Brew or directly using a pre-built installer.
    - For python, I recommend installing `pyright (LSP)` and `ruff(LSP+Linter+Formatter)` through Mason.
- Buffers
    - Buffers are everything you've loaded before (in-memory texts).
    - It's like a pile of books on your desk.
    - Each buffer has a unique number. Thus you can always go to a specific buffer ":bufferN"
    - If you try to quit a modified file without saving, you will get anrror message. Vim will pull the file from the buffer into the current window.
    - Buffers has 3 states.
        - Active  : It is displayed in the current window.
        - Hiddne  : It is not displayed in the current window, and was previously loaded. 
        - Inactive: It is not displayed in the current window, and was previously loaded but closed. 
    - You can check buffers through command ":buffers, :ls, :files"
        - `:buffers[!] [flags]` / `:ls[!] [flags]` / `:files[!] [flags]`
        - When "!" is included command, it will show not only ordinary buffers but also unlisted buffers which is a kind of help documents or neotree systems or quickfix list.
            -`:buffers!`
        - `:buffers` shows list in buffers.
            - Buffer No. / Indicator / Path / Line No. of cursor
            - Each buffer has a unique number. Thus you can alwasy call each buffer with 
                - `:buffer N` or `:N<C-^>`
            - Indicator
                - `u` (unlisted buffer)
                - `%` (current buffer)
                - `#` (recently loaded buffer)
                - `a` (active buffer: loaded and displayed)
                - `h` (hidden buffer: loaded but invisible)
                - `+` (modified buffer)
                - `-` (immutable buffer)
                - `=` (readonly buffer)
                - ex)
                    - 1: %a and 2: a
                    - buffer 1 is displayed in window and cursor is in it.
                    - buffer 2 is displayed in window but cursor is not in.
        - `:bdelete N1 N2` delete a Nth buffer in buffers.
        - `:bufdo {cmd}` execute {cmd}
            - Also see `tabdo`,`argdo`,`windo`,`cdo`,`ldo`

- Quickfix list
    - It is list to save the location of searching pattern.
    - `:vim[grep] {pattern} {file}` add lists to quickfix list. 
        - `:vim {pattern} /usr/**`: find `{pattern}` in directory `/usr/` and add locations to quickfix list.
    - `:copen` opens a window to show the current list of searching patterns.
    - `:cn[ext]`,`:cp[revious]`, `:cfir[st]`, `:cla[st]` are used to navigae files in the quickfix list.
    - `:cdo s/foo/boo` are used to substitute words `foo` to `boo` in files of quickfilx list

- Registers
    - Coming soon.
## Review
- Same behavior as `VIM`
    - If you're a `CLI` user who is familiar with `VIM`, this is great.
    - Very difficult to learn for `GUI` users.
- High degree of freedom
    - The wide world of customization opens up a whole new world for those who want to customize their text editor.
- Compatibility with Windows
    - Lint or LSP for `nvim-cmp` requires `npm`, which is the package manager for Node js.
- I've relied on the work of many people, and I'm very grateful for their help.

## Reference
- [Neovim-starter](https://github.com/moong00n/neovim-starter)
- [lsp-zero.nvim introduction](https://lsp-zero.netlify.app/v3.x/introduction.html)
- [Dash board theme](https://github.com/goolord/alpha-nvim/discussions/16#discussioncomment-8419966)
