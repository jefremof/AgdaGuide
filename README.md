# AgdaGuide
A guide for getting started with Agda language quickly

## Обзор экосистемы:
**0. Основные источники информации:**

[Туториал от создателя языка](https://www.cse.chalmers.se/~ulfn/papers/afp08/tutorial.pdf)

[Agda User Manual](https://agda.readthedocs.io/en/latest/getting-started/index.html)

[Базовые модули (`Nat`, `String`, `List`, etc...)](https://github.com/agda/agda/tree/master/src/data/lib/prim/Agda/Builtin)

[Отлично оформленные лекции](https://github.com/jespercockx/agda-lecture-notes/blob/master/agda.pdf)

[Список репозиториев с использованием Agda](https://github.com/xgrommx/agda-ecosystem)

Стандартная библиотека и её интерактивная версия:
- https://github.com/agda/agda-stdlib/blob/master/README.md
- https://agda.github.io/agda-stdlib/

---
**1. Для Agda нет ни одного линтера.**<br>
Однако есть [рекоммендации](https://github.com/agda/agda-stdlib/blob/master/doc/style-guide.md) по стилю кода

--- 
**2. Для Agda уже написана реализация golden tests.**

https://github.com/agda/agda-stdlib/blob/master/src/Test/Golden.agda<br>
Пример того, как следует использовать эту реализацию, также содержится в [репозитории](https://github.com/agda/agda-stdlib/tree/master/tests)

---
**3. Для Agda есть готовые Github Actions**<br>
https://github.com/wenkokke/setup-agda

---
**4. Парсеры на Agda**

Комбинаторные парсеры:

https://github.com/nad/parser-combinators<br>
https://www.cse.chalmers.se/~nad/publications/danielsson-parser-combinators.pdf<br>
Работает с `stdlib 2.0`, может потребоваться убрать лишний импорт.

Аналогичный проект, есть пример для `JSON`:<br>https://github.com/gallais/agdarsec

у меня так и не получилось скомпилировать его с указанной в репозитории версией `stdlib` (некоторые импорты относятся к другим версиям)

---
**5. Примеры интересных проектов на Agda:**

Сертифицированный компилятор под стековую машину:<br>
http://liamoc.net/posts/2015-08-23-verified-compiler/index.html

Комплияция Middleweight Java в JVM байткод:<br>
https://github.com/ajrouvoet/jvm.agda/tree/master

Интерпретатор Brainfuck:<br>
https://github.com/wouter-swierstra/Brainfuck/blob/master/README.md

Комбинаторные парсеры: (+ занимательная статья)<br>
https://github.com/gallais/agdarsec

X86-64 Assembly от создателя языка:<br>
https://github.com/UlfNorell/x86-agda

лекция, на которой он пишет evaluator арифметических выражений:<br>
https://youtu.be/NrSW7YsneVg

---


## Тесты и доказательства
Даже если функция не содержит ошибок, остаётся вопрос валидации - "Делает ли она то, что нужно?". Это создаёт необходимость в написании тестов.
Тесты для функции f можно написать в следующем формате:

`_ : (f x y) == expected; _ = refl`

Также, можно обернуть их в приватный модуль:

```
module X

record X : ...

private
	module test where
		_ : (f x y) == expected; _ = refl
```
(https://news.ycombinator.com/item?id=24567404)

Написание доказательств с помощью Agda возможно благодаря изоморфизму Карри-Ховарда.
Здесь подробно разобрана эта тема:
https://github.com/jespercockx/agda-lecture-notes/blob/master/agda.pdf

## Обзор стандартной библиотеки:
To be done
 
