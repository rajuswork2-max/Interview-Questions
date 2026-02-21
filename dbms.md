# Database Management Systems (DBMS) Interview Questions

## Basic Level

**Q1: What is a DBMS and what are its advantages over a standard file system?**
**Answer:**
A DBMS is software used to store, retrieve, and manage data efficiently. 
Advantages over flat files (like Excel/CSV) include:
* **No Data Redundancy:** Data is stored in one place, avoiding duplication.
* **Data Integrity:** Enforces rules and constraints (like ensuring ages cannot be negative).
* **Concurrency:** Allows multiple users to read/edit data at the exact same time without overwriting each other.
* **Security:** Provides user authentication and access controls.

**Q2: Define Primary Key and Foreign Key.**
**Answer:**
* **Primary Key:** A column (or set of columns) that uniquely identifies every row in a table. It cannot be `NULL` and must be entirely unique.
* **Foreign Key:** A column in one table that links to the Primary Key of another table. It is used to establish and enforce relationships between the data in the two tables.

**Q3: What are DDL, DML, and DCL commands in SQL?**
**Answer:**
* **DDL (Data Definition Language):** Defines the database structure. Example: `CREATE`, `ALTER`, `DROP`.
* **DML (Data Manipulation Language):** Manipulates the actual data. Example: `SELECT`, `INSERT`, `UPDATE`, `DELETE`.
* **DCL (Data Control Language):** Controls access to the database. Example: `GRANT`, `REVOKE`.

## Intermediate Level

**Q4: Explain the ACID properties of a transaction.**
**Answer:**
ACID ensures database transactions are processed reliably:
* **Atomicity:** "All or Nothing." If a transaction has 3 steps and step 3 fails, steps 1 and 2 are rolled back holding no effect.
* **Consistency:** The database must remain in a valid state before and after the transaction, following all defined constraints.
* **Isolation:** Concurrent transactions execute independently and do not interfere with each other. 
* **Durability:** Once a transaction is committed, it is saved permanently, even in the event of a power failure.

**Q5: What are the different types of SQL Joins?**
**Answer:**
* **INNER JOIN:** Returns only the rows where there is a match in *both* tables.
* **LEFT JOIN:** Returns *all* rows from the left table, and the matched rows from the right table (unmatched right columns become `NULL`).
* **RIGHT JOIN:** Returns *all* rows from the right table, and the matched rows from the left table.
* **FULL OUTER JOIN:** Returns all rows when there is a match in either the left or right table.

**Q6: What is Normalization? Why do we do it?**
**Answer:**
Normalization is the process of organizing data to reduce redundancy and improve data integrity. It involves dividing large tables into smaller, linked tables. We do it to prevent data anomalies during Insert, Update, or Delete operations (e.g., updating a customer address once instead of in 50 different order rows).

## Advanced Level

**Q7: Explain the difference between Clustered and Non-Clustered Indexes.**
**Answer:**
* **Clustered Index:** Dictates the physical storage order of the data on the disk. Because data can only be sorted one way physically, a table can only have **one** clustered index (usually the primary key).
* **Non-Clustered Index:** Like an index at the back of a book. It stores a sorted list of the columns you are indexing alongside a pointer to the physical location of the full row. A table can have **multiple** non-clustered indexes.

**Q8: What is a Stored Procedure vs. a Trigger?**
**Answer:**
* **Stored Procedure:** Pre-compiled SQL code that you can save and call manually whenever you need it. Used to encapsulate complex business logic.
* **Trigger:** Special block of SQL code that executes **automatically** in response to specific events (like `INSERT`, `UPDATE`, or `DELETE`) on a particular table. Used for automated auditing or enforcing complex rules.

**Q9: How do you solve the N+1 query problem?**
**Answer:**
The N+1 problem occurs (often when using ORMs) when your code executes 1 query to fetch a list of N objects, and then executes N additional individual queries to fetch their related data (causing a massive performance hit).
* **Solution:** Use "Eager Loading". Instead of looping through the N objects to fetch relations, use `JOIN` or SQL `IN` clauses to fetch all related data upfront in 1 or 2 queries total.
