---
id: 3d5czzfdwc6b9r17uu2qfa4
title: Temporal Joins
desc: ''
updated: 1709357201851
created: 1709356528765
---

## Example

Example 1: Employee Salary History

Imagine a database with two tables: Employees and SalaryHistory.

    Employees table contains EmployeeID, Name, and other details.
    SalaryHistory table contains EmployeeID, Salary, StartDate, and EndDate (indicating the period for which a particular salary was valid).

A temporal join can be used to find out what salary each employee was earning on a specific date. For example, to find the salary of each employee on January 1, 2023, you would perform a temporal join between these tables where the join condition checks if January 1, 2023, falls between the StartDate and EndDate of the salary records.

## Description

- "

A temporal join is a join operation on two temporal relations, in which each tuple has additional attributes indicating a time interval. The temporal join predicates include conventional join predicates as well as a temporal constraint that requires the overlap of the intervals of the two joined tuples. The result of a temporal join is a temporal relation.

Besides binary temporal joins that operate on two temporal relations, there are n-ary temporal joins that operate on more than two temporal relations. Besides temporal overlapping, there are other temporal conditions such as “before” and “after” [1]. This entry will concentrate on the binary temporal joins with overlapping temporal condition since most of the previous work has focused on this kind of joins.
"

## References

- https://link.springer.com/referenceworkentry/10.1007/978-0-387-39940-9_401 