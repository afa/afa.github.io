---
layout: default
title: Записные мелочи
---
## ZSH мелочи, плагины

### начальная настройка

поставить `oh-my-zsh` -- [site](https://ohmyz.sh) [github](https://github.com/ohmyzsh/ohmyzsh)

### timer
показывает время выполнения команды
```sh
~/.zshrc
TIMER_THRESHOLD=10
# после какой задержки показывать чтобы не спамить
plugins=(... timer ...)
```

### подключение алиасов
аналогично подключать файлы в алиасы
```sh
~/.zshrc
[ -f ~/.aliases ] && source ~/.aliases
```
