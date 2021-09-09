---
layout: post
title:  "Database Terminology and Approaches"
date:   2021-09-08 19:00:36 +0530
categories: Database
---

### **What is Database Terminologies?** <br/>

<br/>
**Database:** Collection of related data <br/>
**Data:** Known facts that can be recorded & have implicit meaning <br/>
	- Example: Names, Telephone Number, Address of People<br/>
	<br/>
**Database has following Implicit Properties**<br/> 
 - A database represents some aspects of the real world (**Mini-World** or **Universe of Discourse**)<br/>
 - logically coherent(일관성 있는) collection of data with some inherent meaning<br/>
 <br/>
### **Database Management System** <br/>
	- Computerized system that enable users to create and maintain database.<br/>
	- General Software System that factilitates the process of **defining**, **constructing**, **manipulating** and **sharing database** among the various users <br/>
	- The database definition or descriptiive information stored by DBMS inform of a database catalog or dictionary, is called **Meta-Data** (데이터의 데이터를 의미한다.) <br/>

**Defining:** Specifying **data type**, **structure** and **contraints of Data** to be stored.<br/>
**Constructing:** The database process of storing the data on some storage medium that is controlled by DBMS<br/>
**Manipulating:** Database includes functions such as querying(묻다) the database to retrieve(검색), updating database to reflect changes in Mini world. and generating reports from data.<br/>
**Sharing:** A database allows multiple users and programs to access.<br/>
<br/>

![Image Alt MemoryLayout](/assets/database.png) <br/>

### Let's Understand with Example: University Database for maintaining information concerning student, courses and grades <br/>

The Database organized with **Five Files** stores data on each student: <br/>
	- The Course File: Stores data on each courses <br/>
	- The Section File: Stores data on each section of a course <br/>
	- The Grade_Report File: Stores the grades that student recieve <br/>
	- The Student File: stores data on each student <br/>
	- The Prerequisite File: Stores prerequisite for each courses <br/>
<br/>
To define this database, we must specify the structure of the records each file by specifying Different type of **Data - Elements** <br/>
**Student:** Student_Number, class, major <br/>
**Course:** Course_Name, Course_Number, Credit_Hour <br/>
Also specify the **Data type**: Student_Number: integer ... etc <br/>
<br/>

### Database Manipulation Involves **Querying & Updating**<br/>
**Query:** <br/>
	- Retrieve the transcript - a list of all courses and grades of "Smith"<br/>
	- List of all names of student who took section of the "Database" in fall 2008 <br/>
	- List of all Prerequisite for "Database" Course <br/>

**Updates** <br/>
	- Change the class of "Smith" to Sophomore <br/>
	- Create a New section <br/>
	- Enter new Grade <br/>

**Characteristic of Database Approach**<br/>
	- Self-describing nature of a database system: **DBMS catalog** as structure of each file the type and storage format of each data item and various constraint on the data (**META DATA**)<br/>
	<br/>
	- Insulation between programs and data and data abstraction: **Program-Data Independence** DBMS access program do not require such changes in most cases. The structure of data file is stored in DBMS Catalog sperately from the access program <br/>
	<br/>
	- Support multiple views of the data: Each user may see different view of database <br/>
	<br/>
	- Sharing of data and multiuser transaction processing: A multiple user DBMS must allow multiple user to access the database at the same time. Therefore, DBMS must include **concurrency control**. <br/>
	<br/>
<br/>
**Advantages of using DBMS Apporach**<br/>
1. Controlling Redundancy <br/>
2. Restricted unauthroized access <br/>
3. Providing storage structures and search technique for efficient query processing<br/>
4. Providing persistent storage for program object <br/>
5. Providing backup and recovery <br/>
6. Providing multiple User Interface<br/>
7. Representing Complex Relationships among Data <br/>
8. Enforcing Integrity Constraints <br/>

**When not to use DBMS?**
	- High Initial investment in hardware,software, and training <br/>
	- The generality that a DBMS provides for defining and processing data <br/>
	- Overhead for providing security, concurrency control, recovery and integrity functions <br/>
**Therefore, It may be more desirable to develop customized database application under following circumstances:** <br/>
	- Simple, well-defined database application that are not expected to change at all <br/>
	- Stringent, real-time requirements for some application programs that may not be met because of DBMS overhead <br/>
	- Embedded Systems with limited storage capacity, where a general - purpose DBMS would not fit <br/>
	- No multiple user access to data <br/>





	
