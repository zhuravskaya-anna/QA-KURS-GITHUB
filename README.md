GitHub. HW_2

работу выполняем в существующем репозитории, к котором есть созданные закомиченные ранее файлы  (не возможно создавать ветки в пустом репозитории, т.к ветка создается для изменения исходного кода)

**1. На локальном репозитории сделать ветки для:**

- Postman
- Jmeter
- CheckLists
- Bag Reports
- SQL
- Charles
- Mobile testing

имена веток должны быть без пробелов , можно использовать  символ `_`   

`git branch Bag_Reporting`  

`git branch Mobile_testing`

`git branch Jmeter` 

`git branch CheckLists`

`git branch SQL`

`git branch Charles`

`git branch Postman`

 

*ветки можно создать отдельными шагами с использованием команды 'git branch' либо   в одну строку, через символы `;`   или  `&&`*

**2. Запушить все ветки на внешний репозиторий**

`git push origin --all`

*или 'git push -u origin --all'  чтобы в дальнейшем не писать --set-upstream при пуше ветки  -u здесь прописывается*

**3. В ветке Bag Reports сделать текстовый документ со структурой баг репорта git checkout Bag_Reports**

`git checkout Bag_Reporting` перейти в ветку
`vim bug.md`  оформить с использованием  языка разметки Markdown

          `Summary`  - Что произошло? Где появилась ошибка? Когда или при каких условиях найден дефект? Короткое описание проблемы, явно указывающее на причину и тип ошибочной ситуации.

          `Project`    Название тестируемого проекта
          `Component`  Название части или функции тестируемогопродукта
          `Version`    Версия на которой была найдена ошибка
          `Severity`   Серьезность  Наиболее распространена пятиуровневая система градации серьезности дефекта:

            `Blocker`   Блокирующий
            `Critical`  Критический 
            `Major`     Значительный 
            `Minor`     Незначительный
            `Trivial`   Тривиальный

          `Priority`   Приоритет дефекта:

            `High` Высокий 
            `Medium` Средний
            `Low` Низкий

          `Status`      Статус бага. Зависит от используемой процедуры и жизненного цикла бага (

          `Author`      Создатель баг репорта
          `Assigned To` Имя сотрудника, назначенного на решение проблемы

          `Окружение`   Информация об окружении, на котором был найден баг

          'Description' Описание
              'Precondition'  начальные условия если есть специфичные действия или шаги воспроизведения достаточно объемные, то указываются  начальные условия
              'Steps to Reproduce' Шаги, по которым можно легко воспроизвести ситуацию, приведшую к ошибке.
              'Actual Result'   Фактический Результат полученный после прохождения шагов к воспроизведению
              'Expected Result' Ожидаемый правильный результат

          'Attachment' Прикрепленный файл  


**4. Запушить структуру багрепорта на внешний репозиторий**

`git add .`  добавить  в отслеживание в репозиторий

`git commit -m "add bug.md"`   сохранить изменения (закомитить)
`git push --set-u origin Bag_Reporting`  отправить на внешний репозиторий в  определенную ветку ***Выполнив эту команду один раз с флагом `--set-upstream` или сокращенно `-u` , например так `git push --set-u origin Bag_Reporting` , вы сделаете удаленную ветку Bag_Reporting  репозитория origin отслеживаемой. И в дальнейшем вы сможете не указывать репозиторий и ветку, отправляя изменения просто командой git push и они автоматически будут попадать в отслеживаемую ветку***
 
либо  можно серию команд  в одну строку, через символы `;`  или  `&&` 

**5. Вмержить ветку Bag Reports в Main**

`git checkout main`  Чтобы вмерджить ветку в мастер, нужно сначала перейти в мастер, 
`git merge Bag_Reporting`	  затем выполнить  слияние веток

**6. Запушить main на внешний репозиторий.**

***git commit  использовать не нужно, т.к коммит сохранен***
`git push origin main`  можно ограничиться git push  но  чтобы избежать недоразумений, лучше всегда  указывать ветку

**7. В ветке CheckLists набросать структуру чек листа.**

`git checkout CheckLists` перейти в ветку

`vim checklist.md`  оформить с использованием  языка разметки Markdown


        'Description' Описание проверки
        'Results'     результат проверки
          'NT'	    - проверка не проводилась
          'PASS'      - проверка успешная
          'FAIL'      - проверка НЕ успешна
          'PARTIAL'   - заблонировано  существующим багом
          'BLOCKET BY'- проверка НЕ возможна (отсутвует функционал)
        'Version'    Версия  которая тестируется 
        'Bug ID'     номер бага
        'Tester'     тестировщик
 
**8. Запушить структуру на внешний репозиторий**

`git add . `
`git commit -m "add checklist.md"`
`git push origin CheckLists`

**9. На внешнем репозитории сделать Pull Request ветки CheckLists в main**

Перейти на веб версию github в нужный репозиторий, изменить ветку на Checklists, нажать `Pull Request`

в окне сравнения веток нажать кнопку `Create pull request`

после нажатия кнопки появится окно ввода сообщения `Pull Request`

 нажимаем `Create pull request`в окне сравнения веток нажать кнопку `Merge pull request`

**10. Синхронизировать Внешнюю и Локальную ветки Main**

`git checkout main`

`git pull origin main`
