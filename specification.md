# Техническое задание

«Угадай мелодию» — это онлайн-игра, в которой игроку нужно угадывать исполнителей, названия и жанры определённых мелодий.

## 1. Описание функциональности

### 1.1. Страницы приложения

Приложение состоит из нескольких последовательно переключающихся экранов: Welcome (/), Game (/game), Login (/login), Result (/result), GameOver (/lose).

В ходе игры пользователь переходит от первого экрана к последнему.

Часть экранов отвечает за игровой процесс: экран начала игры и экран игрового шага.

Другая часть экранов отвечает за вспомогательные сценарии, такие как авторизация.

Обращение к несуществующей странице (например, через адресную строку) не приводит к появлению ошибок в приложении, а корректно обрабатывается маршрутизацией. Пользователь перенаправляется на страницу «404». Дизайн страницы остаётся на усмотрение студента. В самом простом случае это может быть страница с текстом **404 Not Found** и ссылкой для перехода на главную страницу приложения.

#### 1.1.1. Приветственный экран

На приветственном экране показываются правила игры и кнопка старт для начала новой игры.

#### 1.1.2. Игровые экраны

По ходу игры пользователю нужно ответить на все предложенные вопросы. При этом даётся возможность ошибиться три раза за игру.

При каждой ошибке в верхнем правом углу высвечивается красная нота.

Если игрок ошибается третий раз, ему засчитывается поражение и он перемещается на экран проигрыша.

В левом верхнем углу экрана появляется ссылка на приветственный экран. Нажатие на эту ссылку возвращает пользователя на приветственный экран.

##### 1.1.2.1. Угадай исполнителя

При переходе на этот экран композиция начинает проигрываться автоматически.

Пользователю предлагается выбрать одного исполнителя из нескольких предложенных вариантов.

##### 1.1.2.2. Угадай жанр

При переходе на этот экран первая композиция начинает проигрываться автоматически.

В этом режиме пользователю даётся четыре композиции, каждую из которых можно запустить самостоятельно.

Среди предложенных песен нужно выбрать только те, которые относятся к определённому жанру.

В каждый момент времени может играть не более одной композиции.

Правильный ответ засчитывается только в случае, когда пользователь правильно выбрал все композиции.

Если он допускает хотя бы одну ошибку, ответ считается неправильным.

##### 1.1.2.3. Экран победы

Для просмотра результатов игры пользователю требуется выполнить аутентификацию (см. взаимодействие с сервером).

После успешного прохождения игры пользователю показывается экран с результатами и предложением сыграть ещё раз.

При нажатии на кнопку **Попробовать ещё раз** пользователь сразу попадает на первый вопрос с тем же набором вопросов, что и в прошлый раз.

##### 1.1.2.4. Экран поражения

На экране поражения отображается причина проигрыша: сообщение о том, что кончились попытки.

На экране есть кнопка **Попробовать ещё раз**, чтобы начать игру с начала.

## 2. Взаимодействие с сервером

Все необходимые данные загружаются с сервера.

Сервер доступен по адресу: https://15.design.htmlacademy.pro/guess-melody.

Спецификация по взаимодействию с сервером в формате OpenAPI — https://15.design.htmlacademy.pro/spec/guess-melody.

В случае ошибки запроса к серверу отображается информационное сообщение. Дизайн сообщения остаётся на усмотрение разработчика.

Сервер принимает данные в виде JSON объекта.

Авторизация на сервере происходит на основании токена. Токен передаётся с каждым запросом в заголовке X-Token.

## 3. Дополнительно

Покройте код проекта тестами. Напишите тесты для всех компонентов, редьюсеров, асинхронных операций, действий (action).
  
