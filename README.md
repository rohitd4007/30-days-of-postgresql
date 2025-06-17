# 30-days-of-postgresql

# Day 1: Introduction to PostgreSQL

## ✅ What is PostgreSQL?

- Open-source, object-relational database.
- ACID compliant.
- Supports complex queries, JSON, full-text search, etc.

## ✅ Key Features

- Extensible and powerful
- Community-supported
- SQL & NoSQL (via JSON)

## 🛠️ Task

- Visit: https://www.postgresql.org
- Read documentation


# Day 2: Installation and Setup

## 🔧 How to Install

### Windows/Mac
- Use the installer from: https://www.postgresql.org/download/

### Ubuntu/Linux
```bash
sudo apt update
sudo apt install postgresql postgresql-contrib
```


---

# Day 3: Creating Tables

## ✅ Create `users` Table
```sql
CREATE TABLE users (
    id SERIAL PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(150) UNIQUE NOT NULL,
    age INTEGER,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

```


---

# Day 4: Inserting Data

## ✅ Single Insert
```sql
INSERT INTO users (name, email, age)
VALUES ('Ravi Sharma', 'ravi@example.com', 28);

```



---


# Day 5: Reading Data – SELECT


## ✅ Syntax
```sql
SELECT column1, column2 FROM table;
SELECT * FROM users;
```


---


# Day 6: Filtering Data – WHERE

## ✅ Syntax
```sql
SELECT * FROM products WHERE stock > 50;
SELECT * FROM users WHERE age IS NOT NULL;
```


---


# Day 7: Updating Data

## ✅ Syntax
```sql
UPDATE users
SET age = 30
WHERE email = 'ravi@example.com';

```

---


# Day 8: Deleting Data

## ✅ Syntax
```sql
DELETE FROM users WHERE age < 18;

```



---


# Day 9: Constraints in PostgreSQL

## ✅ Common Constraints
- `PRIMARY KEY`
- `NOT NULL`
- `UNIQUE`
- `CHECK`
- `DEFAULT`
- `FOREIGN KEY`

## ✅ Example with CHECK
```sql
CREATE TABLE orders (
    id SERIAL PRIMARY KEY,
    amount DECIMAL CHECK (amount > 0)
);

```

---


# Day 10: PostgreSQL Data Types

## ✅ Common Types

| Type      | Example       |
|-----------|----------------|
| INTEGER   | 1, 20, -5      |
| SERIAL    | Auto-increment |
| VARCHAR   | Strings        |
| TEXT      | Long text      |
| BOOLEAN   | true / false   |
| TIMESTAMP | Date & Time    |
| DECIMAL   | 99.99          |

## 🛠️ Task
Try creating a table using at least 5 different data types.


```
