# Homework 2 Solution

## 1.1 
a
π<sub>ssn</sub>(σ<sub>companyid=601</sub>Person) ∩ 
π<sub>ssn</sub>(σ<sub>companyid=700 ∧ sharenum > 500 </sub> (Holding)) 

Or there is another solution:

π<sub>ssn</sub>(σ<sub>companyid=601</sub>Person ⨝ σ<sub>companyid=700 ∧ sharenum > 500 </sub> (Holding)) 

## 1.2 

p(ManagerCompany(ssn, companyid), π <sub> Person.ssn, Holding.companyid</sub>(Person ⨝<sub>Person.managerid = Holding.ssn</sub> Holding))



p(NotCover, π <sub>ssn</sub>(ManageCompany- π <sub> ssn, companyid</sub> ( Holding)))



Cover ←  π<sub>ssn</sub>(Person)- NotCover

## 1.3

p(tmp1, Holding)

p(tmp2, Holding)

π <sub>ssn</sub>(σ<sub>Holding.companyid ≠ tmp1.companyid ∧Holding.companyid  ≠ tmp2.companyid ∧ tmp2.companyid≠ tmp1.companyid</sub>(Holding ⨝<sub>ssn</sub> tmp1 ⨝<sub>ssn</sub> tmp2))

## 2.1     

|A | B |
|---|---|
|1 | x |
|2 | y |
|2 | y |
|2 | z |

## 2.2 

|A | B | C |  A|
|---|---|---| ---|
|1 | x | a | 1 |
|2 | y | c | 1 |
|2 | y | b | 1 |
|2 | z | c | 1 |
|1 | x | a | 2 |
|2 | y | c | 2 |
|2 | y | b | 2 |
|2 | z | c | 2 |

## 2.3 

|A | B | C | B | D |
|---|---|---|---|---|
|1 | x | a | 1 | c |
|1 | x | a | 3 | a |
|2 | y | c | 2 | c |
|2 | y | b | 2 | c |

## 2.4


|A | B | C |
|---|---|---|
|1 | x | a |
|2 | y | b |
|2 | z | c |

## 2.5

|A | B | C | B | C | D |
|---|---|---|---|---|---|
|1 | x | a | 2 | y | c |

## 3.1 

description: Find the id and name of the stores which have <= 100 employees or located in New York.

```sql
select storeid, s_name from Store 
where employee_numer <= 100 or city = "New York"
```

## 3.2 

description: Find the name of the stores which supply pencils.

```sql
select dinstinct s_name 
from Store, Goods, Supply
where Goods.g_id = "pencil" 
    and Goods.g_id = Supply.g_id
    and Store.storeid = Supply.storeid
```



## 3.3

description: Find the name and city of the stores which supply all the goods that store "0808" has.

```sql
select distinct s_name, city
from Store
where not exists(
    select * from Supply as S1
    where S1.storeid = "0808" 
    and not exists(
        select * from Supply as S2 
        where S2.storeid = Store.storeid and 
        S2.g_id = S1.g_id
    )
)
```

