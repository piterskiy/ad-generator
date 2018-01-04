# Ad Generator #
* Contributors: [Airat Halitov](https://github.com/AiratHalitov)
* Requires at least: 3.8
* Tested up to: 4.9.1
* Stable tag: 1.0.2
* License: GPLv3
* License URI: http://www.gnu.org/licenses/gpl-3.0.html

Генератор объявлений для различных досок объявлений

## Description ##

Генератор объявлений (рандомизатор текста) для досок объявлений, типа авито и т.д.

## Installation ##

1. Visit 'Plugins > Add New'
2. Click 'Upload Plugin'
3. Upload the file 'ad-generator.zip'
4. Activate Ad Generator from your Plugins page.
5. Add [ad_generator] shortcode to WordPress Page.

# Configuration #

1. Create new WordPress Page, add [ad_generator] shortcode and save
2. Go to page and use ad generator

## Changelog ##

### 1.0.2 ###
* Решил проблему с переносом строк
* Добавил файлы для GitHub
* Настроил правильный вывод результатов

### 1.0.1 ###
* Объединил всё в одну функцию. Убрал лишнее и поправил ошибки
* Проверил на тестовом сайте - всё работает
Дальше:
* Нужно навести красоту
* Сделать так, чтобы генерировалось с переносами строк

### 1.0.0 ###
* Initial Release

***

# Documentation #

## Что такое рандомизатор текста?

Это - программа для промышленного создания псевдоуникального контента. Используется, например, при регистрации сайта во множестве каталогов. Чтобы в каждом каталоге сайт описывался уникальным с точки зрения поисковиков текстом. В отличие от аналогичных инструментов (синонимайзеры, доргены) позволяет максимально сохранить читабельность результирующих текстов.

## Как работает рандомизатор?
Берем некий исходный текст. Например: 
 
> Бытует мнение, что и копирайтинг (написание текстов) и рерайтинг (переработка готовых текстов) с успехом можно доверить текстовому рандомизатору – специальной программе.

### Обрабатываем его специальным образом:
1. Если "текст 1" можно заменить на "текст 2" или на "текст 3", то вместо "текст 1" вставляем инструкцию {текст 1|текст 2|текст 3}. 
1. Если "текст" можно опустить, то вместо "текст" вставляем инструкцию {|текст}. 
1. Если можно перемешать последовательность "текст 1 текст 2 текст 3", то вместо нее вставляем инструкцию [текст 1|текст 2|текст 3]. 
1. Если можно перемешать последовательность "текст 1, текст 2, текст 3", то вместо нее вставляем инструкцию [+,+текст 1|текст 2|текст 3]. 
1. Если можно перемешать абзацы "абзац1 абзац2 абзац3", то можно просто писать абзац1|абзац2|абзац3. 
1. Если нужно вставить в текст какой-то спецсимвол "{", "}", "|", "[", "]", "+" или "\", то его следует экранировать: "\{", "\}", "\|", "\[", "\]", "\+" или "\\".

**Инструкции могут иметь неограниченную вложенность.**



### Вариант обработки на скорую руку: 
 
> {{Бытует|Существует|Есть|Имеется} мнение|{Некоторые|Многие} думают}, что и
> [+и+
>  {копирайтинг (написание текстов)
>  |написание текстов (копирайтинг)
>  |написание текстов
>  |копирайтинг
>  }
> |{рерайтинг (переработку готовых текстов)
>  |переработку готовых текстов (рерайтинг)
>  |переработку готовых текстов
>  |рерайтинг
>  }
> ] [{|с успехом}|можно] доверить
> [+–+{текстовому рандомизатору|рандомизатору {|текста|текстов}}
> |{специальной|особой} {программе|проге}
> ].

Скармливаем этот код рандомизатору и получаем кучу вариантов, таких как: 
 
> Некоторые думают, что и написание текстов и рерайтинг (переработку готовых текстов) с успехом можно доверить особой программе – рандомизатору.

или 
 
> Есть мнение, что и переработку готовых текстов и написание текстов можно доверить текстовому рандомизатору – особой проге.

Для приведенного в примере кода существует 24576 различных вариантов результирующих текстов.

### Итак, повторим: 
* {текст 1|текст 2|текст 3} - перебор
* [текст 1|текст 2|текст 3] - перестановки
* [+разделитель+текст 1|текст 2|текст 3] - перестановки с разделителем
* \{ \} \| \[ \] \+ \\ - экранизация спецсимволов
* Поддерживается вложенность дирректив

***

# Contributing #
Firstly, thanks for even thinking about contributing. You're awesome!

To make things easier we've created these guidelines:

## Issues: ##

* When opening an issue please keep it to one bug / enhancement / question etc. this to simplify the discussion.
* Please test the master branch to confirm the issue still exists.
* Be as descriptive as you can. Screen shots are always welcome.

## Pull Requests ##

* The general rule is to use 1 PR for 1 Issue. This helps the merge master quickly figure out how the new code affects the plugin.
* All Pull Request must be made from int "master". You will be responsible for checking that your branch is up to date.
* All pull requests must be related to an existing / new issue.
* If you have the chops please include Unit Tests along with your Pull Request.

We appreciate all your efforts. Your contributions make Ad-Generator even better!
