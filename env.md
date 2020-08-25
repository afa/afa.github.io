---
layout: default
title: Разворачивание рабочего окружения
---
# Рабочее окружение
## десктопы

### shell

zsh + oh-my-zsh

plugins:

__общего назначения__

* timer
* git
* git-flow

__рельсы__

* rails
* bundler
* rbenv

терминалом работают terminator или guake

### графика

* gnuplot -- рисовалка графиков

### тексты

редактор -- vim. обычно в ипостаси gvim, с включенной мышкой (`set mouse=a`)

грепалка -- ag (the silver searcher)

парсилка табличных данных -- awk

поиск файлов -- fzf, плюс интеграция с vim

конвертор видео в аудио -- ffmpeg, плюс функция на стандартный вызов

рисовалка графов -- graphview, дефолтно утилита `dot` (`dotty` для просмотра)

# others

* wiki, git based -- [gollum](https://github.com/gollum/gollum)

# порядок настройки, для вбивания в ansible

1. поставить систему
1. настроить сеть (wifi)
1. развернуть порты и поставить стартовый комплект
  * от рута
  * portsnap fetch
  * portsnap extract
  * cd /usr/ports/ports-mgmt/portmaster&&make install clean
  * portmaster shells/zsh sysutils/rcm devel/git
1. chsh afa, поставить шеллом zsh (/usr/local/bin/zsh для freebsd)
1. добавить пользователя в sudoers, переключиться на пользователя
