# Python Basic Utilities - MySQL `pbumysql`

Available on [PyPi](https://pypi.org/project/pbumysql/)

> **This package is still in development!**

**Table of Contents**

1. [Installation](#installation)
2. [Usage](#usage)
3. [Classes](#classes)
    1. [AbstractMysqlStore](#abstractmysqlstore) - abstract class for handling MySQL table access
    2. [AbstractMysqlDocument](#abstractmysqldocument) - abstract class for wrapping rows representing entities
    3. [MysqlConnection](#mysqlconnection) - a wrapper for a MySQL connection


## Installation

Install via pip:

```bash
pip install pbumysql
```

## Usage

It is good practice associating a sub-class of `AbstractMysqlDocument` with a sub-class of `AbstractMysqlStore`. This is
done through the `object_class` parameter in the `super()` constructor call of the store class. Any method for querying 
rows will use that class to deserialise the row into the provided class, which should extend `AbstractMysqlDocument`.

Example: let's say we want to implement access to a collection containing user documents. We'll define a class `User`
that extends `AbstractMysqlDocument` and a class `UserStore` that extends `AbstractMysqlStore`.

- TODO: add code example of store and entity definition
- TODO: add code example of store and entity usage

## Classes

### AbstractMysqlStore

This is an abstract class and cannot be instantiated directly. Instead, define a class that extends this class.

**Constructor**

`__init__(connection, table_name, object_class, logger=None)`

- `connection` - an instance of [`MysqlConnection`](#mysqlconnection)
- `table_name` - the name of the table containing the rows
- `object_class` - used for all the query methods to deserialise the row into a class with attributes for easier access
- `logger` - a logger instance with `.info` / `.error` / `.warn` methods available

**Methods**

TODO: describe methods
  
### AbstractMysqlDocument

TODO: add documentation

### MysqlConnection

TODO: add documentation
