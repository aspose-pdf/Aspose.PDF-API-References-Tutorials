---
title: Texto e imagen como párrafo
linktitle: Texto e imagen como párrafo
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a agregar texto y una imagen como párrafos en línea en un documento PDF usando Aspose.PDF para .NET.
type: docs
weight: 530
url: /es/net/programming-with-text/text-and-image-as-paragraph/
---

Este tutorial explica cómo agregar texto y una imagen como párrafos en línea en un documento PDF usando Aspose.PDF para .NET. El código fuente de C# proporcionado demuestra el proceso paso a paso.

## requisitos previos

Antes de continuar con el tutorial, asegúrese de tener lo siguiente:

- Conocimientos básicos del lenguaje de programación C#.
- Aspose.PDF para la biblioteca .NET instalada. Puede obtenerlo del sitio web de Aspose o usar NuGet para instalarlo en su proyecto.

## Paso 1: configurar el proyecto

Comience por crear un nuevo proyecto de C# en su entorno de desarrollo integrado (IDE) preferido y agregue una referencia a la biblioteca Aspose.PDF para .NET.

## Paso 2: importa los espacios de nombres necesarios

Agregue las siguientes directivas using al principio de su archivo C# para importar los espacios de nombres requeridos:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Drawing;
```

## Paso 3: establezca la ruta al directorio del documento

 Establezca la ruta a su directorio de documentos usando el`dataDir` variable:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

## Paso 4: Cree un nuevo documento y página

 Crear un nuevo`Document` objeto y agregue una página a su colección de páginas:

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Paso 5: Cree un TextFragment y agréguelo como un párrafo

 Crear un`TextFragment`objeto y agréguelo a la colección de párrafos de la página:

```csharp
TextFragment text = new TextFragment("Hello World.. ");
page.Paragraphs.Add(text);
```

## Paso 6: Agrega una imagen como un párrafo en línea

 Crear un`Aspose.Pdf.Image` objeto y configúrelo como un párrafo en línea para que aparezca justo después del párrafo anterior:

```csharp
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
image.IsInLineParagraph = true;
image.File = dataDir + "aspose-logo.jpg";
image.FixHeight = 30; // Opcional: establecer la altura de la imagen
image.FixWidth = 100; // Opcional: establecer el ancho de la imagen
page.Paragraphs.Add(image);
```

 Reemplazar`"aspose-logo.jpg"` con el nombre de archivo de la imagen real y ajuste la altura y el ancho de la imagen opcional según lo desee.

## Paso 7: Agregue otro TextFragment como un párrafo en línea

 Vuelva a inicializar el`TextFragment` objeto con contenido diferente y agréguelo como un párrafo en línea:

```csharp
text = new TextFragment(" Hello Again..");
text.IsInLineParagraph = true;
page.Paragraphs.Add(text);
```

## Paso 8: Guarde el documento PDF

Guarde el documento PDF modificado:

```csharp
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
```

 Asegúrese de reemplazar`"TextAndImageAsParagraph_out.pdf"` con el nombre de archivo de salida deseado.

### Ejemplo de código fuente para texto e imagen como párrafo usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instanciar instancia de documento
Document doc = new Document();
// Agregar página a la colección de páginas de la instancia del documento
Page page = doc.Pages.Add();
// Crear TextFragmnet
TextFragment text = new TextFragment("Hello World.. ");
// Agregar fragmento de texto a la colección de párrafos del objeto Página
page.Paragraphs.Add(text);
// Crear una instancia de imagen
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
// Establezca la imagen como párrafo en línea para que aparezca justo después
// El objeto de párrafo anterior (TextFragment)
image.IsInLineParagraph = true;
// Especifique la ruta del archivo de imagen
image.File = dataDir + "aspose-logo.jpg";
// Establecer la altura de la imagen (opcional)
image.FixHeight = 30;
// Establecer ancho de imagen (opcional)
image.FixWidth = 100;
//Agregar imagen a la colección de párrafos del objeto de página
page.Paragraphs.Add(image);
// Reinicializar el objeto TextFragment con diferentes contenidos
text = new TextFragment(" Hello Again..");
// Establecer TextFragment como párrafo en línea
text.IsInLineParagraph = true;
// Agregue TextFragment recién creado a la colección de párrafos de la página
page.Paragraphs.Add(text);
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nText and image added successfully as an inline paragraphs.\nFile saved at " + dataDir);
```

## Conclusión

¡Felicidades! Ha aprendido con éxito cómo agregar texto y una imagen como párrafos en línea en un documento PDF usando Aspose.PDF para .NET. Este tutorial proporcionó una guía paso a paso, desde configurar el proyecto hasta guardar el documento modificado. Ahora puede incorporar este código en sus propios proyectos de C# para personalizar el diseño de texto e imágenes en archivos PDF.