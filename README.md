# Тестовое задание на позицию frontend-разработчик

Напутствие к тестовому заданию. При решении задания нельзя использовать готовые фреймворки и компоненты. Нас интересует как вы умеете решать подобные задачи и создавать что-то с нуля.

# Fizz-buzz задачи

## Задача №1

Написать функцию `dscount`, которая подсчитывает количество идущих подряд символов `s1` и `s2` в строке, без учёта регистра.
Функция должна пройти следующие тесты, как минимум:

```js
"use strict";

// Yor code here ...
Ваш код реализации функции dscount
// ... //

// Для удобства можно использовать эти тесты:
try {
    test(dscount, ['ab___ab__', 'a', 'b'], 2);
    test(dscount, ['___cd____', 'c', 'd'], 1);
    test(dscount, ['de_______', 'd', 'e'], 1);
    test(dscount, ['12_12__12', '1', '2'], 3);
    test(dscount, ['_ba______', 'a', 'b'], 0);
    test(dscount, ['_a__b____', 'a', 'b'], 0);
    test(dscount, ['-ab-аb-ab', 'a', 'b'], 2);
    test(dscount, ['aAa', 'a', 'a'], 2);

    console.info("Congratulations! All tests passed.");
} catch(e) {
    console.error(e);
}

// Простая функция тестирования
function test(call, args, count, n) {
    let r = (call.apply(n, args) === count);
    console.assert(r, `Found items count: ${count}`);
    if (!r) throw "Test failed!";
}
```

Данный код - для примера и не обязателен к использованию в таком виде. Можно вносить модификации.

- Обратите внимание на производительность вашего решения.
- Решение должно быть компактным.
- Решение должно быть простым, умещаться в одном файле и содержать минимум строк кода.


----

# Рефакторинг
Задачи на работу с чужим кодом.

## Задача №1
Посмотрите на код:

```js
function func(s, a, b) {

	if (s.match(/^$/)) {
		return -1;
	}
	
	var i = s.length -1;
	var aIndex =     -1;
	var bIndex =     -1;
	
	while ((aIndex == -1) && (bIndex == -1) && (i > 0)) {
	    if (s.substring(i, i +1) == a) {
	    	aIndex = i;
    	}
	    if (s.substring(i, i +1) == b) {
	    	bIndex = i;
    	}
	    i = i - 1;
	}
	
	if (aIndex != -1) {
	    if (bIndex == -1) {
	        return aIndex;
	    }
	    else {
	        return Math.max(aIndex, bIndex);
	    }
	}
	
	if (bIndex != -1) {
	    return bIndex;
	}
	else {
	    return -1;
	}
}
```

Что можно улучшить? Как бы вы его переписали?

## Задача №2
```js
function drawRating(vote) {
	if (vote >= 0 && vote <= 20) {
    	return '★☆☆☆☆';
	}
	else if (vote > 20 && vote <= 40) {
		return '★★☆☆☆';
	}
	else if (vote > 40 && vote <= 60) {
		return '★★★☆☆';
	}
	else if (vote > 60 && vote <= 80) {
		return '★★★★☆';
	}
	else if (vote > 80 && vote <= 100) {
		return '★★★★★';
	}
}

// Проверка работы результата
console.log(drawRating(0) ); // ★☆☆☆☆
console.log(drawRating(1) ); // ★☆☆☆☆
console.log(drawRating(50)); // ★★★☆☆
console.log(drawRating(99)); // ★★★★★
```

Что можно улучшить? Как бы вы переписали функцию `drawRating` при условии что на вход функции `drawRating` должна приходить переменная vote, содержащая значение от 0 до 100. Интересует именно логика реализации функции, не визуальное отображение звезд.


----

# Практические задачи

## Задача №1
Реализуйте функцию `parseUrl(string)`, которая будет парсить URL строку и возвращать объект с распарсенными данными.
Пример:

```js
let a = parseUrl('http://tutu.ru:8080/do/any.php?a=1&b[]=a&b[]=b#foo')

// Вернет объект, в котором будут следующие свойства:
console.log( a.href == "http://tutu.ru:8080/do/any.php?a=1&b[]=a&b[]=b#foo" )
console.log( a.hash == "#foo" )
console.log( a.port == "8080" )
console.log( a.host == "tutu.ru:8080" )
console.log( a.protocol == "http:" )
console.log( a.hostname == "tutu.ru" )
console.log( a.pathname == "/do/any.php" )
console.log( a.origin == "http://tutu.ru:8080" )
```
Желательно задачу решить как можно меньшим числом строк кода и затратив на реализацию минимум времени.

----

## Комментарии

Результат выполнения задания нужно будет оформить здесь же, на гитхабе.
В качестве ответа не нужно присылать никаких(!) ZIP архивов и наборов файлов. Все ваши ответы должны быть оформлены на https://github.com/ .
Вы присылаете только ссылку на ваш репозиторий. У нас в компании применяется GIT, и если вы его не знаете, вам стоит освоить базу самостоятельно.
Если у вас еще нет аккаунта, то это хороший повод его завести.

Если есть вопросы, вы всегда их можете задать, связавшись с человеком, который выдал вам задание.
