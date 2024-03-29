# Welcome to the GITHUB!

## Все команды по Markdown находятся по [ссылке](https://gist.github.com/fomvasss/8dd8cd7f88c67a4e3727f9d39224a84c)

### Пробую курсивный текст

_Курсивный текст_

### Пробую полужирный текст

__Полужирный текст__

### Пробую зачеркнутый текст

~~Зачеркнутый текст~~

## Пробую нормированный список

1. Проба раз

2. Проба два

3. Проба три

## Выделение кода (Чек-лист по созданию проекта)

```

cd /D/

mkdir Hello-World

cd Hello-World

touch README.md

cd ..

git init

git remote add origin 'URL'

git remote -v

git add --all

git commit -m 'Прошел задание по созданию локального/сетевого репозитория'

git status 

git push -u origin master

```

## Хеш - идентификатор коммита

Git преобразует информацию о коммитах с помощью алгоритма SHA-1 и для каждого из них рассчитывает уникальный идентификатор — хеш.

Хеш — основной идентификатор коммита и позволяет узнать его автора, дату и содержимое закоммиченных файлов.

Все хеши, а также таблицу соответствий хеш → информация о коммите Git хранит в папке .git.

При вводе команды git log - первые символы  (sabbdsak6234fdsfs212dsad) - это и есть хеш.

## Лог

Можно вызвать не только полный лог, но и сокращённый — это делается командой git log --oneline.

В сокращённом логе выводятся сокращённые хеши — их можно использовать точно так же, как и полные.

---

Разберём элементы, из которых состоит описание:

строка из цифр и латинских букв после слова commit — это хеш коммита;

Author — имя автора и его электронная почта;

Date — дата и время создания коммита;

в конце находится сообщение коммита.

---

## HEAD

В числе прочих файлов в папке .git есть служебный файл HEAD. Он указывает на самый свежий коммит.

Вместо хеша последнего коммита можно написать слово HEAD — Git вас поймёт.

---

## Статус файла

Статусом untracked помечается файл, о существовании которого Git знает, но не следит за изменениями в нём. 

Этот статус — противоположность tracked, в который попадают все файлы, отслеживаемые Git.

Файл переходит в статус staged после выполнения git add.

Статус modified означает, что файл был изменён.

Большинство файлов в проектах «шагает» по следующему циклу: «изменён» → «добавлен в список на коммит» → «закоммичен» → «изменён» → и так далее.

---

## Схема состояний

```mermaid
graph LR;

untracked -- "git add" --> staged;

  staged    -- "???"     --> tracked/comitted;

```

## Изменение коммита

### Изменение сообщения коммита или добавление нового файла

--amend рассчитан на работу с последним коммитом (HEAD).

Дополнить коммит новыми файлами можно с помощью git commit --amend --no-edit. 

Благодаря опции --no-edit сообщение к коммиту останется таким, каким и было.

Изменить сообщение к коммиту позволяет команда git commit --amend -m "Обновлённое сообщение коммита".

### Откат коммитов

Команда git restore --staged <file> переведёт файл из staged обратно в modified или untracked.

Команда git reset --hard <commit hash> «откатит» историю до коммита с хешем <hash>. 

Более поздние коммиты потеряются!

Команда git restore <file> «откатит» изменения в файле до последней сохранённой (в коммите или в staging) версии.

## Просмотр измений файлов

Команда git diff сравнит последнюю закоммиченную версию файла с той, что находится в состоянии modified.

Команда git diff --staged покажет изменения в staged-файлах относительно последних закоммиченных версий.

---

## Игнорирование файлов

 Игнорирование файлов — механизм, который нельзя игнорировать. 

Вот что важно помнить:

Если нужно, чтобы Git игнорировал какие-то файлы, стоит составить файл .gitignore.

Посмотреть, что игнорируется, можно с помощью команды git status --ignored.

Сам файл .gitignore — это обычный файл в репозитории.

Его тоже стоит закоммитить.

Шаблонов много, но их легко найти в интернете вместе с примерами использования.

---
