---
title: Texto e imagen como párrafo en archivo PDF
linktitle: Texto e imagen como párrafo en archivo PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a agregar texto y una imagen como párrafos en línea en un archivo PDF usando Aspose.PDF para .NET.
type: docs
weight: 530
url: /es/net/programming-with-text/text-and-image-as-paragraph/
---
Este tutorial explica cómo agregar texto y una imagen como párrafos en línea en un archivo PDF mediante Aspose.PDF para .NET. El código fuente de C# proporcionado muestra el proceso paso a paso.

## Prerrequisitos

Antes de continuar con el tutorial, asegúrese de tener lo siguiente:

- Conocimientos básicos del lenguaje de programación C#.
- Biblioteca Aspose.PDF para .NET instalada. Puede obtenerla desde el sitio web de Aspose o usar NuGet para instalarla en su proyecto.

## Paso 1: Configurar el proyecto

Comience creando un nuevo proyecto C# en su entorno de desarrollo integrado (IDE) preferido y agregue una referencia a la biblioteca Aspose.PDF para .NET.

## Paso 2: Importar los espacios de nombres necesarios

Agregue las siguientes directivas using al comienzo de su archivo C# para importar los espacios de nombres requeridos:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Drawing;
```

## Paso 3: Establezca la ruta al directorio del documento

 Establezca la ruta a su directorio de documentos utilizando el`dataDir` variable:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

## Paso 4: Crear un nuevo documento y página

 Crear uno nuevo`Document` objeto y agrega una página a su colección de páginas:

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Paso 5: Crea un TextFragment y agrégalo como párrafo

 Crear un`TextFragment` objeto y agregarlo a la colección de párrafos de la página:

```csharp
TextFragment text = new TextFragment("Hello World.. ");
page.Paragraphs.Add(text);
```

## Paso 6: Agrega una imagen como párrafo en línea

 Crear un`Aspose.Pdf.Image` objeto y configúrelo como un párrafo en línea para que aparezca justo después del párrafo anterior:

```csharp
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
image.IsInLineParagraph = true;
image.File = dataDir + "aspose-logo.jpg";
image.FixHeight = 30; // Opcional: Establecer la altura de la imagen
image.FixWidth = 100; // Opcional: Establecer el ancho de la imagen
page.Paragraphs.Add(image);
```

 Reemplazar`"aspose-logo.jpg"` con el nombre del archivo de imagen real y ajuste la altura y el ancho opcionales de la imagen según lo desee.

## Paso 7: Agrega otro TextFragment como un párrafo en línea

 Reiniciar el`TextFragment` objeto con contenido diferente y agregarlo como un párrafo en línea:

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

 Asegúrese de reemplazar`"TextAndImageAsParagraph_out.pdf"` con el nombre del archivo de salida deseado.

### Código fuente de muestra para texto e imagen como párrafo utilizando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crear una instancia de documento
Document doc = new Document();
// Agregar página a la colección de páginas de la instancia de Documento
Page page = doc.Pages.Add();
// Crear TextFragmnet
TextFragment text = new TextFragment("Hello World.. ");
// Agregar fragmento de texto a la colección de párrafos del objeto Página
page.Paragraphs.Add(text);
// Crear una instancia de imagen
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
// Establecer la imagen como párrafo en línea para que aparezca inmediatamente después
// El objeto del párrafo anterior (TextFragment)
image.IsInLineParagraph = true;
// Especificar la ruta del archivo de imagen
image.File = dataDir + "aspose-logo.jpg";
// Establecer la altura de la imagen (opcional)
image.FixHeight = 30;
// Establecer el ancho de la imagen (opcional)
image.FixWidth = 100;
// Agregar imagen a la colección de párrafos del objeto de página
page.Paragraphs.Add(image);
// Reinicializar el objeto TextFragment con contenido diferente
text = new TextFragment(" Hello Again..");
// Establecer TextFragment como párrafo en línea
text.IsInLineParagraph = true;
// Agregar un TextFragment recién creado a la colección de párrafos de la página
page.Paragraphs.Add(text);
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nText and image added successfully as an inline paragraphs.\nFile saved at " + dataDir);
```

## Conclusión

¡Felicitaciones! Aprendió a agregar texto e imágenes como párrafos en línea en un documento PDF con Aspose.PDF para .NET. Este tutorial le proporcionó una guía paso a paso, desde la configuración del proyecto hasta el guardado del documento modificado. Ahora puede incorporar este código en sus propios proyectos de C# para personalizar el diseño del texto y las imágenes en los archivos PDF.

### Preguntas frecuentes

#### P: ¿Cuál es el propósito del tutorial "Texto e imagen como párrafo en archivo PDF"?

A: El tutorial "Texto e imagen como párrafo en un archivo PDF" tiene como objetivo guiar a los usuarios sobre cómo agregar texto e imágenes como párrafos en línea dentro de un documento PDF utilizando Aspose.PDF para .NET. El tutorial proporciona instrucciones paso a paso y ejemplos de código C# para demostrar el proceso.

#### P: ¿Cómo ayuda este tutorial a agregar texto e imágenes como párrafos en línea?

R: Este tutorial ayuda a los usuarios a comprender cómo utilizar Aspose.PDF para .NET para incorporar texto e imágenes como párrafos en línea dentro de un documento PDF. Si siguen los pasos y los ejemplos de código proporcionados, los usuarios pueden crear archivos PDF con diseños personalizados que combinan texto e imágenes.

#### P: ¿Qué requisitos previos se requieren para seguir este tutorial?

R: Antes de comenzar el tutorial, debe tener conocimientos básicos del lenguaje de programación C#. Además, debe tener instalada la biblioteca Aspose.PDF para .NET. Puede obtenerla del sitio web de Aspose o instalarla en su proyecto mediante NuGet.

#### P: ¿Cómo configuro mi proyecto para seguir este tutorial?

R: Para comenzar, cree un nuevo proyecto de C# en su entorno de desarrollo integrado (IDE) preferido y agregue una referencia a la biblioteca Aspose.PDF para .NET. Esto le permite utilizar las características de la biblioteca para trabajar con documentos PDF, fragmentos de texto e imágenes.

#### P: ¿Puedo usar este tutorial para agregar varios párrafos de texto e imágenes en un PDF?

R: Sí, puede utilizar los ejemplos de código proporcionados para agregar varias instancias de párrafos de texto e imágenes dentro del mismo documento PDF. Este tutorial demuestra cómo crear párrafos en línea, lo que facilita la inclusión de diferentes combinaciones de texto e imágenes.

#### P: ¿Cómo especifico el contenido y la apariencia de los párrafos de texto y las imágenes?

 A: El tutorial demuestra cómo crear`TextFragment`objetos para representar párrafos de texto y`Aspose.Pdf.Image` objetos para representar imágenes. Puede personalizar el contenido, las dimensiones y la apariencia tanto del texto como de las imágenes utilizando los ejemplos de código proporcionados.

#### P: ¿Puedo ajustar el diseño de los párrafos en línea?

 R: Sí, puedes ajustar el diseño de los párrafos en línea controlando su posición, dimensiones y orden dentro de la página. El tutorial muestra cómo configurar atributos en línea, como`IsInLineParagraph`, para controlar el diseño de párrafos de texto e imágenes.

#### P: ¿Cómo guardo el documento PDF modificado?

 A: Para guardar el documento PDF modificado, puede utilizar el`Save` método de la`Document` objeto. El tutorial proporciona ejemplos de código que demuestran cómo guardar el documento PDF resultante.