![quill](https://raw.githubusercontent.com/getquill/quill/master/quill.png)
# Quill
Compile-time Language Integrated Query for Scala

[![Build Status](https://img.shields.io/travis/getquill/quill.svg)](https://api.travis-ci.org/getquill/quill.svg?branch=master)
[![Codacy Badge](https://img.shields.io/codacy/36ab84c7ff43480489df9b7312a4bdc1.svg)](https://www.codacy.com/app/fwbrasil/quill)
[![codecov.io](https://img.shields.io/codecov/c/github/getquill/quill.svg)](http://codecov.io/github/getquill/quill?branch=master)
[![Join the chat at https://gitter.im/getquill/quill](https://img.shields.io/badge/gitter-join%20chat-green.svg)](https://gitter.im/getquill/quill?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

# Overview #

Quill provides a Quoted Domain Specific Language (QDSL) to express queries in Scala and execute them in a target query language. The library's core is designed to support multiple target languages but the current version only supports the generation of Structured Language Queries (SQL) for interaction with relational databases.

Example usage:

```tut
import io.getquill._

case class Person(name: String, age: Int)

val q = quote {
	query[Person].filter(p => p.name == "Flavio")
}
```

1. The database's schema is expressed using a case class for each table. No additional mapping code is necessary.
2. Queries are defined inside a `quote` block. Quill parses each quoted block of code (quotation) at compile time and translates them to an internal Abstract Syntax Tree (AST)
3. The `db.run` call reads the quotation's AST and translates it to the target language at compile time, emitting the SQL string as a compilation message. As the query string is known at compile time, the runtime overhead is very low and similar to using database driver directly.
4. If configured, the query is verified against the database at compile time and the compilation fails if it is not valid.

# Getting started #



# Queries #

## Quotation ##

## Joins ##



# Sources #

## Probing ##

# Dynamic queries #

# Extending quill #

## Custom encoding ##

## Infix ##

# Internals #

# Known limitations #

# Acknowledgments #

# Contributing #

# License #

See the [LICENSE](https://github.com/getquill/quill/blob/master/LICENSE.txt) file for details.