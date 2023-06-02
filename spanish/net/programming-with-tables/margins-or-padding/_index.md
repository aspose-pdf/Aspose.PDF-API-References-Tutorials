---
title: márgenes o relleno
linktitle: márgenes o relleno
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a establecer márgenes o relleno en una tabla con Aspose.PDF para .NET.
type: docs
weight: 140
url: /es/net/programming-with-tables/margins-or-padding/
---

En este tutorial, lo guiaremos paso a paso a través del proceso de uso de Aspose.PDF para .NET para establecer márgenes o relleno en una tabla. Proporcionaremos explicaciones y fragmentos de código para ayudarlo a comprender e implementar esta funcionalidad en su código fuente de C#.

## Paso 1: configurar el documento y la página
Para comenzar, debe configurar el documento y la página con el siguiente código:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crea una instancia del objeto Document llamando a su constructor vacío
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Paso 2: crear una tabla
continuación, crearemos un objeto de tabla usando la clase Aspose.Pdf.Table:

```csharp
// Crear una instancia de un objeto de tabla
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Agregue la tabla a la colección de párrafos de la sección deseada
page.Paragraphs.Add(tab1);
```

## Paso 3: Establecer anchos de columna y borde de celda predeterminado
Para establecer los anchos de columna y el borde de celda predeterminado de la tabla, use el siguiente código:

```csharp
// Establecer los anchos de columna de la tabla
tab1. ColumnWidths = "50 50 50";
// Establezca el borde de celda predeterminado usando el objeto BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## Paso 4: Configuración del borde de la tabla y el relleno de celdas
Para configurar el borde de la tabla y el relleno de la celda, cree un objeto MarginInfo y configure sus propiedades:

```csharp
// Cree un objeto MarginInfo y establezca sus márgenes izquierdo, inferior, derecho y superior
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;

// Establezca el relleno de celda predeterminado en el objeto MarginInfo
tab1. DefaultCellPadding = margin;

// Establecer el borde de la tabla usando otro objeto BorderInfo personalizado
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
```

## Paso 5: agregar filas y celdas
Ahora, agreguemos filas y celdas a la tabla. Crearemos una nueva fila y le agregaremos celdas:

```csharp
// Crear filas en la tabla y luego celdas en las filas
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add();
```

## Paso 6: agregar texto a las celdas
Para agregar texto a una celda, cree un objeto TextFragment y agréguelo a la celda deseada:

```csharp
TextFragment mytext = new TextFragment("col3 with large text string");
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
```

## Paso 7: Guardar el PDF
Para guardar el documento PDF, utilice el siguiente código:

```csharp
dataDir = dataDir + "MarginsOrPadding_out.pdf";
// Guardar el PDF
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir);
```

### Ejemplo de código fuente para márgenes o relleno usando Aspose.Words para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crea una instancia del objeto Document llamando a su constructor vacío
Document doc = new Document();
Page page = doc.Pages.Add();
// Crear una instancia de un objeto de tabla
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Agregue la tabla en la colección de párrafos de la sección deseada
page.Paragraphs.Add(tab1);
// Establecer con anchos de columna de la tabla
tab1.ColumnWidths = "50 50 50";
// Establecer borde de celda predeterminado usando el objeto BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// Establecer el borde de la tabla usando otro objeto BorderInfo personalizado
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// Cree el objeto MarginInfo y establezca sus márgenes izquierdo, inferior, derecho y superior
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Establezca el relleno de celda predeterminado en el objeto MarginInfo
tab1.DefaultCellPadding = margin;
// Crear filas en la tabla y luego celdas en las filas
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add();
TextFragment mytext = new TextFragment("col3 with large text string");
// Row1.Cells.Add("col3 con cadena de texto grande para colocar dentro de la celda");
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
// Row1.Cells[2].Paragraphs[0].FixedWidth= 80;
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
dataDir = dataDir + "MarginsOrPadding_out.pdf";
// Guardar el PDF
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir); 
```

## Conclusión
¡Felicidades! Ha aprendido con éxito cómo establecer márgenes o relleno en una tabla usando Aspose.PDF para .NET. Este conocimiento lo ayudará a mejorar sus capacidades de formato de documentos y hacer que sus tablas sean visualmente atractivas.