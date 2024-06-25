# Wordpress

Создается wordpress на stage и prod средах

## Описание проекта

Автоматически разворачивается Docker-compose в  нужном окружении и в нем разворачивается wordpress. 

## Установка и настройка
Этапы:
 - Предварительно развернуть gitlab-runner используя роль gitlab_runner локально. Для этого надо добавить свой tag и токен тут https://gitlab.com/devops-talker84/wp/-/runners/new 
 - deploy_docker. Используя роли common и docker развернуть docker ansible/install-docker.yaml
 - deploy_wordpress и deploy_nginx. Испольуя роли wordpress и wordpress_prod и nginx развернуть wordpress на server2. Запускается вручную
 - deploy_zabbix. Используя роли Zabbix и Zabbix-agent установить zabbix и его агенты на 1 и 2 серверах

### Требования

- Ubuntu 22.04 2cpu /4 ram
- доступ на сервера по ssh
- Настроенные url и сертификаты 
stage - https://delta.trainee.lol/
prod - https://gamma.trainee.lol/

### Установка

Пошаговые инструкции по установке:

```sh
git clone https://gitlab.com/devops-talker84/wp.git
cd wp
