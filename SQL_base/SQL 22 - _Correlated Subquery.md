# Correlated Subquery
## I - Introduction
A correlated subquery is a subqeury that uses the values of the outer query.
Because of this dependecy, a correlated subquery cannot be executed independently.
Moreover, a correlated subquery is executed repeatedly, once for each row evaluated by the outer query.

## II - Examples 
1. The following example finds the products whose list price is equal to the highest list price of the products within the same category:
```
SELECT
    product_name,
    list_price,
    category_id
FROM
    production.products p1
WHERE
    list_price IN (
        SELECT
            MAX(p2.list_price)
        FROM
            production.products p2
        WHERE
            p2.category_id = p1.category_id
        GROUP BY
            p2.category_id
    )
ORDER BY 
    category_id,
    product_name
```


