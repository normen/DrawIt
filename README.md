# DrawIt.vim
```
╔══════════╗        ┌──────┐        ┌─────┐
║VIM Plugin║--for-->│arrows│──and──>│boxes│
╚══════════╝   |    └──────┘        └─────┘
            ┌──▼────┐ ^     ╲
            │drawing├─┘      and lines!
            └───────┘     
```

### Introduction
This is my fork of the fantastic [DrawIt](http://www.drchip.org/astronaut/vim/index.html#DRAWIT) vim plugin by DrChip.

#### Fork changes
- removes the `<space>` mapping in favor of `<Leader>x` 
- adds `<shift-hjkl>` and `<shift-yubn>` to draw
- fixes for known bugs (see `:h drawit-history`)
- updated documentation
- based on latest version 15a from DrChip.org

### Docs

**Use `:h drawit` to access the full help**

#### Install

Using [vim-plug](https://github.com/junegunn/vim-plug):
```
  Plug 'normen/DrawIt'
```

#### Setup
##### Mappings
  - `<Leader>di` - start DrawIt mode
  - `<Leader>ds` - stop DrawIt mode

To change/free the default mapping just map these functions otherwise, the defaults won't be used.
```
  map <Leader>dr <Plug>DrawItStart
  map <Leader>dx <Plug>DrawItStop
```

##### Options

To always start out in utf-single-line mode set
```
  let g:drawit_mode = 'S'
```

##### Statusline

To embed the DrawIt status in a statusline plugin use this function:
```
  function DrawItMode()
    if !exists("b:dodrawit") | return '' | endif
    return b:dodrawit && b:di_erase ? "ERASE" : b:dodrawit ? "DRAW" : ""
  endfunction
```

Then e.g. for [lightline]() use:
```
let g:lightline = { 
  \   'left': [
  \             [ 'mode', 'paste', 'drawit_mode'],
  (....)
  \           ],
  \ 'component_function': {
  \   'drawit_mode': 'DrawItMode',
  \ },
\ }
```

