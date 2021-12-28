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
- Removes the `<space>` mapping in favor of `<Leader>x` 
- Adds the erase-fix for utf-mode from [rigelrozanski](https://github.com/rigelrozanski/DrawIt)

### Docs
`:h drawit`

### History
- **v2021-12-28**
  - removed `<space>` mappings
  - added help hint about `g:drawit_mode`
  - added erase-fix from [rigelrozanski](https://github.com/rigelrozanski/DrawIt)
  - updated to the latest v15a from [DrChip](http://www.drchip.org/)
