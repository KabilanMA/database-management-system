#Introduction to Database Management System
### What is Database?

> Oracle defines database as an organized collection of structured information, or data, typically stored electronically in a computer system.

As a traditional method of saving the data in the file system back in the days, created many issues.

Issues are Data Redundancy and Inconsistency[^1], Difficult in accessing data[^2], Integrity Problem[^3], No atomicity of updates[^4],

[^1]:Data Redundancy and Inconsistency.
The file system will consist of multiple file formats which may be incompatible with different operating systems and the files may have duplicate data which needs to be cleared out regularly, even after a single update in the file. When the system fails when writing to the file system, it may leave the whole file in an inconsistent state.

[^2]:Difficulty in accessing data.
When accessing data, one needs to write a different program to carry out each new task. When concurrent access is not handled perfectly it may leave the data in an inconsistent state. 

[^3]:Integrity Problem.

Integrity constraints become buried in the program code rather than being stated explicitly, therefore adding a new constraint and updating the existing constraints is a difficult task.

[^4]:No atomicity of updates.

Failures in updating the file leave the data in an inconsistent state with partial updates carried out. Consider the traditional example of the bank money transfer process; when transferring money from one account to another account, imagine a particular amount is removed from one account.