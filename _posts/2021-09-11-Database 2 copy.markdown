---
layout: post
title:  "Database Introduction Part 2"
date:   2021-09-11 19:00:36 +0530
categories: Database
---

### **Data Model** <br/>


A set of concepts:<br/>
	- To describe the **structure** of a database<br/>
	- The **operations for manipulating these structures<br/>
	- **constraints** that the database should obey<br/>
The **relational model** is the most widely used data model<br/>
<br/>
**Database Schema:** The description of a database + descriptions of database structure, data types, and the constraints on the database. <br/>
(데이터베이스 스키마는 데이터 베이스 전체 또는 일부의 논리적 구조를 표현한것으로 데이터 베이스 내에서 데이터가 어떤 구조로 저장되는지를 나타낸다) <br/>
<br/>
**Three-Schema Archietecture** <br/>
<br/>
	1. **Internal/physical schema**: describes physical storage structures and access paths. (How will it be arrange)<br/>
	2. **Conceptual schema**: describe the structure and constraints for the whole database. (Logical/ We will be using **relational data model**) <br/>
	3. **External schemas**: describe the various user views. <br/>
<br/>
**Example of a Database Schema**<br/>
<br/>
- **Conceptual Schema**: Logical structure that we are going to have in the database / Defining classes<br/>
	1. Students (sid: string, name: string, login: string, age:int, gpa: real) <br/>
	2. Courses (cid: string, cname: string, credits: int) <br/>
	3. Enrolled (sid:string, cid: string, grade: string) <br/>
- **Physical schema**: actual storage of data (How many students, courses, enrollment we have?) <br/>
	1. Relations stored as unordered files <br/>
	2. Index on first column of Students. <br/>
- **External Schema** (View): How it will be structured?<br/>
	1. Course_info(cid:string, enrollment:int) <br/>
<br/>

**Diagram for the three schema architecture** <br/>
![Image Alt MemoryLayout](/assets/threeschema.png) <br/>
<br/>

**Data Independence**<br/>
- **Logical Data Independence**<br/>
The capacity to change the conceptual schema without having to change the external schemas and their associated application programs <br/>
<br/>
- **Physical Data Independence:** <br/>
The capacity to change the internal schema without having to change the conceptual schema. <br/>
<br/>
**Schemas (Structure) VS. Instance**<br/>
Database State/Instance (Snapshot of Database: What is data actual stored in different component of the database that any particualr moment): <br/>
	- The actual data stored in a dabase at a **particular moment in time**. <br/>
	- The term **Instance** is also applied to individual database components. <br/>
	- **Schemas (defined variables)**, **Instance (the value of stored in those variable in that time)** <br/>
<br/>

**Diagram for Schema** <br/>
![Image Alt MemoryLayout](/assets/schema.png) <br/>

Schema Diagram displays only some aspects of a schema, such as the name of record types and data items, and some types of constraints. <br/>
<br/>
**DBMS Language**
- **Data Definition Language (DDL)**: Used to specify the **conceptual schema** of a database <br/>
- **Data Manipulation Language (DML)**: Used to specify database retrievals and updates <br/>
- SQL is a combination of both DDL and DML for most of DBMS based on relational model <br/>