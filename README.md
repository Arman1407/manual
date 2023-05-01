# ИНСТРУКЦИЯ

## Синтаксис языка Markdown

* **Выделение заголовков.** Количество символов (#)  задает уровень заголовка (до 6 уровней), ставится в начале.

* **Подчеркивание текста** (не менее 3 подряд) выделяют заголовки первого ("=") и второго ("-") уровней.

* **Полужирное начертание** - символы (**) или (__) ставятся в начале и конце текста. Пример: **полужирный** или __полужирный__.

* **Курсивное начерание** - символы (*) или (_) ставятся в начале и конце текста. Пример: *курсив* или _курсив_.

* **Полужирное курсивное начертание** - символы (***) или (___) ставятся в начале и конце текста. Пример: ***полужирный курсив*** или ___полужирный курсив___.

* **Комбинированный текст** - текст совмещает все три способа указанные выше. Пример: _***Комбинированный текст*** - текст совмещает все_ **три способа**.

* **Зачерунутый текст** - символы (~~) ставятся в начале и конце текста. Пример: ~~зачёркунутый текст~~.

* **Ненумерованные списки** - символ (*) в начале строки.

* **Нумерованные списки** - цифры, после цифры ставится точка

* **ctrl + S** - сохранение текущего состояния перерд фиксацией (git add), без сохранения не зафиксируется, без фиксации не закомичется.

* __cd название папки__ переключение между папками

* __cd ..__ возвращает на предыдущую папку

## Работа с изображениями

Чтобы вставить изображение в текст необходимо: 
![название файла](имя файла). Пример: ![Синтаксис языка Markdown](Синтаксис.png)

![сумма четных чисел до 15](сумма четных чисел до 15.png)

## Команды git

1. **git init** - инициализирует создание репозитория в данной папке (без этого git не работает).

2. **git status** - отражает текущее состояние репозитория. Показывает файлы, в которых были произведены изменения, удалённые и новые, требующие добавления.

3. **git config --global user.name "User Name"** - для авторизации ввести имя. Вводится один раз. При необходимости в другом репозитарии для отображения вводится другое имя без --global.

4. **git config --global user.email mail@gmail.com** - для авторизации ввести адрес эл.почты. Вводится один раз. Эл.адрес должен совпадать с тем, на который зарегистрирован аккаунт в Гитхабе.

5. **git config --global core.editor editor** - установка текстового редактора, в котором будут открываться файлы для решения конфликтов.

6. **git config --list** - просмотр всех установленных настроек.

7. **git add название файла** - фиксирует изменения в этом файле.

    * 7.1. **git add .** - фиксирует все изменения в репозитории.
    * 7.2. **git add -A** - добавляет удалённые файлы из текущей директории и из всего локального репозитория.

8. **git rm название файла** - удаляет файлы по их имени.

9. **git reset** - отменяет все незафиксированные изменения по умолчанию только из индекса.

    * 9.1. **git reset --hard** - безвозвратно удаляет незафиксированные текущие изменения из локального репозитория и из индекса.

10. **git commit -m "название изменения"** - сохраняет фиксированные изменения.

11. **git log** - отражает все коммиты, созданные в этой ветке.

    + 11.1. **git log --graph** - отражает схему веток и коммитов
    + 11.2. **git log --diff-filter=D --summary** - отображает коммиты содержащие удаленные файлы.

12. **git diff** - разница между текущим файлом и закомиченным. 

13. **git branch** - список веток в локальном репозитории.
 
    * 13.1. **git branch название ветки** - создать новую ветку.
    * 13.2. **git branch -d название ветки** - удалить ветку.
    * 13.3. **git branch -m старое название ветки новое название ветки** - перенаименование ветки
    * 13.4. **git branch -r** - список всех существующих веток удалённого репозитория.

14. **git merge** - слияние веток

15. **git checkout название ветки** - перейти в друю ветку (если на конце ввести первые четыре знака коммита то переходим на него).

    * 15.1. **git checkout master** - возврат в актуальную (рабочую) версию коммита.
    * 15.2. **git checkout -b название ветки** - создаёт ветку с указанным именем и автоматически переключит на неё.
    * 15.3. **git checkout origin/branch-name -b branch-name** - переносит на компьютер ветку с удалённого репозитория.

16. **git clone** - клонирование репозитория.

17. **git pull** - получить последнюю версию удалённого репозитория. _**Будьте внимательны, вызов этой команды сотрёт все незафиксированные изменения.**_

18. **git push** - отправляет все зафиксированные изменения на удалённый (другой) репозиторий.

    * 18.1 **git push origin название ветки** - отправляет ветку на сервер
    * 18.2. **git push origin --delete название-ветки** - удаление внешней ветки

19. **git clean -f -d** - удаляет ненужные, неотслеживаемые файлы и прочий мусор.

20. **git cherry -v master** - показывае какие коммиты у вас прибавились по сравнению с веткой master. Показывает количество коммитов

21. **Восстановление удаленной ветки**
    1. _git reflog_ - узнать хеш (SHA1) последнего коммита в удалённой ветке. 
    2. _git checkout SHA1_ - cкопируйте этот хеш и вставьте в команду.
    3. _git checkout -b название-ветки_ - восстановите удалённую ветку.

22. **git stash clear** - очистка всех скрытых состояний.

23. **git rebase -i** - совмещение двух и более коммитов.  Если перебазирование происходит относительно master-ветки, то начать следует с команды git rebase -i master. Однако, если перебазирование происходит не относительно ветки, то нужно будет перебазироваться относительно HEAD. В том случае, если необходимо совместить все коммиты с первым старейшим коммитом, то в первой строке нужно написать pick, а для всех остальных коммитов изменить букву на f. 

### Добавочные команды

+ **-a, --all** - перечисляет как удаленные, так и локальные филиалы
+ **-d, --delete** - удаляет полностью объединенную ветку
+ **-D** - удаляет ветку, даже если не объединена
* **-m, --move** - перемещает/перименовывает ветку и её рефлог
* **-M** - перемещает/перименовывает ветку, даже если цель существует
+ **-c, --copy** - копирует ветку и её рефлог
* **-C** - копирует ветку, даже если цель существует
* **-l, --list** - показыват список названия ветвей
+ **-f, --force** - принудительное создание, перемещение/перименование, удаление
* **-i, --ignore-case** - сортирует и фильтрует по регистру не чуствитльных к регистру
* **--show-current** - показывает текущее название филиала
* **--create-reflog** - создает рефлог филиала
* **--cdit-description** - редактирует описание для ветки
* **--merged _commit_** - выводит ветви, которые объединены
+ **--no-merged _commit_** - выводит ветви, которые не объединены
+ **--collum[=_style_]** - список ветвей в столбцах
+ **--sort _key_** - сортирует по имени поля (ключ)
+ **--points-at _object_** - выводит ветви объекта

## Работа с GitHub

### Внутренняя работа (обмен информации между локальным и удаленным репозиторием)

1. создать аккаунт в GitHub 
2. создать локальный репозиторий (init) или использовать имеющийcя, или вставить код из GitHub в git по команде clone
3. подружить/связать локальный и удаленный репозиторий, для этого создать удаленный репозиторий в GitHub и выбрать алгоритм действий, исходя из п. 2
4. провести работу с файлами в локальном репозитории на git (при необходимости создать папку README.md - она осуществляет предпросмотр)
5. отправить (push) локальный репозиторий в удаленный (на GitHub), при необходимости авторизоваться на удаленном репозитории
6. провести работу с файлами в удаленном репозитории на GitHub
7. выкачать (pull) актуальное состояние из удаленного репозитория на локальный
8. Итог: проводим работу с файлами, отправляем/выкачиваем репозитории с git на GitHub.

### Обмен информацией с другими пользователями GitHub

1. делаем форк (fork) интересующего репозитория, т.е. копируем репозиторий с другого аккаунта в свой аккаунт (в GitHub)
2. отправляем удаленный репозиторий (git clone) в локальный репозитория (в git)
3. создаем новую папку в локальном репозитории с предполагаемыми изменениями
4. производим все изменения в новой ветке этой папки **не забываем проверить в какой ты ветке/папке**
5. отправляем (push) эти изменения на свой аккаунт в GitHu.
6. на удаленном репозитории в GitHub по команде pull reqyest отправляем данные другому пользователю.
