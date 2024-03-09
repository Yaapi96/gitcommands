## Введение

Практическая работа по Git представляет собой набор команд и действий, которые позволяют изучить основные принципы работы с системой контроля версий Git. 
В ходе выполнения задания я познакомился с основными командами Git, такими как git init, git add, git commit, git branch, git merge и другими, а также научился работать с локальными и удаленными репозиториями, создавать коммиты, управлять ветками и многое другое.
## Шаги

1. Создал учетную запись на GitHub:
   * Задал имя пользователя и адрес электронной почты:
      
      ```
      git config --global user.name "zzzatoox"
      git config --global user.email "zzzatoox@mail.ru"
      ```
2. Создал репозиторий на GitHub:
   * Создал локальный репозиторий:
   
      ```
      git init
      ```
3. Создал пустой текстовый документ:
    ```
    echo. > paragraphs.txt
    ```
4. Добавил первый абзац в текстовый документ:
    ```
    echo Первый абзац >> paragraphs.txt
    ```
    * Добавил изменения в индекс:
      
    ```
    git add paragraphs.txt
    ```
    * Закоммитил:
      
    ```
    git commit -m "Первый абзац"
    ```
    ![](/gitimages/git_commit.png)
5. Просмотрел статус текущего репозитория:
    ```
    git status
    ```
    ![](/gitimages/git_status.png)
6. Добавил еще один файл:
    ```
    echo. > another.txt
    ```
7. Создал коммит:
    ```
    git commit -m "Еще один текстовый документ"
    ```
    ![](/gitimages/git_commit_2.png)
8. Посмотрел протокол коммитов:
    ```
    git log
    ```
    ![](/gitimages/git_log.png)
9. Посмотрел изменения в файле по сравнению с последним коммитом:
    ```
    git diff
    ```
10. Убрал изменения относительно последнего коммита из файла:
    ```
    git checkout -- paragraphs.txt
    ```
11. Посмотрел существующие ветки:
    ```
    git branch
    ```
    ![](/gitimages/git_branch.png)
12. Создал новую ветку:
    ```
    git branch newbranch
    ```
13. Переключился на новую ветку:
    ```
    git checkout newbranch
    ```
    ![](/gitimages/git_checkout_newbranch.png)
14. Создал новую ветку и сразу же переключилися на нее:
    ```
    git checkout -b newbranch2
    ```
    ![](/gitimages/git_checkout_newbranch2.png)
15. Удалил ветку:
    ```
    git branch -d newbranch2
    ```
    ![](/gitimages/git_branch_d.png)
17. Добавил merge изменения из указанной ветки в текущую:
    ```
    git checkout newbranch
    git merge master
    ```
18. Создал конфликт:
    * Переключился на ветку master
    
    ```
    git checkout master
    ```
    * Изменил файл paragraphs.txt
    * Добавил и закоммитил
      
      ```
      git add paragraphs.txt
      git commit -m "Стер все и добавил абзац"
      ```
      ![](/gitimages/conflict1.png)
    * Изменил файл paragraphs.txt
    * Добавил и закоммитил
    
      ```
      git add paragraphs.txt
      git commit -m "Стер все и добавил абзац"
      ```
      ![](/gitimages/conflict2.png)
    * Переключился на ветку master и попытался выполнить слияние:
      
      ```
      git checkout master
      git merge newbranch
      ```
      ![](/gitimages/conflict3.png)
19. Посмотрел в каких файлах есть конфликты:
    ```
    git status
    ```
    ![](/gitimages/git_status_conflict.png)
    * Так выглядит текстовый документ при конфликте:
    
    ![](/gitimages/conflict4.png)
20. Устранил конфликт:
    * Выбрал текст, который хочу оставить - "Стер все и добавил абзац", удалив разметку Git
    * Добавил и закоммитил
      
      ```
      git add paragraphs.txt
      git commit -m "Устранен конфликт слияния в paragraphs.txt"
      ```
      ![](/gitimages/conflict5.png)
19. Переключился на указанный коммит:
    ```
    git checkout 04b16e3
    ```
    ![](/gitimages/git_checkout_resolved_conflict.png)
18. Сделал ребазирование *rebase* текущей ветки:
    ```
    git rebase master
    ```
18. Удалил ветку:
    ```
    git branch -d newbranch
    ```
19. Пропустил текущий конфликтный коммит и перешел к следующему:
    ```
    git rebase --skip
    ```
20. Отправил изменения из локального репозитория для указанной ветки в удаленный (дистанционный):
    ```
    git remote add origin https://github.com/zzzatoox/gitcommands.git
    git push origin master
    ```
    ![](/gitimages/git_push.png)
21. Забрал изменения из репозитория, для которого были созданы удаленные ветки по умолчанию:
    ```
    git pull origin master
    ```
    ![](/gitimages/git_pull1.png)
22. Забрал изменения удаленной ветки из репозитория основной ветки по умолчанию:
    ```
    git checkout -b feature-branch
    echo. > another2.txt
    git add another2.txt
    git commit -m "еще один файл сорянчик"
    git push origin feature-branch
    git pull origin feature-branch:master
    ```
    ![](/gitimages/git_pull2.png)
23. Клонировал репозиторий:
    ```
    git clone https://github.com/zzzatoox/gitcommands.git
    ```
    ![](/gitimages/git_clone.png)
