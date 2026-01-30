---
layout: post
title: Mejorando la Extracción Limpia de Texto al Hacer Web Scraping con Python
categories: programming
author:
  - Carlos A. Planchón
lang: es
---
Los proyectos de web scraping enfrentan consistentemente problemas similares de extracción de texto. La biblioteca `parsel` de Python maneja efectivamente selectores XPath y CSS, pero persisten problemas recurrentes: errores de codificación de texto (por ejemplo, `cafÃ©` en lugar de `café`), espacios en blanco excesivos y estructuras HTML malformadas que requieren limpieza manual.

Desarrollé `parsel_text` para abordar estos problemas sistemáticamente. La biblioteca extiende `parsel` integrando `BeautifulSoup` para análisis flexible de HTML y `ftfy` para corrección automática de codificación. En lugar de reemplazar `parsel`, que sigue siendo superior para tareas de análisis estructurado, `parsel_text` proporciona funcionalidad especializada para extraer texto limpio y normalizado.

### Mejoras principales

**Corrección de codificación:** `ftfy` normaliza el texto automáticamente, resolviendo errores comunes de codificación como `cafÃ©` → `café`.

**Normalización de espacios en blanco:** Los espacios redundantes y saltos de línea se eliminan sin operaciones manuales de `.strip()` o expresiones regulares.

**Análisis HTML:** `BeautifulSoup` maneja estructuras HTML profundamente anidadas o malformadas de manera más confiable que los analizadores XML estrictos.


* * *

### Uso

```
from parsel import Selector
from parsel_text import get_xpath_text

html_content = """
<div id="content">
    <p>Hello, world!</p>
    <p>Welcome to the parsel_text library.</p>
</div>
"""

selector = Selector(text=html_content)
text = get_xpath_text(selector, xpath="//p/text()")
print(text)
```

**Salida:**

```
Hello, world!
Welcome to the parsel_text library.
```

La biblioteca maneja la extracción y normalización de texto en una sola operación.

* * *

### Cuándo usar `parsel_text`

Usa `parsel_text` cuando trabajes con sitios que tienen HTML inconsistente o problemas de codificación. Es particularmente útil para proyectos que requieren limpieza automática de texto a través de múltiples fuentes.

Para páginas bien estructuradas con formato consistente, el `parsel` estándar sigue siendo suficiente. `parsel_text` aborda casos donde la calidad del HTML es pobre o la codificación no es confiable.

* * *

### Rendimiento

`parsel_text` es más lento que `parsel` solo debido al procesamiento adicional de `BeautifulSoup` y `ftfy`. Este compromiso favorece la calidad del texto sobre la velocidad. Para operaciones de scraping a gran escala donde el rendimiento es crítico, usar `parsel` directamente puede ser más apropiado.

* * *

### Características adicionales

La biblioteca incluye varias funciones de utilidad: `get_results_row_text` devuelve una lista de texto limpio de un objeto selector, `get_bs4_soup_text` extrae texto directamente de objetos BeautifulSoup, y el parámetro `fix_mojibake` permite control opcional sobre el comportamiento de corrección de texto.

* * *

**Referencias:**

[Documentación Oficial de Parsel](https://parsel.readthedocs.io)

[Repositorio GitHub](https://github.com/carlosplanchon/parsel_text)
