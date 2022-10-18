# Notes on 'Intro to Git'

Наименование коммитов: 

*https://www.conventionalcommits.org/ru/v1.0.0/*

Настройка ssh ключей по инструкции

Скачивание обновлений из гита в локальный каталог:

```
git pull --rebase
```

```
git add
git commit -m
git push
```

Удаление файла из директории и прописывание этого в коммит для отправки

```
git rm PEOPLE.md
# равносильно rm + git add
```

Оценка внесенных изменений в файлы. 

Следует запускать ! перед каждым коммитом.

```
git diff

git diff --staged
```

Чтобы удалить каталог из гита, который уже был добавлен и находится на гитхабе

```
git rm folder_name
git commit -m 'remove folder_name'
git push
```

Если файл добавлен в .gitignore, 
но продолжает трекаться:

```
git rm -rf --cached .
git add .
git commit -m "fix gitignore"
```

Коллекция .gitignore файлов 

*https://github.com/github/gitignore*


Анализ списка коммитов, отсортированных по дате добавления, сверху самые свежие

```
git log

git log -p
```

Показать целевой коммит по хешу

```
git show 5120bea3e5528c29f8d1da43731cbe895892eb6d


# или первые 8 символов
git show 5120bea3
```

Определить, кто менял последним файл:

```
git blame INFO.md
```

Команда git grep ищет совпадение с указанной строкой во всех файлах проекта. Например, упоминание в тексте коммита слова "hexlet"

```
git grep -i hexlet
```

ИНСТРУКЦИИ:

Просмотр истории коммитов

*https://git-scm.com/book/ru/v2/Основы-Git-Просмотр-истории-коммитов*

Найти ошибки

*https://git-scm.com/book/ru/v2/Инструменты-Git-Обнаружение-ошибок-с-помощью-Git*

Поиск

*https://git-scm.com/book/ru/v2/Инструменты-Git-Поиск*


Очистка файлов - удаление из каталога и поля зрения гита
```
# Выполняем очистку
# -f – force, -d – directory

git clean -fd
```

Отмена записей об изменениях, оттреченных гитом

