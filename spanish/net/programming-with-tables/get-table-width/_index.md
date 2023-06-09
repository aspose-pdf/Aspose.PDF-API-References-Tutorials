---
title: Obtener ancho de tabla
linktitle: Obtener ancho de tabla
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a obtener el ancho de una tabla en un documento PDF usando Aspose.PDF para .NET.
type: docs
weight: 90
url: /es/net/programming-with-tables/get-table-width/
---

En este tutorial, vamos a aprender cómo obtener el ancho de una tabla en un documento PDF usando Aspose.PDF para .NET. Explicaremos el código fuente en C# paso a paso. Al final de este tutorial, sabrá cómo obtener el ancho de una tabla en un documento PDF. ¡Empecemos!

## Paso 1: Configuración del entorno
Primero, asegúrese de haber configurado su entorno de desarrollo C# con Aspose.PDF para .NET. Agregue la referencia a la biblioteca e importe los espacios de nombres necesarios.

## Paso 2: Creación de un nuevo documento y página
Creamos un nuevo documento PDF y agregamos una página en este documento.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Paso 3: Inicializar una nueva tabla
Inicializamos una nueva tabla y establecemos el ajuste de la columna en "AutoFitToContent".

```csharp
Table table = new Table
{
ColumnAdjustment = ColumnAdjustment.AutoFitToContent
};
```

## Paso 4: Agregar fila y celdas en la tabla
Agregamos una fila en la tabla y agregamos celdas en esa fila.

```csharp
Row row = table.Rows.Add();
Cell cell = row.Cells.Add("Text of cell 1");
cell = row.Cells.Add("Text from cell 2");
```

## Paso 5: Obtenga el ancho de la mesa
Usamos el método "GetWidth()" para obtener el ancho de la tabla.

```csharp
Console.WriteLine(table.GetWidth());
```

### Ejemplo de código fuente para obtener el ancho de la tabla usando Aspose.PDF para .NET

```csharp
// Crear un nuevo documento
Document doc = new Document();
// Agregar página en el documento
Page page = doc.Pages.Add();
// Inicializar nueva tabla
Table table = new Table
{
	ColumnAdjustment = ColumnAdjustment.AutoFitToContent
};
// Agregar fila en la tabla
Row row = table.Rows.Add();
// Agregar celda en la tabla
Cell cell = row.Cells.Add("Cell 1 text");
cell = row.Cells.Add("Cell 2 text");
// Obtener ancho de mesa
Console.WriteLine(table.GetWidth());

System.Console.WriteLine("Extracted table width succesfully!");
```

## Conclusión
En este tutorial, aprendimos cómo obtener el ancho de una tabla en un documento PDF usando Aspose.PDF para .NET. Puede usar esta guía paso a paso para obtener anchos de tabla en sus propios proyectos de C#.