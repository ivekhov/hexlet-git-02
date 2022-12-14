# Notes on 'Intro to Git'

Наименование коммитов: 

*https://www.conventionalcommits.org/ru/v1.0.0/*

Настройка ssh ключей по инструкции

Скачивание обновлений из гита в локальный каталог:

```
git pull --rebase
```

Команда add добавляет файл в индекс. 
Команда commit выполняет коммит того файла, 
который добавлен в индекс.

```
git add
git commit -m
git push
```

Удаление файла из директории и прописывание этого в коммит для отправки

```
git rm PEOPLE.md
# равносильно git rm + git add, т е удалению файла
# и отправке записи об удалении в индекс
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

Просмотр сокращенной версии лога 

```
git log --oneline
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

отмена последнего действия в гите по 
конкретному хешкоду коммита. В этом случае запись 
в логе коммита остается, но его результат отбрасывается. 

```
git revert HASH-CODE
```

Жесткая команда удаления/отмены коммита. 

```
# отмена коммита
git reset 

# удаление коммиита из буквальное из логов

# HEAD - последний сделанный коммит
git reset --hard HEAD

# HEAD - удаление двух последних коммитов
git reset --hard HEAD~2

# по умолчанию флаг --mixed
# запись о коммите в логе удаляется, но 
# изменения, сделанный им в файлах, остаются
```

Дописать изменения в существующий коммит
чтобы не создавать новый коммит и не мусорить лог

```
# ранее уже был сделан какой-то коммит

git add FILE_THAT_WAS_FORGOTTEN
git commit --amend
```

Переключиться на конкретный коммит по хешу.
Так попадаем в определенный коммит.

```
git checkout HASH-CODE

# выход и возврат в главную ветку
git checkout main
```

Определение места положения

```
git  branch
```

Ссылки:

*https://trunkbaseddevelopment.com*

*https://learngitbranching.js.org/?locale=ru_RU*


Список .gitignore файлов под разные языки

*https://github.com/github/gitignore*


Опция спрятать текущие коммиты

```
...
git stash  # комит прячется
...
git stach pop # комит возвращается
```

------

## Как работать на совместных проектах и в Open Source

1. Форкнуть репозиторий в своем аккаунте через интерфейс кнопкой Fork
2. Клонируется форк репозитория к себе в локальное хранилище
3. как брать конкретную фичу из проекта:
    - отбирать по названиям в интерфейсе гитхаба в списке фич и обсуждений к ним
    - взять нужную, написать в гитхабе коммент, что берется, продублить в слак (для хекслета)

4. Создается отдельная ветка под разработку фичи. Переключаемся в нее. Идет разработка фичи.
5. Делается коммит с названием фичи и номера issue в сообщении и делается пуш в свой форк данной ветки
6. В интерфейса гитхаба:
    - в форкнутом репозитории по кнопке Pull request пишется название пуллреквеста и его описание, назначение и схема: из форка и конкретной ветки в мастер родительского репозитория  
    - в основном репозитории под своим сообщением о взятии коммита поставить отметку и название того пуллреквеста, который был сделан

7. Получить ответ от держателя основного репорзитория о принятии/комментарии по предложенному решению. Держатель основного репо его откроет и прокомментит в гитхабе

Видео: как сделать пуллреквест

*https://www.youtube.com/watch?v=pUT3mx1ZRUM*

