# devops-netology
This repository is for the course on netology "DevOps"


# update README.md

# Для глобального репозитория devops-netology:
Никакие файлы не будут игнорироваться.

# Для локального репозитория terraform:
Будут игнорироваться конфигурационные файлы Terraform, логи ошибок, файлы состояния terraform, файлы с переменными которые используется в конфигурации terraform

* все файлы из директории .terraform из любой поддиректории проекта - "**/.terraform/*"
* все файлы которые полностью совпадают по названию - crash.log, override.tf, override.tf.json, .terraformrc, terraform.rc
* все файлы имеющие расширения .tfvars и .tfstate- *.tfvars, *.tfstate
* все файлы подходящие под шаблоны - *.tfstate.*, crash.*.log, *.tfvars.json, *_override.tf, *_override.tf.json где вместо * можно подставить любое значение.




