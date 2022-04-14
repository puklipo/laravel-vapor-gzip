# Gzip Response middleware for Laravel Vapor

## Requirement
- PHP ^8.0
- Laravel 9.x

## Installation
```
composer require puklipo/laravel-vapor-gzip
```

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

## LICENSE
MIT
