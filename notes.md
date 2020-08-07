---
layout: default
title: notes
---

## aliases:
```sh
    alias weather='LANG=ru curl wttr.in'
```

help по ключам - `curl wttr.in/:help`

.vim/ftdetect/vim_common.vim
```vim
au BufNewFile,BufRead .vim_common set filetype=vim
```

.vim/ftdetect/aliases.vim
```vim
au BufNewFile,BufRead .aliases set filetype=sh
```

.zshrc ++
```sh
[ -f ~/.aliases ] && source ~/.aliases
```

###aliases transmission:
_required_
`transmission-remote` --  -l, (-t)+remove,remove-and-delete
__default prefix: tr, -l &mdash; l, -r &mdash; r, r-a-d &mdash; d__
```sh
  alias trl='transmission-remote -l'
  alias trt='transmission-remote -t'
```

## mosaic check: functions
```sh
function chk_moz() {
  x=`ssh mozaic service --status-all|ag --nomultiline -o "\[ \+ \].*(apache2|mysql|postgres)"|wc -l|sed 's/^[\t ]*//g'`
  if [[ $x == '2' ]]
  then
    echo -e "\033[1;32mservice ok\033[0m"
  else
    echo $x
  fi
  return
}
function chk_moz_curl() {
  x=`curl -I -s --fail http://project.megarulez.ru/forums/ |head -1|ag --nomultiline -o "HTTP.+200 OK"|wc -l|sed 's/^[\t ]*//g'`
  if [[ $x == "1" ]]
  then
    echo -e "\033[1;32mrequest ok\033[0m"
  else
    echo $x
  fi
  return
}
function chk_moz_body() {
  x=`curl -s --fail http://project.megarulez.ru/forums/ |head -10|tail -1|ag --nomultiline -o "vBulletin 3.8.9 Beta 3"|wc -l|sed 's/^[\t ]*//g'`
  if [[ $x == "1" ]]
  then
    echo -e "\033[1;32mbody ok\033[0m"
  else
    echo $x
  fi
  return
}
function moz_up() {
  x=`ssh mozaic uptime`
  u=`echo "$x"|ag --nocolor -o '\b[0-9:]{5,8}\s+up\s+\K.+(?=,\s+\d+\s+user)'`
  l=`echo "$x"|ag --nocolor -o 'load\saverage:\s+\K[0-9., ]+$'`
  echo -e "\033[1;32mup: $u\nla: $l\033[0m"
  return
}
function moz_mem() {
  x=`ssh mozaic free -m`
  # awk -F ' ' '/^Mem:/ { print $7 }'
  f=`echo "$x"|awk -F ' ' '/^Mem:/ { print $7 }'`
  s=`echo "$x"|awk -F ' ' '/^Swap:/ { print $4 }'`
  echo -e "\033[1;32mmem avail: $f\nswap free: $s\033[0m"
  return
}
function moz() {
  chk_moz
  chk_moz_curl
  chk_moz_body
  moz_up
  moz_mem
}
```
## commons
```sh
alias notes="$EDITOR ~/notes"
```
