# pydoc.vim

## Intro
This plugin integrates the Python documentation view and search tool, `pydoc`, into Vim.
**IMPORTANT** **pydoc.vim is an ftplugin and has to be installed in your ftplugin directory.
Installing it in the plugin directory won't work**.

## Installation
[pathogen.vim](https://github.com/tpope/vim-pathogen)
```bash
git clone https://github.com/fs111/pydoc.vim ~/.vim/bundle/pydoc.vim
```

## Usage
You may view the documentation of a Python module or class by typing:
```vimscript
:Pydoc foo.bar.baz
```
Or search a word in the documentation by typing:
```vimscript
:PydocSearch foobar
```
Vim will split the current window to show the Python documentation found by
pydoc (the buffer is named '\_\_doc\_\_'). __The name may cause problems if you already have a file with the same name__.

pydoc.vim also allows you to view the documentation of the 'word' (see `:help
word`) under the cursor by pressing `<Leader>pw` or the 'WORD' (see `:help WORD`)
under the cursor by pressing `<Leader>pW`. This is very useful if you want to
jump to the docs of a module or class found by 'PydocSearch' or if you want
to see the docs of a module/class in your source code. Additionally, `K` is
mapped to show invoke pydoc when you are editing python files.

## FAQ
> How do I change the way pydoc.vim presents its results?
```vimscript
let g:pydoc_open_cmd = 'vsplit' " Split the current window vertically
let g:pydoc_open_cmd = 'newtab' " Open the doc in a new tab
```
---
> How do I disable highlighting on the search term?
```vimscript
let g:pydoc_highlight = 0
```
This is enabled by default, so place this in your .vimrc if you would like it disabled.

---
> How do I change the height of the pydoc window?
```vimscript
let g:pydoc_window_lines = [Insert Line Count]
```
