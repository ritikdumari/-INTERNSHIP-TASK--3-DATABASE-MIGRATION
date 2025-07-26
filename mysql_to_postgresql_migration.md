# 🔄 Data Migration: MySQL to PostgreSQL

**Internship Task**  
**Goal**: Migrate data from a MySQL database to PostgreSQL and ensure data integrity.

---

## 🧰 Tools Used

- MySQL (source database)
- PostgreSQL (target database)
- `pgloader` (for automated migration)
- Optional: DBeaver / MySQL Workbench / pgAdmin (for checking data)

---

## 📌 Step-by-Step Process

### ✅ Step 1: Export MySQL Credentials

Make sure your MySQL database is accessible and you have:

- Host
- Port
- Database name
- Username & Password

Example MySQL connection string:


---

### ✅ Step 2: Prepare PostgreSQL Database

Create a new PostgreSQL database where data will be migrated.

You can use the `createdb` command:

```bash
createdb target_db

✅ Step 3: Install pgloader
pgloader is an open-source tool used to migrate MySQL data to PostgreSQL easily.

Install on Ubuntu/Debian:

sudo apt install pgloader


✅ Step 4: Run Migration Command
Use the following command to migrate data:

pgloader mysql://user:password@localhost/source_db postgresql://pg_user:pg_pass@localhost/target_db


✅ Step 5: Verify Data in PostgreSQL
After migration, connect to PostgreSQL using psql or any GUI tool and run some queries to verify the data.

Example checks:

-- Check row count of a table
SELECT COUNT(*) FROM users;

-- Spot check some records
SELECT * FROM orders LIMIT 10;

Data Integrity Checks
After migration:

✅ Row count matches between MySQL and PostgreSQL

✅ No NULLs in NOT NULL columns

✅ Foreign key constraints working

✅ Sample record checks passed

If needed, you can run parallel queries on both DBs and compare results.

📁 Sample Verification Query

-- MySQL
SELECT COUNT(*) FROM customers;

-- PostgreSQL
SELECT COUNT(*) FROM customers;





