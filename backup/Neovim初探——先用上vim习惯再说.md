# 前言

之前虽然通过不断地练习和折磨逐渐掌握并熟悉了了Vim的键位，在听说了NeoVim的强大功能之后还是忍不住想要试试挑战一下使用NeoVim，因此在这里开个帖子记录一下NeoVim使用过程中遇到的情况和总结的经验。

---

# Windows

由于目前使用最多的操作系统仍然是Windows，因此我决定先从Windows开始——虽然Vim在Windows的状况比Linux要多，尤其是以两个操作系统所使用的换行符不同导致的一系列bug。

## 安装

对于Windows而言，只需要使用winget命令即可：

```powershell
winget install neovim.neovim
```

开启的方式与Linux一致：

```powershell
nvim
```

初步开启的界面和vim并没有太多的区别，甚至号召捐款的公益广告语也一样。

## 配置

由于neovim的配置有.vim和.lua两种语法，.vim文件的语法和vimrc基本一致，因此存储配置文件的位置也不同。在windows中，由于Windows自7（Vista）开始混乱地采用C:\users\\<用户名>\AppData这种方式来管理配置，因此neovim的配置文件存储位置也变成了

C:\users\\[username]\Appdata\Local\nvim目录，而配置文件的文件名则可以为:init.vim 或者init.lua

在开启nvim之后，还可以通过:echo stdpath('config') 来显示neovim的存储配置文件的目录

### .lua与.vim

两者可以互相转换，我将原来的.vimrc通过微软的copilot进行了转换，没有出现问题

```lua
-- 设置颜色主题
vim.cmd('colorscheme desert')

-- 基本设置
vim.opt.compatible = false
vim.opt.number = true
vim.opt.swapfile = false
vim.opt.encoding = 'utf-8'
vim.opt.fileencodings = { 'utf-8', 'gb18030' }
vim.opt.backspace = { 'eol', 'start', 'indent' }
vim.opt.laststatus = 2
vim.opt.cursorline = true
vim.opt.cursorcolumn = true
vim.opt.linebreak = true
vim.opt.autoindent = true
vim.opt.smartindent = true
vim.opt.ignorecase = true
vim.opt.smartcase = true
vim.opt.ruler = true
vim.opt.showcmd = true
vim.opt.showmode = true
vim.opt.clipboard:append { 'unnamed', 'unnamedplus' }
vim.opt.showmatch = true
vim.opt.incsearch = true
vim.opt.backup = false
vim.opt.autoread = true
vim.opt.wildmenu = true
vim.opt.wildmode = { 'longest:list', 'full' }
vim.opt.foldenable = false
vim.opt.tabstop = 4
vim.opt.softtabstop = 2
vim.opt.expandtab = true
vim.opt.shiftwidth = 4
vim.opt.mouse = 'a'

-- 自动命令
vim.api.nvim_create_autocmd({ 'BufNewFile', 'BufFilePre', 'BufRead' }, {
  pattern = '*.md',
  command = 'set filetype=markdown'
})

-- 启用插件和语法
vim.cmd('filetype plugin indent on')
vim.cmd('syntax on')

```

