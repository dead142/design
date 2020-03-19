## Автоматическая загрузка классов и пространтсво имен

## Пространство имен 

### Глобальное пространство имен
 
```php 
<?php
// app/models/Dog.php

class Dog
{

}
 
```
###Простое использование пространств имён
 
```php
<?php

namespace Dog;

// app/models/another.php

class Dog
{

}
$dog = new Dog\Dog();
```
 
### Использование класса из одного пространства имен в другом 

Объявим новый класс:

```php

<?php

namespace Cat;

// app/routes.php

$cat = new \Cat\Cat();
```

Использлование класса Dog в классе Cat
```php
<?php

namespace Cat;

use Dog\Dog;

// app/routes.php

$dog= new Dog();
```

### AS (Переимнование используемых классов)

```php
<?php

namespace Dog;

use Cat\Cat as Caaaaaat;

// app/routes.php

$cat = new Caaaaaat();
```
## Автоматическая загрузка классов 

### Автозагрузка через spl_autoload_register

```php
 spl_autoload_register(function ($classname) {
 	$filename =  $classname .".php";
 	require_once($filename);
 });
 
 
 
 $obj = new SomeClass();
 $obj::work();
```

### Автозагрузка через composer

Создать ```composer.json```
``` 
{
  "autoload": {
    "psr-4": {
      "Foo\\": "src/",
      "App\\Plugins\\": "plug/"
    }
  }
}
```
И выполнить команду ``` composer dump-autoload```, которая создаст необходимые файлы для автозагрузки.

К примеру, при такой структурк файлов, можно создать класс ```FoooooClass``` в директории ```src```

```php
<?php


namespace Foo;


class FoooooClass {
	public static function work(){
		echo 'Hello! Hello! Hello!';
	}
}
```

Тогда, автозагручик в той же папке примет вид:

```php
<?php
require_once __DIR__ . '/../vendor/autoload.php';

\Foo\FoooooClass::work();
```
 
Матриал взят с сайта [https://tyapk.ru/blog/post/php-autoload](https://tyapk.ru/blog/post/php-autoload)