---
title: Imagen y número de página en la sección de pie de página de encabezado en línea
linktitle: Imagen y número de página en la sección de pie de página de encabezado en línea
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a agregar una imagen y un número de página en el encabezado y el pie de página usando párrafos en línea con Aspose.PDF para .NET.
type: docs
weight: 120
url: /es/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section-inline/
---
En este tutorial, lo guiaremos paso a paso sobre cómo agregar una imagen y un número de página en la sección de encabezado y pie de página de un documento PDF usando Aspose.PDF para .NET. Usaremos el código fuente de C# provisto para crear una página, configurar el encabezado y el pie de página, agregar una imagen y texto usando párrafos en línea en el encabezado del documento PDF.

## Paso 1: Configuración del entorno

Antes de comenzar, asegúrese de tener lo siguiente:

- Un entorno de desarrollo .NET instalado.
- La biblioteca Aspose.PDF para .NET descargada y referenciada en su proyecto.

## Paso 2: Crear el documento PDF y la página

El primer paso es crear un nuevo objeto Documento y una página en el documento PDF. Así es cómo:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Crear un nuevo objeto Documento
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// Crear una página en el documento.
Aspose.Pdf.Page page = pdf1.Pages.Add();
```

El código anterior crea un nuevo objeto Documento y una página vacía en el documento PDF.

## Paso 3: agregar el encabezado con una imagen y texto en línea

Ahora que se creó la página, podemos agregar una sección de encabezado con una imagen y texto usando párrafos en línea. Así es cómo:

```csharp
// Crear una sección de encabezado
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Establecer el encabezado de la página
page. Header = header;

// Cree un objeto TextFragment para el primer texto en línea
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a robust component developed by");

// Especificar color de texto
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

//Crear un objeto de imagen para la imagen
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Establecer la ruta de la imagen
image1.File = dataDir + "aspose-logo.jpg";

// Definir las dimensiones de la imagen.
image1.FixWidth = 50;
image1.FixHeight = 20;

// Indicar que el primer texto en línea es una imagen
image1.IsInLineParagraph = true;

// Crear un segundo texto en línea
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;

// Agregar elementos al encabezado
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);
```

El código anterior crea una sección de encabezado, establece el encabezado de la página con esta sección, agrega un TextFragment con texto en línea y un objeto de imagen en línea.

## Paso 4: Guardar el documento PDF modificado

Una vez que se agrega el encabezado con la imagen y el texto en línea, podemos guardar el documento PDF modificado. Así es cómo:

```csharp
// Guarde el documento PDF modificado
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");
```

El código anterior guarda el documento PDF editado en el directorio especificado.

### Ejemplo de código fuente para la imagen y el número de página en la sección del pie de página del encabezado en línea usando Aspose.PDF para .NET 
```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crea una instancia de un objeto Document llamando a su constructor vacío
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// Crear una página en el objeto Pdf
Aspose.Pdf.Page page = pdf1.Pages.Add();

// Crear sección de encabezado del documento
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Establecer el encabezado para el archivo PDF
page.Header = header;

// Crear un objeto de texto
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a Robust component by");

// Especificar el color
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

// Crear un objeto de imagen en la sección.
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Establecer la ruta del archivo de imagen
image1.File = dataDir + "aspose-logo.jpg";

// Establecer el ancho de la imagen Información
image1.FixWidth = 50;
image1.FixHeight = 20;

// Indica que InlineParagraph de seg1 es una imagen.
image1.IsInLineParagraph = true;
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);

// Guardar el PDF
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");

```

## Conclusión

¡Felicidades! Ha aprendido a agregar una imagen y un número de página en la sección de encabezado y pie de página de un documento PDF utilizando párrafos en línea con Aspose.PDF para .NET. Ahora puede personalizar el encabezado y el pie de página de sus documentos PDF de manera flexible.
