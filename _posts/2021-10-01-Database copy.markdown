---
layout: post
title:  "The Relational Data Model and Relational Database Constraints"
date:   2021-10-01 22:24:36 +0530
categories: Databse
---

### **Definition** <br/>


Based on the concept of a Relation<br/>
A relation looks like a table of values<br/>
(Relation is a table (Collection of Tuples) and Tuple is just a row)<br/>
   - Contains a set of rows, formally called **tuples**<br/>
      - Each row represents certain facts that correspond to a real-world entity or relationship<br/>
   - Column header/name indicates the meaning of the data items in that column <br/>
      - Column header is formally called an attribute name (or just attribute) <br/>
<br/>
<br/>

**Example of a Relation** <br/>
<br/>

![Image Alt MemoryLayout](/assets/relation1.png) <br/>
<br/>

**Key of a Relation**
- Each row has a value of data item (or set of items) that uniquely identifies that row in the table <br/>
   - **The Key** (Distinguish one tuple from other) <br/>
   - **In the STUDENT table, SSN is the key** <br/>
- Sometimes row-ids or sequential numbers are assigned as keys to identify the rows in table <br/>
<br/>

**Schema** <br/>
<br/>

The **Schema** (or description) of a Relation: <br/>
- Denoted by R(A1,A2,...An)<br/>
- **R** is the name of the relation, attributes of the relation are **A1,A2,...An** <br/>
- Example: CUSTOMER(cust-id,Cust-name,Address,Phone#)<br/>
- A **Tuple** is an ordered set of values (When you specify the value) <br/>
   - <632895,"John Smith", "101 Main St. Atlanta, GA 30332","(404) 892 2000"> <br/>
- A relation is a **Set** of such tuples (rows) <br/>
<br/>

**Characteristics Of Relations** <br/>
<br/>


Ordering of tuples in a relation instance (state): <br/>
   - The tuples **are not considered to be ordered**<br/>
Ordering of attributes in relation schema R(and of values within each tuptle): <br/>
   - Depends on the notation <br/>
      - R(A1,A2,...An) <br/>
      - T= {<name,"John">, <SSN,123456789>} <br/>


**Relational Integrity Constraints** <br/>
<br/>

**Conditions** that must hold on **all** valid relation states <br/>
Four main types in the relational model: <br/>
1. Key Constraints <br/>
2. Entity Integrity Constraints<br/> 
3. Referential integrity constraints <br/>
4. Domain Constraints <br/>
   - Every value in a tuple must be from the domain of its attribute <br/>
   - Or it could be null, if allowed for that attribute <br/>
      - represent values that are unknown or not available <br/>
<br/>

**Key Constraints** <br/>
<br/>

**Superkey** of R: <br/>
- No two tuples in any valid relation stae r(R) will have the same value for SK <br/>
   - For any distinct tuples t1 and t2 in r(R), t[SK] != t2[SK] <br/>
   <br/>
**Key** of R: <br/>
- A "minimal" superkey
- Removal of any attribute from K results in a set of attributes that does not meet the criterion of SuperKey** <br/>
<br/>
A key is a Superkey but not vice versa  <br/>

- Remove some attribute, if it is still SK then it is not a Key <br/>
- Example: **SSN** for employee is a candiate key, however, **SSN** + **PHONE#** Also unique because the present of the **SSN** there. 
- Super Key - may or may not have some unnecessary attribute or non unique attribute (SuperKey may or may not be a minimal form while key or candiate key will always have uniqueness property) <br/>
<br/>

**Key Constraints Example** <br/>
Example: Consider the **CAR** relation schema:<br/> 
- CAR (State, Reg#, SerialNo, Make, Model, Year) <br/>
- Has two keys: Key1 = {State,Reg#}; Key2 = {SerialNo} <br/>
   - Both are also **superkeys of CAR** <br/>
   - {SerialNo,Make} is a **superkey but not a key** <br/>
- In general: <br/>
   - Any key is a **superkey** <br/>
   - Any set of attributes that includes a key is a superkey <br/>
   - **A minimal superkey is also key** <br/>
<br/>

- Each key is a **Candidate Key** <br/>
- If a relation has several candidate keys, one is chosen by the **primary key** <br/>
   - The primary key attributes are underlined<br/>
      - CAR(state, reg#, <u>SerialNo</u>,Make,Model,Year) <br/>
   - Primary key value uniquely identifies each tuple in relation <br/>
   
   ![Image Alt MemoryLayout](/assets/key1.png) <br/>

<br/>

**Entity Integrity(Act of implementing that constraints)** <br/>
<br/>

The primary key attributes **PK** of each relation schema R cannot have null values in any tuples of r(R) <br/>

   - If PK has several attributes, null is not allowed in any of these attributes <br/>

Other attributes of R may be constrained to disallow null values<br/>

Also called NOT NULL constraints <br/>
<br/>

**Referential Integrity** <br/>
<br/>
A constraint involving two relations <br/>

- Used to specify a relationship among tuples in two relations: <br/>
   - referencing relation(Secondary Relation) and referenced relation(Primary Source of data) <br/>
- Tuples in the referencing relation R1 have attributes FK (called foreign key attributes) that reference the primary key attributes PK of the referenced relation R2 <br/>

<br/>

**Referential Integrity (or foreign key) constraint** <br/>
<br/>

- The value in the foreign key column(s), FK, of the referencing relation, R1, can be either: <br/>

   - an existing value of a corresponding primary key PK, in the referenced relation R2 <br/>
   - a null, if FK in R1 is not part of R1's own primary key <br/>

 ![Image Alt MemoryLayout](/assets/ref1.png) <br/>

 Why we pick EMPLOYEE's SSN as the primary key?, In the Deaprtment "Mgr_ssn" uses the EMPLOYEE's SSN. Therefore, <br/>
 **MGR_SSN** is the foreign key attribute. This **MGR_SSN** refers to primary key **SSN** <br/>
<br/>





