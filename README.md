# Games Store

Project for IPP/ESTG Class "Segurança em Aplicações Web"

## Main Components

### **[Backend](https://gitlab.com/ighour-learn/ipp/saw/backend)** - Backend web service made in PHP.
### **[Frontend](https://gitlab.com/ighour-learn/ipp/saw/frontend)** - Frontend made in Javascript (ReactJS).

*Detailed info about components is in their own repository.*

## Objectives

* The app was created to maintain a list of games sold by users.
* The main purpose is to avoid security problems in application, specially about validation, sanitization, unauthorized access of files and resources, password cracking etc.

## Screenshots

* **Games List - Common**

![Web view of Games List](sample/main_web.png)

* **Games List - Mobile**

![Mobile view of Games List](sample/main_mobile.png)

* **Users List - Mobile**

![Mobile view of Users List](sample/users_mobile.png)

## Live

Live version is not available yet.

## Built With

* [Docker](https://www.docker.com/) - Deploy applications using containers.
* [MariaDB](https://mariadb.org/) - SQL database.
* [phpMyAdmin](https://www.phpmyadmin.net/) - Intuitive web interface to access database.

## Modelling

* **Application Architecture**

![Application Architecture](https://gitlab.com/ighour-learn/ipp/saw/trabalho/uploads/734fbe7148390d7de48afbf01cb83393/App_Arquitecture__1___1_.png)

## Installation

This installation guide uses *[Docker-Compose](https://docs.docker.com/compose/)* to run applications. If you want to install with another method, you need to configure your environment to correctly run the PHP application, connected to a SQL Database, and the JS application.

### 1. Clone project

* *git clone git@gitlab.com:ighour-learn/ipp/saw/trabalho.git* **or** *git clone https://gitlab.com/ighour-learn/ipp/saw/trabalho.git*

### 2. Get Submodules (backend and frontend)

* *git submodule init*

* *git submodule update*

### 3. Configure backend .env

* **HEADER_ACCESS_CONTROL_ALLOW_ORIGIN** - Allowed request origins. Here will be the address of frontend application (e.g. http://localhost:8001). Or you can just put * to allow all origins.

* **DATABASE_HOST** - Address of database (e.g. 127.0.0.1).
* **DATABASE_NAME** - Database name (e.g. mydatabase).
* **DATABASE_USER** - Database user (e.g. user).
* **DATABASE_PASSWORD** - Database user password (e.g. password).

* **JWT_KEY** - A random hash with good length (e.g. asud832que9jSAde32e081DSAIJwqre321r1sDqq324e1).
* **JWT_EXPIRE** - Time before JWT expires, in miliseconds (e.g. 3600000).

* **MAILER_HOST** - Valid mailer host and fallback host to send emails (e.g. smtp1.example.com;smtp2.example.com).
* **MAILER_USERNAME** - Mailer username (e.g. user).
* **MAILER_PASSWORD** - Mailer password (e.g. password).
* **MAILER_SECURE** - Mailer secure type (e.g. tls).
* **MAILER_PORT** - Mailer port (e.g. 587).

### 4. Configure frontend .env

* **REACT_APP_API_URL** - Address of backend with slash at end (e.g. http://localhost:80/).
* **REACT_APP_API_DEFAULT_AVATAR_PATH** - Relative path of default user avatars on backend (e.g. img/avatar.png).
* **REACT_APP_API_DEFAULT_GAME_PATH** - Relative path of default game images on backend (e.g. img/game.png).

*If you change default path of images, you need to put desired path into backend folder (/app/public/img...).*

### 5. Install dependencies

* For backend, you need to install dependencies with composer. Use *composer install -o* on backend folder (or run the file *docker-composer.sh* to open a container with composer and run the same command inside it).

* For frontend, you need to install dependencies with npm (or similar). Use *npm install* on frontend folder (or run the file *docker-npm.sh* to open a container with node and run the same command inside it).

### 6. Migrate backend database

* Run the *migrate.sql* file in backend/db folder on your SQL database.

### 7. Run backend seeds

* Run the *seed.sql* file in backend/db folder on your SQL database.

### 8. Build project with Docker-Compose

* *docker-compose build*

### 9. Deploy with Docker-Compose

* *docker-compose up*

### 10. Default ports for applications

* **Backend** (PHP): 8000

* **phpMyAdmin**: 8001

* **Frontend** (ReactJS): 8002

* **Frontend** (Builded ReactJS): 8003

## Authors

* **Célio Ighour** - *Owner* - [My Portfolio](https://ighour.talosdev.com) | [Github](https://github.com/ighour) | [Gitlab](https://gitlab.com/ighour) | [LinkedIn](https://www.linkedin.com/in/c%C3%A9lio-ighour-de-castro-rodrigues-0a278a13a/) | [StackOverflow](https://stackexchange.com/users/10652400/ighour)
* **Simona Alecs** - *Developer*

## Reports

A full report of this project is available in portuguese [here](https://gitlab.com/ighour-learn/ipp/saw/trabalho/uploads/216334f761a6e80050bc466b2e770c12/Trabalho.pdf).