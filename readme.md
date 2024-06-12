# Шпаргалка по GIT и GITHUB

#### HEAD
Один из служебных файлов папки .git. Он указывает на коммит, который сделан последним (то есть на самый новый).
#### COMMIT
![image info](https://pictures.s3.yandex.net/resources/M2_T5_02_1685969923.png)
Состоит:
<ol>
	<li>1-ая строка из цифр и латинских букв после слова commit — это хеш коммита;</li>
	<li>Author — имя автора и его электронная почта;</li>
	<li>Date — дата и время создания коммита;</li>
	<li>в конце находится сообщение коммита.</li>
</ol>

#### HASH -- идентификатор коммита
Хеш — это короткая (4040 символов в случае SHA-1) строка, которая состоит из цифр 0—9 и латинских букв A—F (неважно, заглавных или строчных).<br>
Хеширование (от англ. hash, «рубить», «крошить», «мешанина») — это способ преобразовать набор данных и получить их «отпечаток» (англ. fingerprint).<br>
Git хеширует (преобразует) информацию о коммите с помощью алгоритма SHA-1 (от англ. Secure Hash Algorithm — «безопасный алгоритм хеширования») и получает для каждого коммита свой уникальный хеш — результат хеширования.<br>
Информация о коммите — это набор данных: когда был сделан коммит, содержимое файлов в репозитории на момент коммита и ссылка на предыдущий, или родительский (англ. parent), коммит.<br>
Git хранит таблицу соответствий *хеш → информация о коммите*.
## Статусы файлов  

```mermaid
	graph LR;
	untracked -- "git add" --> staged;
	modified -- "git add" --> staged -- "git commit" --> tracked;
	staged -- "Изменения" --> modified;
	tracked -- "Изменения" --> modified;	
```

| Статус   | Определение |
| -------- | ------- |
| untracked | англ. «неотслеживаемый» |
| staged | англ. «подготовленный» |
| tracked | англ. «отслеживаемый» |
| modified | англ. «изменённый» |

## Шпаргалка по GITHUB
| Команда   | Определение |
| -------- | ------- |
| ls -la .ssh/ | проверка наличия SSH-ключей |
| $ ssh-keygen -t ed25519 -C "ваш@mail" | генерация SSH-пары ключей |
| pbcopy | копирует поток данных в буфер обмена |
| ssh -T git@github.com | проверяет правильность ключа |
| git remote add | привязать удалённый репозиторий к локальному  |
| git remote -v | убедиться, что репозитории связаны |
| git push | отправить изменения на удалённый репозиторий  |
| git push -u origin main | свяжет локальную ветку с одноимённой удалённой, использовать первый раз  |

## Шпаргалка по GIT
| Команда   | Определение |
| -------- | ------- |
| git init | от англ. initialize — «инициализировать» папку |
| rm -rf .git | «разгитить» папку |
| git status | проверить состояние репозитория |
| git add | подготовить файл к сохранению |
| git add --all | подготовить все файлы к сохранению |
| git commit -m | выполнить коммит |
| git log | просмотреть историю коммитов |
| git log | получить сокращённый лог |
| git version | посмотреть версию |
| git config --global | работа с файлом настройки .gitconfig |
| git config --list  | вывести содержимое файла конфигурации Git |
| git config --global | работа с файлом настройки .gitconfig |


## Шпаргалка. Базовые команды в консоли

pwd (от англ. print working directory, «показать рабочую папку») — покажи, в какой я папке;<br>
ls (от англ. list directory contents, «отобразить содержимое директории») — покажи файлы и папки в текущей папке;<br>
ls -a — покажи также скрытые файлы и папки, названия которых начинаются с символа .;<br>
cd first-project (от англ. change directory, «сменить директорию») — перейди в папку first-project;<br>
cd first-project/html — перейди в папку html, которая находится в папке first-project;<br>
cd .. — перейди на уровень выше, в родительскую папку;<br>
cd ~ — перейди в домашнюю директорию (/Users/Username);<br>
cd / — перейди в корневую директорию.<br>

### Работа с файлами и папками<br>

#### Создание<br>
touch index.html (англ. touch, «коснуться») — создай файл index.html в текущей папке;<br>
touch index.html style.css script.js — если нужно создать сразу несколько файлов, можно напечатать их имена в одну строку через пробел;<br>
mkdir second-project (от англ. make directory, «создать директорию») — создай папку с именем second-project в текущей папке.<br>

#### Копирование и перемещение<br>
cp file.txt ~/my-dir (от англ. copy, «копировать») — скопируй файл в другое место;<br>
mv file.txt ~/my-dir (от англ. move, «переместить») — перемести файл или папку в другое место.<br>

#### Чтение<br>
cat file.txt (от англ. concatenate and print, «объединить и распечатать») — распечатай содержимое текстового файла file.txt.<br>

#### Удаление<br>
rm about.html (от англ. remove, «удалить») — удали файл about.html;<br>
rmdir images (от англ. remove directory, «удалить директорию») — удали папку images;<br>
rm -r second-project (от англ. remove, «удалить» + recursive, «рекурсивный») — удали папку second-project и всё, что она содержит.<br>
#### Полезные возможности<br>
Команды необязательно печатать и выполнять по очереди. Можно указать их списком — разделить двумя амперсандами (&&).<br>
У консоли есть собственная память — буфер с несколькими последними командами. По ним можно перемещаться с помощью клавиш со стрелками вверх (↑) и вниз (↓).<br>
Чтобы не вводить название файла или папки полностью, можно набрать первые символы имени и дважды нажать Tab. Если файл или папка есть в текущей директории, командная строка допишет путь сама.<br>
Например, вы находитесь в папке dev. Начните вводить cd first и дважды нажмите Tab. Если папка first-project есть внутри dev, командная строка автоматически подставит её имя. Останется только нажать Enter.<br>
