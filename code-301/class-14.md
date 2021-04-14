# DB Normalization

![db normalization](https://camo.githubusercontent.com/35b563175cd93d75c92051e13dceb4af27e683febb70d397b3afb57bc5a70b10/68747470733a2f2f7777772e65647572656b612e636f2f626c6f672f77702d636f6e74656e742f75706c6f6164732f323031392f31302f4e6f726d616c697a6174696f6e2d696e2d53514c2e6a7067)

## Introduction to Database Normalization

Database normalization is a database schema design technique, by which an existing schema is modified to minimize redundancy and dependency of data.

Normalization split a large table into smaller tables and define relationships between them to increases the clarity in organizing data.

## Some Facts About Database Normalization

1. The words normalization and normal form refer to the structure of a database.
2. Normalization was developed by IBM researcher E.F. Codd In the 1970s.
3. Normalization increases clarity in organizing data in Databases.

Normalization of a Database is achieved by following a set of rules called 'forms' in creating the database.

![1st norm](https://camo.githubusercontent.com/fd04ae98ae2d51eb27c4ba137ccc74db4f0bd0caacbd07a286cd2579d0a7548f/68747470733a2f2f692e7974696d672e636f6d2f76692f6d5574415062623145434d2f6d617872657364656661756c742e6a7067)

### First Normal Form (1NF)

Each column is unique in 1NF.

![ta1st norm](https://camo.githubusercontent.com/b583f8eb0e0475bd2d66862a1543eef50b8bc6c88187e99789d9d8c4ecd5c805/68747470733a2f2f312e62702e626c6f6773706f742e636f6d2f2d3832584d454e6578486d632f566a59364c48306d6268492f4141414141414141414e732f597161444962496d737a592f73313630302f314e462e676966)

### Second Normal Form (2NF)

The entity should be considered already in 1NF, and all attributes within the entity should depend solely on the unique identifier of the entity.

![2nd norm](https://camo.githubusercontent.com/4376c0775565be3289eb891dc0411a7af2efc205604351e0de214068b3c929f3/68747470733a2f2f7777772e657373656e7469616c73716c2e636f6d2f77702d636f6e74656e742f75706c6f6164732f323031342f30362f5365636f6e644e6f726d616c466f726d53616d706c6544617461332e706e67)

### Third Normal Form (3NF)

The entity should be considered already in 2NF, and no column entry should be dependent on any other entry (value) other than the key for the table.

If such an entity exists, move it outside into a new table.

3NF is achieved, considered as the database is normalized.

### Fourth Normal Form (4NF)

Tables cannot have multi-valued dependencies on a Primary Key.

### Fifth Normal Form (5NF)

A composite key shouldn't have any cyclic dependencies.

Well, this is a highly simplified explanation for Database Normalization. One can study this process extensively, though. After working with databases for some time, you'll automatically create Normalized databases, as it's logical and practical.
