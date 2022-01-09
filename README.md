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
`:h drawit`

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
