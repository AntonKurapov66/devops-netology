# Домашнее задание к занятию "Оркестрация группой Docker контейнеров на примере Docker Compose" - `Курапов Антон`

## Задача 1

* Установите docker и docker compose plugin на свою linux рабочую станцию или ВМ.
* Зарегистрируйтесь и создайте публичный репозиторий с именем "custom-nginx" на https://hub.docker.com;
* скачайте образ nginx:1.21.1;
* Создайте Dockerfile и реализуйте в нем замену дефолтной индекс-страницы(/usr/share/nginx/html/index.html), на файл index.html с содержимым:
* Соберите и отправьте созданный образ в свой dockerhub-репозитории c tag 1.0.0 (ТОЛЬКО ЕСЛИ ЕСТЬ ДОСТУП).
* Предоставьте ответ в виде ссылки на https://hub.docker.com/<username_repo>/custom-nginx/general .

* ![alt text](https://github.com/AntonKurapov66/devops-netology/blob/main/homeworks/docker_01/img/01_0.PNG)

* ![alt text](https://github.com/AntonKurapov66/devops-netology/blob/main/homeworks/docker_01/img/01_2.PNG)

* ![alt text](https://github.com/AntonKurapov66/devops-netology/blob/main/homeworks/docker_01/img/01_3.PNG)

* ![alt text](https://github.com/AntonKurapov66/devops-netology/blob/main/homeworks/docker_01/img/01_4.PNG)

https://hub.docker.com/repository/docker/antonkurapov/custom-nginx/general

## Задача 2

* Запустите ваш образ custom-nginx:1.0.0 командой docker run в соответвии с требованиями:
  *  имя контейнера "ФИО-custom-nginx-t2"
  *  контейнер работает в фоне
  *  контейнер опубликован на порту хост системы 127.0.0.1:8080
* Переименуйте контейнер в "custom-nginx-t2"
* Выполните команду date +"%d-%m-%Y %T.%N %Z" ; sleep 0.150 ; docker ps ; ss -tlpn | grep 127.0.0.1:8080  ; docker logs custom-nginx-t2 -n1 ; docker exec -it custom-nginx-t2 base64 /usr/share/nginx/html/index.html
* Убедитесь с помощью curl или веб браузера, что индекс-страница доступна.

* ![alt text](https://github.com/AntonKurapov66/devops-netology/blob/main/homeworks/docker_01/img/02_0.PNG)

* ![alt text](https://github.com/AntonKurapov66/devops-netology/blob/main/homeworks/docker_01/img/02_1.PNG)

* ![alt text](https://github.com/AntonKurapov66/devops-netology/blob/main/homeworks/docker_01/img/02_2.PNG)

## Задача 3

* Воспользуйтесь docker help или google, чтобы узнать как подключиться к стандартному потоку ввода/вывода/ошибок контейнера "custom-nginx-t2".
* Подключитесь к контейнеру и нажмите комбинацию Ctrl-C.
* Выполните docker ps -a и объясните своими словами почему контейнер остановился.

*  Контейнер остановился потому что мы напрямую в стандартный поток ввода ввели команду SIGINT которая завершает работу.

* Перезапустите контейнер
* Зайдите в интерактивный терминал контейнера "custom-nginx-t2" с оболочкой bash.
* Установите любимый текстовый редактор(vim, nano итд) с помощью apt-get.
* Отредактируйте файл "/etc/nginx/conf.d/default.conf", заменив порт "listen 80" на "listen 81".
* Запомните(!) и выполните команду nginx -s reload, а затем внутри контейнера curl http://127.0.0.1:80 ; curl http://127.0.0.1:81.
* Выйдите из контейнера, набрав в консоли exit или Ctrl-D.
* Проверьте вывод команд: ss -tlpn | grep 127.0.0.1:8080 , docker port custom-nginx-t2, curl http://127.0.0.1:8080. Кратко объясните суть возникшей проблемы.

*   порт 81 не проброшен из контейнера на хост, доступ к nginx по этому порту с хоста будет невозможен.

* Удалите запущенный контейнер "custom-nginx-t2", не останавливая его.(воспользуйтесь --help или google)

* ![alt text](https://github.com/AntonKurapov66/devops-netology/blob/main/homeworks/docker_01/img/03_0.PNG)

* ![alt text](https://github.com/AntonKurapov66/devops-netology/blob/main/homeworks/docker_01/img/03_1.PNG)

* ![alt text](https://github.com/AntonKurapov66/devops-netology/blob/main/homeworks/docker_01/img/03_2.PNG)

* ![alt text](https://github.com/AntonKurapov66/devops-netology/blob/main/homeworks/docker_01/img/03_3.PNG)


## Задача 4

* Запустите первый контейнер из образа centos c любым тегом в фоновом режиме, подключив папку текущий рабочий каталог $(pwd) на хостовой машине в /data контейнера, используя ключ -v.
* Запустите второй контейнер из образа debian в фоновом режиме, подключив текущий рабочий каталог $(pwd) в /data контейнера.
* Подключитесь к первому контейнеру с помощью docker exec и создайте текстовый файл любого содержания в /data.
* Добавьте ещё один файл в текущий каталог $(pwd) на хостовой машине.
* Подключитесь во второй контейнер и отобразите листинг и содержание файлов в /data контейнера.

* ![alt text](https://github.com/AntonKurapov66/devops-netology/blob/main/homeworks/docker_01/img/04_0.PNG)

* ![alt text](https://github.com/AntonKurapov66/devops-netology/blob/main/homeworks/docker_01/img/04_1.PNG)


## Задача 5

В команде docker-compose up -d подтянется по дефолту docker-compose.yaml потому что так предусмотренно разработчиками docker, по дефолту docker-compose смотрит только на docker-compose.yaml / Если необходимо чтобы запускался файл compose.yaml, команда должна быть следующего вида docker-compose -f compose.yaml up -d

* ![alt text](https://github.com/AntonKurapov66/devops-netology/blob/main/homeworks/docker_01/img/05_0.PNG)

* ![alt text](https://github.com/AntonKurapov66/devops-netology/blob/main/homeworks/docker_01/img/05_1.PNG)

* ![alt text](https://github.com/AntonKurapov66/devops-netology/blob/main/homeworks/docker_01/img/05_2.PNG)

* ![alt text](https://github.com/AntonKurapov66/devops-netology/blob/main/homeworks/docker_01/img/05_3.PNG)

* ![alt text](https://github.com/AntonKurapov66/devops-netology/blob/main/homeworks/docker_01/img/05_4.PNG)











