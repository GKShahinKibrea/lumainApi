# First class (Laravel Lumen Introduction)
Demand of Api Developer
* one databse Multiple of Software
* Multiple Sofware Connected With Each Other
* On Company Share Data With Another Company

Big Example of Api
* All google Service - YouTube, Gmail, Google Drive, Play Store
* Facebook Service - Facebook, Messenger, Login
* Money Transfer Service - Skrill, Paypal, Payoneer, Bkash
* AI/Machine Learning - Face Recognition, Finger Print, Object Detection

What is Laravel lumen
* Lumen is a laravel micro service
* Lumen is used for building fast and secure rest API
* Lumen can use with web app, mobile app, IOT services, desktop app.
* Lumen uses rate is higher than other micro services in php
* silex use per second 1000 , Slim 3 use per second 1800, Lumen use per second 1900

# Second class (Laravel Lumen Tools)
Tools
1. VS Code
2. PhpStrom
3. Xammp
4. Postman
5. Composer

# Third class (Create And Run New Project)
Installing Lumen
* composer create-project --prefer-dist laravel/lumen blog

Project Run
* php -S localhost:8000 -t public

# Four class (Lumen API File Structure)
File Structure:

* controllers: our app logics.
* middlewares: API Security here.
* migrations: Database schema here.
* model: Data model here.
* routes: Endpoints for the API.
* .env: Database Connection.
* web: Main Routing Point
# Five class (Lumen API Basic Routing)
Methods For Rest API

* $router->get($url,$callback);
* $router->post($url,$callback);
* $router->put($url,$callback);
* $router->delete($url,$callback);
* post, put, delete route only postman

$router->get('/get', function () use ($router) {
    return "This is get method";
});

$router->post('/post', function () use ($router) {
    return "This is post method";
});

$router->put('/put', function () use ($router) {
    return "This is put method";
});

$router->delete('/delete', function () use ($router) {
    return "This is delete method";
});

$router->post('/kibu',function() {
    return "I am Golam Kibrea";
});



