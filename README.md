# HW-4

## Question-1

```
db.widgetSales.aggregate([
  {
    $group: {
      _id: {
        date: { $dateToString: { format: "%Y-%m", date: "$date" }}
      },
      monthlySales: { $sum: { $multiply: ["$unitPrice", "$quantity"] } },
    }
  },
  { $out : "widgetSalesMonthlyAgg" }
])

```

```
db.widgetSalesMonthlyAgg.find()
```



### Question-2

## Can you show what a sample query would look like?

```
db.orders.find({productName: "Iron rod"},{status: 1, _id:0})
```


## What kind of index would you advise for the fastest query response? Create it
```
db.orders.createIndex({productName: 1, status: 1})
```

## What is the index size?

```
db.orders.stats()
```

##  The index size is 20480


## Why do you think this index will be the fastest?

## Answer: The index would be fastest because it will search the collection by productName first and then the matched productName by status instead of searching all the documents for the given variables.


### Question 3

## Can you complete the missing nodes and relationships



![HW3](https://user-images.githubusercontent.com/91687301/153677698-57c5da00-a3c6-4267-bf02-644d10b33f8c.png)
