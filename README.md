## Full Stack Developer Interview Questions

### React

1. **How do you handle form validations in React?**
   - **Answer:** Form validations in React can be handled using controlled components and validation libraries like Formik or Yup. Controlled components manage form inputs via state and can validate inputs on change or on submit.

2. **What is the purpose of `useMemo` and when would you use it?**
   - **Answer:** `useMemo` is a hook that memoizes a computed value, recomputing it only when its dependencies change. It's useful for optimizing performance in situations where a costly calculation is required on every render.

3. **Explain the lifecycle methods of class components in React.**
   - **Answer:** Class component lifecycle methods include `componentDidMount` (invoked after the component is mounted), `componentDidUpdate` (invoked after the component updates), and `componentWillUnmount` (invoked just before the component is unmounted).

4. **How does the Context API improve state management in React applications?**
   - **Answer:** The Context API allows you to pass data through the component tree without prop drilling, making it easier to manage and share state across deeply nested components.

5. **What are higher-order components (HOCs) in React?**
   - **Answer:** HOCs are functions that take a component and return a new component, allowing you to reuse component logic. They enhance or modify the behavior of the original component without changing its implementation.

### Node.js

1. **What is the purpose of the `cluster` module in Node.js?**
   - **Answer:** The `cluster` module allows you to create child processes (workers) that share the same server port. This is useful for taking advantage of multi-core systems, improving the performance and reliability of a Node.js application.

2. **How do you handle file uploads in a Node.js application?**
   - **Answer:** File uploads can be handled using middleware like `multer` in an Express application. `multer` processes multipart/form-data, storing uploaded files and making them available in the request object.

3. **What is the difference between `process.nextTick()` and `setImmediate()` in Node.js?**
   - **Answer:** `process.nextTick()` schedules a callback to be invoked in the same phase of the event loop, before the next I/O event. `setImmediate()` schedules a callback to be executed in the next iteration of the event loop.

4. **How do you secure a Node.js application?**
   - **Answer:** Securing a Node.js application involves using HTTPS, validating and sanitizing user inputs, employing security headers with `helmet`, managing dependencies, and protecting against common vulnerabilities like SQL injection and cross-site scripting (XSS).

5. **What is middleware in Express, and how does it work?**
   - **Answer:** Middleware in Express is a function that has access to the request, response, and next objects. It processes requests, performs tasks like authentication or logging, and can modify the request/response or terminate the request-response cycle.

### MongoDB

1. **How do you create and manage indexes in MongoDB?**
   - **Answer:** Indexes in MongoDB are created using the `createIndex` method on a collection. Indexes can be single-field, compound, multi-key, text, or geospatial. Managing indexes involves analyzing query performance and using the `explain` method to ensure indexes are used effectively.

2. **What is the purpose of the aggregation framework in MongoDB?**
   - **Answer:** The aggregation framework processes and transforms documents within a collection, enabling operations like filtering, grouping, and sorting. It's used for advanced data analysis and aggregation tasks.

3. **How does MongoDB handle replication?**
   - **Answer:** MongoDB uses replica sets for replication. A replica set consists of a primary node and multiple secondary nodes. The primary node receives all write operations, which are then replicated to the secondaries. This provides data redundancy and high availability.

4. **Explain the purpose of the `$lookup` operator in MongoDB.**
   - **Answer:** The `$lookup` operator performs a left outer join to a collection in the same database, allowing you to combine documents from different collections based on a specified field.

5. **How do you perform a text search in MongoDB?**
   - **Answer:** Text search in MongoDB is performed by creating a text index on the fields you want to search. You can then use the `$text` operator in your query to search for documents that match a given text.

### PostgreSQL

1. **What is a stored procedure in PostgreSQL, and how is it different from a function?**
   - **Answer:** A stored procedure in PostgreSQL is a set of SQL statements stored in the database and executed as a single unit. Unlike functions, stored procedures can perform transaction control (COMMIT and ROLLBACK) and do not have to return a value.

2. **Explain the concept of table partitioning in PostgreSQL.**
   - **Answer:** Table partitioning in PostgreSQL divides a large table into smaller, more manageable pieces called partitions. This improves performance and maintenance by allowing queries to scan only relevant partitions and making it easier to manage large datasets.

3. **How do you use the `EXPLAIN` command in PostgreSQL?**
   - **Answer:** The `EXPLAIN` command in PostgreSQL is used to analyze and display the execution plan of a query. It shows how the database engine will execute the query, including details about joins, scans, and indexes, helping to optimize query performance.

4. **What are CTEs (Common Table Expressions) in PostgreSQL, and how do you use them?**
   - **Answer:** CTEs are temporary result sets that can be referenced within a `SELECT`, `INSERT`, `UPDATE`, or `DELETE` statement. They improve query readability and organization. Example:
   ```sql
   WITH sales_cte AS (
     SELECT salesperson_id, SUM(amount) AS total_sales
     FROM sales
     GROUP BY salesperson_id
   )
   SELECT * FROM sales_cte WHERE total_sales > 10000;
   ```

5. **How do you handle JSON data in PostgreSQL?**
   - **Answer:** PostgreSQL supports JSON data types (`json` and `jsonb`). You can store, query, and manipulate JSON data using operators and functions. The `jsonb` type is more efficient for indexing and querying. Example of a JSON query:
   ```sql
   SELECT data->>'name' AS name
   FROM users
   WHERE data->>'role' = 'admin';
   ```

### GraphQL

1. **What is a resolver in GraphQL, and how does it work?**
   - **Answer:** A resolver is a function that resolves a value for a type or field in a GraphQL schema. Resolvers retrieve data from a data source (e.g., database) and return it to the client. They are defined for each field in the schema and can perform operations like querying, mutating, and transforming data.

2. **How do you handle pagination in GraphQL?**
   - **Answer:** Pagination in GraphQL can be handled using `limit` and `offset` arguments or by implementing cursor-based pagination. Cursor-based pagination uses a cursor to keep track of the current position in the result set, enabling efficient and scalable pagination.

3. **What are the benefits of using GraphQL fragments?**
   - **Answer:** GraphQL fragments allow you to reuse common field selections across multiple queries or mutations. This reduces redundancy, improves query readability, and ensures consistency in the requested data.

4. **Explain how to use aliases in GraphQL queries.**
   - **Answer:** Aliases in GraphQL allow you to rename the fields in the response, enabling you to fetch the same field with different arguments in a single query. Example:
   ```graphql
   query {
     user1: user(id: "1") {
       name
     }
     user2: user(id: "2") {
       name
     }
   }
   ```

5. **How do you handle batch requests in GraphQL?**
   - **Answer:** Batch requests in GraphQL can be handled using tools like DataLoader. DataLoader batches and caches multiple requests to the same data source, reducing the number of database queries and improving performance.

---

