# Домашнее задание к занятию "Системы контроля версий" - `Курапов Антон`

## Задание 1. Создать и настроить репозиторий для дальнейшей работы на курсе

### Создание репозитория и первого коммита

* ![alt text](https://github.com/AntonKurapov66/devops-netology/blob/main/homeworks/git_01/img/01_0.PNG)
* ![alt text](https://github.com/AntonKurapov66/devops-netology/blob/main/homeworks/git_01/img/01_1.PNG)

### Создание файлов .gitignore и второго коммита и Эксперимент с удалением и перемещением файлов (третий и четвёртый коммит)

* ![alt text](https://github.com/AntonKurapov66/devops-netology/blob/main/homeworks/git_01/img/01_2.PNG)
* ![alt text](https://github.com/AntonKurapov66/devops-netology/blob/main/homeworks/git_01/img/01_3.PNG)
* ![alt text](https://github.com/AntonKurapov66/devops-netology/blob/main/homeworks/git_01/img/01_4.PNG)

ответ на вопрос про игнорирование лежит в https://github.com/AntonKurapov66/devops-netology/blob/main/README.md продублирую здесь: 
* все файлы из директории .terraform из любой поддиректории проекта - "**/.terraform/*"
* все файлы которые полностью совпадают по названию - crash.log, override.tf, override.tf.json, .terraformrc, terraform.rc
* все файлы имеющие расширения .tfvars и .tfstate- *.tfvars, *.tfstate
* все файлы подходящие под шаблоны - *.tfstate.*, crash.*.log, *.tfvars.json, *_override.tf, *_override.tf.json где вместо * можно подставить любое значение.


### Проверка изменения

* ![alt text](https://github.com/AntonKurapov66/devops-netology/blob/main/homeworks/git_01/img/01_5.PNG)

### Отправка изменений в репозиторий

* ![alt text](https://github.com/AntonKurapov66/devops-netology/blob/main/homeworks/git_01/img/01_6.PNG)

для GIT PUSH использовал Login/Personal Access Token на GITHUB. Personal Access Token, который был создан в 1 пункте.







