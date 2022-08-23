# H 0.1 - A Specification

This document contains the standard specification, as specified by the original language developers, of the H programming language. As of writing this, it is not subjected to copyright protection and redistribution of this specification is allowed to be done by anyone, compiler/interpreter vendors and developers alike. The specification may not specify on how to implement every possible use case of the H programming language, in in such cases the compiler/interpreter vendor is free to implement such use case however they wanted. One thing to note, however, is that compiler/interpreter vendors are encouraged to provide warnings whenver non-standard use cases are implemented.

This page will give the reader, whether an implementer or a developer, an overview of the H programming language.

## Design Philosophies

The H programming language is intended to imitate natural language, and as a result a majority of language features are going to be designed to imitate natural language (especially English), regardless of the amount of unnecessary verbosity added by doing so. However, despite the English-like nature of the language, it must also remain both unambiguous and Turing complete, both of which adds additional verbosity to the language.

## Execution Model

The H programming language is designed so it can be both compiled and interpreted. This means that the execution model will be based on the assumption that the language will be compiled, as it is easier to interpret a compiled language than to compile an interpreted language. This introduces the following implications for the language.

Unlike other language that are intended to be compiled, H does not have a concept of a _main_ function. 

### Memory Layout and Management

Unlike other languages, H will not introduce the concept of stack-allocated memory nor memory safety. All data, by default, will be allocated on the heap, and the developer is placed in charge of managing memory. Neither the compiler nor the interpreter will perform any checks, start-time, compile-time, or runtime, to ensure memory safety. As a result, memory access and write violations will result in undefined behaviours.

### Packages

An H program is often divided up into _packages_, which are logical translation units. Packages can contain functions, constants, global variables, static variables, and more. A more detailed description of packages will be provided later on.

### Functions

Functions works more or less the same way as other programming language. 