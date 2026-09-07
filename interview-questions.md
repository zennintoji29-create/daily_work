# 🎯 Placement & Core Technical Interview Prep

> Most frequently asked technical interview questions across OOPs, DBMS, OS, and System Design.


---

### 📘 [Entry #4/5] Database Normalization: 1NF, 2NF, 3NF & BCNF Explained
> **Track:** `INTERVIEW-QUESTIONS` | **Updated:** Sep 8, 2026, 03:43 AM

#### 💡 Overview
Eliminating data redundancy and anomaly bugs in relational schema design.

#### 💻 Code & Implementation
```sql
-- 1NF (First Normal Form):
-- Rule: Each column must contain atomic (indivisible) values; no repeating groups.
-- ❌ Bad: Student (id, name, subjects="Math, Science, English")
-- ✅ Good: StudentSubject (student_id, subject_name) with individual rows

-- 2NF (Second Normal Form):
-- Rule: Must be in 1NF AND no Partial Dependencies (all non-key attributes fully depend on primary key).

-- 3NF (Third Normal Form):
-- Rule: Must be in 2NF AND no Transitive Dependencies (non-key attributes cannot depend on other non-key attributes).
-- Example: Employee(emp_id, emp_name, dept_id, dept_name)
-- Fix: Split into Employee(emp_id, emp_name, dept_id) and Department(dept_id, dept_name)
```

#### 🎯 Key Concepts & Takeaways
- Normalization prevents Insertion, Update, and Deletion anomalies in relational databases.
- 3NF is the industry standard balance between avoiding redundancy and minimizing expensive JOIN operations.
