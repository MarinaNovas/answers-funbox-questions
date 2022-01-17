# Ответы на тестовые задания для Funbox.Level I

## Q1

Расскажите, чем, на ваш взгляд, отличается хорошее клиентское приложение от плохого с точки зрения

- пользователя;
- менеджера проекта;
- дизайнера;
- верстальщика;
- серверного программиста.

### A1

#### Для пользователя:

1. User-friendly дизайн интерфейса;
2. Интуитивно-понятный интерфейс;
3. Быстрая загрузка данных;
4. Отзывчивый и работающий интерфейс для любого типа устройства и браузера;

 #### Для менеджера проектов: _(не было опыта работы с менеджерами проектов)_
 
 1. качественное техническое задание;
 2. быстрая масштабируемость проектаж;
 3. рентабельность;

#### Для дизайнера:

1. иметь возможность реализовать все свои задумки при создании проекта;
2. популярность проекта у целевой аудитории;

#### Для верстальщика:

1. Незамысловатая и лаконичная структура проекта;
2. Отсутствие необходимости поддержки IE и Safari;

#### Для серверного программиста: 

1. удобная архитектура приложения
2. быстрая обработка запросов
3. хорошо защищенная база данных
4. безопасные и надежные сервера

## Q2 
Опишите основные особенности разработки крупных многостраничных сайтов, функциональность которых может меняться в процессе реализации и поддержки. 

_(Не было опыта работы с крупными многостраничными проектами, а просто многостраничные сайтами был)_

### A2

Создание многостраничного веб-приложения (далее –**«MPA»**) занимает довольно много времени. Это связано с тем, что для каждой страницы веб-приложения необходимо верстать отдельный код и делать отдельный дизайн. 

MPA в основном были созданы для настольных браузеров, и, хотя сегодня все делают интерфейсы своих веб-сайтов гибкими для мобильных браузеров, полная адаптация для MPA это трудоемкий процесс. Стоит отметить, что на сегодня модель веб-приложения, которая требует перехода между страницами устаревает (или уже устарела).

Из собственного опыта могу сказать, что бывает, когда Клиенту необходимо сделать адаптацию древнейшего 40 страничного сайта и у него нет конкретных пожеланий каким он должен быть, просто чтобы смотрелось хорошо на разных устройствах, но при этом десктопная версия осталась без изменений. И в этом случае приходится вносить серьезные изменения в верстку и создавать новые визуальные эффекты, в противном случае сайт будет смотреться как веб-сайт в портретном режиме. 

Но самое обидное, что эта работа довольно длительная и совершенно неоправданная в долгосрочной перспективе, так как если в какой-то момент Клиент решит, что ему необходимо создать собственное приложение на основе многостраничного веб-сайта, все равно нужно будет создавать UI / UX, визуальные эффекты и серверную часть с нуля.

Касательно технологического стека и инструментов, которые использовались при работе с MPA. Несмотря на то что разработка занимает довольно много времени, MPA создаются с использованием достаточно простого технологического стека.  
Из моего опыта, front-end часть обычно создавалась с помощью HTML, CSS/SCSS, Boodstrap, Javascript, JQuery. После того, как front-end была сделана она “натягивалась” на CMS (Wordpress,MODX). 
Если это Node.js Express сайт, то для определения визуального интерфейса используются движки представлений Handlebars или Pug.

## Q3
При разработке интерфейсов с использованием компонентной архитектуры часто используются термины Presentational Components и Сontainer Сomponents. Что означают данные термины? Зачем нужно такое разделение, какие у него есть плюсы и минусы?

### A3

При работе с данными из вне (серверные запросы, redux) и их дальнейшем отображении, уместно использовать подход(паттерн) разделения компонентов на Presentational и Container.

Presentational component— это stateless компонент, в котором отображают данные.

Container component— это stateful компонент, в котором принимают и работают с данными.

Этот подход помогает разделить получение и отображение данных, что делает возможным повторное использование одного и того же Presentational компонента с разными источниками.
Единственный недостаток, по моему скромному мнению, вначале, когда еще недостаточно опыта и нет интуитивного чувства, когда стоит извлекать компоненты в контейнеры, не получается это сделать правильно с первого раза и процесс рефакторинга промежуточных компонентов может занять какое-то время.

## Q4
Как устроено наследование в JS? Расскажите о своем опыте реализации JS-наследования без использования фреймворков.
### A4
JS поддерживает прототипное наследование. Каждый объект имеет скрытое свойство [[Prototype]], которое может ссылаться либо на другой объект, либо null.
Объект, на который ссылается [[Prototype]], называется «прототипом».

Мы можем использовать obj.__proto__ для доступа к прототипу.

При этом объект получает возможность обращаться к тем свойствам прототипа, которых у него нет. Когда происходит обращение к свойству объекта и такого свойства не обнаруживается, то поиск свойства происходит по цепочке прототипов.

JS ES2015 (ES6)  также поддерживает такую языковую конструкции как класс. Класс в данном случае лишь имитирует классическую модель наследования и предоставляет более удобный синтаксис для реализации портативного наследования. Именно по этой причине в JS нет множественного наследования, так как объект имеет единственный [[Prototype]]. 

Проекта, где бы я использовала JS наследование в чистом виде у меня сожалению нет...

## Q5
Какие библиотеки можно использовать для написания тестов end-to-end во фронтенде? Расскажите о своем опыте тестирования веб-приложений.
### A5

В моем инструментарии, с недавнего времени, задействованы Cypress, Jest, Enzyme, React Testing Library.

Jest, Enzyme, React Testing Library – применяются для юнит и интегральных тестов и иногда их вполне бывает достаточно, а если нет, то можно использовать Cypress для End-To-End тестирования или его еще называют сквозное тестирование. 

## Q6
Вам нужно реализовать форму для отправки данных на сервер, состоящую из нескольких шагов. В вашем распоряжении дизайн формы и статичная верстка, в которой не показано, как форма должна работать в динамике. Подробного описания, как должны вести себя различные поля в зависимости от действий пользователя, в требованиях к проекту нет. Ваши действия?

### A6

В данном случае все зависит от контекста, т.е. имеет ли разработчик свободу действий, какие внутренние правила установлены. Такие моменты обычно оговариваются заранее.

В большинстве случаев правильно было бы обратиться к руководству с конкретными предложениями относительно реализации и, исходя из этого обсуждения, применять дальнейшие активные действия.

## Q7
Расскажите, какие инструменты помогают вам экономить время в процессе написания, проверки и отладки кода.

###A7
При разработке всегда пользовался Visual Studio Code с различными расширениями, snippet'ы. 

Также использую Сhrome DevTools и React Developer Tools.


## Q8
Какие ресурсы вы используете для развития в профессиональной сфере? Приведите несколько конкретных примеров (сайты, блоги и так далее). Какие ещё области знаний, кроме тех, что непосредственно относятся к работе, вам интересны?

### A8
https://medium.com/@dan_abramov

https://dev.to/d_ir

https://themindstudios.com/blog/tag/tech-trends/

https://nickbulljs.medium.com/

etc…

official documentation 

На сейчас для меня интересна инженерная графика и моделирование. Планирую восстановить некоторые знания в памяти, чтобы поэкспериментировать с WebGL. Т.е. пока непосредственно к работе это не относится, просто интерес.

Также львиную долю времени уделяю английскому: смотрю видео, читаю стать...

## Q9
Расскажите нам немного о себе и предоставьте несколько ссылок на последние работы, выполненные вами.
### A9
Расскажите нам немного о себе и предоставьте несколько ссылок на последние работы, выполненные вами.

Целеустремленная перфекционистка, но при этом стараюсь быть жизнерадостным и легким в общении человеком. Поддерживаю здоровый образ жизни.

Учебные проекты на React:
1) Game Tic Tac Toe Использовались классы и состояния:
   deploy: https://game-tic-tac-toe-sms.herokuapp.com/
   github: https://github.com/MarinaNovas/paper-rock-scissors
   
2) Game Paper Rock Scissors. Использовался фкнциональный подход и хуки. 
   deploy: https://paper-rock-scissors-sms.herokuapp.com/
   github: https://github.com/MarinaNovas/paper-rock-scissors

3) Quiz game. Использовался фкнциональный подход, хуки, Trivia API (https://opentdb.com/api_config.php)
   github: https://github.com/MarinaNovas/Quiz-app-React
