---
title: Texto e imagen como párrafo en archivo PDF
linktitle: Texto e imagen como párrafo en archivo PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Cree archivos PDF con texto e imágenes con Aspose.PDF para .NET. Aprenda a agregar texto e imágenes en línea paso a paso.
type: docs
weight: 530
url: /es/net/programming-with-text/text-and-image-as-paragraph/
---
## Introducción

En el mundo digital actual, los archivos PDF son un formato de documento universal con el que la mayoría de nosotros nos encontramos a diario. Ya sea un informe, un libro electrónico o una factura comercial, los archivos PDF facilitan el intercambio de información en varias plataformas. Pero, ¿qué sucede si desea personalizar un PDF mediante programación? Ahí es donde entra en juego Aspose.PDF para .NET. En este tutorial, lo guiaremos en la inserción de texto e imágenes como párrafos en línea en un archivo PDF utilizando Aspose.PDF para .NET.

## Prerrequisitos

Antes de sumergirnos en el código, asegurémonos de que tienes todo lo que necesitas para seguirlo sin problemas:

-  Biblioteca Aspose.PDF para .NET: necesitará instalar Aspose.PDF para .NET. Puede descargarla[aquí](https://releases.aspose.com/pdf/net/).
- Visual Studio: cualquier versión que admita .NET funcionará bien.
- Conocimientos básicos de C#: será útil tener cierta familiaridad con C#, pero no te preocupes: ¡te guiaré paso a paso!
- Documento PDF listo: si desea agregar una imagen personalizada, téngala lista.

 También puedes obtener una prueba gratuita de la biblioteca.[aquí](https://releases.aspose.com/) , o si estás trabajando en un proyecto a gran escala, considera comprarlo[aquí](https://purchase.aspose.com/buy) ¿Necesitas más detalles? Consulta la documentación[aquí](https://reference.aspose.com/pdf/net/).

## Importar paquetes

Para comenzar a utilizar Aspose.PDF para .NET, debe importar los espacios de nombres necesarios. Estos espacios de nombres permiten que su código C# interactúe con las funcionalidades de Aspose.PDF.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Facades;
using System;
```

Sencillo, ¿verdad? Ahora pasemos a la parte divertida: crear tu propio archivo PDF.

## Guía paso a paso: Cómo crear un PDF con texto e imagen en línea

Vamos a dividirlo en pasos fáciles de seguir y digeribles. Imagina que estás armando un rompecabezas; cada paso es como encontrar y colocar la pieza correcta.

## Paso 1: Inicializar el documento PDF

El primer paso es crear un nuevo documento PDF con Aspose.PDF. Este documento servirá como base para agregar texto e imágenes.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crear una instancia de documento
Document doc = new Document();
```

 ¿Qué está pasando aquí? Simplemente estamos creando un nuevo documento usando el`Document`Clase y definición del directorio donde desea guardar el PDF. ¡Es como abrir un lienzo en blanco para su obra maestra!

## Paso 2: Agrega una página a tu PDF

Un documento no sirve de mucho sin páginas, ¿no? Vamos a añadir una página en blanco a tu documento.

```csharp
// Agregar página a la colección de páginas de la instancia de Documento
Page page = doc.Pages.Add();
```

Este fragmento de código agrega una nueva página a la colección de páginas de su documento. Piense en ello como si estuviera abriendo una página en blanco en un cuaderno.

## Paso 3: Agregar texto como párrafo

A continuación, agregaremos un párrafo de texto. Aquí podrás insertar tu mensaje o encabezado.

```csharp
// Crear fragmento de texto
TextFragment text = new TextFragment("Hello World.. ");
// Agregar fragmento de texto a la colección de párrafos del objeto Página
page.Paragraphs.Add(text);
```

 Aquí creamos un`TextFragment` Objeto para contener el texto "Hola mundo...", que luego se agrega a la página como un párrafo. Es como escribir la primera oración de un documento PDF.

## Paso 4: Agregar una imagen como párrafo en línea

Ahora que tenemos el texto, vamos a darle un toque más interesante agregando una imagen como párrafo en línea. Un párrafo en línea simplemente significa que la imagen aparecerá justo después del texto, de manera similar a cómo se muestran las imágenes en los documentos de Word.

```csharp
// Crear una instancia de imagen
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
// Establecer la imagen como párrafo en línea para que aparezca inmediatamente después
// El objeto del párrafo anterior (TextFragment)
image.IsInLineParagraph = true;
// Especificar la ruta del archivo de imagen
image.File = dataDir + "aspose-logo.jpg";
```

 En este fragmento, creamos un`Image` objeto, indíquele que se alinee con el texto y especifique la ruta al archivo de imagen. Esto es el equivalente a pegar una imagen justo después de una oración en un documento. Puede cambiar "aspose-logo.jpg" por la imagen que desee.

## Paso 5: Establecer el tamaño de la imagen (opcional)

¿Quieres cambiar el tamaño de la imagen? No hay problema. Aspose.PDF te ofrece la opción de ajustar la altura y el ancho de la imagen antes de agregarla a tu documento.

```csharp
// Establecer la altura de la imagen (opcional)
image.FixHeight = 30;
// Establecer el ancho de la imagen (opcional)
image.FixWidth = 100;
```

Esta parte es opcional, pero te ayuda a controlar el tamaño de la imagen en tu PDF. Es como cambiar el tamaño de una foto antes de imprimirla.

## Paso 6: Agregar imagen a la colección de párrafos

Hemos preparado la imagen. Ahora, insertémosla en el documento como un párrafo en línea.

```csharp
// Agregar imagen a la colección de párrafos del objeto de página
page.Paragraphs.Add(image);
```

Esta línea agrega la imagen justo después del texto en la colección de párrafos. Es como presionar el botón "Insertar imagen" en un editor de texto.

## Paso 7: Agregar otro párrafo de texto en línea

¿Qué sucede si desea agregar más texto justo después de la imagen? Hagámoslo insertando otro fragmento de texto en línea.

```csharp
// Reinicializar el objeto TextFragment con contenido diferente
text = new TextFragment(" Hello Again..");
// Establecer TextFragment como párrafo en línea
text.IsInLineParagraph = true;
// Agregar un TextFragment recién creado a la colección de párrafos de la página
page.Paragraphs.Add(text);
```

 Estamos reutilizando el`TextFragment`Aquí, coloque el objeto con el texto nuevo ("Hola de nuevo...") y colóquelo en línea, justo después de la imagen. Esto le da a su PDF un aspecto fluido y coherente.

## Paso 8: Guarde el documento PDF

¡Ya casi hemos terminado! Ahora, guardemos el documento en el directorio especificado.

```csharp
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nText and image added successfully as inline paragraphs.\nFile saved at " + dataDir);
```

Este último paso guarda el archivo en su directorio con el nombre "TextAndImageAsParagraph_out.pdf". ¡Felicitaciones! ¡Ha creado un PDF con texto e imágenes en línea!

## Conclusión

Y ya está: crear un PDF con texto e imágenes como párrafos en línea con Aspose.PDF para .NET es tan sencillo como seguir estos pasos. Con solo unas pocas líneas de código, puede agregar contenido dinámico a sus archivos PDF, haciéndolos más atractivos y profesionales a la vista. Ya sea para un informe empresarial o un libro electrónico, tener control sobre el diseño de sus archivos PDF puede marcar una gran diferencia.

## Preguntas frecuentes

### ¿Puedo agregar varias imágenes como párrafos en línea?  
 Sí, puedes agregar varias imágenes creando archivos separados.`Image` objetos y agregarlos a la colección de párrafos.

### ¿Puedo controlar la posición del texto y la imagen en el PDF?  
Sí, al usar propiedades como márgenes, puedes controlar la ubicación precisa de tu texto e imágenes.

### ¿Aspose.PDF para .NET es gratuito?  
 No, es un producto con licencia, pero puedes obtenerlo[prueba gratis](https://releases.aspose.com/) o comprar una licencia[aquí](https://purchase.aspose.com/buy).

### ¿Puedo agregar hipervínculos al texto?  
 Sí, Aspose.PDF te permite agregar hipervínculos dentro de fragmentos de texto. Consulta la[documentación](https://reference.aspose.com/pdf/net/) Para más detalles.

### ¿Puedo personalizar la fuente y el estilo del texto?  
¡Por supuesto! Puedes personalizar fácilmente las fuentes, los colores y otras propiedades de estilo de los fragmentos de texto.