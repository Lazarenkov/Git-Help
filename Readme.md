# Консольные команды Git
## Управление репозиторием
### Удаление  репозитория
* **-rm -rf .git** -  удалить текущий репозиторий
* **-rm -rf .git** - удалить текущий репозиторий включая .gitignore и другие системные файлы гита
### Клонирование remote-репозитория
* **git clone https://www...** - клонирование репозитория

  * после этого нужно зайти в скачанную папку - **cd c://...**
### Пуш на remote-репозиторий
* **git push -u origin master** - отправить коммит в удаленный (remote) репозиторий *origin* в ветку *master*
> флаг **-u** связывает текущую ветку явно с конкретным ремоут репозиторием *master*
* **git push --all** - отправить все ветки в удаленный (remote) в репозиторий

---

## Инфо о репозитории
* **git log** - история коммитов
* **git status** - текущий статус
* **git remote -v** - инфо об удаленном (remote) репозитории

---

## Работа с ветками
### Управление ветками
* **git branch**- просмотр все существующих веток в репозитории в т.ч. ремоут
* **git branch *name*** - создать новую ветку с именем *name*
* **git checkout *name*** - переключиться на ветку с именем *name*
* **git checkout -b *name*** - создать и сразу переключиться на ветку с именем *name*
* **git checkout --track *origin/name*** - создать ветку с именем *name* которая сразу будет трекаться с веткой *name* в ремоут репозитории
* **git log --oneline --graph** - построить граф веток
* **git brach -d *name*** - удалить ветку с именем *name*
### Слияние веток
* ***git merge --no-ff *name*** - слить из *name* в current branch
* ***git merge --no-ff *name* -m '*сообщение*'** - слить из *name* в current branch и добавть *сообщение*
### Удаленные (remote) ветки
* ***git fetch*** - склонировать себе ремоут ветку из ремоут репозитория
* ***git pull*** - склонировать себе ремоут ветку из ремоут репозитория с разу начать смердживание ее с локальной веткой с аналогичным названием


---
## Тэги
> Добавление
> * **Git tag -a *v.1.0* -m *'Версия 1.0'*** - добавить к последнему коммиту тег *v.1.0* с названием *'Версия 1.0'* 
> * **Git tag -a *v.1.0* -m *'Версия 1.0'* <*commit-id*>** - добавить к коммиту с идентификатором *commit-id* тег *v.1.0* с названием *'Версия 1.0'* 
* **git push --tags** - отправить теги на  удаленный (remote) репозиторий
> Удаление
> * **git tag -d *v.1.0*** - удалить тег только из локального репозитория
> > Связка для удаления из удаленного (remote) репозитория
> > > * **git push --delete *origin v1.0*** - удалить тег  *v1.0* из ветки *origin* в удаленном (remote) репозитории
> > > * **git tag -d *v.1.0*** - удалить этот же из локального репозитория 

---
## Работа с историей
* **git log -p -- *index.html*** - посмотреть лог для файла *index.html*
*  **git log --grep *'Initial'*** - грепать коммиты по слову *'Initial'* 
*  **git log -$'*Page*' -p** - грепать коммиты по куску кода *Page*
> По умолчанию грепается только текущая ветка. Чтобы грепать по всем нужно добавить флаг
> * **- --all**
* **git blame --1*index.html*** - показать кто менял какие строки кода и когда в файле 1*index.html*
---
## Коммиты
* **git add *index.html*** - добавить фаил *index.html* в staging area
* **git add*** - добавить все фаилы в staging area
* **git add** ***.js** - добавить все фаилы c расширением .js в staging area
* **git commit** - комит без сообщения, будет работать только если в staging area есть изменения через git add
> крайне не желательно коммитить без добавления сообщения через флаг -m
* **git commit -m 'Message'** - комит c сообщением *Message*, будет работать только если в staging area есть изменения через git add
*  **git commit -a -m 'Message'** - комит c сообщением *Message*, будет работать если в staging area нет изменений, при этом сначала будет запущен git add *



git rebase -i для редактирования истории коммитов
revert 


