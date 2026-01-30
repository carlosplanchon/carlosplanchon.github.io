---
layout: post
title: "Outfancy: Una Biblioteca de Visualización de Datos en Terminal Creada como Proyecto de Aprendizaje"
categories: programming
author:
  - Carlos A. Planchón
meta: "#programming #visualization #terminal"
lang: es
---
En 2014, desarrollé Outfancy, una biblioteca de visualización de datos basada en terminal. A los 16 años, necesitaba una forma simple de imprimir tablas y gráficos en el terminal sin dependencias complejas. Pocas bibliotecas abordaban esta necesidad específica en ese momento.

La biblioteca maneja varias tareas de salida de terminal: mostrar datos estructurados como tablas, imprimir actualizaciones de una sola línea para monitoreo en tiempo real y renderizar gráficos básicos con dependencias mínimas. La implementación sirvió como práctica para programación orientada a objetos y técnicas de renderizado de terminal.

* * *

### Implementación

Renderizado de tablas en Outfancy:

```
import outfancy.table
import time

# Ejemplo 1: Imprimiendo una tabla más grande con más columnas y datos
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

Los anchos de columna se adaptan automáticamente según el contenido. Un sistema heurístico infiere tipos de datos para generar etiquetas de columna, aunque también se admite especificación manual:

```
print(table.render(dataset, label_list=["Id", "Name", "Surname", "City", "Salary"]))
```

Monitoreo en tiempo real con `Oneline`:

```
# Ejemplo 2: Monitoreo de datos en tiempo real con la función Oneline
oneline_table = outfancy.table.Oneline()

print("\nReal-Time Data Monitoring Example:")
for i in range(10):
    data = [dataset[i][0], dataset[i][1].ljust(10), f"Processing {i*10}%"]
    print(oneline_table.render(data))
    time.sleep(1)
```

![](/media/outfancy_realtime_table.png)

La biblioteca incluye funcionalidad experimental de gráficos de líneas usando caracteres ASCII para gráficos basados en terminal. Para uso en producción, [plotille](https://github.com/tammoippen/plotille) proporciona una implementación más robusta.

* * *

### Alternativas actuales

Las bibliotecas modernas como `rich` y `tabulate` ofrecen capacidades de visualización de terminal más maduras. Outfancy sigue siendo funcional para casos de uso básicos que priorizan la simplicidad sobre las características.

* * *

**Explora Outfancy en GitHub:**

[https://github.com/carlosplanchon/outfancy](https://github.com/carlosplanchon/outfancy)
