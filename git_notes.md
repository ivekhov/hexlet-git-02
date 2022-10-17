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