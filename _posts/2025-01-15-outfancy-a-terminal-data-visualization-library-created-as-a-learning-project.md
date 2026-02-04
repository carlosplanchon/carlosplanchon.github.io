---
layout: post
title: "Outfancy: A Terminal Data Visualization Library Created as a Learning Project"
categories: programming
author:
  - Carlos A. Planchón
meta: "#programming #visualization #terminal"
lang: en
---
In 2014, I developed Outfancy, a terminal-based data visualization library. At 16, I needed a simple way to print tables and charts in the terminal without complex dependencies. Few libraries addressed this specific need at the time.

The library handles several terminal output tasks: displaying structured data as tables, printing single-line updates for real-time monitoring, and rendering basic charts with minimal dependencies. The implementation served as practice for object-oriented programming and terminal rendering techniques.

* * *

### Implementation

Table rendering in Outfancy:

```
import outfancy.table
import time

# Example 1: Printing a larger table with more columns and data
dataset = [
    (1, 'Alice', 'Engineer', 'New York', 50000),
    (2, 'Bob', 'Designer', 'Los Angeles', 55000),
    (3, 'Charlie', 'Manager', 'Chicago', 70000),
    (4, 'Diana', 'Analyst', 'San Francisco', 60000),
    (5, 'Eve', 'Developer', 'Austin', 65000),
    (6, 'Frank', 'Data Scientist', 'Seattle', 80000),
    (7, 'Grace', 'Product Manager', 'Miami', 75000),
    (8, 'Hank', 'DevOps Engineer', 'Boston', 72000),
    (9, 'Ivy', 'HR Specialist', 'Denver', 48000),
    (10, 'Jack', 'Software Architect', 'Houston', 90000)
]

table = outfancy.table.Table()
print("Table Example:")
print(table.render(dataset))
```

![](/media/outfancy_table.png)

Column widths adapt automatically based on content. A heuristic system infers data types to generate column labels, though manual specification is also supported:

```
print(table.render(dataset, label_list=["Id", "Name", "Surname", "City", "Salary"]))
```

Real-time monitoring with `Oneline`:

```
# Example 2: Real-time data monitoring with Oneline feature
oneline_table = outfancy.table.Oneline()

print("\nReal-Time Data Monitoring Example:")
for i in range(10):
    data = [dataset[i][0], dataset[i][1].ljust(10), f"Processing {i*10}%"]
    print(oneline_table.render(data))
    time.sleep(1)
```

![](/media/outfancy_realtime_table.png)

The library includes experimental line chart functionality using ASCII characters for terminal-based plotting. For production use, [plotille](https://github.com/tammoippen/plotille) provides a more robust implementation.

* * *

### Current alternatives

Modern libraries like `rich` and `tabulate` offer more mature terminal visualization capabilities. Outfancy remains functional for basic use cases that prioritize simplicity over features.

* * *

**Explore Outfancy on GitHub:**

[https://github.com/carlosplanchon/outfancy](https://github.com/carlosplanchon/outfancy)