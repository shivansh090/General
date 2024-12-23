# Database Optimization: Normalization and Functional Dependency  

---

#### **Normalization: A Step Towards Database Optimization**  
Normalization is a crucial process in database design aimed at improving efficiency and reducing redundancy.

---

#### **Functional Dependency (FD)**  
1. **Definition**  
   - Functional Dependency represents the relationship between attributes in a relation.  
   - Example: If `X → Y`, then `X` is called the **Determinant**, and `Y` is the **Dependent**.  

2. **Types of Functional Dependencies**  
   - **Trivial FD**  
     - A functional dependency `A → B` is trivial if `B` is a subset of `A`. Examples: `A → A`, `B → B`.  
   - **Non-Trivial FD**  
     - A functional dependency `A → B` is non-trivial if `B` is not a subset of `A`. In such cases, `A ∩ B = NULL`.  

3. **Rules of Functional Dependency (Armstrong’s Axioms)**  
   - **Reflexive Rule**  
     - If `A` is a set of attributes and `B` is a subset of `A`, then `A → B` holds.  
     - Condition: `A ⊇ B` implies `A → B`.  
   - **Augmentation Rule**  
     - If `A → B` holds, then adding attributes to both sides does not change the dependency.  
     - Example: `A → B` implies `AX → BX`, where `X` is a set of attributes.  
   - **Transitivity Rule**  
     - If `A → B` and `B → C`, then `A → C`.  

---

#### **Why Normalization?**  
1. **Primary Goal**  
   - Eliminate redundancy from the database to improve efficiency.  
2. **Consequences of Redundancy**  
   - Leads to anomalies during data manipulation.  

---

#### **Anomalies Introduced by Redundancy**  
1. **Insertion Anomaly**  
   - Occurs when a new attribute cannot be added without the presence of other related attributes.  
2. **Deletion Anomaly**  
   - Deletion of data may unintentionally result in the loss of important related information.  
3. **Update (Modification) Anomaly**  
   - Updating a single data value might require multiple rows to be updated.  
   - Can lead to **Data Inconsistency** if updates are not uniformly applied.  

**Impact:**  
- Increased database size.  
- Slower database performance.  

**Solution:**  
- **Normalization** is employed to mitigate these anomalies.  

---

#### **What is Normalization?**  
1. **Definition**  
   - A process to minimize redundancy and eliminate undesirable characteristics like insertion, update, and deletion anomalies.  
2. **Process**  
   - Splits composite attributes into individual attributes.  
   - Divides large tables into smaller ones, connecting them via relationships.  
3. **Outcome**  
   - Reduction of redundancy using **Normal Forms**.  

---

#### **Types of Normal Forms**  
1. **First Normal Form (1NF)**  
   - Every cell in a relation must contain an atomic value.  
   - Multi-valued attributes are not allowed.  

2. **Second Normal Form (2NF)**  
   - Relation must satisfy 1NF.  
   - Eliminate **Partial Dependency**:  
     - All non-prime attributes must be fully dependent on the **Primary Key**.  
     - No non-prime attribute should depend on a part of the Primary Key.  

3. **Third Normal Form (3NF)**  
   - Relation must satisfy 2NF.  
   - Eliminate **Transitivity Dependency**:  
     - A non-prime attribute cannot depend on another non-prime attribute.  

4. **Boyce-Codd Normal Form (BCNF)**  
   - Relation must satisfy 3NF.  
   - For every FD `A → B`, `A` must be a superkey.  
   - Prime attributes must not depend on other prime or non-prime attributes.  

---

#### **Advantages of Normalization**  
1. **Minimized Data Redundancy**  
2. **Improved Database Organization**  
3. **Maintained Data Consistency**  

--- 

This structured understanding helps in systematically designing and optimizing databases while ensuring data integrity and efficient performance.
