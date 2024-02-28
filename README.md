# Gzip Response middleware for Laravel Vapor

## Requirement
- PHP ^8.1 (+ext-zlib)
- Laravel ^10.x

## Installation
```bash
composer require puklipo/laravel-vapor-gzip
```

### Laravel 11 (Slim skeleton)
Add to `bootstrap/app.php`

```php
use Puklipo\Vapor\Middleware\GzipResponse::class;

->withMiddleware(function (Middleware $middleware) {
     $middleware->append(GzipResponse::class);
})
```

### Laravel 10
Add to `app/Http/Kernel.php`

```diff
    protected $middleware = [
        // \App\Http\Middleware\TrustHosts::class,
        \App\Http\Middleware\TrustProxies::class,
        \Illuminate\Http\Middleware\HandleCors::class,
        \App\Http\Middleware\PreventRequestsDuringMaintenance::class,
        \Illuminate\Foundation\Http\Middleware\ValidatePostSize::class,
        \App\Http\Middleware\TrimStrings::class,
        \Illuminate\Foundation\Http\Middleware\ConvertEmptyStringsToNull::class,
+       \Puklipo\Vapor\Middleware\GzipResponse::class,
    ];
```

## When this package abandoned
You can use just the `GzipResponse.php`. Copy to your Laravel project, and change namespace.

```php
namespace App\Http\Middleware;

```

## LICENSE
MIT
