# Gzip Response middleware for Laravel Vapor

自分で使うだけなのでpackagistへの登録はしてない。

```
composer config repositories.pop-culture-studio/laravel-vapor-gzip vcs https://github.com/pop-culture-studio/laravel-vapor-gzip
composer require pop-culture-studio/laravel-vapor-gzip:dev-main
```

`app/Kernel.php`

```diff
    protected $middleware = [
        // \App\Http\Middleware\TrustHosts::class,
        \App\Http\Middleware\TrustProxies::class,
        \Illuminate\Http\Middleware\HandleCors::class,
        \App\Http\Middleware\PreventRequestsDuringMaintenance::class,
        \Illuminate\Foundation\Http\Middleware\ValidatePostSize::class,
        \App\Http\Middleware\TrimStrings::class,
        \Illuminate\Foundation\Http\Middleware\ConvertEmptyStringsToNull::class,
+        \PopCultureStudio\Vapor\Middleware\GzipResponse::class,
    ];
```
