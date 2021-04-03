# BorodaPravitMirom_platform
##BorodaPravitMirom Platform repository
Написал dockerfile использующий nginx и отдающий файлы находящиеся в директории app,когда пытаешься перейти по адресу http://localhost:8000/{{filename}}
Запулить image можно borodapravitmirom/webotus:1
Добавил init контейнер, который создает html
Запустил под с фронтом сайта hipster, создал yaml пода и добавил недостуающие переменные, что бы пофиксить запуск пода
