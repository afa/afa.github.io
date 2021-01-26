---
layout: default
title: Язык рисования графов dot
---
## Объявление

* ненаправленный граф -- graph
* направленный граф -- digraph
* подграф -- subgraph
* метка -- label, для графа, ноды или связи (последние -- в опциях, _[label=text]_)
* rankdir -- направление ранжирования нод, BT, LR, для графа
* для направленных графов связи рисуются `->`, для ненаправленных `--`
* не забывать в конце выражения точку с запятой
* `node[shape=record]; teacher [label = "{<f0> Teacher|<f1> \n  |<f2> \n   }"];` -- рисует ноду с записями

субграф, начинающийся с cluster_ -- выделяет подструктуру

[примеры на языке dot](http://dkhramov.dp.ua/opisanie-grafov-na-iazyke-dot)
[рисование графов с dot & graphviz](https://tonyballantyne.com/graphs.html)
[аттрибуты@graphviz.org](http://graphviz.org/doc/info/attrs.html)
