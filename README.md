# Требования к проекту
---

# Содержание
1 [Введение](#intro)  
1.1 [Назначение](#appointment)  
1.2 [Бизнес-требования](#business_requirements)  
1.2.1 [Исходные данные](#initial_data)  
1.2.2 [Возможности бизнеса](#business_opportunities)  
1.2.3 [Границы проекта](#project_boundary)  
1.3 [Аналоги](#analogues)  
2 [Требования пользователя](#user_requirements)  
2.1 [Программные интерфейсы](#software_interfaces)  
2.2 [Интерфейс пользователя](#user_interface)  
2.3 [Характеристики пользователей](#user_specifications)  
2.3.1 [Классы пользователей](#user_classes)  
2.3.2 [Аудитория приложения](#application_audience)  
2.3.2.1 [Целевая аудитория](#target_audience)  
2.3.2.1 [Побочная аудитория](#collateral_audience)  
2.4 [Предположения и зависимости](#assumptions_and_dependencies)  
3 [Системные требования](#system_requirements)  
3.1 [Функциональные требования](#functional_requirements)  
3.1.1 [Основные функции](#main_functions)  
3.1.1.1 [Вход пользователя в приложение](#user_logon_to_the_application)  
3.1.1.2 [Настройка профиля активного пользователя](#setting_up_the_profile_of_the_active_user)  
3.1.1.3 [Выбор любимых жанров фильмов](#download_news)  
3.1.1.4 [Просмотр каталога рекомендаций](#view_information_about_an_individual_newsletter) 
3.1.1.5 [Оценивание фильмов](#film_evaluation)
3.1.1.6 [Выход пользователя из учётной записи](#active_user_change)  
3.1.1.7 [Регистрация нового пользователя после входа в приложение](#add_new_user)  
3.1.2 [Ограничения и исключения](#restrictions_and_exclusions)  
3.2 [Нефункциональные требования](#non-functional_requirements)  
3.2.1 [Атрибуты качества](#quality_attributes)  
3.2.1.1 [Требования к удобству использования](#requirements_for_ease_of_use)  
3.2.1.2 [Требования к безопасности](#security_requirements)  
3.2.2 [Внешние интерфейсы](#external_interfaces)  
3.2.3 [Ограничения](#restrictions)  

<a name="intro"/>

# 1 Введение

<a name="appointment"/>

## 1.1 Назначение
В этом документе описаны функциональные и нефункциональные требования к приложению «FilmSpace». Этот документ предназначен для команды, которая будет реализовывать и проверять корректность работы веб-сервиса. 

<a name="business_requirements"/>

## 1.2 Бизнес-требования

<a name="initial_data"/>

### 1.2.1 Исходные данные
Фильмы давно стали частью жизни современного человека. Ещё несколько десятилетий назад просмотр фильмов был доступен только благодаря телевидению и показам в кинотеатрах. Также киноиндустрия в начале своего развития не могла похвастаться широким разнообразием жанров, поэтому люди не имели возможности выбрать фильм для просмотра. С развитием киноиндустрии и появлением интернета появилось больше возможностей в выборе и просмотре фильмов. Однако в таком большом разнообразии фильмов, которой существует сейчас, очень часто бывает сложно ориентироваться, поэтому проблема выбора фильма остается. Поэтому сейчас создается множество интернет-сервисов, позволяющих фильтровать фильмы по жанру, рейтингу, длительности и другим характеристикам.

<a name="business_opportunities"/>

### 1.2.2 Возможности бизнеса
Множество людей сталкиваются с неопределенностью в выборе фильма, так как не знают, понравится ли он им. Поэтому такие люди хотели бы иметь сервис, задачей которого являлось бы подборка рекомендаций фильмов для пользователя, на основе его предпочтений, путем анализа оценок просмотренных им фильмов и рекомендаций фильмов от пользователей с похожими вкусами.

<a name="project_boundary"/>

### 1.2.3 Границы проекта
Приложение «FilmSpace» позволит зарегистрированным пользователям получать рекомендации фильмов от пользователей со схожими предпочтениями, оценивать фильмы и оставлять на них отзывы, просматривать фильмы онлайн либо же скачивать их на устройство. Незарегистрированные пользователи смогут лишь посмотреть трейлеры (рекламные видео фильмов), видеть рейтинг фильма, а также иметь возможность читать комментарии.

<a name="analogues"/>

## 1.3 Аналоги
Netflix — американская развлекательная компания, а также стриминговый сервис фильмов и сериалов. Сама платформа Netflix является платной и позволяет просматривать фильмы и отзывы на них. 

Ivi — российская медиакомпания, работающая на рынке легального онлайн-видео. Среди проектов компании популярный в России частично бесплатный онлайн-кинотеатр ivi.ru и первый в России детский видеосервис deti.ivi.ru, который вскоре закрылся. Значительная часть контента всех проектов доступна для просмотра бесплатно и без регистрации. Оставшуюся долю составляет премиальный контент сервиса ivi+: контент категории «суперпремьеры» (не только новинки, в премиальном контенте есть ленты 2000-х годов). Основной источник монетизации — реклама, может демонстрироваться перед фильмом, во время фильма или после него.

В отличие от Netflix и Ivi рекомендация фильмов в сервисе «FilmSpace» осуществляется по выбранным пользователем жанрам и исходя из его оценок. Так же в рекомендациях учитываются оценки пользователей с похожими предпочтениями.

<a name="user_requirements"/>

# 2 Требования пользователя

<a name="software_interfaces"/>

## 2.1 Программные интерфейсы
Продукт должен являться веб-сайтом и иметь понятное пользователю оформление. Front-end часть должна быть создана средствами HTML/CSS и React JS. Серверная часть должна быть написана на Python-фреймворке Django. Хранение информации о пользователях и фильмах будет осуществляться в базе данных PostgreSQL. Для управления серверными данными сервис должен предусматривать панель администратора. 

<a name="user_interface"/>

## 2.2 Интерфейс пользователя
Окно входа в веб-сервис.  
![Окно входа в приложение](https://github.com/kirillgogol/TRITPO_lab2/blob/main/login.png)  
Окно регистрации нового пользователя.  
![Окно регистрации нового пользователя](https://github.com/kirillgogol/TRITPO_lab2/blob/main/registration.png)  
Окно выбора интересующих жанров.  
![ Окно выбора интересующих жанров](https://github.com/kirillgogol/TRITPO_lab2/blob/main/genres.png)  
Окно рекомендованных пользователю фильмов.  
![ Окно рекомендованных пользователю фильмов.](https://github.com/kirillgogol/TRITPO_lab2/blob/main/recomendations.png)  
Окно фильмов для оценивания.  
![Окно фильмов для оценивания](https://github.com/kirillgogol/TRITPO_lab2/blob/main/evaluation.png)  

<a name="user_specifications"/>

## 2.3 Характеристики пользователей

<a name="user_classes"/>

### 2.3.1 Классы пользователей

| Класс пользователей | Описание |
|:---|:---|
| Анонимные пользователи | Пользователи, которые не хотят регистрироваться в приложении. Имеют доступ к частичному функционалу: могут просматривать фильмы на платформе, но не могут выбирать свои предпочтения, а так же оставлять комментарии и оценивать фильмы |
| Зарегистрированные пользователи | Пользователи, которые вошли в приложение под своим именем (псевдонимом), желающие просматривать фильмы, отобранные согласно их предпочтениям. Имеют доступ к полному функционалу |

<a name="application_audience"/>

### 2.3.2 Аудитория приложения

<a name="target_audience"/>

#### 2.3.2.1 Целевая аудитория
1)	Младшая возрастная категория – люди возрастом до 18 лет, обладающие минимальной компьютерной грамотностью.
2)	Средняя возрастная категория – люди возрастом от 18 до 60 лет, обладающие минимальной компьютерной грамотностью.
<a name="collateral_audience"/>

#### 2.3.2.2 Побочная аудитория
Люди старшей возрастной категории, обладающие вышеперечисленными качествами.

<a name="assumptions_and_dependencies"/>

## 2.4 Предположения и зависимости
1.	Веб-сервис не работает при отсутствии подключения к Интернету;
2.	Веб-сервис должен обрабатывать большое количество запросов в секунду;
3.	Веб-сервис должен иметь большое количество доступной памяти для хранения данных.

<a name="system_requirements"/>

# 3 Системные требования

<a name="functional_requirements"/>

## 3.1 Функциональные требования

<a name="main_functions"/>

### 3.1.1 Основные функции

<a name="user_logon_to_the_application"/>

#### 3.1.1.1 Вход пользователя в приложение
**Описание.** Пользователь имеет возможность использовать приложение без создания собственного профиля либо войдя в свою учётную запись.

| Функция | Требования | 
|:---|:---|
| Вход в приложение без создания собственного профиля | Приложение должно предоставить пользователю возможность войти в приложение анонимно |
| <a name="registration_requirements"/>Регистрация нового пользователя | Приложение должно запросить у пользователя ввести имя для создания учётной записи. Пользователь должен либо ввести имя, либо отменить действие |
| *Пользователь с таким именем существует* | *Приложение должно известить пользователя об ошибке регистрации и запросить ввод псевдонима. Пользователь должен либо ввести псевдоним, либо отменить действие* |

<a name="setting_up_the_profile_of_the_active_user"/>

#### 3.1.1.2 Настройка профиля зарегистрированного пользователя
**Описание.** Зарегистрированный пользователь может изменять любимые жанры фильмов. 
| Функция | Требования | 
|:---|:---|
| Редактирование информации о любимых жанрах фильмов | Зарегистрированный пользователь должен иметь возможность редактировать свои любимые жанры фильмов |

<a name="download_news"/>

#### 3.1.1.3 Выбор любимых жанров фильмов
**Описание.** Сразу после регистрации пользователь может заполнить анкету любимых жанров фильмов.
| Функция | Требования | 
|:---|:---|
| Заполнение анкеты любимых жанров фильмов | После регистрации пользователя приложение должно предоставлять анкету с возможностью выбора любимых жанров фильмов |

<a name="view_information_about_an_individual_newsletter"/>

#### 3.1.1.4 Просмотр каталога рекомендаций
**Описание.** Зарегистрированный пользователь может просматривать каталог рекомендуемых ему фильмов.

| Функция | Требования | 
|:---|:---|
| Просмотр каталога рекомендуемых фильмов | Сервис должен предоставлять пользователю список рекомендуемых фильмов согласно оценке его предпочтений |


<a name="film_evaluation"/>

#### 3.1.1.5 Оценивание фильмов
**Описание.** Зарегистрированный пользователь может оценивать фильмы и оставлять комментарии.

| Функция | Требования | 
|:---|:---|
| Выбор оценки фильму | Сервис должен предоставлять пользователю возможность выбора его оценки фильму |
| Оставление комментария | Сервис должен предоставлять пользователю возможность оставления комментария к фильму |


<a name="active_user_change"/>

#### 3.1.1.6 Выход зарегистрированного пользователя из учётной записи
**Описание.** Зарегистрированный пользователь имеет возможность выйти из учётной записи.

**Требование.** Приложение должно предоставить зарегистрированному пользователю возможность выйти из учётной записи с возвратом к окну входа в приложение.

<a name="add_new_user"/>

#### 3.1.1.7 Регистрация нового пользователя после входа в приложение
**Описание.** Анонимный пользователь имеет возможность зарегистрироваться в приложении.

**Требование.** Приложение должно предоставить анонимному пользователю возможность [зарегистрироваться в приложении](#registration_requirements). 

<a name="restrictions_and_exclusions"/>

### 3.1.2 Ограничения и исключения
1. Приложение работает только при наличии подключения к Интернету.

<a name="non-functional_requirements"/>

## 3.2 Нефункциональные требования

<a name="quality_attributes"/>

### 3.2.1 Атрибуты качества

<a name="requirements_for_ease_of_use"/>

#### 3.2.1.1 Требования к удобству использования
1. Доступ к основным функциям приложения не более чем за две операции;
2. Все функциональные элементы пользовательского интерфейса имеют названия, описывающие действие, которое произойдет при выборе элемента;
3. Пошаговая инструкция использования основных функций приложения отображена в справке;
4. Обновление информации о фильмах происходит каждые 15 минут в фоновом режиме.

<a name="security_requirements"/>

#### 3.2.1.2 Требования к безопасности
Сервис предоставляет гарантию безопасности личных данных пользователей, дает возможность редактировать профиль пользователя.
<a name="external_interfaces"/>

### 3.2.2 Внешние интерфейсы
Окна приложения удобны для использования пользователями с плохим зрением:
  * размер шрифта не менее 14пт;
  * функциональные элементы контрастны фону окна.

<a name="restrictions"/>

### 3.2.3 Ограничения
1. Приложение реализовано на платформе Django Framework 4.1.2;
2. Профиль пользователя хранится в файле с расширением XML, название файла совпадает с именем (псевдонимом);
3. Данные о фильмах хранятся в базе данных PostgreSQL;
4. Качество видео контента зависит от скорости подключения.
