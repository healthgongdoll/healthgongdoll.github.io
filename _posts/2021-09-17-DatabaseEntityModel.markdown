---
layout: post
title:  "Entity-Relationship (ER) Model Properties"
date:   2021-09-17 11:24:36 +0530
categories: Database
---

### **Entity-Relationship Model** <br/>


**Displaying an Entity type** <br/>
Entity type is displayed in a **Rectangular Box**<br/>
Attributes are displayed in **Ovals** <br/> 
    - Each attribute is **connected to its entity type** <br/>
    - Components of a **Composite attribute are connected to the oval representing the composite attribute** <br/>
    - Each key attribute is **Underlined** <br/>
    - Multivalued attributes displayed in **Double Ovals** <br/>
<br/>

![Image Alt MemoryLayout](/assets/entity.png) <br/>

<br/>

**Entity Type CAR** <br/>
<br/>

![Image Alt MemoryLayout](/assets/entity1.png) <br/>

- Name of Entity: **CAR** <br/>
- Rest of Ovals: **Attributes** <br/>
- Multivalue Attribute: **Color** <br/>
- Key Attribute: **Registration**, **Vehicle_id** <br/>
- Composite Attribute (Two Sub Ovals): **Registration**, **State**, **Number** <br/>
<br/>

**CAR** is the **Entity Set** <br/>
<br/>

**Refining the initial design by introducing relationships** <br/>
<br/>

- Some aspects in the requirements will be represented as **relationships** <br/>
- ER model has three main concepts: **Entities**, **Attributes**, **Relationships** <br/>
- A **relationship** is association of two or more distinct entities with a specific meaning: <mark style='background-color: #fff5b1'>EMPLOYEE John SMITH **works** on the productX PROJECT</mark> <br/>
<br/>

**Relationships and Relationship Types** <br/>
<br/>

- Relationships of the same type: **Relationship Type** <br/>
**WORKS_ON** relationship type: **EMPLOYEE** and **PROJECT** <br/>
- The degree of a relationship type is tyhe number of participating entity types <br/>
Both **MANAGES** and **WORKS_ONE** are <mark style='background-color: #fff5b1'> binary relationships </marks> <br/>
- In ER diagram, **relationship type** is represented as: **DIAMOND SHAPED BOX connected to the participating entity type via straight lines** <br/>

![Image Alt MemoryLayout](/assets/entity2.png) <br/>
1. Between the same pair of entity types, we can have more relationship <br/>
2. In the Diagram we use simple line not using the arrows (NO Direction)<br/>
3. Left to right fashion <br/>

<br/>

**Relationship Type vs Relationship Set** <br/>
<br/>
Relationship Type: <br/>
    - Schema description of a relationship <br/>
    - Identifies the relationship name, participating entity types, and certain relationship constraints  <br/>
<br/>
Relationship Set: <br/>
    - Current set of relationship instances in the database <br/>
    - Current state of a relationship type <br/>
    <br/>

**Refining the COMPANY database schema by introducing relationships** <br/>
<br/>
Six relationship types are identified <br/>
    - All are binary relationships (degree 2) <br/>
    - Listed below with their participating entity types: <br/> 
        1. WORKS_FOR(between EMPLOYEE, DEPARTMENT) <br/>
        2. MANAGES (also between EMPLOYEE, DEPARTMENT) <br/>
        3. CONTROLS (between DEPARTMENT, PROJECT) <br/>
        4. WORKS_ON (between EMPLOYEE, PROJECT) <br/>
        5. SUPERVISION (between EMPLOYEE (as subordinate), EMPLOYEE(as supervisor)) <br/>
        6. DEPENDENTS_OF (between EMPLOYEE, DEPENDENT) <br/>
<br/>

![Image Alt MemoryLayout](/assets/entity3.png) <br/>

<br/>

**Relationship vs. Attribute** <br/>
Some attributes are refined/merged into relationships: <br/>
Manager of Department -> MANAGES <br/>
Works_on of Employee -> WORKS_ON <br/>
Department of EMPLOYEE -> WORKS FOR <br/>
<br/>

![Image Alt MemoryLayout](/assets/entity4.png) <br/>
It is better to have relationship not having separate attributes <br/>

<br/>

**Constraints on Relationship Types** <br/>
<br/>
Ratio Constraints <br/>
    - Cardinality Ratio (specifies maximum participation) <br/>
        1. One-to-One (1:1) <br/>
        2. One-to-Many (1:N) or Many-to-One (N:1) <br/>
        3. Many-to-Many (M:N) <br/>
        <br/>
    - Participation Constraint or Existence Dependency Constraint (Specifies minimum participation) <br/>
        1. Zero (optional participation, not existence-dependent) <br/>
        2. One or More (mandatory participation, existence-dependent) <br/>
        <br/>
<br/>

**Many to One (N:1) Relationship** <br/>
<br/>

![Image Alt MemoryLayout](/assets/entity5.png) <br/>

- Fundemental Definition of Many-To-One relationship is that when there is a relationship type in which multiple entity from one entity set <br/>
    can be linked together with the certain entity on the another side <br/>
- Department: Usually there are more than one employee, more than one employee is connected to single entity in the department entity diagram <br/>
- Students enrolled in courses (Many to one relationship) <br/>
<br/>

**Many to Many (M:N) Relationship** <br/>
<br/>

![Image Alt MemoryLayout](/assets/entity6.png) <br/>

- Usually more than one project connected with one employee, Employee can work with multiple projects <br/>
- Analyzing in business requirement is important in conceptual schema because that will decide what kind of constraints we have to implement <br/>
- Cardinality constraints puts on the maximum participation (They do not say anything about minimum participation) and minimum participation decided by participation constraints <br/>
<br/>

**Notation for Ratio Constraints** <br/>
<br/>

- Cardinality ratio (of binary relationship): 1:1, 1:N, N:1, or M:N ( **PLACE THE NUMBERS ON THE RELATIONSHIP EDGES** )<br/> 
![Image Alt MemoryLayout](/assets/entity7.png) <br/>

- Participation constraints <br/>
    1. Total (existence dependency): minimum 1 (The minimum value of cardinality will be 1, Maximum indicated with the number)<br/>
    2. Partial: mimimum zero (normal single line) <br/>
    <br/>
![Image Alt MemoryLayout](/assets/entity8.png) <br/>
<br/>

**Alternative (Min,Max) Notation** <br/>
- Specified on each participation of an entity type in a relationship type <br/>
    1. Department has exactly one manager and an employee can manage at most one department <br/>
        - (0,1) for EMPLOYEE in MANAGES (EMPLOYEE could be a manager minimum 0 for department maximum 1 for department <br/>
        - (1,1) for DEPARTMENT in MANAGES (DEPARTMENT will have minimum 1 manager and maximum 1 manager) <br/>
    2. An employee can work for exactly one department, a department can have any number of employees. <br/>
        - (1,1) for EMPLOYEE in WORKS_FOR <br/>
        - (0,n) for DEPARTMENT in WORKS_FOR <br/>
<br/>

![Image Alt MemoryLayout](/assets/entity9.png) <br/>
<br/>

**Attributes of Relationship types**<br/>
<br/>
A relationship type can have attributes: <br/>
- HoursPerWeek of WORKS_ON <br/>
    - describe the number of hours per week an EMPLOYEE works on a PROJECT <br/>
    - value of HoursPerWeek depends on a particular (employee,project) combination <br/>
<br/>

![Image Alt MemoryLayout](/assets/entity10.png) <br/>

<br/>

**Recursive Relationship Type** <br/>
<br/>

- A relationship type between the same participating entity type in **distinct roles**; aslo called **self-referencing** <br/>
- Example: the SUPERVISION relationship <br/>
- EMPLOYEE participates twice in two distinct roles: **Supervisor**, **Supervisee** <br/> 
![Image Alt MemoryLayout](/assets/entity11.png) <br/>
<br/>

**Weak Entity Types** <br/>
<br/>

An entity that is identification-dependent on another entity type. <br/>
    - Usually, a multivalued and composite attribute of another entity type (identifying entity type) <br/>
    - A DEPENDENT entity is identified by the EMPLOYEE entity <br/>
<br/>
Double line notation for weak entity type and its "weak relationship type" <br/>
