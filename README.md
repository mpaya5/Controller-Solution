# Controller Does Not Exist
## Solution of the problem "Target class [YourController] does not exist" in Laravel 8

If you're receiving that problem in Laravel 8:
> Illuminate\Contracts\Container\BindingResolutionException

**Target class [YourController] does not exist.**

And in the `Stack trace` you receive also this:
>Illuminate\Container\Container::build

[vendor/laravel/framework/src/Illuminate/Container/Container.php:811](https://github.com/yumewebs/Controller-Solution/blob/main/Container/Container.php)

You will need to add you're controller in the [`web.php`](https://github.com/yumewebs/Controller-Solution/blob/main/web.php) like that:

### EXTRA
> I'm creating this repository because when I was studying a Course of Laravel, the guy who was teaching me this was using `Laravel 5.6` and I was using `Laravel 8` and it was so hard to me to find a solution in Internet, because there are more solutions of Laravel 5 and 6 than 8.

**Remember** to create your routes like that:
```
Route::get('/', [HomeController::class, 'index'])->name('home');
Route::get('/configuracion', [UserController::class, 'config'])->name('config');
Route::post('/user/update', [UserController::class, 'update'])->name('user.update');
