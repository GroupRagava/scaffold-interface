[![SensioLabsInsight](https://insight.sensiolabs.com/projects/4c35ba52-551e-4d62-adb8-ff5199c54801/big.png)](https://insight.sensiolabs.com/projects/4c35ba52-551e-4d62-adb8-ff5199c54801)

[![Build Status](https://travis-ci.org/amranidev/scaffold-interface.svg?branch=master)](https://travis-ci.org/amranidev/scaffold-interface)
[![StyleCI](https://styleci.io/repos/45497055/shield?style=flat)](https://styleci.io/repos/45497055)
[![Built For Laravel](https://img.shields.io/badge/built%20for-laravel-blue.svg)](http://laravel.com)
[![Total Downloads](https://poser.pugx.org/amranidev/scaffold-interface/downloads)](https://packagist.org/packages/amranidev/scaffold-interface)
[![Latest Stable Version](https://poser.pugx.org/amranidev/scaffold-interface/v/stable)](https://packagist.org/packages/amranidev/scaffold-interface)
[![Latest Unstable Version](https://poser.pugx.org/amranidev/scaffold-interface/v/unstable)](https://packagist.org/packages/amranidev/scaffold-interface)
[![License](https://poser.pugx.org/amranidev/scaffold-interface/license)](https://packagist.org/packages/amranidev/scaffold-interface)

## A Smart CRUD Generator

> Using laravel v5.1.* ??, it recommended to use scaffold-interface v1.4.11

> Using laravel v5.3.* ??, make sure that routes path is configured, [config file](https://github.com/amranidev/scaffold-interface/blob/master/config/config.php#L69)

![Scaffold](http://i.imgur.com/65uhrP7.gif)

####Features:

+ Generate your model,views,controller and migrations just in a few clicks.

+ Views support Bootstrap and Materializecss.

+ Generate OneToMany relationships including views and controllers.

+ Generate ManyToMany relationships, available only (dev-master).

+ AdminLTE dashboard template with users management system (users-roles-permissions) using [laravel-permission](https://github.com/spatie/laravel-permission).

+ Softdeletes and timestamps.

+ A delete confirmation message.

+ Using an interface to design your table.

+ Rollbacking possibility.

+ Generate CRUD for packages, see [Lpackager](https://github.com/amranidev/lpackager), [CRUD for packages/modules](http://amranidev.github.io/blog/site/crud-generator-for-packages/).

> NOTE : if you want to generate OneToMany relationships between two different packages, all you have to care about is the controller namespace, that can be a kind of troubleshooting.

###I. Package installation

  1. Run composer require to install Scaffold-Interface:
  
    Add the package to your dependencies in composer.json:
    
    ```json
    require : {
        "Amranidev/scaffold-interface": "v1.5.*"
    }
    ```
    
    Then update composer:
    
    ```
    $ composer update
    ```
    
  3. Add the service providers to config/app.php:

    ```php
    Amranidev\ScaffoldInterface\ScaffoldInterfaceServiceProvider::class,
    Amranidev\Ajaxis\AjaxisServiceProvider::class,
    Spatie\Permission\PermissionServiceProvider::class,
    ```

  4. Publish the assets in your application with:

    ```
    $ php artisan vendor:publish
    ```
    
    * What does this package publishes:
      * app/Http/Controllers/UserController.php
      * app/Http/Controllers/RoleController.php
      * app/Http/Controllers/PermissionController.php
      * resources/views/scaffold-interface
      * public/js/scaffold-interface-js
      * public/css/scaffold-interface-css
      * config/amranidev/config.php
      * database/migrations/migration_file
      
  5. Migrate for the Scaffold Interface table:
  
    ```
    $ php artisan migrate

    ```
  6. Auth scaffolding:
  
    ```
    $ php artisan make:auth
    ```

Congratulations, you have successfully installed Scaffold Interface!

###II. Quick Start
  
  1. Access to Scaffold Interface:
    
     http://{your-project}/scaffold to get into Scaffold Interface.
  
  2. Table creation:

     You can add many of attributes such as a string, date, longtext,etc.

  3. After the creation, to complete your scaffolding, go to the terminal and run:  
     
     ```
     $ php artisan migrate
     
     ```
  
  4. Finally :
     
     Go to http://{your-project}/{your-model} to see the result.
      
  5. Rollback :  

      If you want to rollback the table just check this:
      
      ![Imgur](http://i.imgur.com/dnYc2ZE.png)

      Before you make your rollback make sure that you have rolled back your table in the database.

  6. Dashboard:
      
      Go ahead and create a new user, `$ php artisan tinker`:
      
      ```
      $user = new \App\User();
      $user->name = "john doe";
      $user->email = "jhondoe@example.com";
      $user->password = Hash::make("password");
      $user->save();
      ```
      
      Then add HasRole to app/User.php:
      
      ```php
      use Illuminate\Foundation\Auth\User as Authenticatable;
      use Spatie\Permission\Traits\HasRoles;

      class User extends Authenticatable
      {
        use HasRoles;

        // ...
      }
      ```
      
      Well, it's time to click on dashboard button or go to http://{your-project}/dashboard.
      
####Contribution

 Any ideas are welcome. Feel free to submit any issues or pull requests.

####Credits

+ [Athi Krishnan](https://github.com/athikrishnan)
+ [JeroenG](https://github.com/Jeroen-G)
+ [Ihab Shoully](https://github.com/shoully)
+ [All Contributors](../../contributors)

####TODOS

 - [ ] 100% Code coverage + Maximum code quality.
 - [ ] Allow to generate ManyToMany relationships.

####DONE
 - [x] Users management system (users-roles-permissions).
 - [x] AdminLTE Dashboard.  
 - [x] Improve Vuejs.
 - [x] Add a select for OneToMany (on data fields) in interface.  
 - [x] Laravel 5.3 supported.
 - [x] Laravel 5.2 supported.
 - [x] Laravel 5.1 supported.

####Contact : amranidev@gmail.com
