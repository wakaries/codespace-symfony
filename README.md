

symfony new taska-basic --webapp

create-project symfony/skeleton
git init
composer require webapp



Crear modelo de datos

Migración

````
php bin/console make:user
php bin/console make:entity
php bin/console make:migration
php bin/console doctrine:migrations:migrate
````

Comando

````
php bin/console make:command
````

Messenger

````
php bin/console messenger:consume async -vv
````





https://symfony.com/doc/current/components/messenger.html

https://stefanoalletti.wordpress.com/2022/02/26/ddd-hexagonal-architecture-cqrs-with-symfony-doctrine/



## VARIOS


https://github.com/ramsey/uuid

---
## Preparación

1. Modelo de datos
2. CRUDs
3. Plantillas
4. Webpack
5. Seguridad
6. Behat
7. Bundles
8. Workflow
9. Messenger
10. API
11.

---
MÓDULO A - Básico
1. Symfony
    - HttpKernel
    - Dependency injection
    - Maker
    - Console / Command
2. Acceso a datos
    - Doctrine
    - Fixtures
3. Controller / CRUD
    - Routing
    - Twig
    - CRUD
    - Form
4. Componentes front
    - Webpack
5. Seguridad
    - Security
6. API
    - JWT
7. I18n
    - Translation
8. Tests
    - phpunit
    - Behat

MÓDULO B - Avanzado
1. Bundles
    - Bundles
    - HTTP Client
2. Workflow
    - Workflow
3. CQRS
    - Events
    - Messenger
    - Redis
    - Mercure
    - Notifier / Mailer
    - Monolog
4. MISC
    - Process
    - Cron


composer create-project symfony/skeleton backend
composer require symfony/webapp-pack

### BEHAT
composer require friends-of-behat/mink-extension friends-of-behat/mink-browserkit-driver friends-of-behat/symfony-extension --dev

En la máquina de redis ejecutar:
redis-cli

keys *

