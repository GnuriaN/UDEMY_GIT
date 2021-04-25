# Git command

`git init` - инициализация репозитория

`git status` - показать текущий статус проекта

`git add` - добавление файлов в состояние staged 

`git commit -m"message"` - сделать коммит с сообщением `message`

`git commit -a -m"message"` - добавить все модифицированные файлы (за исключением новых или не отслеживаемых) и делает коммит с сообщением `message`

`git commit --amend -m"message"` - добавляет изменения, изменяет сообщение `message` у последнего коммита.

`git reset` - отмена изменений в проекте

`git reset [--soft | --mixed | --hard] [COMMIT]`    
- `--soft` - возвращает на указанный коммит и **переводит все коммиты** после указанного в **отслеживаемую зону (staged)**
- `--mixed` - возвращает на указанный коммит и **переводит все коммиты** после указанного в **неотслеживаемую зону (unstaged)**
- `--hard` - возвращает на указанный коммит и **УДАЛЯЕТ ВСЕ** коммиты после указанного.
- `COMMIT` - указатель на коммит или на HEAD.
  - `HEAD^` - откатиться на 1 коммит.
  - `HEAD^^` или `HEAD~2` - откатиться на 2 коммита.
  - `HASH` - указатель на HASH коммита.

**Комментарий**: нужно быть очень внимательным при использование `git reset`

`git checkout` - используется для перемещения, между коммитами, версиями отдельных файлов и ветками.

`git checkout [COMMIT | BRANCH]`:
- `COMMIT` - указатель на коммит
- `BRANCH` - указатель на ветку

`git checkout [COMMIT | BRANCH] -- [FILES]`:
- `--` - указатель, что дальше нет команд, только текст
- `FILES` - путь до фала(ов)

`git clean -n` - выведет список не отслеживаемых файлов которые можно удалить
`git clean -f` - удаляет файлы из репозитория 

---

`git remote` - управляет набором отслеживаемых репозиториев

`git remote -v` - список удалённых репозиториев

`git remote add <NAME> <URL>` - добавление репозитория
- `<NAME>` - название репозитория
- `<URL>` - ссылка, путь к репозиторию

`git push <name> <BRANCH>` - отправить изменения в репозиторий по ссылке `<NAME>` ветку `<BRANCH>`

`git pull <name> <BRANCH>` - забрать изменения из репозиторий по ссылке `<NAME>` ветку `<BRANCH>`

> `push` первого изменения на сервер осуществляется командой:
` git push --set-upstream <NAME> <BRANCH>`

