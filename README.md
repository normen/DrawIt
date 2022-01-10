# DrawIt.vim

Draw ASCII art in VIM

```
┌──────────┐        ┌──────┐        ╔═════╗
│VIM Plugin│--for-->│arrows│──and──>║boxes║
└──────────┘   |    └──────┘        ╚═════╝
            ┌──▼────┐ ^     ╲
            │drawing├─┘      and lines!
            └───────┘     
```

### Introduction
This is my fork of the fantastic [DrawIt](http://www.drchip.org/astronaut/vim/index.html#DRAWIT) vim plugin by DrChip.

### Fork changes
- removes the `<space>` mapping in favor of `<Leader>x` 
- adds `<shift-hjkl>` to draw
- fix mapping restoration
- fix utf erase bug
- updated documentation
- some fixes and cleanups (see `:h`)
- based on latest version 15a from DrChip.org

### Docs

**Use `:h drawit` to access the full help**

##### Mappings
  - `<Leader>di` - start DrawIt mode
  - `<Leader>ds` - stop DrawIt mode

To change the default mapping just map it otherwise:
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

