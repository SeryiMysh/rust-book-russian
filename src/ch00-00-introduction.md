# Введение

> Примечание: Данная редакция книги идентична книге [Язык программирования 
> Rust][nsprust] доступной в печатном и электронном формате ebook на сайте 
> [No Starch Press][nsp].

[nsprust]: https://nostarch.com/rust
[nsp]: https://nostarch.com/

Добро пожаловать в *Язык программирования Rust*, это вводная книга по языку 
Rust. Язык программирования Rust позволяет вам писать быстрые и надежные 
приложения. Высокоуровневая эргономика и низкоуровневый контроль, часто 
встречающиеся разногласия в дизайне языков программирования; Rust призван 
решить данный конфликт. Благодаря мощной балансировке технической 
производительности и огромному опыту наших разработчиков, Rust даёт 
возможность контролировать эти низкоуровневые детали (такие как использование 
памяти) без всяких проблем, традиционно связанных с таким контролем.

## Кому нужен Rust

Rust идеальный язык для множества людей по разным причинам. Давайте сделаем
краткий обзор по некоторым группам, самым важным из них.

### Команды разработчиков

Rust предоставляет полезный инструмент для совместной работы больших команд
разработчиков с разным уровнем знаний системного программирования. Низкоуровневый
программный код склонен к множеству труднообнаруживаемых ошибок, которые в 
большинстве других языков могут быть найдены только с помощью обширного 
тестирования и внимательного анализа кода опытными разработчиками. В языке Rust, 
компилятор играет роль шлюза, приостанавливая компиляцию кода содержащего подобные 
неуловимые ошибки, включая ошибки совместного доступа. Используя в работе данный 
компилятор, команда может тратить свое время на логику программы, а не на поиск 
ошибок.

Так же Rust предоставляет современные инструменты разработчика для мира системного 
программирования:

* Cargo, встроенный менеджер зависимостей и инструмент сборки, выполняет добавление, 
  компиляцию и управляет зависимостями безболезненно и согласовано внутри экосистемы 
  Rust.
* Rustfmt обеспечивает единый стиль программирования для всех разработчиков.
* Сервер языка Rust предоставляет Интегрированным Средам Разработки (IDE)
  сервис для автодополнения кода и встроенной информации об ошибках.

Используя эти и другие инструменты существующие в экосистеме Rust, разработчики 
могут быть более продуктивными при написании кода системного уровня.

### Студенты

Rust для студентов и тех кто интересуется изучением концепции работы систем. 
Используя Rust, множество людей могут получить информацию по таким темам
как разработка операционных систем. Наше сообщество очень дружелюбно и будет
счастливо ответить на любые вопросы студентов. Прилагая усилия, такие как эта книга, 
команда Rust хочет сделать системные концепции более доступными для большего числа 
людей, особенно для новичков.

### Компании

Сотни компаний, мелких и крупных, используют Rust в работе для различных задач. 
Данные задачи включают в себя инструменты коммандной строки, веб-сервисы, 
инструментарий DevOps, встроенные устройства, анализ и кодирование аудио и видео, 
криптовалюты, биоинформатика, поисковые машины, приложения для Интернета вещей, машинное 
обучение и даже некоторые важные части веб-браузера Firefox.

### Разработчики программ с открытым исходным кодом

Rust is for people who want to build the Rust programming language, community,
developer tools, and libraries. We’d love to have you contribute to the Rust
language.

### Людей которые ценят скорость и стабильность

Rust is for people who crave speed and stability in a language. By speed, we
mean the speed of the programs that you can create with Rust and the speed at
which Rust lets you write them. The Rust compiler’s checks ensure stability
through feature additions and refactoring. This is in contrast to the brittle
legacy code in languages without these checks, which developers are often
afraid to modify. By striving for zero-cost abstractions, higher-level features
that compile to lower-level code as fast as code written manually, Rust
endeavors to make safe code be fast code as well.

The Rust language hopes to support many other users as well; those mentioned
here are merely some of the biggest stakeholders. Overall, Rust’s greatest
ambition is to eliminate the trade-offs that programmers have accepted for
decades by providing safety *and* productivity, speed *and* ergonomics. Give
Rust a try and see if its choices work for you.

## Для кого эта книга

This book assumes that you’ve written code in another programming language but
doesn’t make any assumptions about which one. We’ve tried to make the material
broadly accessible to those from a wide variety of programming backgrounds. We
don’t spend a lot of time talking about what programming *is* or how to think
about it. If you’re entirely new to programming, you would be better served by
reading a book that specifically provides an introduction to programming.

## Как пользоваться данной книгой

In general, this book assumes that you’re reading it in sequence from front to
back. Later chapters build on concepts in earlier chapters, and earlier
chapters might not delve into details on a topic; we typically revisit the
topic in a later chapter.

You’ll find two kinds of chapters in this book: concept chapters and project
chapters. In concept chapters, you’ll learn about an aspect of Rust. In project
chapters, we’ll build small programs together, applying what you’ve learned so
far. Chapters 2, 12, and 20 are project chapters; the rest are concept chapters.

Chapter 1 explains how to install Rust, how to write a Hello, world! program,
and how to use Cargo, Rust’s package manager and build tool. Chapter 2 is a
hands-on introduction to the Rust language. Here we cover concepts at a high
level, and later chapters will provide additional detail. If you want to get
your hands dirty right away, Chapter 2 is the place for that. At first, you
might even want to skip Chapter 3, which covers Rust features similar to those
of other programming languages, and head straight to Chapter 4 to learn about
Rust’s ownership system. However, if you’re a particularly meticulous learner
who prefers to learn every detail before moving on to the next, you might want
to skip Chapter 2 and go straight to Chapter 3, returning to Chapter 2 when
you’d like to work on a project applying the details you’ve learned.

Chapter 5 discusses structs and methods, and Chapter 6 covers enums, `match`
expressions, and the `if let` control flow construct. You’ll use structs and
enums to make custom types in Rust.

In Chapter 7, you’ll learn about Rust’s module system and about privacy rules
for organizing your code and its public Application Programming Interface
(API). Chapter 8 discusses some common collection data structures that the
standard library provides, such as vectors, strings, and hash maps. Chapter 9
explores Rust’s error-handling philosophy and techniques.

Chapter 10 digs into generics, traits, and lifetimes, which give you the power
to define code that applies to multiple types. Chapter 11 is all about testing,
which even with Rust’s safety guarantees is necessary to ensure your program’s
logic is correct. In Chapter 12, we’ll build our own implementation of a subset
of functionality from the `grep` command line tool that searches for text
within files. For this, we’ll use many of the concepts we discussed in the
previous chapters.

Chapter 13 explores closures and iterators: features of Rust that come from
functional programming languages. In Chapter 14, we’ll examine Cargo in more
depth and talk about best practices for sharing your libraries with others.
Chapter 15 discusses smart pointers that the standard library provides and the
traits that enable their functionality.

In Chapter 16, we’ll walk through different models of concurrent programming
and talk about how Rust helps you to program in multiple threads fearlessly.
Chapter 17 looks at how Rust idioms compare to object-oriented programming
principles you might be familiar with.

Chapter 18 is a reference on patterns and pattern matching, which are powerful
ways of expressing ideas throughout Rust programs. Chapter 19 contains a
smorgasbord of advanced topics of interest, including unsafe Rust, macros, and
more about lifetimes, traits, types, functions, and closures.

In Chapter 20, we’ll complete a project in which we’ll implement a low-level
multithreaded web server!

Finally, some appendixes contain useful information about the language in a
more reference-like format. Appendix A covers Rust’s keywords, Appendix B
covers Rust’s operators and symbols, Appendix C covers derivable traits
provided by the standard library, Appendix D covers some useful development
tools, and Appendix E explains Rust editions.

There is no wrong way to read this book: if you want to skip ahead, go for it!
You might have to jump back to earlier chapters if you experience any
confusion. But do whatever works for you.

<span id="ferris"></span>

An important part of the process of learning Rust is learning how to read the
error messages the compiler displays: these will guide you toward working code.
As such, we’ll provide many examples that don’t compile along with the error
message the compiler will show you in each situation. Know that if you enter
and run a random example, it may not compile! Make sure you read the
surrounding text to see whether the example you’re trying to run is meant to
error. Ferris will also help you distinguish code that isn’t meant to work:

| Ferris                                                                 | Значение                                          |
|------------------------------------------------------------------------|--------------------------------------------------|
| <img src="img/ferris/does_not_compile.svg" class="ferris-explain"/>    | This code does not compile!                      |
| <img src="img/ferris/panics.svg" class="ferris-explain"/>              | This code panics!                                |
| <img src="img/ferris/unsafe.svg" class="ferris-explain"/>              | This code block contains unsafe code.            |
| <img src="img/ferris/not_desired_behavior.svg" class="ferris-explain"/>| This code does not produce the desired behavior. |

In most situations, we’ll lead you to the correct version of any code that
doesn’t compile.

## Исходный код

The source files from which this book is generated can be found on
[GitHub][book].

[book]: https://github.com/rust-lang/book/tree/master/src
