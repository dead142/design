# ЗАДАЧА

**По теме:** «Классы, работа с конструктором»

**Цель работы:** закрепление практических навыков работы с классами и конструктором

**Формируемые компетенции:** ПК 5.4 «Производить разработку модулей информационной системы в соответствии с техническим заданием», ПК 5.3 Разрабатывать подсистемы безопасности информационной системы в соответствии с техническим заданием


### Задача 1
Написать программу, змейку, которая съедает линию.

Пример вывода результата:

1. \>-------------------
2. \*>------------------
3. \*\*\*\*\*\*\*\*\*\*>---------
4. \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*>---

### Задача 2*

Выполнить задачу №1 в двухмерном пространстве. Перемещение змейки генерируется генератором случайных чисел с учетом возможных ходов. Пространство перемещения задается в виде двухмерного массива.

1. |---*-----------|
2. |---\*\*\*\*\*\*>-----|
3. |---------------|
4. |---------------|

### Методические материалы и помощь

1. [https://www.youtube.com/watch?v=Vhj04XyXXJo](https://www.youtube.com/watch?v=Vhj04XyXXJo)
2. Пример кода с занятия

```php
class CarModel {
	// Состояние объекта
	public $color;
	public $speed;
	public $price;
	private $isSale;
	protected $information;

	public function __construct($someInformation){
		$this->information = $someInformation;
	}
	private function somePrivate(){
		echo $this->isSale;
		
	}
}
$someInformation = 'tesla';
$tesla = new CarModel($someInformation);
$tesla->color = 'black';
$tesla->speed = '300';
$tesla->price = '1$';
//$tesla->isSale = 666; // Cannot access private property CarModel::$isSale
// $tesla->information = 666; // Cannot access protected property CarModel::$information
// $tesla->information; //Cannot access protected property CarModel::$information
var_dump($tesla);

$someInformation = 'Это vw';
$vw = new CarModel($someInformation);
$vw->color = 'grey';
$vw->speed = '100';
$vw->price = '100$';

var_dump($vw);
```

## Шкала оценивания и критерии оценки

| Оценка  | Критерии оценивания выполнения задач (домашнего задания) |
| :------------- | ------------- |
| 5  | Ход решения верный, все его шаги выполнены правильно, получен верный ответ  |
| 4  | Ход решения верный, все его шаги выполнены правильно, но допущена вычислительная ошибка  |
| 3  | Ход решения верный, задание решено не полностью  |
| 2  | Другие случаи, не соответствующие указанным критериям  |



