# DrawIt.vim

Draw ASCII art in VIM

```
 ┌─────┐╔═════╗+------+
 │BOXES│║LINES║|ARROWS|
 └─────┘╚══╦══╝+---+--+
    │      ║       │
    │      ║   ┌───┘
    v      ▼   v
     *************     
 ****    DrawIt   **** 
*          in         *
 ****     VIM!    **** 
     *************     
```

### Introduction
This is my fork of the fantastic [DrawIt](http://www.drchip.org/astronaut/vim/index.html#DRAWIT) vim plugin by DrChip.

### Fork changes
- some fixes and cleanups (see below)
- Removes the `<space>` mapping in favor of `<Leader>x` 

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

### History
- **v2022-01-09**
  - remove cecutil
- **v2022-01-08**
  - fixed restoring key maps with special leaders (space)
  - fixed shift-left mapping restoring
- **v2021-12-28**
  - removed `<space>` mappings
  - added help hint about `g:drawit_mode`
  - added erase-fix from [rigelrozanski](https://github.com/rigelrozanski/DrawIt)
  - updated to the latest v15a from [DrChip](http://www.drchip.org/)
