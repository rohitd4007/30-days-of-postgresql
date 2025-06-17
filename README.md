# 30-days-of-postgresql

# 📅 Day 1: Introduction to PostgreSQL

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


# 📅 Day 2: Installation and Setup

## 🔧 How to Install

### Windows/Mac
- Use the installer from: https://www.postgresql.org/download/

### Ubuntu/Linux
```bash
sudo apt update
sudo apt install postgresql postgresql-contrib
```


---

# 📅 Day 3: Creating Tables

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

# 📅 Day 4: Inserting Data

## ✅ Single Insert
```sql
INSERT INTO users (name, email, age)
VALUES ('Ravi Sharma', 'ravi@example.com', 28);

```



---


# 📅 Day 5: Reading Data – SELECT


## ✅ Syntax
```sql
SELECT column1, column2 FROM table;
SELECT * FROM users;
```


---


# 📅 Day 6: Filtering Data – WHERE

## ✅ Syntax
```sql
SELECT * FROM products WHERE stock > 50;
SELECT * FROM users WHERE age IS NOT NULL;
```


---


# 📅 Day 7: Updating Data

## ✅ Syntax
```sql
UPDATE users
SET age = 30
WHERE email = 'ravi@example.com';

```

---


# 📅 Day 8: Deleting Data

## ✅ Syntax
```sql
DELETE FROM users WHERE age < 18;

```



---


# 📅 Day 9: Constraints in PostgreSQL

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


# 📅 Day 10: PostgreSQL Data Types

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


# 📅 Day 11: Updating Records

### 🔹 Update Existing Data in Tables

```sql
-- Update name for user with id 1
UPDATE "User"
SET name = 'Updated Name'
WHERE id = 1;
```

---

# 📅 Day 12: Deleting Records

### 🔹 Remove Unwanted Rows

```sql
-- Delete user with id 2
DELETE FROM "User"
WHERE id = 2;
```

---

# 📅 Day 13: Constraints (NOT NULL, UNIQUE, CHECK)

### 🔹 Enforcing Rules on Data

```sql
-- Add NOT NULL constraint to column
ALTER TABLE products
ALTER COLUMN name SET NOT NULL;

-- Add UNIQUE constraint
ALTER TABLE products
ADD CONSTRAINT unique_name UNIQUE(name);

-- Add CHECK constraint
ALTER TABLE products
ADD CONSTRAINT check_price CHECK (price > 0);
```

---

# 📅 Day 14: Default Values

### 🔹 Set Defaults for Columns

```sql
-- Add default stock value
ALTER TABLE products
ALTER COLUMN stock SET DEFAULT 0;
```

---

# 📅 Day 15: Aliases

### 🔹 Rename Columns/Tables in Output

```sql
-- Alias column and table
SELECT name AS product_name, price
FROM products AS p;
```

---

# 📅 Day 16: Sorting Results

### 🔹 ORDER BY Clause

```sql
-- Sort products by price descending
SELECT *
FROM products
ORDER BY price DESC;
```

---

# 📅 Day 17: Filtering with LIKE & ILIKE

### 🔹 Search with Patterns

```sql
-- Case-sensitive search
SELECT * FROM "User"
WHERE email LIKE '%gmail.com';

-- Case-insensitive search
SELECT * FROM "User"
WHERE email ILIKE '%GMAIL.COM';
```

---

# 📅 Day 18: LIMIT and OFFSET

### 🔹 Pagination

```sql
-- Fetch first 5 products
SELECT * FROM products
LIMIT 5;

-- Skip first 5 and fetch next 5
SELECT * FROM products
OFFSET 5 LIMIT 5;
```

---

# 📅 Day 19: Aggregate Functions (SUM, AVG, COUNT)

### 🔹 Get Summary Stats

```sql
SELECT COUNT(*) AS total_users FROM "User";
SELECT AVG(price) AS avg_price FROM products;
SELECT SUM(stock) AS total_stock FROM products;
```

---

# 📅 Day 20: GROUP BY Clause

### 🔹 Group and Aggregate

```sql
-- Total stock per product name
SELECT name, SUM(stock) as total_stock
FROM products
GROUP BY name;
```

---

