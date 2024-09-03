# DESCRIPTON:

Window functions, like aggregate functions, perform an aggregation on a defined set (a group) of rows, but rather than returning one value per group,
window functions can return multiple values for each group. The group of rows to perform the aggregation on is the window.

#ORDER OF EXECUTION

It is important to note that window functions are performed as the last step in SQL processing prior to the ORDER BY clause.
