# Homework 2

* Assigned: Feb 21
* Due: Mar 5 at 10:00AM
* Worth 3.75% of your grade

## Submission

### Format
1. Type your answer (markdown or latex or ...).
2. Each question occupies separate pages.

### Submit your pdf on GradeScope

## 1. Relational Algebra

**(2 points each, 6 points total)**

Consider the simplified Employee Stock Ownership Database below (primary keys are in **bold**):

* Person(**ssn**, companyid, salary, managerid)

This is an employee table. *companyid* is a foreign key which points to *Company*.
We assume one employee can only works at one company. *managerid* is a foreign key
which points to *Person* itself.

* Company(**companyid**, companyname, location)

* Holding(**ssn**, **companyid**, sharenum)

This table describes an employee(*ssn*) owns *sharenum* stocks of *companyid*.

Construct relational algebra for the following queries:

* **Q1**: Find the *ssn* of the persons who work at Google(*companyid* = 601) and hold more than 500 *sharenum*
   of stock from Facebook(*companyid* = 700).

* **Q2**: Find the *ssn* of the persons who own all the different kinds of stocks his/her manager owns.
    (Note: we only consider the type(*companyid*), we do not consider the *sharenum*).

* **Q2**: Find the *ssn* of the persons who own at least three different types of stocks.


## 2. More Relational Algebra

**(2 point each, 10 points total)**

T1

|A | B | C |
|---|---|---|
|1 | x | a |
|2 | y | c |
|2 | y | b |
|2 | z | c |


T2

B | C | D
---|---|---
1 | x | c
2 | y | c
3 | x | a


Write the result table for the relational algebra expressions:

Note: Here, we assume the attributes whose values are all numbers are the same type: integers
and all the letters are the same type: char.


1. π<sub>A,B</sub>(T1)

2. T1 × π<sub>A</sub>(T1)

3. T1 ⨝<sub>T1.B=T2.C</sub> T2

4. T1 − (T1 ∩ T2)

5. T1 ⨝<sub>T1.A&lt;T2.B</sub> (σ<sub>B&lt;=2</sub>(T2))


## 3. SQL

**(2 points each, 6 points total)**

Here are three relationship, (primary keys are in **bold**):

* Store(**storeid**, s_name, employee_number, city)

* Goods(**g_id**, g_name, price)

* Supply(**storeid**, **g_id**)

### Requirements:

First, describe the meaning of following relational algebra expressions in one or two sentences.
Second, translate the following relational algebra expressions in SQL. Make sure your SQL can be executed.


1. π<sub>storeid, s_name</sub>(σ<sub>employee_number<=100 or city = "New York"</sub>(Store))

2. π<sub>s_name(((σ<sub>g_name = "pencil"</sub>Goods) ⨝ Supply) ⨝ Store)

3. π<sub>s_name, city(Supply÷π<sub>g_id</sub>(σ<sub>storeid='0808'</sub>(Supply))⨝ Store)
