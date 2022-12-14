# Инструкция для работы с Git и удалёнными репозиториями

## Что такое Git?
Git - это одна из реализаций распределённых систем контроля версий, имеющая как и локальные, так и удалённые репозитории. Является самой популярной реализацией систем контроля версий в мире.

## Настройка
При первом использовании Git необходимо представиться. Для этого нужно ввести в терминале 2 команды:
![](настройка.jpg)

Также проверим последнюю установленную версию
![](version.jpg)
## Подготовка репозитория
Для создание репозитория необходимо выполнить команду *git init*  в папке с репозиторием и у Вас создастся репозиторий (появится скрытая папка .git) 

![](init.jpg)

Для того, чтобы посмотреть какие файлы находятся в папке, нужно набрать команду *ls*. ![](ls.jpg)
___
## Создание коммитов
Если объяснять простым языком, то ***коммит*** - это огромная копия вашего проекта в момент времени, когда этот коммит был сделан. Также Git хранит всю историю о том, когда какой коммит был сделан и кем.
___
### Git add
Для добавления измений в коммит используется команда *git add*. Чтобы использовать команду *git add* напишите *git add <имя файла>*

![](add.jpg)

### Просмотр состояния репозитория
Для того, чтобы посмотреть состояние репозитория используется команда *git status*. Для этого необходимо в папке с репозиторием написать *git status*, и Вы увидите были ли измения в файлах, или их не было.

![](status.jpg)

При этом, если всё хорошо, то файл будет гореть "зелёным", если нет, то "красным". Тогда надо будет проделать ещё раз команду <*git add*> затем <*git status*>.

![](status2.jpg)

### Создание коммитов
Для того, чтобы создать коммит(сохранение) необходимо выполнить команду *git commit*. Выполняется она так: *git commit -m "<сообщение к коммиту>*. Все файлы для коммита должны быть ***ДОБАВЛЕНЫ*** и сообщение к коммиту писать ***ОБЯЗАТЕЛЬНО***.

![](commit.jpg)

## Перемещение между сохранениями
Для того, чтобы перемещаться между коммитами, используется команда *git checkout*. Представим, что нам надо посмотреть, как выглядел наш репозиторий после второго коммита. Для этого используем команду *git checkout* и хэш второго коммита *git checkout <номер коммита>*. Кстати, можно не указывать его целиком, достаточно первых 6 символов. 

![](checkout.jpg)

Чтобы вернуться к актуальному состояниюи продолжить работу наберите команду *git checkout master*.

## Журнал изменений
Не все коммиты будете делать вы, какие-то будут делать ваши коллеги по команде, поэтому вам может понадобиться изучить историю коммитов. Для того, чтобы посмтреть все сделанные изменения в репозитории, используется команда *git log*. Для этого достаточно выполнить команду *git log* в папке с репозиторием. Листать историю коммитов можно стрелочками, а чтобы выйти нужно нажать на клавиатуре кнопку <**q**>.

![](log2.jpg)
___
## Ветки в Git
Почти каждая система контроля версий в какой-то форме поддерживает ветвление. Используя ветвление, вы отклоняетесь от основной линии разработки и продолжаете работу независимо от неё, не вмешиваясь в основную линию. Ветки в Git, как и коммиты, невероятно легковесны. Ветка в Git — это простой перемещаемый указатель. Так как создание множества веток никак не отражается на памяти или жестком диске, удобно создавать отдельные ветки под каждую задачу.

### Создание ветки

Для того, чтобы создать ветку, используется команда *git branch*. Делается это следующим образом в папке с репозиторием: *git branch <название новой ветки>*

![](branch.jpg)

Команда *git branch* позволяет не только создавать ветки, но и просматривать существующие. Ветка, на которой вы находитесь помечается звездочкой.

![](branch2.jpg)

Если мы попробуем сделать изменения, то они произойдут в ветке main, а не в новой ветке newImage.
Сообщим Git, что хотим переключиться на другую ветку:

![](branch3.jpg)

Рекомендуется на каждую задачу создавать отдельную ветку, а потом вливать ее в общую ветку разработки.
Чтобы создать новую ветку и переключиться на неё с помощью одной команды:

![](checkout2.jpg)

## Слияние веток
Как объединять изменения из двух разных веток, после того как вы выполнили свою задачу в отдельной ветке? Для того чтобы дабавить ветку в текущую ветку используется команда *git merge <name branch>*.

Слияния создают особый вид коммита, который имеет сразу двух родителей. Коммит с двумя родителями обычно означает, что мы хотим объединить изменения из одного коммита с другим коммитом и всеми их родительскими коммитами.

Втащим все изменения из ветки newImage в ветку main:

![](merge.jpg)

## Удаление веток
Для удаления ветки ввести команду "git branch -d 'name branch'"

![](branch-d.jpg)
___
## Просмотр изменений в файле
Для вывода изменений в файлах по сравнению с последним коммитом, используется команда *git diff* без параметров. Команда выводит изменения в файлах, которые еще не были добавлены в индекс. Сравнение происходит с последним коммитом
Чтобы показать изменения в файлах, включая файлы, добавленные в индекс, используется команда **git diff --cached**

![](diff.jpg)

# Шпаргалка по синтаксису Markdown

**Markdown (маркдаун)** — облегчённый язык разметки созданный с целью написания максимально читабельного и удобного для правки текста, но пригодного для преобразования в языки для продвинутых публикаций (HTML, Rich Text и др.).
 Сегодня его широко используют в написании статей, документации (в том числе на GitHub), справочных текстов и др.

[https://learn.microsoft.com/ru-ru/contribute/markdown-reference] (спарвочник по Markdown)

[https://ru.wikipedia.org/wiki/Markdown] (Markdown в википедиа)

## Заголовки
Для того чтобы написать HTML заголовок в Markdown, необходимо использовать знак # (хэш). Если необходимо несколько уровней заголовков, h1 - h6, нужно изменить количество хэшей (#) перед текстом заголовка.

![](заголовки.jpg)

# Заголовок 1
## Заголовок 2
### Заголовок 3
##### Заголовок 4
##### Заголовок 5
###### Заголовок 6

## Списки
Markdown поддерживает оба вида списков. Для организации маркерованного списка используются знаки *, + и -. От них зависит вид маркеров. Чтоб сделать многоуровневый список, нужно будет сделать отступы (4 или 8 пробелов).

![](списки1.jpg)

С нумерованными списками все еще проще:

![](списки2.jpg)

## Горизонтальные разделители
В HTML мы используем тег <hr \>, в Markdown для этого служат три или более дефиса, звездочки или знака равно (-, *, =).

![](горизраздел.jpg)


## Курсивное и жирное выделение
Вобще, оформление текста с Markodown становится очень простым и быстрым. Для курсива необходимо поставить знаки * вокруг текста. Для жирного начертания обрамим текст двумя звездочками, а для жирного курсива - тремя. Алтернативный синтаксис - использование знака _ по тем же правилам.


*курсив*

_курсив_

**жирный**

__жирный__

***жирный курсив***

___жирный курсив___

Чтобы совмещать и курсив и жирное начертание можно писать так:
_вот такой наглядный **пример**_

## Ссылки

Существует два варианта оформления ссылок. Первый - обычная вставка в текст:

![](ссылки.jpg)

[Использование ссылок в документации] (https://learn.microsoft.com/ru-ru/contribute/how-to-write-links)

## Изображения
Изображения помещаются на страницу также, как и ссылки, с одним отличием: в начале записи используется знак 

![](image.jpg)

## Таблицы
Создание таблиц с Markdown намного нагляднее, чем в HTML. Форматирование интуитивно понятно, добавлю только что для выравнивания текста внутри ячеек используются знаки : в строке, отделяющей заголовок от основной таблицы.

![](table.jpg)

## Цитаты
Для обозначения цитат в языке Markdown используется знак «больше» («>»). Его можно вставлять как перед каждой строкой цитаты, так и только перед первой строкой параграфа. Также можно создавать вложенные цитаты (цитаты внутри цитат). Для их разметки используются дополнительные уровни знаков цитирования («>»).

![](zitata2.jpg)

> Первый уровень цитирования
>> Второй уровень цитирования
>>> Третий уровень цитирования
