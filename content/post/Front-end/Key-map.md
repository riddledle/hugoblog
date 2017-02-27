+++
date = "2016-09-08T19:42:29+08:00"
description = "Vim快捷键的映射"
title = "Vim Key Map"

+++

# [Mapping keys in Vim](http://vim.wikia.com/wiki/Mapping_keys_in_Vim_-_Tutorial_(Part_1))
This is the official tutorial for key mappings in vim.

## Modes
Vim has many modes,these 3 and their corresponding mappings are basic:

```

 n Normal mode - ':nmap' or ':nnoremap' 
 i Insert mode - ':imap' or ':inoremap' 
 v Visual and select mode - ':vmap' or 'vnoremap' 
 
 ```

## The general syntax 

```

 {cmd}  {attr}  {lhs}  {rhs} 
 
```

## Storing the key maps

For permanent use just store the map commands in $HOME/.vimrc(or $HOME/_vimrc or $VIM/_vimrc)file.

 - NOTICE:No need to add the prefix ':' character

## Map `''`
Since the '' character is used to seperate a map command from the next command,there're 3 ways to include a '' in {rhs}

```

     <Bar>  - works when '<'is not in 'cpoptions' 
     \\    - works when 'b' is not in 'cpoptions' 
     ^V    - always works,in Vim and Vi 
 
 ```

(here ^V stands for CTRL-V; to get one CTRL-V you have to type it twice; you
cannot use the <> notation "<C-V>" here).

All three work when you use the default setting for 'cpoptions'.

See [:help map-which-keys](http://vimdoc.sourceforge.net/htmldoc/map.html#map-which-keys) for more.
