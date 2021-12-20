# SQL Notes

**SELECT** - list function
**FROM** - indicate the tables or views
**WHERE** - Conditions of what rows included
**GROUP BY** - indicate categorization of results
**HAVING** - indicate conditions under which a category will be included.
**ORDER BY**  - sorts the result
# 
Processing order: E.G - ==SELECT c1, c2 FROM t1 WHERE [condition on rows] GROUP BY c1, c2 HAVING [conditions on groups] ORDER BY c1;==
# 
**DISTINCT** - eliminate duplicate rows
E.G - **SELECT DISTINCT**(c1) **FROM** t1;
# 
**AS** - alternative column header name
E.G - **SELECT** X **AS** Y,
**FROM** t1
**WHERE**[condition]
X - original name, Y - alternative name
# 
Operator for WHERE:
**BETWEEN** - **WHERE** X **BETWEEN** n **AND** m
**AND** - T if all conditions T
**OR** - T if either conditions T
**ANY** - T if any of subquery values meet the condition
**EXISTS** - T if the subquery returns one or more records
**NOT** - displays a record if the conditions not T
**IN** - T if the operand is equal to one of a list of expressions
# 
**LIKE** - compare strings
E.G - **SELECT** c1 **FROM** t1 **WHERE** c1 **LIKE** ‘%abc’;
List items that end with abc
‘abc%’ start with abc
‘a%c’ start with a, end with c
‘\_a%’ contain a on second place
‘a\_\_%’ at least 3 digits
# 
**IS NOT NULL**
E.G - **SELECT** * **FROM** t1 **WHERE** c1 **IS NOT NULL**
**IN** - to indicate certain value
E.G - **SELECT** c1, c2, c3 **FROM** t1 **WHERE** c1 **IN** (‘x’, ‘y’,’z’);
(from table 1, select c1, c2, c3 when c1 is x, y or z)
==< > not equal to==
GROUP BY:
**AVG** -
**SUM** -
**MIN** -
**MAX** -
**COUNT** -
E.G - **SELECT** c1, **COUNT**(c1) **FROM** t1 **GROUP BY** c1;
E.G - **SELECT** c1, **COUNT**(c1) FROM t1 GROUP **BY** c1 **HAVING COUNT**(c1) > 1;
(having after group by work on group condition)
# 
**INNER JOIN**  - match primary and foreign key
E.G - **SELECT** *
**FROM** t1
**INNER JOIN** t2 **ON** t1.c1 = t2.c2
**INNER JOIN** t3 **ON** t2.c2 = t3.c3
**INNER JOIN** t4 **ON** t3.c3 = t4.c4
**WHERE** [condition]
(c1= pk in t1, c2= pk in t2)
# 
**NATURAL JOIN**  - duplicate columns is eliminated in the result table
E.G - **SELECT** c1,c2 **FROM** t1 **NATURAL JOIN** t2
# 
**CROSS JOIN** - cross product
# 
**LEFT OUTER JOIN** - produces a complete set of records from table A
E.G - **SELECT** * **FROM** t1 **LEFT OUTER JOIN** t2 **ON** t1.c1 = t2.c2
# 
A set of records ==only in table A== but not in table B
E.G - **SELECT** * **FROM** t1 **LEFT OUTER JOIN** t2 **ON** t1.c1 = t2.c2 **WHERE** t2.pk **IS NULL**
# 
**FULL OUTER JOIN** - includes all columns from each table
E.G - **SELECT** * **FROM** t1 **FULL OUTER JOIN** t2 **ON** t1.c1 = t2.c2
# 
**SELF JOIN** - require aliases
E.G - **SELECT** E.EmployeeID, E.EmployeeName, M.EmployeeName AS Manager
**FROM** Employee E, Employee M
**WHERE** E.EmployeeSupervisor=M.EmployeeID






