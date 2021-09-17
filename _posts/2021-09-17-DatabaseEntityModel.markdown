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
