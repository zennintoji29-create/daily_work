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

---

### 📘 [Entry #7/31] Top 4 Pillars of Object-Oriented Programming (OOPs)
> **Track:** `INTERVIEW-QUESTIONS` | **Updated:** Sep 7, 2026, 10:15 PM

#### 💡 Overview
Clear explanations and real-world code examples of the 4 core OOP principles asked in technical interviews.

#### 💻 Code & Implementation
```java
// 1. Encapsulation: Bundling data and methods into a class, hiding internal details
class BankAccount {
    private double balance; // Private data
    public double getBalance() { return balance; } // Public getter
    public void deposit(double amount) {
        if (amount > 0) balance += amount;
    }
}

// 2. Abstraction: Hiding implementation complexity and exposing essential interface
abstract class Vehicle {
    abstract void startEngine(); // Abstract method
}

// 3. Inheritance: Reusing code from parent class
class Car extends Vehicle {
    @Override
    void startEngine() {
        System.out.println("Car engine started with key ignition.");
    }
}

// 4. Polymorphism: Compile-time (Overloading) and Runtime (Overriding)
class Calculator {
    int add(int a, int b) { return a + b; }
    double add(double a, double b) { return a + b; } // Overloading
}
```

#### 🎯 Key Concepts & Takeaways
- **Encapsulation**: Protects internal state using access modifiers (`private`, `protected`, `public`).
- **Abstraction**: Focuses on *what* the object does rather than *how* it does it.
- **Inheritance**: IS-A relationship enabling code reuse.
- **Polymorphism**: Ability of an object to take on many forms.

---

### 📘 [Entry #12/31] Database Normalization: 1NF, 2NF, 3NF & BCNF Explained
> **Track:** `INTERVIEW-QUESTIONS` | **Updated:** Sep 7, 2026, 10:15 PM

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

---

### 📘 [Entry #16/31] Process vs Thread & CPU Scheduling Basics
> **Track:** `INTERVIEW-QUESTIONS` | **Updated:** Sep 7, 2026, 10:15 PM

#### 💡 Overview
Essential OS concepts: context switching, shared memory vs isolation, and deadlock conditions.

#### 💻 Code & Implementation
```markdown
### 📌 Process vs Thread Comparison
| Feature | Process | Thread |
|---|---|---|
| **Definition** | A program in execution | A lightweight unit of execution within a process |
| **Memory** | Isolated address space | Shares memory space with peer threads |
| **Creation Cost** | High (Heavyweight) | Low (Lightweight) |
| **Communication** | Inter-Process Communication (IPC, Sockets, Pipes) | Direct shared memory access |

### 🔒 4 Necessary Conditions for Deadlock (Coffman Conditions)
1. **Mutual Exclusion**: At least one resource must be held in non-shareable mode.
2. **Hold and Wait**: A process holds a resource while waiting for additional resources.
3. **No Preemption**: Resources cannot be forcibly taken; must be released voluntarily.
4. **Circular Wait**: A closed chain of processes exists where each process holds a resource needed by the next.
```

#### 🎯 Key Concepts & Takeaways
- Threads within the same process share heap memory, code segments, and open files, but have independent stacks and registers.
- Deadlock can be prevented by breaking any one of the four Coffman conditions (e.g. enforcing a strict resource allocation order).

---

### 📘 [Entry #23/31] Top 4 Pillars of Object-Oriented Programming (OOPs)
> **Track:** `INTERVIEW-QUESTIONS` | **Updated:** Sep 7, 2026, 10:16 PM

#### 💡 Overview
Clear explanations and real-world code examples of the 4 core OOP principles asked in technical interviews.

#### 💻 Code & Implementation
```java
// 1. Encapsulation: Bundling data and methods into a class, hiding internal details
class BankAccount {
    private double balance; // Private data
    public double getBalance() { return balance; } // Public getter
    public void deposit(double amount) {
        if (amount > 0) balance += amount;
    }
}

// 2. Abstraction: Hiding implementation complexity and exposing essential interface
abstract class Vehicle {
    abstract void startEngine(); // Abstract method
}

// 3. Inheritance: Reusing code from parent class
class Car extends Vehicle {
    @Override
    void startEngine() {
        System.out.println("Car engine started with key ignition.");
    }
}

// 4. Polymorphism: Compile-time (Overloading) and Runtime (Overriding)
class Calculator {
    int add(int a, int b) { return a + b; }
    double add(double a, double b) { return a + b; } // Overloading
}
```

#### 🎯 Key Concepts & Takeaways
- **Encapsulation**: Protects internal state using access modifiers (`private`, `protected`, `public`).
- **Abstraction**: Focuses on *what* the object does rather than *how* it does it.
- **Inheritance**: IS-A relationship enabling code reuse.
- **Polymorphism**: Ability of an object to take on many forms.

---

### 📘 [Entry #30/31] Database Normalization: 1NF, 2NF, 3NF & BCNF Explained
> **Track:** `INTERVIEW-QUESTIONS` | **Updated:** Sep 7, 2026, 10:17 PM

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

---

### 📘 [Entry #4/35] Process vs Thread & CPU Scheduling Basics
> **Track:** `INTERVIEW-QUESTIONS` | **Updated:** Sep 8, 2026, 10:26 AM

#### 💡 Overview
Essential OS concepts: context switching, shared memory vs isolation, and deadlock conditions.

#### 💻 Code & Implementation
```markdown
### 📌 Process vs Thread Comparison
| Feature | Process | Thread |
|---|---|---|
| **Definition** | A program in execution | A lightweight unit of execution within a process |
| **Memory** | Isolated address space | Shares memory space with peer threads |
| **Creation Cost** | High (Heavyweight) | Low (Lightweight) |
| **Communication** | Inter-Process Communication (IPC, Sockets, Pipes) | Direct shared memory access |

### 🔒 4 Necessary Conditions for Deadlock (Coffman Conditions)
1. **Mutual Exclusion**: At least one resource must be held in non-shareable mode.
2. **Hold and Wait**: A process holds a resource while waiting for additional resources.
3. **No Preemption**: Resources cannot be forcibly taken; must be released voluntarily.
4. **Circular Wait**: A closed chain of processes exists where each process holds a resource needed by the next.
```

#### 🎯 Key Concepts & Takeaways
- Threads within the same process share heap memory, code segments, and open files, but have independent stacks and registers.
- Deadlock can be prevented by breaking any one of the four Coffman conditions (e.g. enforcing a strict resource allocation order).

---

### 📘 [Entry #13/35] Top 4 Pillars of Object-Oriented Programming (OOPs)
> **Track:** `INTERVIEW-QUESTIONS` | **Updated:** Sep 8, 2026, 10:27 AM

#### 💡 Overview
Clear explanations and real-world code examples of the 4 core OOP principles asked in technical interviews.

#### 💻 Code & Implementation
```java
// 1. Encapsulation: Bundling data and methods into a class, hiding internal details
class BankAccount {
    private double balance; // Private data
    public double getBalance() { return balance; } // Public getter
    public void deposit(double amount) {
        if (amount > 0) balance += amount;
    }
}

// 2. Abstraction: Hiding implementation complexity and exposing essential interface
abstract class Vehicle {
    abstract void startEngine(); // Abstract method
}

// 3. Inheritance: Reusing code from parent class
class Car extends Vehicle {
    @Override
    void startEngine() {
        System.out.println("Car engine started with key ignition.");
    }
}

// 4. Polymorphism: Compile-time (Overloading) and Runtime (Overriding)
class Calculator {
    int add(int a, int b) { return a + b; }
    double add(double a, double b) { return a + b; } // Overloading
}
```

#### 🎯 Key Concepts & Takeaways
- **Encapsulation**: Protects internal state using access modifiers (`private`, `protected`, `public`).
- **Abstraction**: Focuses on *what* the object does rather than *how* it does it.
- **Inheritance**: IS-A relationship enabling code reuse.
- **Polymorphism**: Ability of an object to take on many forms.

---

### 📘 [Entry #18/35] Database Normalization: 1NF, 2NF, 3NF & BCNF Explained
> **Track:** `INTERVIEW-QUESTIONS` | **Updated:** Sep 8, 2026, 10:27 AM

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

---

### 📘 [Entry #20/35] Top 4 Pillars of Object-Oriented Programming (OOPs)
> **Track:** `INTERVIEW-QUESTIONS` | **Updated:** Sep 8, 2026, 10:27 AM

#### 💡 Overview
Clear explanations and real-world code examples of the 4 core OOP principles asked in technical interviews.

#### 💻 Code & Implementation
```java
// 1. Encapsulation: Bundling data and methods into a class, hiding internal details
class BankAccount {
    private double balance; // Private data
    public double getBalance() { return balance; } // Public getter
    public void deposit(double amount) {
        if (amount > 0) balance += amount;
    }
}

// 2. Abstraction: Hiding implementation complexity and exposing essential interface
abstract class Vehicle {
    abstract void startEngine(); // Abstract method
}

// 3. Inheritance: Reusing code from parent class
class Car extends Vehicle {
    @Override
    void startEngine() {
        System.out.println("Car engine started with key ignition.");
    }
}

// 4. Polymorphism: Compile-time (Overloading) and Runtime (Overriding)
class Calculator {
    int add(int a, int b) { return a + b; }
    double add(double a, double b) { return a + b; } // Overloading
}
```

#### 🎯 Key Concepts & Takeaways
- **Encapsulation**: Protects internal state using access modifiers (`private`, `protected`, `public`).
- **Abstraction**: Focuses on *what* the object does rather than *how* it does it.
- **Inheritance**: IS-A relationship enabling code reuse.
- **Polymorphism**: Ability of an object to take on many forms.

---

### 📘 [Entry #29/35] Top 4 Pillars of Object-Oriented Programming (OOPs)
> **Track:** `INTERVIEW-QUESTIONS` | **Updated:** Sep 8, 2026, 10:28 AM

#### 💡 Overview
Clear explanations and real-world code examples of the 4 core OOP principles asked in technical interviews.

#### 💻 Code & Implementation
```java
// 1. Encapsulation: Bundling data and methods into a class, hiding internal details
class BankAccount {
    private double balance; // Private data
    public double getBalance() { return balance; } // Public getter
    public void deposit(double amount) {
        if (amount > 0) balance += amount;
    }
}

// 2. Abstraction: Hiding implementation complexity and exposing essential interface
abstract class Vehicle {
    abstract void startEngine(); // Abstract method
}

// 3. Inheritance: Reusing code from parent class
class Car extends Vehicle {
    @Override
    void startEngine() {
        System.out.println("Car engine started with key ignition.");
    }
}

// 4. Polymorphism: Compile-time (Overloading) and Runtime (Overriding)
class Calculator {
    int add(int a, int b) { return a + b; }
    double add(double a, double b) { return a + b; } // Overloading
}
```

#### 🎯 Key Concepts & Takeaways
- **Encapsulation**: Protects internal state using access modifiers (`private`, `protected`, `public`).
- **Abstraction**: Focuses on *what* the object does rather than *how* it does it.
- **Inheritance**: IS-A relationship enabling code reuse.
- **Polymorphism**: Ability of an object to take on many forms.

---

### 📘 [Entry #32/35] Top 4 Pillars of Object-Oriented Programming (OOPs)
> **Track:** `INTERVIEW-QUESTIONS` | **Updated:** Sep 8, 2026, 10:28 AM

#### 💡 Overview
Clear explanations and real-world code examples of the 4 core OOP principles asked in technical interviews.

#### 💻 Code & Implementation
```java
// 1. Encapsulation: Bundling data and methods into a class, hiding internal details
class BankAccount {
    private double balance; // Private data
    public double getBalance() { return balance; } // Public getter
    public void deposit(double amount) {
        if (amount > 0) balance += amount;
    }
}

// 2. Abstraction: Hiding implementation complexity and exposing essential interface
abstract class Vehicle {
    abstract void startEngine(); // Abstract method
}

// 3. Inheritance: Reusing code from parent class
class Car extends Vehicle {
    @Override
    void startEngine() {
        System.out.println("Car engine started with key ignition.");
    }
}

// 4. Polymorphism: Compile-time (Overloading) and Runtime (Overriding)
class Calculator {
    int add(int a, int b) { return a + b; }
    double add(double a, double b) { return a + b; } // Overloading
}
```

#### 🎯 Key Concepts & Takeaways
- **Encapsulation**: Protects internal state using access modifiers (`private`, `protected`, `public`).
- **Abstraction**: Focuses on *what* the object does rather than *how* it does it.
- **Inheritance**: IS-A relationship enabling code reuse.
- **Polymorphism**: Ability of an object to take on many forms.
