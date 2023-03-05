# Laravel-10.x Basics :
This readme file aims to provide an overview of the basics for Laravel 10.x, a PHP web application framework.

## Installation :
To use Laravel 10.x, you need to have PHP 7.4 or higher and a database such as MySQL or PostgreSQL installed on your system. You can install Laravel by following the steps below:

* Install Composer (a dependency manager for PHP) if you haven't already. You can download Composer from https://getcomposer.org/.

* Open a terminal or command prompt and run the following command to install Laravel:
```go
composer create-project laravel/laravel my-project-name
```
* Note : Replace  `my-project-name`  with the name of your project.

## Routing :
Routing is the process of defining the URL patterns that your application should respond to. In Laravel, you define routes in the `routes/web.php` file. Here's an example:
```PHP
Route::get('/hello', function () {
    return 'Hello, world!';
});
```
This defines a route that responds to the URL `/hello` with the message "Hello, world!". You can define routes for different HTTP methods (e.g. `GET`, ` POST`, `PUT`, etc.) and pass parameters to them.

## Controllers :
Controllers are classes that handle HTTP requests and return responses. You can create a controller in Laravel using the following command:
```go
php artisan make:controller MyController
```
This will create a MyController class in the `app/Http/Controllers` directory. You can define methods in the controller that correspond to different routes in your application.
```php
class MyController extends Controller
{
    public function index()
    {
        // Return a view
    }

    public function store(Request $request)
    {
        // Process the form data and redirect
    }
}

```

## Views :
Views are templates that define the HTML markup for your application. You can create a view in Laravel using the following command:
```go
php artisan make:view my-view
```
This will create a my-view.blade.php file in the `resources/views` directory. You can include variables in the view using the Blade templating engine.
```php
<h1>{{ $title }}</h1>

<ul>
@foreach ($items as $item)
    <li>{{ $item }}</li>
@endforeach
</ul>

```
## Database :
Laravel provides a powerful ORM (Object-Relational Mapping) called Eloquent for working with databases. You can define models to represent database tables and use them to query and manipulate data.
```php
class User extends Model
{
    protected $table = 'users';
}

```
You can perform basic CRUD (Create, Read, Update, Delete) operations on the model using methods like `create`, `find`, `update`, and `delete`.
```php
// Create a new user
$user = User::create([
    'name' => 'Elazzouzi Hassan',
    'email' => 'elazzouzihassan@example.com',
    'password' => bcrypt('password'),
]);

// Find a user by ID
$user = User::find(1);

// Update a user
$user->update(['name' => 'Wizardy']);

// Delete a user
$user->delete();

```

## Conclusion :
This has been a brief overview of the basics for Laravel 10.x. Laravel provides many more features and tools for building web applications, such as middleware, authentication, and testing. You can learn more about Laravel by visiting [Laravel](https://laravel.com/docs/10.x "Laravel Docs").


