# AgdaGuide
A guide for getting started with Agda language quickly

## Обзор экосистемы:
**0. Языковая база:**

Туториал от создателя языка:
- https://www.cse.chalmers.se/~ulfn/papers/afp08/tutorial.pdf

Agda User Manual
- https://agda.readthedocs.io/en/latest/getting-started/index.html

Базовые модули (`Nat`, `String`, `List`, etc...):
- https://github.com/agda/agda/tree/master/src/data/lib/prim/Agda/Builtin

Стандартная библиотека и её интерактивная версия:
- https://github.com/agda/agda-stdlib/blob/master/README.md
- https://agda.github.io/agda-stdlib/

Отлично оформленные лекции:
- https://github.com/jespercockx/agda-lecture-notes/blob/master/agda.pdf

---
**1. Для Agda нет ни одного линтера.**

Однако есть рекоммендации по стилю кода
- https://github.com/agda/agda-stdlib/blob/master/doc/style-guide.md

--- 
**2. Для Agda уже написана реализация golden tests.**

https://github.com/agda/agda-stdlib/blob/master/src/Test/Golden.agda

Пример того, как следует использовать эту реализацию, также содержится в репозитории:
- https://github.com/agda/agda-stdlib/tree/master/tests

---
**3. Для Agda есть готовые Github Actions**

https://github.com/wenkokke/setup-agda

---
**4. Примеры интересных проектов на Agda:**

Сертифицированный компилятор под стековую машину:
- http://liamoc.net/posts/2015-08-23-verified-compiler/index.html

Комплияция Middleweight Java в JVM байткод:
- https://github.com/ajrouvoet/jvm.agda/tree/master

Интерпретатор Brainfuck:
- https://github.com/wouter-swierstra/Brainfuck/blob/master/README.md

X86-64 Assembly от создателя языка
- https://github.com/UlfNorell/x86-agda


лекция, на которой он пишет программу для вычисления простых арифметических выражений (с поддержкой переменных)
- https://youtu.be/NrSW7YsneVg



## Тесты и доказательства
Даже если функция не содержит ошибок, остаётся вопрос валидации - "Делает ли она то, что нужно?". Это создаёт необходимость в написании тестов и доказательств.
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
 
