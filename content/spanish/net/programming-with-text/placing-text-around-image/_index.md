---
title: Colocar texto alrededor de una imagen en un archivo PDF
linktitle: Colocar texto alrededor de una imagen en un archivo PDF
second_title: Aspose.PDF para referencia de API .NET
description: Aprenda a colocar texto alrededor de una imagen en un archivo PDF usando Aspose.PDF para .NET.
type: docs
weight: 260
url: /es/net/programming-with-text/placing-text-around-image/
---
En este tutorial, explicaremos cómo colocar texto alrededor de una imagen en un archivo PDF usando la biblioteca Aspose.PDF para .NET. Revisaremos el proceso paso a paso de crear una tabla, agregar una imagen y colocar texto alrededor de la imagen utilizando el código fuente C# proporcionado.

## Requisitos

Antes de comenzar, asegúrese de tener lo siguiente:

- La biblioteca Aspose.PDF para .NET instalada.
- Un conocimiento básico de la programación en C#.

## Paso 1: configurar el directorio de documentos

 Primero, debe establecer la ruta al directorio donde desea guardar el archivo PDF generado. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el`dataDir`variable con la ruta al directorio deseado.

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

 Creamos una tabla usando el`Table` class y agréguela a la colección de párrafos de la página.

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
page.Paragraphs.Add(table1);
```

## Paso 4: Establecer anchos y márgenes de columnas de tabla

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

## Paso 6: agregue texto alrededor de la imagen

 Creamos variables de cadena que contienen texto con formato HTML y creamos un`HtmlFragment`objeto. Luego, agregamos el texto HTML a la celda de la tabla que contiene la imagen.

```csharp
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b>Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>" ;

Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
row1.Cells[1].Paragraphs.Add(TitleText);
```

## Paso 7: agregue texto adicional

 creamos otro`HtmlFragment` objeto que contiene texto adicional con formato HTML y agréguelo a una celda de tabla separada.

```csharp
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
```

## Paso 8: guarde el documento PDF

Finalmente, guardamos el documento PDF en el archivo de salida especificado.

```csharp
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

### Código fuente de muestra para colocar texto alrededor de una imagen usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crear una instancia de un objeto de documento
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Crear una página en el Pdf
Aspose.Pdf.Page page = doc.Pages.Add();
// Crear una instancia de un objeto de tabla
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
// Agregue la tabla en la colección de párrafos de la sección deseada.
page.Paragraphs.Add(table1);
// Establecer con anchos de columna de la tabla.
table1.ColumnWidths = "120 270";
// Cree un objeto MarginInfo y establezca sus márgenes izquierdo, inferior, derecho y superior
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Establezca el relleno de celda predeterminado en el objeto MarginInfo
table1.DefaultCellPadding = margin;
// Crea filas en la tabla y luego celdas en las filas.
Aspose.Pdf.Row row1 = table1.Rows.Add();
// Crear un objeto de imagen
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
// Especificar la ruta del archivo de imagen
logo.File = dataDir + "aspose-logo.jpg";
// Especificar la imagen Altura fija
logo.FixHeight = 120;
// Especificar la imagen Ancho fijo
logo.FixWidth = 110;
row1.Cells.Add();
// Agregue la imagen a la colección de párrafos de la celda de la tabla
row1.Cells[0].Paragraphs.Add(logo);
// Cree variables de cadena con texto que contenga etiquetas html
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b> Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>";
//Cree un objeto de texto para agregarlo a la derecha de la imagen.
Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
// Agregue los párrafos de texto que contienen texto HTML a la celda de la tabla
row1.Cells[1].Paragraphs.Add(TitleText);
// Establecer la alineación vertical del contenido de la fila como Superior
row1.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
// Crea filas en la tabla y luego celdas en las filas.
Aspose.Pdf.Row SecondRow = table1.Rows.Add();
SecondRow.Cells.Add();
// Establezca el valor de intervalo de fila para la segunda fila como 2
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

En este tutorial, aprendió cómo colocar texto alrededor de una imagen en un documento PDF usando la biblioteca Aspose.PDF para .NET. Si sigue la guía paso a paso y ejecuta el código C# proporcionado, puede crear una tabla, agregar una imagen y colocar texto alrededor de la imagen en un documento PDF.

### Preguntas frecuentes

#### P: ¿Cuál es el propósito del tutorial "Colocar texto alrededor de una imagen en un archivo PDF"?

R: El tutorial "Colocar texto alrededor de una imagen en un archivo PDF" muestra cómo utilizar la biblioteca Aspose.PDF para .NET para colocar texto alrededor de una imagen en un documento PDF. El tutorial proporciona una guía paso a paso y código fuente C# para ayudarle a crear una tabla, agregar una imagen y colocar texto alrededor de la imagen.

#### P: ¿Por qué querría colocar texto alrededor de una imagen en un documento PDF?

R: Colocar texto alrededor de una imagen mejora la presentación visual de sus documentos PDF, haciéndolos más atractivos e informativos. Esta técnica se utiliza a menudo en documentos, folletos, informes y otros materiales en los que se desea combinar imágenes y texto de una manera estéticamente agradable.

#### P: ¿Cómo configuro el directorio de documentos?

R: Para configurar el directorio de documentos:

1.  Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el`dataDir` variable con la ruta al directorio donde desea guardar el archivo PDF generado.

#### P: ¿Cómo creo una tabla y le agrego una imagen?

 R: El tutorial lo guía a través del proceso de creación de una tabla usando el`Table` clase y agregar una imagen a la tabla usando el`Image` clase. Especificará la ruta, el alto y el ancho del archivo de imagen antes de agregarlo a una celda de la tabla.

#### P: ¿Cómo coloco el texto alrededor de la imagen?

 R: Para colocar texto alrededor de la imagen, creará texto con formato HTML usando el`HtmlFragment` clase. Este texto contendrá tanto un título como un cuerpo de texto. Luego agregará este texto HTML a una celda de la tabla adyacente a la celda de la imagen.

#### P: ¿Puedo personalizar la apariencia del texto y la imagen?

R: Sí, puedes personalizar la apariencia del texto y la imagen usando etiquetas y propiedades HTML. Por ejemplo, puede establecer tamaños de fuente, colores, estilos y alineación del texto. Además, puede ajustar el tamaño y las dimensiones de la imagen.

#### P: ¿Cómo guardo el documento PDF?

 R: Después de agregar la imagen y el texto a la tabla, puede guardar el documento PDF usando el`Save` método de la`Document` clase. Proporcione la ruta del archivo de salida deseada como argumento para el`Save` método.

#### P: ¿Cuál es el resultado esperado de este tutorial?

R: Si sigue el tutorial y ejecuta el código C# proporcionado, generará un documento PDF que demuestra cómo colocar texto alrededor de una imagen. El documento de salida contendrá una tabla con una imagen y texto a su alrededor.

#### P: ¿Puedo utilizar formatos de imagen diferentes además de JPG?

 R: Sí, puede utilizar diferentes formatos de imagen admitidos por la biblioteca Aspose.PDF, como PNG, BMP, GIF y más. Al crear el`Image` objeto, especifique la ruta del archivo del formato de imagen deseado.

#### P: ¿Se requiere una licencia Aspose válida para este tutorial?

R: Sí, se requiere una licencia Aspose válida para que este tutorial funcione correctamente. Puede comprar una licencia completa u obtener una licencia temporal de 30 días en el sitio web de Aspose.