<h1>ПРАКТИЧЕСКАЯ РАБОТА №6</h1>
Цель: разработать API учета финансов. Необходимо реализовать функции регистрация, авторизация, RefreshToken, 
вывод данных пользователя, редактирование данных пользователя, изменение пароля пользователя. Реализовать CRUD действия по теме, поиск, пагинацию данных. Также, необходимо реализовать фильтрацию, логическое удаление и восстановление данных и историю действий.

Зависимости: 
1. conduit – взаимодействие с БД 
2. jaguar_jwt – библиотека позволяет добавить в приложение авторизацию по JWT токену 
3. quiver – библиотека для работы со списками.

В файле database.yaml прописано соединение с базой данных. 
В функции main указаны данные порта и запускаемого сервиса.

Класс AppService реализует методы для инициализации и подключения к БД, а также содержит маршруты API-запросов.
AppUtils - содержит метод для получения ID авторизованного пользователя.
В папке models содержатся модели идентичные сущностям в БД. Миграции и их валидация создаются при помощи команды conduit db generate и conduit db validate соответственно. Последней командой обновляем таблицы в бд - conduit db upgrade

Контроллеры:
-	action_controller.dart – вывод истории действий пользователя
-	app_auth_controller.dart – авторизация и регистрация пользователя
-	app_token_controller.dart – проверка наличия JWT-токена
-	app_user_controller.dart – получение информации о профиле, изменении данных пользователя, смена пароля
-	filter_controller.dart – фильтрация финансовых операций
-	operation_controller.dart – создание/удаление/изменение/просмотр действия с финансовыми операциями
-	pagination_controller.dart – пагинация финансовых операций
-	recover_operation_controller.dart – вывод/восстановление удаленных данных
-	search_operation_controller.dart – поиск финансовых операций
