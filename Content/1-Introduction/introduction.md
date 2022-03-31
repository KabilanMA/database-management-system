# Introduction to Database Management System
### What is Database?

Oracle defines database as, 
> An organized collection of structured information, or data, typically stored electronically in a computer system.

As a traditional method of saving the data in the file system back in the days, created many issues.

Issues are Data Redundancy and Inconsistency[^1], Difficult in accessing data[^2], Integrity Problem[^3], No atomicity of updates[^4], Security problems[^5], and etc.
Database system offers solution to all the above problem.

### Level of Abstraction

Database systems comprise of complex data structures. Thus, to make the system efficient for retrieval of data and reduce the complexity of the users, developers use the method of Data Abstraction. There are three level of abstraction. 
1. Physical Level
2. Logical Level
3. View Level

##### Physical Level
This represents actual physical storage structure and access paths to it. This is very close to hardware rather than user.

##### Logical Level
This discribes data stored in database, and the relationships among the data and contraints of the entire database.

##### View Level
This is very close to the user, where the user can query and see different data in different views, therefore this stays on the top of the hierarchy.

# Insert the Hierarchy Image

### Schema
This is analogous to the variable data type information in programming languages, thus representing the logical structure of the database. It comprises of Physical and Logical schema each representing database design at the physical and logical level respectively.<br>
Application depends on the logical schema, therefore database system provide the ability to modify the physical schema without changing the logical schema. In general, the interface between the various levels and components should be wll defined so that changes in some parts do not seriously influence others.

### Instance
Instance is similar to the variable value in programming languages.

### Data Models
Data models are collection tools for describing Data, Data Relationships, Data Semantics, Data Constraints, etc. There are different types of models that are used for different purposes, Relational models, Entity-Relationship data models, Object-based data models, Semistructured data models, Network and Hierarchical data models, etc.

## Relational Model

Edgar Frank "Ted" Codd (19 August 1923 – 18 April 2003) was an English computer scientist who, while working for IBM, invented the relational model for database management, the theoretical basis for relational databases and relational database management systems[[ref](https://en.wikipedia.org/wiki/Edgar_F._Codd)].<br>
A relational database system provides a connection between different entities (logical schema) and this connection between each entity is known as a relation. The relational data model is the pathway to database management and therefore latter part of this document will elucidate the database system considering the relational model.

## Data Manipulation Language (DML)

DML also known as query language is used for accessing and manipulating the data organized by the appropriate data model. There are two classes of DML languages, Procedural and Declarative.<br><br>
A **procedural language** is where the user specifies what data is required and also how to get those data. Due to its complexity for the application developer and the undependability of programmers' code, this is not widely used in high-level application development. Some examples of declarative aka non-procedural languages are;<br>
<ul>
  <li>FORTRAN</li>
  <li>COBOL</li>
  <li>ALGOL</li>
  <li>BASIC</li>
  <li>C</li>
  <li>Pascal</li>
</ul>
In **Declarative(non-procedural) languages** user specifies what data is required without specifying how to get those data. Therefore it reduces some complexity for the application developers. Some examples of declarative query languages are;
<ul>
  <li>SQL</li>
  <li>PROLOG</li>
  <li>LISP</li>
</ul>
<br>
Check <a href="https://www.geeksforgeeks.org/difference-between-procedural-and-non-procedural-language/">here</a> the difference between procedural and declarative query languages.
<br>

## Data Definition Language (DDL)

A data definition language (DDL) is a computer language used to create and modify the structure of database objects in a database.<br>
DDL compiler generates a set of tables templates stored in a data dictionary, which contains metadata (i.e., data about data) that is database schema, integrity constraints, authorization, etc.<br>
**SQL** is the most widely used non-procedural (declarative) data definition and data manipulation language.<br><br>
### SQL Example code as DDL
```SQL
CREATE TABLE student(
  ID VARCHAR(5),
  name VARCHAR(20) NOT NULL, 
  dept_name VARCHAR(20),
  tot_cred NUMERIC(3,0) CHECK (tot_cred >= 0),
  PRIMARY KEY (ID),
  FOREIGN KEY (dept_name) REFERENCES department(dept_name)
    ON DELETE SET NULL
);
```
### SQL Example code as DML
```SQL
SELECT name, dept_name, tot_cred
FROM student
WHERE student.ID = '23121'
```


[^1]:Data Redundancy and Inconsistency: The file system will consist of multiple file formats which may be incompatible with different operating systems and the files may have duplicate data which needs to be cleared out regularly, even after a single update in the file. When the system fails when writing to the file system, it may leave the whole file in an inconsistent state.

[^2]:Difficulty in accessing data: When accessing data, one needs to write a different program to carry out each new task. When concurrent access is not handled perfectly it may leave the data in an inconsistent state. 

[^3]:Integrity Problem: Integrity constraints become buried in the program code rather than being stated explicitly, therefore adding a new constraint and updating the existing constraints is a difficult task.

[^4]:No atomicity of updates: Failures in updating the file leave the data in an inconsistent state with partial updates carried out. Consider the traditional example of the bank money transfer process; when transferring money from one account to another account, imagine a particular amount is removed from one account.

[^5]:Security problems: When multiple users accessing the data, there should be some constraints on which user should be allowed to view which part of the whole data set.
