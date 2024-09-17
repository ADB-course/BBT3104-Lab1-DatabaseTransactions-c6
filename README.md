[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/r-tQZu0l)
# BBT3104-Lab1of6-DatabaseTransactions


| **Key**                                                               | Value                                                                                                                                                                              |
|---------------|---------------------------------------------------------|
| **Group Name**                                                               | c6 |
| **Semester Duration**                                                 | 19<sup>th</sup> August - 25<sup>th</sup> November 2024                                                                                                                       |

## Flowchart
![Alt text]("C:\Users\nyath\OneDrive\Desktop\Flowchart.jpg")

## Pseudocode
**Step 1.Turn off autocommit;**
**Step 2.Set isolation level to SERIALIZABLE;**
**Step 3.Start transaction;**

**Step 4.Retrieve latest order number:**
    **Step 5.Set @orderNumber = (SELECT MAX(orderNumber) + 1 FROM orders);**

**Step 6.Insert new order into orders table with order number @orderNumber;**

**Step 7.Create savepoint before inserting first product;**

**Step 8 .Insert first product into orderdetails;**
**Step 9 .Update quantity in stock for first product;**

**Step 10.Create savepoint before inserting second product;**

**Step 11.Insert second product into orderdetails;**
**Step 12.Update quantity in stock for second product;**

**Step 13.If error occurs with second product:**
   **Step 14. Rollback to savepoint before second product;**

**Step 15.Create savepoint before inserting third product;**

**Step 16.Insert third product into orderdetails;**
**Step 17.Update quantity in stock for third product;**

**Step 18.Insert payment for the order;**

**Step 19.Commit transaction;**
**Step 20.End.**

## Support for the Sales Departments' Report

**To facilitate tracking which orders have not been fully paid, the database could **be #improved by adding a payment status and a balance field to the orders table. This would track:**

**Total amount for the order: Automatically calculated based on the order details.**
**Amount paid: Tracked through the payments table.**
**Outstanding balance: Calculated as the difference between the total amount and the payments received.**


