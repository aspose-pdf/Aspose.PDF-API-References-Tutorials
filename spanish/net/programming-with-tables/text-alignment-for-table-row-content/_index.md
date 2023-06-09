---
title: Alineación de texto para contenido de fila de tabla
linktitle: Alineación de texto para contenido de fila de tabla
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a alinear el contenido de las filas en una tabla PDF con Aspose.PDF para .NET.
type: docs
weight: 210
url: /es/net/programming-with-tables/text-alignment-for-table-row-content/
---

En este tutorial, lo guiaremos paso a paso para alinear el contenido de una fila en una tabla de un documento PDF utilizando Aspose.PDF para .NET. Explicaremos el código fuente de C# provisto y le mostraremos cómo implementarlo.

## Paso 1: Creación del documento PDF
Primero, crearemos el documento PDF:

```csharp
var dataDir = "YOUR DOCUMENTS DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## Paso 2: inicialización de la tabla
A continuación, inicializaremos la tabla:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## Paso 3: Configuración del color del borde de la tabla
Configuraremos el color del borde de la tabla:

```csharp
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## Paso 4: Configurar el borde de la celda de la tabla
Vamos a configurar el borde de la celda de la tabla:

```csharp
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## Paso 5: Bucle para agregar 10 filas a la tabla
Ahora usaremos un ciclo para agregar 10 filas a la tabla:

```csharp
for (int row_count = 0; row_count < 10; row_count++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row.VerticalAlignment = VerticalAlignment.Center;

     row.Cells.Add("Column("+row_count+",1)"+DateTime.Now.Ticks);
     row.Cells.Add("Column("+row_count+",2)");
     row.Cells.Add("Column("+row_count+",3)");
}
```

## Paso 6: Configuración de la alineación de la línea vertical
Vamos a configurar la alineación vertical de las filas de la tabla:

```csharp
row.VerticalAlignment = VerticalAlignment.Center;
```

## Paso 7: agregar contenido a las celdas de fila
Vamos a agregar contenido a las celdas de fila:

```csharp
row.Cells.Add("Column("+row_count+",1)"+DateTime.Now.Ticks);
row.Cells.Add("Column("+row_count+",2)");
row.Cells.Add("Column("+row_count+",3)");
```

## Paso 8: agregar la tabla a la página del documento
Ahora agreguemos la tabla a la página del documento:

```csharp
Page tocPage = doc.Pages.Add();
tocPage.Paragraphs.Add(table);
```

## Paso 9: Guardar el documento PDF
Finalmente, guardaremos el documento PDF:

```csharp
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

### Código fuente de ejemplo para Alineación de texto para contenido de fila de tabla usando Aspose.PDF para .NET

```csharp
var dataDir = "YOUR DOCUMENT DIRECTORY";

// Crear documento PDF
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Inicializa una nueva instancia de la tabla.
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Establezca el color del borde de la tabla como LightGray
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// establecer el borde para las celdas de la tabla
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// crear un bucle para agregar 10 filas
for (int row_count = 0; row_count < 10; row_count++)
{
	// agregar fila a la tabla
	Aspose.Pdf.Row row = table.Rows.Add();
	row.VerticalAlignment = VerticalAlignment.Center;

	row.Cells.Add("Column (" + row_count + ", 1)" + DateTime.Now.Ticks);
	row.Cells.Add("Column (" + row_count + ", 2)");
	row.Cells.Add("Column (" + row_count + ", 3)");
}
Page tocPage = doc.Pages.Add();
// Agregar objeto de tabla a la primera página del documento de entrada
tocPage.Paragraphs.Add(table);
// Guardar documento actualizado que contiene objeto de tabla
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

## Conclusión
¡Felicidades! Ahora ha aprendido cómo alinear el contenido de una fila en una tabla en un documento PDF utilizando Aspose.PDF para .NET. Esta guía paso a paso le mostró cómo crear un documento, inicializar una tabla, configurar el borde y la alineación, agregar contenido y guardar el documento PDF. Ahora puedes aplicar este conocimiento a tus propios proyectos.