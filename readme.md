# Git: Полный курс для начинающих и не только
URL: https://www.udemy.com/course/git-alishev/learn/lecture/14211812

Моё мнение, курс можно прослушать (ну нет там домашек, что плохо), НО покупать только **распродаже**!

[Git Book по русский](https://git-scm.com/book/ru/v2)

---

# Git command

[`git init`](https://git-scm.com/docs/git-init) - инициализация репозитория

[`git status`](https://git-scm.com/docs/git-status) - показать текущий статус проекта

[`git add`](https://git-scm.com/docs/git-add) - добавление файлов в состояние staged 

[`git commit`](https://git-scm.com/docs/git-commit)` -m"message"` - сделать коммит с сообщением `message`

`git commit -a -m"message"` - добавить все модифицированные файлы (за исключением новых или не отслеживаемых) и делает коммит с сообщением `message`

`git commit --amend -m"message"` - добавляет изменения, изменяет сообщение `message` у последнего коммита.

[`git reset`](https://git-scm.com/docs/git-reset) - отмена изменений в проекте

`git reset [--soft | --mixed | --hard] [COMMIT]`    
- `--soft` - возвращает на указанный коммит и **переводит все коммиты** после указанного в **отслеживаемую зону (staged)**
- `--mixed` - возвращает на указанный коммит и **переводит все коммиты** после указанного в **неотслеживаемую зону (unstaged)**
- `--hard` - возвращает на указанный коммит и **УДАЛЯЕТ ВСЕ** коммиты после указанного.
- `COMMIT` - указатель на коммит или на HEAD.
  - `HEAD^` - откатиться на 1 коммит.
  - `HEAD^^` или `HEAD~2` - откатиться на 2 коммита.
  - `HASH` - указатель на HASH коммита.

**Комментарий**: нужно быть очень внимательным при использование `git reset`

[`git checkout`](https://git-scm.com/docs/git-checkout) - используется для перемещения, между коммитами, версиями отдельных файлов и ветками.

`git checkout [COMMIT | BRANCH]`:
- `COMMIT` - указатель на коммит
- `BRANCH` - указатель на ветку

`git checkout [COMMIT | BRANCH] -- [FILES]`:
- `--` - указатель, что дальше нет команд, только текст
- `FILES` - путь до фала(ов)

[`git clean`](https://git-scm.com/docs/git-clean)` -n` - выведет список не отслеживаемых файлов которые можно удалить
`git clean -f` - удаляет файлы из репозитория 

---

[`git remote`](https://git-scm.com/docs/git-remote) - управляет набором отслеживаемых репозиториев

`git remote -v` - список удалённых репозиториев

`git remote show <NAME>` - показать информацию об удалённом репозитории `<NAME>`

`git remote add <NAME> <URL>` - добавление репозитория
- `<NAME>` - название репозитория
- `<URL>` - ссылка, путь к репозиторию

[`git push`](https://git-scm.com/docs/git-push)` <NAME> <BRANCH>` - отправить изменения в репозиторий по ссылке `<NAME>` ветку `<BRANCH>`

[`git pull`](https://git-scm.com/docs/git-pull)` <name> <BRANCH>` - забрать изменения из репозиторий по ссылке `<NAME>` ветку `<BRANCH>`

`git push --delete <NAME> <BRANCH> ` - удалить ветку `<BRANCH>` на удалённом репозитории `<NAME>`

> `push` первого изменения на сервер осуществляется командой:
` git push --set-upstream <NAME> <BRANCH>`

[`git clone`](https://git-scm.com/docs/git-clone)` <URL>` - загрузить удалённый репозиторий

---

[`git branch`](https://git-scm.com/docs/git-branch) - получить список всех имеющихся веток и и показывает на текущий `HEAD`

`git branch -d <BRANCH>` удалить ветку `<BRANCH>`
> - `-d` - простое удаление
> - `-D` - `--force` удаление. Удаление ветки `<BRANCH>` не смотря ни на что.

`git branch -r` - получить список всех веток которые находятся на удалённом репозитории

[`git checkout`](https://git-scm.com/docs/git-checkout)` <BRANCH>` - переключиться на ветку `<BRANCH>`

`git checkout -b <BRANCH>` - создать и переключиться на ветку `<BRANCH>`

[`git merge`](https://git-scm.com/docs/git-merge)` <BRANCH>` - слить ветку <BRANCH> c текущей (куда указывает `HEAD`) веткой

[`git fetch`](https://git-scm.com/docs/git-fetch) - получить информацию об изменениях в удалённом репозитории
> `git pull` = `git fetch && git merge <name> <BRANCH>`.

---

[`git rebase`](https://git-scm.com/docs/git-rebase)` <BRANCH>` - сделать перебазирование текущей ветки поверх ветки `<BRANCH>`

---

[`git cherry-pick`](https://git-scm.com/docs/git-cherry-pick)` [COMMAND] <hash>` - взять коммит и скопировать его в текущую ветку
- `--edit` - и поменять сообщение коммита
- `--no-commit` - и помещаем в отслеживаемую зону без коммита в нашу ветку
- `-x` - и указать в сообщение hash исходного коммита
- `--signoff` - и указать того, кто совершил cherry-pick 

---

[`git log`](https://git-scm.com/docs/git-log) - получить историю коммитов в репозитории

`git log --oneline` - получить историю коммитов в репозитории в виде hash message

`git log --oneline --graph` - тоже самое, но в виде дерева (графа)

[`git show`](https://git-scm.com/docs/git-show)` <hash>` - показать содержимое коммита
