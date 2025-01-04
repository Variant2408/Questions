1. **What is [indexing](https://www.youtube.com/watch?v=DLCY8_A97LY&list=PLFdAYMIVJQHOWJgRrjv_RH-ng95B2h3ON&index=7&ab_channel=NikhilLohia)? Why it is needed.**<br>
       Indexing in a database is a technique used to optimize the performance of queries by minimizing the amount of data the database needs to process.
       It involves creating a data structure (an index) that allows for faster data retrieval operations on a table, much like an index in a book helps
       you locate topics quickly.<br>
    **Most database systems use B-trees or hash tables to implement indexes.**<br>
      The index contains a reference to the actual data in the table.<br>
      
      Types of Indexes:<br>
       **.Primary Index:** Automatically created for the primary key column(s).<br>
       **.Secondary Index:** Created explicitly for other columns to optimize specific queries.<br>
       **.Clustered Index:** Reorders the physical order of the table's data to match the index.<br>
       **.Non-Clustered Index:** Maintains a separate structure from the table data.<br>
       
       A table can only have one clustered index.<br>
       CREATE CLUSTERED INDEX idx_employee_id ON Employees(EmployeeID);<br>

   A non-clustered index creates a separate structure from the data.<br>
   It contains a sorted list of pointers (or references) to the actual data rows.<br>
   Unlike clustered indexes, the data is not reordered; the index simply provides a mapping to locate the data.<br>
   Access involves first searching the index, then using the pointers to fetch the actual data.<br>
   A table can have multiple non-clustered indexes<br>
   CREATE NONCLUSTERED INDEX idx_salary ON Employees(Salary);<br>

   **Why Indexing is Needed**<br>
          1. **Improved Query Performance:** Without an index, the database performs a full table scan, checking each<br>
              row to find matching data, which can be slow for large datasets.<br>
          2. **Efficient Sorting:** Indexes help in sorting data quickly, making ORDER BY and GROUP BY operations faster.<br>
          3. **Faster Joins:** When tables are joined, indexes on the join columns can speed up the process significantly.<br>
          4. **Improved Search Operations:** Searching for specific rows using conditions like WHERE, LIKE, or range queries (BETWEEN, <, >) is more efficient with indexes.<br>
          5. **Reduced Disk I/O:** Indexes minimize the number of disk reads by narrowing down the data blocks that need to be accessed.<br>

   **Trade-Offs of Indexing**<br>
          1.**Additional Storage:** Indexes consume disk space and memory.<br>
          2.**Slower Write Operations:** INSERT, UPDATE, and DELETE operations can be slower because the index needs to be updated each time the data changes.<br>
          3.**Overhead for Maintenance:** Regular maintenance, such as rebuilding or reorganizing indexes, may be required to maintain performance.<br>

    indexing is as important in NoSQL databases as it is in SQL, but it adapts to the unique requirements of NoSQL's diverse data models and query mechanisms.<br>
    Redis does not have traditional indexing mechanisms like SQL or document stores<br>
    


   

