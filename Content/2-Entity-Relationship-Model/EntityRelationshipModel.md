# Entity-Relationship Model

## Modeling
A database model shows the logical structure of a database, including the relationships and constraints that determine how data can be stored and accessed. The main objective of this design process is to avoid redundancy and incompleteness.<br>
A database can be modeled as a collection of entities[^1] and relationship[^2] among entities

#### Instructor Entity Set
| instructor_id | instructor_name |
|---------------|-----------------|    
| 76766 | Crick |                    
| 45565 | Katz |
| 10101 | Srinivasan |
| 98345 | Kim |
|76543 | Singh |
| 22222 | Einstein |

#### Student Entitty Set
| sudent_ID | student_name |
|-----------|--------------|
| 98988 | Tanaka |
| 12345 | Shankar |
| 00128 | Zhang |
| 76543 | Brown |
| 76653 | Aoi |
| 23121 | Chavez |

| 44553 (Peltier) | advisor | 22222(Einstein) |
|-----------------|---------|-----------------|
|Student entity | Relationship | Instructor entity |
<br>

An attribute can also be associated with a relationship set

## Degree of a Relationship Set
Binary Relationship
  - Involves two entity sets (or degree two).
  - It is rare to see a relationship involving more than two entity sets, therefore binary relationship set is the commanly used relationship degree.

## Mapping Cardinality Constraints
Cardinality indicate the the number of entites to which another entity can be associated via a relationship set. For a binary relationship set the mapping cardinality must be one of the following types:
  - One to one
  - One to many
  - Many to one
  - Many to many

## Attributes
An entity is represented by a set of attributes, that is descriptive properties possessed by all members of an entity set.
Example :
  - instructor = (ID, name, street, city, salary) <br>

Domain is the set of permitted values for each attribute
Attribute can be either simple or composite, or Single-valued or multivalued or derived.

- Single Attribute:
  - Eg: first_name
- Composite Attributes
  - Eg: name, which consist of first name, middle name, and last name
- Multivalued Attribute
  - Eg: phone_number
- Derived attribute
  - Eg: age, given date_of_birth

### Attribute Redundancy
An entity should be well defined, thus the attribute redundancy in two or more entities are prevented<br>
Suppose we have entity sets instructor and department;
- instructor, with attributes: ID, name, dept_name, salary
- department, with attributes: dept_name, building, budget
We can model a relation set **inst_dept** for each instructor to associate with a department. Here the attribute **dept_name** appears in both entity sets. Therefore, when we define the instructor entity set, we should remove dept_name from it, anyways we will reintroduce **dept_name** attribute in the instructor entity when we convert it into tables to establish the relationship. 

### Keys
A **super key** of an entity set is a set of one or more attributes whose values uniquely determine entity.<br>
- Eg: consider instructor table
  - ID
  - ID, name
<br>
A **candidate key** of an entity set is a minimal super key
- Eg: consider instructor table
  - ID
<br>
Although several candidate keys may exist, one of the candidate keys is selected to be the **primary key**

#### Keys for relationship sets
Consider many-to-many relationship set takes between instructor and department, here (ID, dept_name) is the super key. It is also a candidate key and the primary key

## ER Diagram

<a href="{./Videos/LucideChartPari01.mp4}" title="Link Title"><img src="{../Intruduction/Images/abstraction-heirarchy.JPG}" alt="Alternate Text" /></a>

[^1]:An Entity is an object that exists and is distinguishable from other objects and is represented by a set of attributes. An entity set is a set of entites of the same type that share the same properties.
[^2]:A relationship is an association among several entites. A relationship set is a mathematical relation among n >= 2 entities, each taken from entity sets.
