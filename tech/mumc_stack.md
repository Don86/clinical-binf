# MUMC Website Stack

I'm writing these notes because I'm not primarily a front-end dev, so extensive documentation is required to somewhat mitigate the inevitable use-it-or-lose-it depreciation of web dev skills.

### The Stack

 - PHP
 - Laravel (PHP framework)
 - Composer (PHP package manager)
 - MySQL (DB Server)
 - jQuery (JS library)
 - Bootstrap (CSS framework with some JS components)
 - LESS (CSS preprocessor)

### Misc

 - PHPstorm (IDE)
 - Summernote (WYSIWYG editor)

## Laravel

Src: [Laracasts: Laravel 5 fundamentals](https://laracasts.com/series/laravel-5-fundamentals/episodes/1)

## Part 1: Set Up with Composer

(Just for `Laravel`, it seems)

First go to getcomposer.org, and get download Composer, say, on the Desktop. Follow their instructions; at the time of writing, this is pretty idiot-proof. This returns a `composer.phar` file, which you can just think of as a `php` archive file-type thing. Move it: `sudo mv composer.phar /usr/local/bin/composer`


```
# Create a temp dir (dummy?) on the desktop
cd Desktop
mkdir composer_temp

# Get phpspec
cd composer_temp
composer require phpspec/phpspec
```

Sidebar: dependencies will be downloaded to `composer_temp/vendor`. Executables will be in `/vendor/bin/`.

```
# Create a project folder, called 'learning-laravel-5'
composer create-project laravel/laravel learning-laravel-5
```

Start a local server, just to preview:

```
php -S localhost:8888 -t public
```

And open `localhost:8888` on the browser.

## Part 2: Homestead

(For VM. Skip first.)

## Part 3: Getting to Know the Framework: Routing, Controllers, and Views

### `routes` folder

Seems like a bunch of `.php` files that dictate what will be called when/where. Since the tutorial, `routes` is no lonegr just a single `.php` file, but a folder instead. Superceded by `web.php`, probably.

(WIP)
