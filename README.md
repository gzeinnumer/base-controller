# base-controller
 
```php
namespace App\Http\Controllers;

use Illuminate\Foundation\Auth\Access\AuthorizesRequests;
use Illuminate\Foundation\Bus\DispatchesJobs;
use Illuminate\Foundation\Validation\ValidatesRequests;
use Illuminate\Routing\Controller as BaseController;

class Controller extends BaseController
{
    use AuthorizesRequests, DispatchesJobs, ValidatesRequests;

    public function funN()
    {
        return "Super";
    }
}
```

```php
namespace App\Http\Controllers;

use Illuminate\Foundation\Auth\Access\AuthorizesRequests;
use Illuminate\Foundation\Bus\DispatchesJobs;
use Illuminate\Foundation\Validation\ValidatesRequests;
use App\Http\Controllers\Controller;

class Home extends Controller
{
    public function index()
    {
        return $this->funN();
    }
}
```

```php
use App\Http\Controllers\Home;
Route::get('/funN', [Home::class, 'index']);
```

```
php artisan serve --port=8000
```
```
http://localhost:8000/funN
```

---

```
Copyright 2021 M. Fadli Zein
```