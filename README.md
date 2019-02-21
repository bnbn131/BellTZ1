
1. Создать новый проект в IntelliJ IDEA.
File -> New -> Project… -> (Set project SDK = 1.8 …/версия Java 8) Next -> (Set create project from template, template = Command Line App) Next -> (Project name: = example, Project location: = любое) Next
2. Добавить в проект файл .gitignore. Данный файл хранит информацию о том какие файлы не надо отслеживать в Git (не надо хранить сжатую копию и историю изменений)
   Обычно данный файл состоит из найденных в интернете шаблонных строк для созданного проекта, предоставляется IDE и дополняется работником проекта. Для данного примера создайте пустой файл .gitignore.
3. Создайте Git репозиторий вашего нового проекта
VCS -> Enable Version Control Integration -> (Select a ver… Git) Ok 
    После выполнения данного пункта создаётся Git репозиторий, а вся его история будет хранится в корне проекта в невидимой папке .git. Если её удалять Git репозиторий пропадет.
    Добавьте себя как автора в данном репозитории, чтобы все коммиты были помечены как сделанные вами.

4.  Зайдите в корень проекта –> щелкните правой кнопкой мыши в пустом месте папки –> выберите Git Bash Here -> введите git config --local user.name {ваши инициалы в компании VPupkin}  git config --local user.email {ваша почта в компании}
    PS. у меня не заработала, скорее всего из-за чего то стоящего у меня по типу cygwin, но вообще должно работать. https://stackoverflow.com/questions/15566025/intellij-idea-with-git-remember-author. Может в будущих версиях IntelliJ IDEA  поправят.
5. Совершите коммит
VSC -> Commit… -> (Set all ticks – так вы отметите все измененные файлы, которые надо коммитить.   Set Commit Message = init commit – так вы будете видеть в истории коммита, убедитесь, что в поле Author данные из предыдущего пункта ) -> Commit
6. Создайте ветку develop (то есть вы ответвитесь от master)
VCS -> Git ->Branches… -> new Branch -> (введите имя ветки develop) Ok
7. Перейдите в ветку master
    В правом нижнем углу вы увидите Git develop, щелкните на стрелочки рядом -> master -> checkout
8. Создайте новую ветвь haha (то есть вы ответвитесь от master)
    В правом нижнем углу вы увидите Git develop, щелкните на стрелочки рядом -> New branch -> (введите имя haha) Ok
9. Удалите комментарий в классе main, нажмите ctrl+S (сохраните файл) -> закоммитьте изменения
10. Зайдите (смените) текущую ветку на develop
11. Измените комментарий в классe main на // write -> закоммитьте изменения
12. Смёрджите ветку master с веткой haha
    Перейдите в ветку master -> VCS -> Git -> Merge Branches -> (set branch haha, set no fast forward) -> Merge
13. Смёрджите ветку master с веткой develop
    После нажатия Merge  вы увидите, что возникла проблема (конфликт мёрджа) -> щелкните 2 раза на проблемный файл -> в открывшемся окне укажите нужный result (в окне result) -> Apply -> Ok
	Конфликт возник т.к. в обоих ветках менялась одна и та же строка.
14. Совершите коммит изменений, при конфликте мерджа его всегда надо совершать.

Мы рассмотрели небольшую част базовых действий с git. Для лучшего понимания необходима практика. Можно прощёлкать каждый пункт меню VCS и загуглить непонятные действия.
