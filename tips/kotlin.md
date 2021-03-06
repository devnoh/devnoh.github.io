# KOTLIN

## Install

$ brew install kotlin

## Kotlin REPL

$ kotlinc-jvm

## Language Features

* Static Typing (cf. Groovy is dynamic typed)
* Object Oriented & Functional
* Lambdas (High Order Functions)
* Null Safety
* Extension Funtions & Operation Overloading
* Generics
* Data Classes

### Java features that Kotlin lacks

* Checked Exceptions
* Primitive types that are not classes
* Static members
* Non-private fields
* Whildtypes

### Kotlin features that Java lacks

* Lambda Expressions (inline functions)
* Extention Functions
* Null Safety
* Smart Casts
* String Templates
* Properties
* Singletons
* Operator Overloading
* Companion Objects
* Data Classes
* Corutines
* ...

-------------------

## Kotlin

* Runs anywhere the JVM can run
* Statically typed
* Objected-oriented
* Functional programming

## Guiding Principles

* Conciseness
* Safety
* Pragmatism
* Interoperability

## Basic Differences Between Kotlin and Java

* var (mutable)
* val (immutable)
* no semicolon(;)
* [] for collections
* type alias
* String.length is a property
* no ternary operator
* no for-loop
* == is structurally equal (structural equality; equals())
* === is referentially equal (referential equality; == in Java)
* != is structurally not equal
* !== is referentially not equal
* and (instead of &)
* or (instead of |)
* is or !is (instead of instanceOf)
* cast using 'as'
* Any is the root class
* smart casting
* $ in string template
* """ for raw string

## Data Types and Null Reference Handling

* Byte, Short, Int, Long, Float, Double, Boolean
* Any, Void, Nothing
* arrayOf, intArrayOf, Array<Int>, Array<Any>

## Access Modifiers

| Access Modifier  | Kotlin                         | Java                            |
| ---------------- | ------------------------------ |-------------------------------- |
| (default)        | As same as public final        | Visible within the same package |
| private          | Visible within the same file   | Can't be used                   |
| protected        | Can't be used                  | Can't be used                   |
| public           | Visible every                  | Visible everywhere              |
| internal         | Visible within the same module | N/A                             |
