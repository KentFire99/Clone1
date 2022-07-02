# e_first_step
---

# project structure
## application root
* ~/larareact

## backend
* php: ^8.0
* laravel: ^8.0
* MySql: ^8.x
* node.js: ^16.x

## frontend
* react.js: ^17.0.2
* typescript: ^4.4.3
* Material UI: ^5.0.3

# Docker Setup for local
1. Commands on the host OS
    ```
    // Docker build
    docker-compose build
    // Docker Start-up
    docker-compose up -d

    // Log in to the container
    docker exec -it app_container /bin/bash --login 

    ```

# setup project
1. After logging in to the container, run the following command

1. Change storage permissions
   ```
   chmod 777 -R storage/
   ```
1. install php components
   ```
   composer install
   ```
1. generate .env
   ```
   cp ./deployments/environments/.env.local .env
   ```
1. app key generate
   ```
   php artisan key:generate
   ```
1. install npm packages
   ```
   npm install
   ```
1. build assets
   ```
   npm run dev
   ```

# DB migration & seeder

1. migration
   ```
   php artisan migrate
   ```
2. seeder
   ```
   php artisan db:seed 
   ```


# boot run
1. boot web server
    ```
    // Access with the following URL
    http://localhost/
    ```
    
# testing mail
    ```
    // Using mailhog. Access with the following URL
    http://localhost:8025/
    ```
# test unit

    ```
    // Specify the target
    php artisan test tests/Feature/app/Http/Controllers/StatefulApi/User/Auth/LoginControllerTest.php
    ```
