---
title: Tabla de renderizado
linktitle: Tabla de renderizado
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a mostrar una tabla en un documento PDF usando Aspose.PDF para .NET.

type: docs
weight: 170
url: /es/net/programming-with-tables/render-table/
---

En este tutorial, lo guiaremos paso a paso para mostrar una tabla en un documento PDF utilizando Aspose.PDF para .NET. Explicaremos el código fuente de C# provisto y le mostraremos cómo implementarlo.

## Paso 1: Crear el documento
Primero, crearemos un nuevo documento PDF:

```csharp
// Ruta al directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Crear un nuevo documento
Document doc = new Document();
```

## Paso 2: configurar los márgenes y la orientación de la página
A continuación, configuraremos los márgenes de la página y estableceremos la orientación en modo horizontal:

```csharp
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo. Left = 37;
marginInfo. Right = 37;
marginInfo. Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;
```

## Paso 3: Crear la tabla y las columnas
Ahora vamos a crear una tabla y establecer los anchos de columna:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "50 100";
```

## Paso 4: agregue filas y celdas a la tabla
A continuación, agregaremos filas y celdas a la tabla mediante un bucle:

```csharp
for (int i = 1; i <= 120; i++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row. FixedRowHeight = 15;
     Aspose.Pdf.Cell cell1 = row.Cells.Add();
     cell1.Paragraphs.Add(new TextFragment("Content 1"));
     Aspose.Pdf.Cell cell2 = row.Cells.Add();
     cell2.Paragraphs.Add(new TextFragment("HHHHH"));
}
```

## Paso 5: agregar la tabla a la página
Ahora agreguemos la tabla a la página del documento:

```csharp
Page curPage = doc.Pages.Add();
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs. Add(table);
```

## Paso 6: mostrar la tabla en una página nueva
A continuación, crearemos una nueva tabla y estableceremos la propiedad "IsInNewPage" en "true" para mostrar la tabla en una nueva página:

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table. ColumnWidths = "100 100";
for (int i = 1; i <= 10; i++)
{
     Aspose.Pdf.Row row = table1.Rows.Add();
     Aspose.Pdf.Cell cell1 = row.Cells.Add();
     cell1.Paragraphs.Add(new TextFragment("LAAAAAAA"));
     Aspose.Pdf.Cell cell2 = row.Cells.Add();
     cell2.Paragraphs.Add(new TextFragment("LAAGGGGGG"));
}
table1.IsInNewPage = true;
paragraphs. Add(table1);
```

## Paso 7: Guardar PDF
Finalmente, guardamos el documento PDF:

```csharp
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable displayed successfully on a page.\nFile saved at location: " + dataDir);
```

### Ejemplo de código fuente para Render Table usando Aspose.Words para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo.Left = 37;
marginInfo.Right = 37;
marginInfo.Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table.ColumnWidths = "50 100";
// Página añadida.
Page curPage = doc.Pages.Add();
for (int i = 1; i <= 120; i++)
{
	Aspose.Pdf.Row row = table.Rows.Add();
	row.FixedRowHeight = 15;
	Aspose.Pdf.Cell cell1 = row.Cells.Add();
	cell1.Paragraphs.Add(new TextFragment("Content 1"));
	Aspose.Pdf.Cell cell2 = row.Cells.Add();
	cell2.Paragraphs.Add(new TextFragment("HHHHH"));
}
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs.Add(table);
/********************************************/
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table.ColumnWidths = "100 100";
for (int i = 1; i <= 10; i++)
{
	Aspose.Pdf.Row row = table1.Rows.Add();
	Aspose.Pdf.Cell cell1 = row.Cells.Add();
	cell1.Paragraphs.Add(new TextFragment("LAAAAAAA"));
	Aspose.Pdf.Cell cell2 = row.Cells.Add();
	cell2.Paragraphs.Add(new TextFragment("LAAGGGGGG"));
}
table1.IsInNewPage = true;
// Quiero mantener la tabla 1 en la página siguiente, por favor...
paragraphs.Add(table1);
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable render successfully on a page.\nFile saved at " + dataDir);
```

## Conclusión
¡Felicidades! Ahora ha aprendido a mostrar una tabla en un documento PDF utilizando Aspose.PDF para .NET. Esta guía paso a paso le mostró cómo crear un documento, configurar los márgenes y la orientación de la página, agregar una tabla y mostrar una tabla en una página nueva. Ahora puedes aplicar este conocimiento a tus propios proyectos.