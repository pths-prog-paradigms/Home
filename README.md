# Home

## Общая информация

Курс рассчитан на год, примерную программу можно
посмотреть [здесь](https://drive.google.com/file/d/1RW6BUFq8tzc5vosG1ZZugVY8tuiPYjr4/view).
Впрочем, она ещё может измениться.

Вопросы о курсе, языке, установке ПО, философии программирования, смысле жизни можно задавать в чате курса.
Ссылки здесь не будет, ибо репозиторий публичный.

Зачёт за курс получается из сдачи домашних заданий.
Можно отслеживать свои результаты в [табличке](https://docs.google.com/spreadsheets/d/1Dqe20GG_ZAacwEb82jjDxvX3i0xg40HO1l2QrvHeMys/edit?resourcekey#gid=0).

Если не озвучено иное, то каждое задание имеет срок выполнения в две недели.
Можно сдавать и позднее, но с существенным понижением баллов.
Каждое задание оценивается исходя из следующих критериев:

- Работоспособность (поведение программы соответствует техзаданию)
- Эффективность (отсутствие неоправданных затрат памяти и времени)
- Соответствие правилам хорошего кода (читаемость, поддерживаемость, развиваемость)

Разумеется, достаточно информации для выполнения дз будет рассказано на занятиях,
но может также потребоваться подключить здравый смысл.

Понятно, что только первый пункт может быть проверен автоматически, и то, не всегда.
Поэтому по вашим решениям будет проводиться code review.
Апелляции по оценкам будут приниматься в разумных пределах — по модулю того, что преподаватель — человек и мог
чего-то не заметить.

## Материалы
### Конспекты:
 - [Основы Котлина](https://github.com/LDemetrios/ProgLectures/blob/main/01-kotlin-basics.pdf)
 - [ООП](https://github.com/LDemetrios/ProgLectures/blob/main/02-kotlin-oop.pdf)
 - [Наследование](https://github.com/LDemetrios/ProgLectures/blob/main/03-inheritance.pdf)
 - GUI конспектов не будет, но есть [примеры с лекции](https://github.com/pths-prog-paradigms/GUI-Samples)
 - [Лямбды](https://github.com/LDemetrios/ProgLectures/blob/main/05-kotlin-lambdae.pdf)
 - Основы Кложура: [кодовым файлом](https://github.com/LDemetrios/ProgLectures/blob/main/basics.clj) или [отформатированной pdf'кой](https://github.com/LDemetrios/ProgLectures/blob/main/06-clojure-basics.pdf)

 Если встроенное отображение github считает, что unable to render code block, попытайтесь скачать файл и открыть его самостоятельно.
 

## Запуск без IDE

Для этого есть отдельный гайд, расположенный [тут](https://github.com/pths-prog-paradigms/Home/blob/main/maven-guide.pdf). Перед этим, всё же, придётся установить Java версии 17 или выше, а также Git. 
- Download [Java](https://www.oracle.com/cis/java/technologies/downloads/)
- Download [Git](https://git-scm.com/download/win)

Для отладки clojure удобно пользоваться [вот этой Online REPL](https://clojurescript.io/), для запуска больших файлов и тестов -- [вот этой](https://www.mycompiler.io/new/clojure).

## Настройка окружения
### Kotlin

Предпочтительная IDE для разработки на Котлине - [Intellij IDEa от JetBrains](https://www.jetbrains.com/idea/download/).
Будет достаточно Community версии.
Котлин в ней уже встроен, так что дополнительно устанавливать его не обязательно.
А вот чтобы IDEa запустилась, придётся установить [Java](https://www.oracle.com/cis/java/technologies/downloads/).
Если вы не знаете, какую версию ставить, лучше выбрать 17.

<details>
<summary>Почему?</summary>
На момент написания последней версией JDK является 21-я, однако она всё ещё находится в состоянии "кандидат в релиз".
В ней есть несколько интересных фич, которые я постараюсь упомянуть на занятиях, но ничего, что бы сильно повлияло на работу.
В версиях 18-20 и вовсе вещи, интересные только программисту, профессионально и глубоко занимающемуся Java, а мы вообще-то на другом языке писать будем...
Так что лучшим решением будет взять последнюю Long-Term Support версию, то есть, JDK-17.
</details>

Итак, Котлин. При запуске Intellij IDEa выберите "New Project".
Из предложенных языков нам, очевидно, нужен Kotlin.
Система сборки в первом семестре не существенна, потом будем использовать Maven.
Если это ваш первый проект, вам, вероятно, стоит поставить галочку "Add sample code".

После создания проекта IDEa откроет вам файл с тем самым sample code.
Нажав на зелёный треугольник возле `fun main` и выбрав опцию _Run_, запускаем программу.

На школьных компьютерах, скорее всего, Intellij IDEa уже установлена.
Если же нет, на занятии можно будет воспользоваться сайтом [play.kotlinlang.org](https://play.kotlinlang.org), и запускать код там.
У сайта есть ограничение на время работы программы, но оно не очень жёсткое (для кода в рамках занятия — точно хватит).

### Clojure

Для Intellij IDEa существует плагин под названием Cursive для поддержки clojure, установите его. 
Лично я рекомендую также Rainbow Brackets Lite.
Создать проект отдельно на clojure не выйдет, нужно создавать проект на java. Система сборки так же Maven. 
После этого в раздел зависимостей (dependencies) в pom.xml допишите

```maven
<dependency>
    <groupId>org.clojure</groupId>
    <artifactId>clojure</artifactId>
    <version>1.11.0</version>
</dependency>
```

Если его нет, создайте:

```maven
<dependencies>
    <dependency>
        <groupId>org.clojure</groupId>
        <artifactId>clojure</artifactId>
        <version>1.11.0</version>
    </dependency>
</dependencies>
```

После этого нажмите правой кнопкой на pom.xml, выберите Maven > Reload Project.

Исходники на clojure имеют расширение .clj.
Чтобы запустить такой файл, выделите его в окне Project и нажмите Ctrl+Shift+F10. 
Для вывода используются функции `print` и `println`, попробуйте запустить код

```clojure
(println "Hello, World!")
```

Чтобы запустить Clojure REPL (Read-Evalutate-Print-Loop console), в меню выберите Run > Edit Configurations,
добавить новую (+ в левом верхнем углу) > Clojure REPL > Local. 
При желании введите имя вместо Unnamed; OK. 
Теперь её можно запускать, выбирая в меню в правом верхнем углу и нажимая Run (зелёный треугольник).

### Clojure на школьных компьютерах

Скачать плагин придётся вручную [отсюда](https://plugins.jetbrains.com/plugin/8090-cursive/versions),
подходящей версии (кажется, это должна быть версия 1.12.3-2021.1, смотрите сами, какая совместима с версией IDEa на компе)
и установить с диска (File > Settings > Plugins > значок шестерёнки > Install Plugin from Disk).

А также нужно скачать три jar-файла со стандартной библиотекой clojure: 
[раз](https://repo1.maven.org/maven2/org/clojure/clojure/1.11.1/clojure-1.11.1.jar),
[два](https://repo1.maven.org/maven2/org/clojure/spec.alpha/0.3.218/spec.alpha-0.3.218.jar),
[три](https://repo1.maven.org/maven2/org/clojure/core.specs.alpha/0.2.62/core.specs.alpha-0.2.62.jar). 
После этого их нужно добавить как зависимости: File > Project Structure > Libraries > + > Java > выбирать по одной! 
Если IDEa спросит "какого типа этот jar", нужно выбрать, что это класс-файлы (Classes).
Затем согласиться, чтобы библиотеки были добавлены ко всем модулям.

## Инструкция по сдаче Д/З

### Один раз
- Зарегистрироваться на [GitHub](https://github.com).
- Установить [Git](https://git-scm.com/download/win) на компьютер, если ещё не установлен.
- Согласно [инструкции](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent?platform=windows),
сгенерировать ssh-ключ и добавить его в ssh-агент (вас интересуют секции _Generating a new SSH key_ и _Adding your SSH key to the ssh-agent_).
Имейте в виду, что при вводе пароля в командной строке не появляются звёздочки, точки или другие заменители пароля — текст просто не появляется.
- Согласно [другой инструкции](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account),
добавить сгенерированный ключ в настройки GitHub.

### Для каждого задания
- Перейти по специальной ссылке, которая будет опубликована в чате. Примите задание. 
Для вас создастся персональный репозиторий, где будут лежать условие, тесты и, возможно, другие файлы.
- В Intellij IDEa найти в меню File > New > Project from Version Control (Если вы начинаете не из существующего проекта, то просто нажмите "Get from VCS").
- В только что созданном репозитории нажать (обычно зелёную) кнопку <> Code, выбрать Local, SSH и скопировать ссылку. 
Ссылка должна иметь вид `git@github.com:pths-prog-paradigms/[Название дз]-[Ваш ник].git`.
- Вставьте ссылку в окно Project from Version Control, в поле URL. Нажмите Clone.
- Выполните задание.
- Локально запускайте тесты, чтобы проверить корректность программы.
Тесты выведут вам в достаточной мере подробную информацию о своих результатах.
- Вместе с тестами к вам попадёт и правильное решение задания. 
Оно написано таким образом, что попытки его скопировать, чуть-чуть изменить и выдать за своё ни к чему не приведут.
- После того как задание выполнено и результаты тестов вас устраивают, выполните Commit (Зелёная галочка на панели Git), 
пометив в открывшейся панели все файлы. Название коммита может быть каким угодно. Выполните Commit & Push.
- Заполните [форму](https://docs.google.com/forms/d/e/1FAIpQLSfV0NAmTDSmFxGjzxQbxpowuUrC5JoR1huBKu02TbeFj-CT2w/viewform).
Ссылка на Pull Request обычно `https://github.com/pths-prog-paradigms/[Название_репозитория]/pull/1` 
(Её можно найти в вашем репозитории, в разделе Pull Requests).
Выберите "Сдача", если пытаетесь сдать в первый раз, "Правки", если нет. (Pull Request создаётся автоматически при создании репозитория)
- Ожидайте review. В случае, если вы недовольны результатом, вы можете два раза сделать правки.
Баллы будут поставлены за лучший результат.
- Оценка определяется по формуле $(B_0 T_0 + B_1 T_1 + B_2 T_2) \cdot (0.7 + 0.03 \cdot R) \cdot (0.7 + 0.03 \cdot E) \cdot Delay$.
    - Здесь $B_0$, $B_1$, $B_2$ — константы, которые можно найти на [соответствующей странице таблицы](https://docs.google.com/spreadsheets/d/1Dqe20GG_ZAacwEb82jjDxvX3i0xg40HO1l2QrvHeMys/edit?resourcekey#gid=2070244031) —
  это максимальные баллы за базовые, продвинутые и бонусные тесты. 
    - $T_0$, $T_1$, $T_2$ — процент пройденных тестов соответственно.
    - $R$ и $E$ — результаты за code review, стиль и эффективность соответственно, от 0 до 10. 
Таким образом, даже полностью провалив ревью, можно получить 49% баллов. 
    - $Delay$ — коэффициент просрочки. Если сдано до дедлайна, он равен 1. 
В течение трёх недель после дедлайна он линейно уменьшается до 0.2, и затем остаётся на этом уровне. 
- Когда code review выполнен, в строке с соответствующей посылкой на [соответствующей странице таблицы](https://docs.google.com/spreadsheets/d/1Dqe20GG_ZAacwEb82jjDxvX3i0xg40HO1l2QrvHeMys/edit?resourcekey#gid=1952257686)
появятся результаты. Вы можете пройти по ссылке на pull-request и прочитать комментарии к коду. 
Если хотите делать правки, алгоритм тот же — меняете файл решения, делаете Commit & Push, заполняете форму.
