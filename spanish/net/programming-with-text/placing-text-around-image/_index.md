---
title: Colocar texto alrededor de la imagen
linktitle: Colocar texto alrededor de la imagen
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a colocar texto alrededor de una imagen en un documento PDF usando Aspose.PDF para .NET.
type: docs
weight: 260
url: /es/net/programming-with-text/placing-text-around-image/
---

En este tutorial, explicaremos cómo colocar texto alrededor de una imagen en un documento PDF utilizando la biblioteca Aspose.PDF para .NET. Pasaremos por el proceso paso a paso de crear una tabla, agregar una imagen y colocar el texto alrededor de la imagen usando el código fuente de C# proporcionado.

## Requisitos

Antes de comenzar, asegúrese de tener lo siguiente:

- La biblioteca Aspose.PDF para .NET instalada.
- Conocimientos básicos de programación en C#.

## Paso 1: configurar el directorio de documentos

 Primero, debe establecer la ruta al directorio donde desea guardar el archivo PDF generado. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el`dataDir` variable con la ruta a su directorio deseado.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: crear un documento y una página

 A continuación, creamos un`Document` objeto y agregarle una página usando el`Pages.Add()` método.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Paso 3: crea una tabla

 Creamos una tabla usando el`Table` class y agréguelo a la colección de párrafos de la página.

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
page.Paragraphs.Add(table1);
```

## Paso 4: establezca los anchos y márgenes de las columnas de la tabla

 Establecemos los anchos de columna de la tabla y creamos un`MarginInfo` objeto para establecer los márgenes.

```csharp
table1. ColumnWidths = "120,270";
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;
table1. DefaultCellPadding = margin;
```

## Paso 5: agregue una imagen a la tabla

 Creamos un`Image` objeto, especifique la ruta del archivo de imagen y establezca la altura y el ancho fijos de la imagen. Luego, agregamos la imagen a la colección de párrafos de la celda de la tabla.

```csharp
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
logo.File = dataDir + "aspose-logo.jpg";
logo.FixHeight = 120;
logo.FixWidth = 110;
row1.Cells.Add();
row1.Cells[0].Paragraphs.Add(logo);
```

## Paso 6: agrega texto alrededor de la imagen

Creamos variables de cadena que contienen texto con formato HTML y creamos un`HtmlFragment` objeto. Luego, agregamos el texto HTML a la celda de la tabla que contiene la imagen.

```csharp
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b>Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>" ;

Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
row1.Cells[1].Paragraphs.Add(TitleText);
```

## Paso 7: Agregar texto adicional

 Creamos otro`HtmlFragment` objeto que contenga texto con formato HTML adicional y agréguelo a una celda de tabla separada.

```csharp
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
```

## Paso 8: Guarde el documento PDF

Finalmente, guardamos el documento PDF en el archivo de salida especificado.

```csharp
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

### Ejemplo de código fuente para colocar texto alrededor de una imagen con Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instanciar objeto de documento
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Crear una página en el Pdf
Aspose.Pdf.Page page = doc.Pages.Add();
// Crear una instancia de un objeto de tabla
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
// Agregue la tabla en la colección de párrafos de la sección deseada
page.Paragraphs.Add(table1);
// Establecer con anchos de columna de la tabla
table1.ColumnWidths = "120 270";
// Cree el objeto MarginInfo y establezca sus márgenes izquierdo, inferior, derecho y superior
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Establezca el relleno de celda predeterminado en el objeto MarginInfo
table1.DefaultCellPadding = margin;
// Crear filas en la tabla y luego celdas en las filas
Aspose.Pdf.Row row1 = table1.Rows.Add();
// Crear un objeto de imagen
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
// Especifique la ruta del archivo de imagen
logo.File = dataDir + "aspose-logo.jpg";
// Especificar la imagen Altura fija
logo.FixHeight = 120;
// Especifique la imagen Ancho fijo
logo.FixWidth = 110;
row1.Cells.Add();
// Agregue la imagen a la colección de párrafos de la celda de la tabla
row1.Cells[0].Paragraphs.Add(logo);
//Cree variables de cadena con texto que contenga etiquetas html
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b> Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>";
// Cree un objeto de texto para agregarlo a la derecha de la imagen
Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
// Agregue los párrafos de texto que contienen texto HTML a la celda de la tabla
row1.Cells[1].Paragraphs.Add(TitleText);
// Establezca la alineación vertical del contenido de la fila como Superior
row1.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
// Crear filas en la tabla y luego celdas en las filas
Aspose.Pdf.Row SecondRow = table1.Rows.Add();
SecondRow.Cells.Add();
// Establezca el valor de rango de fila para la segunda fila como 2
SecondRow.Cells[0].ColSpan = 2;
// Establezca la alineación vertical de la segunda fila como Superior
SecondRow.Cells[0].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
// Agregue los párrafos de texto que contienen texto HTML a la celda de la tabla
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
// Guarde el archivo PDF
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

## Conclusión

En este tutorial, ha aprendido a colocar texto alrededor de una imagen en un documento PDF utilizando la biblioteca Aspose.PDF para .NET. Si sigue la guía paso a paso y ejecuta el código C# provisto, puede crear una tabla, agregar una imagen y colocar texto alrededor de la imagen en un documento PDF.