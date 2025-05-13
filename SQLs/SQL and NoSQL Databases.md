**SQL** (Structured Query Language) and **NoSQL** (Not Only SQL) databases are two main types of databases, each with unique structures, advantages, and use cases.

## Types of Databases

1. [[#Relational Databases]]    
    - Examples: [[MySQL]], [[MariaDB]], [[PostgreSQL]]

1. [[#NoSQL Databases]]    
    - Examples: [[DynamoDB]], [[MongoDB]]

Each type of database has its own unique features, suited to different types of applications and workloads.

---

# Relational Databases

[[SQL and NoSQL Databases]]

Relational Databases (RDBMS) use structured tables to store data in rows and columns, which allows for complex queries using SQL (Structured Query Language). They maintain **ACID** (Atomicity, Consistency, Isolation, Durability) properties, ensuring data reliability and integrity.

### Characteristics of Relational Databases

- **Structured Tables**: Data is stored in structured tables (rows and columns).
- **Primary Key Constraints**: Enforce uniqueness of records.
- **Relationships**: Tables are related through keys (e.g., foreign keys).
- **Data Integrity**: Ensures accurate data through normalisation.

Popular relational databases include:

- [[MySQL]]
- [[MariaDB]]
- [[PostgreSQL]]

For unstructured or dynamic data, see [[#NoSQL Databases]].

---

# NoSQL Databases

[[SQL and NoSQL Databases]]

NoSQL databases handle large volumes of unstructured data and are optimised for specific data models (document, key-value, graph, or column). They prioritise **flexibility** and **horizontal scalability**, making them ideal for modern applications that need to scale rapidly.

### Characteristics of NoSQL Databases

- **Schema-less Design**: Allows for flexible data structures.
- **High Scalability**: Scales horizontally across multiple servers.
- **CAP Theorem**: Priorities availability and partition tolerance over strict consistency.

Types of NoSQL databases include:

- Document-oriented (e.g., [[MongoDB]])
- Key-value store (e.g., [[DynamoDB]])

For applications with complex queries and strict data relationships, see [[#Relational Databases]].