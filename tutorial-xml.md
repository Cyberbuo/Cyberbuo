# Informe de Lenguaje de Marcas - Tema 5: Conversión de Documentos XML

**Alumno:** Sergio  
**Módulo:** Lenguajes de Marcas y Sistemas de Gestión de Información (ASIR)  
**Tarea:** Conversión y adaptación de documentos XML (RA05)

---

## RA05_d) Sintaxis específica de conversión
Para la resolución de esta tarea, se han vinculado los archivos mediante instrucciones de procesamiento y etiquetas de enlace:

1. **XML con XSLT:** Se utiliza la instrucción `<?xml-stylesheet type="text/xsl" href="DISCOS.xslt"?>` en la cabecera del XML.
2. **XSLT con CSS:** Se ha utilizado la etiqueta `<link rel="stylesheet" type="text/css" href="DISCOS.css" />` dentro de la sección `<head>` generada por el XSLT para externalizar los estilos.

## RA05_e) Especificaciones de conversión (Tabla adaptada)
Se ha diseñado una transformación para visualizar los datos en formato de tabla con las siguientes características:
* **Encabezado:** Etiquetas `<th>` para identificar Nombre, Artista, Año, Discográfica y Formato.
* **Colores alternos:** Implementados mediante CSS (`nth-child`) para mejorar la legibilidad, alternando entre Amarillo (`#ffff00`) y Gris (`#cccccc`).

## RA05_f) Herramientas y separación de responsabilidades
Se ha mantenido una separación estricta entre:
* **Datos (XML):** Información pura de los discos.
* **Lógica (XSLT):** Reglas de transformación y estructura de la tabla.
* **Estilo (CSS):** Reglas visuales y estéticas del documento final.

## RA05_g) Conversiones con formatos de salida (Filtrado)
Para cumplir con el requisito de mostrar solo discos **anteriores a 1979**, se ha modificado la regla de selección en el XSLT utilizando un predicado XPath:

```xml
<xsl:for-each select="tienda/disco[año &lt; 1979]">
