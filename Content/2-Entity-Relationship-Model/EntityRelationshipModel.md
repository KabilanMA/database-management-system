# Entity-Relationship Model

## Modeling
A database model shows the logical structure of a database, including the relationships and constraints that determine how data can be stored and accessed. The main objective of this design process is to avoid redundancy and incompleteness.<br>
A database can be modeled as a collection of entities[^1] and relationship[^2] among entities

###### Instructor Entity Set
| instructor_id | instructor_name |
|---------------|-----------------|    
| 76766 | Crick |                    
| 45565 | Katz |
| 10101 | Srinivasan |
| 98345 | Kim |
|76543 | Singh |
| 22222 | Einstein |

###### Student Entitty Set
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
 

[^1]:An Entity is an object that exists and is distinguishable from other objects and is represented by a set of attributes. An entity set is a set of entites of the same type that share the same properties.
[^2]:A relationship is an association among several entites. A relationship set is a mathematical relation among n >= 2 entities, each taken from entity sets.
