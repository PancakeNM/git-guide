# Git guide in Russian 
---
## Навигация

#### ```pwd``` (от англ. print working directory, «показать рабочую папку») — покажи, в какой я папке;

#### ```ls``` (от англ. list directory contents, «отобразить содержимое директории») — покажи файлы и папки в текущей папке;

#### ```ls -a``` — покажи также скрытые файлы и папки, названия которых начинаются с символа ```.```;

#### ```cd first-project``` (от англ. change directory, «сменить директорию») — перейди в папку ```first-project```;

#### ```cd first-project/html``` — перейди в папку ```html```, которая находится в папке ```first-project```;

#### ```cd ..``` — перейди на уровень выше, в родительскую папку;

#### ```cd ~``` — перейди в домашнюю директорию (/Users/Username);

#### ```cd /``` — перейди в корневую директорию.
---

## Работа с файлами и папками
---

### Создание

#### ```touch index.html``` (англ. touch, «коснуться») — создай файл index.html в текущей папке;

#### ```touch index.html style.css script.js``` — если нужно создать сразу несколько файлов, можно напечатать их имена в одну строку через пробел;

#### ```mkdir second-project``` (от англ. make directory, «создать директорию») — создай папку с именем ```second-project``` в текущей папке.
---

### Копирование и перемещение

#### ```cp file.txt ~/my-dir``` (от англ. copy, «копировать») — скопируй файл в другое место;

#### ```mv file.txt ~/my-dir``` (от англ. move, «переместить») — перемести файл или папку в другое место.

### Чтение

#### ```cat file.txt``` (от англ. concatenate and print, «объединить и распечатать») — распечатай содержимое текстового файла ```file.txt```.

### Удаление

#### ```rm about.html``` (от англ. remove, «удалить») — удали файл ```about.html```;

#### ```rmdir images``` (от англ. remove directory, «удалить директорию») — удали папку ```images```;

#### ```rm -r second-project``` (от англ. remove, «удалить» + recursive, «рекурсивный») — удали папку ```second-project``` и всё, что она содержит.
---

## Полезные возможности

#### Команды необязательно печатать и выполнять по очереди. Можно указать их списком — разделить двумя амперсандами (&&).

#### У консоли есть собственная память — буфер с несколькими последними командами. По ним можно перемещаться с помощью клавиш со стрелками вверх (↑) и вниз (↓).

#### Чтобы не вводить название файла или папки полностью, можно набрать первые символы имени и дважды нажать Tab. Если файл или папка есть в текущей директории, командная строка допишет путь сама.

#### Например, вы находитесь в папке ```dev```. Начните вводить ```cd first``` и дважды нажмите Tab. Если папка ```first-project``` есть внутри dev, командная строка автоматически подставит её имя. Останется только нажать Enter.
---

## Хэш

#### Хэш - индентификатор коммита, является набором данных о коммите, преобразованным в хэш

## Лог

#### git log выводит историю коммитов, показывает хэш коммита, автора, дату-время и описание коммита

## HEAD

#### Файл HEAD (англ. «голова», «головной») — один из служебных файлов папки .git. Он указывает на коммит, который сделан последним (то есть на самый новый).

## Статусы 

#### untracked (англ. «неотслеживаемый») Новые файлы в Git-репозитории помечаются как untracked, то есть неотслеживаемые. Git «видит», что такой файл существует, но не следит за изменениями в нём. 
#### У untracked-файла нет предыдущих версий, зафиксированных в коммитах или через команду git add.

#### staged (англ. «подготовленный») После выполнения команды git add файл попадает в staging area (от англ. stage — «сцена», «этап [процесса]» и area — «область»), то есть в список файлов, которые войдут в коммит. В этот момент файл находится в состоянии staged.

#### tracked (англ. «отслеживаемый») Состояние tracked — это противоположность untracked. Оно довольно широкое по смыслу: в него попадают файлы, которые уже были зафиксированы с помощью git commit, 
#### а также файлы, которые были добавлены в staging area командой git add. То есть все файлы, в которых Git так или иначе отслеживает изменения.

#### modified (англ. «изменённый») Состояние modified значит, что Git сравнил содержимое файла с последней сохранённой версией и нашёл отличия. Например, файл был закоммичен и после этого изменён.

#### Для файлов в состояниях staged и modified обычно не указывается, что они также tracked, потому что это состояние подразумевается.

#### Команда git add добавляет в staging area только текущее содержимое файла. Если вы, например, сделаете git add file.txt, а затем измените file.txt, то новое содержимое файла не будет находиться в staging. 
#### Git сообщит об этом с помощью статуса modified: файл изменён относительно той версии, которая уже в staging. Чтобы добавить в staging последнюю версию, нужно выполнить git add file.txt ещё раз.

## Жизненный цикл файла в Git

#### untracked -> [git add] staged + tracked -> [изменили файл] staged, modified + tracked (Обратите внимание: staged и modified у одного файла, но у разных его версий. ) -> [git add] staged + tracked -> 
#### [git commit] tracked -> [изменили файл] modified + tracked -> [git add] staged + tracked -> [сделали коммит] tracked