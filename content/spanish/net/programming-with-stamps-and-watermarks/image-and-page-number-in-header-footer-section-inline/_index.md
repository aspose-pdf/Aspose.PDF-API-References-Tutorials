---
title: Imagen y número de página en la sección de encabezado y pie de página en línea
linktitle: Imagen y número de página en la sección de encabezado y pie de página en línea
second_title: Aspose.PDF para referencia de API .NET
description: Aprenda a agregar una imagen y un número de página en el encabezado y pie de página usando párrafos en línea con Aspose.PDF para .NET.
type: docs
weight: 120
url: /es/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section-inline/
---
En este tutorial, lo guiaremos paso a paso sobre cómo agregar una imagen y un número de página en la sección de encabezado y pie de página de un documento PDF usando Aspose.PDF para .NET. Usaremos el código fuente C# proporcionado para crear una página, configurar el encabezado y el pie de página, agregar imágenes y texto usando párrafos en línea en el encabezado del documento PDF.

## Paso 1: configurar el entorno

Antes de comenzar, asegúrese de tener lo siguiente:

- Un entorno de desarrollo .NET instalado.
- La biblioteca Aspose.PDF para .NET descargada y referenciada en su proyecto.

## Paso 2: Crear el documento y la página PDF

El primer paso es crear un nuevo objeto Documento y una página en el documento PDF. Así es cómo:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Crear un nuevo objeto de documento
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// Crear una página en el documento.
Aspose.Pdf.Page page = pdf1.Pages.Add();
```

El código anterior crea un nuevo objeto Documento y una página vacía en el documento PDF.

## Paso 3: agregar el encabezado con una imagen y texto en línea

Ahora que la página está creada, podemos agregar una sección de encabezado con una imagen y texto usando párrafos en línea. Así es cómo:

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

// Crear un objeto Imagen para la imagen.
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Establecer ruta de imagen
image1.File = dataDir + "aspose-logo.jpg";

// Definir las dimensiones de la imagen.
image1.FixWidth = 50;
image1.FixHeight = 20;

// Indica que el primer texto en línea es una imagen.
image1.IsInLineParagraph = true;

// Crea un segundo texto en línea
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;

// Agregar elementos al encabezado
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);
```

El código anterior crea una sección de encabezado, establece el encabezado de la página con esta sección, agrega un TextFragment con texto en línea y un objeto Imagen en línea.

## Paso 4: Guardar el documento PDF modificado

Una vez añadido el encabezado con la imagen y el texto en línea, podremos guardar el documento PDF modificado. Así es cómo:

```csharp
// Guarde el documento PDF modificado
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");
```

El código anterior guarda el documento PDF editado en el directorio especificado.

### Código fuente de muestra para imagen y número de página en la sección de pie de página del encabezado en línea usando Aspose.PDF para .NET 
```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crear una instancia de un objeto Documento llamando a su constructor vacío
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// Crear una página en el objeto PDF.
Aspose.Pdf.Page page = pdf1.Pages.Add();

// Crear sección de encabezado del documento
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Establecer el encabezado del archivo PDF
page.Header = header;

// Crear un objeto de texto
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a Robust component by");

// Especifica el color
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

// Crea un objeto de imagen en la sección.
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Establecer la ruta del archivo de imagen
image1.File = dataDir + "aspose-logo.jpg";

// Establecer el ancho de la imagen Información
image1.FixWidth = 50;
image1.FixHeight = 20;

// Indica que el InlineParagraph de seg1 es una imagen.
image1.IsInLineParagraph = true;
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);

// Guarde el PDF
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");

```

## Conclusión

¡Enhorabuena! Ha aprendido a agregar una imagen y un número de página en la sección de encabezado y pie de página de un documento PDF usando párrafos en línea con Aspose.PDF para .NET. Ahora puede personalizar el encabezado y pie de página de sus documentos PDF de manera flexible.

### Preguntas frecuentes

#### P: ¿Cuál es la ventaja de utilizar párrafos en línea para agregar una imagen y texto al encabezado de un documento PDF?

R: El uso de párrafos en línea le permite integrar perfectamente imágenes y texto dentro del mismo párrafo, brindando un control preciso sobre su ubicación y formato. Este método es especialmente útil para crear encabezados personalizados con elementos visuales.

#### P: ¿Cómo logra el código fuente de C# proporcionado párrafos en línea para el encabezado de un documento PDF?

R: El código proporcionado demuestra cómo crear un documento PDF, agregar una página y personalizar el encabezado usando párrafos en línea. Agrega un TextFragment con texto en línea, una imagen en línea y otro TextFragment en línea.

#### P: ¿Cómo especifico el color del texto en línea en el encabezado?

 R: El color del texto en línea se especifica usando el`ForegroundColor` propiedad de la`TextState` del`TextFragment` objeto.

#### P: ¿Puedo ajustar las dimensiones de la imagen en línea en el encabezado?

 R: Sí, puedes ajustar las dimensiones de la imagen en línea usando el`FixWidth` y`FixHeight` propiedades de la`Image` objeto. Esto le permite controlar el ancho y el alto de la imagen dentro del encabezado.

#### P: ¿Puedo incluir elementos en línea adicionales, como hipervínculos o diferentes estilos de fuente, en el encabezado?

 R: Sí, puedes incluir elementos en línea adicionales en el encabezado creando más`TextFragment` o`Image` objetos con las propiedades deseadas. Esto le permite personalizar aún más el encabezado, incluidos hipervínculos, diferentes estilos de fuente u otros elementos visuales.

#### P: ¿Cómo puedo garantizar que la imagen y el texto en línea permanezcan alineados y formateados correctamente en diferentes dispositivos y visores?

R: Aspose.PDF para .NET garantiza que las imágenes y el texto en línea estén alineados y formateados correctamente, lo que da como resultado una apariencia consistente en diferentes dispositivos y visores de PDF.

#### P: ¿Puedo aplicar párrafos en línea también a la sección de pie de página?

 R: Sí, puedes aplicar la misma técnica de usar párrafos en línea a la sección de pie de página creando un`Footer` objeto y agregarle elementos en línea como texto e imágenes.

#### P: ¿Es posible combinar párrafos en línea con otros métodos de personalización de encabezados o pies de página?

R: Sí, puede combinar párrafos en línea con otros métodos de personalización de encabezados o pies de página proporcionados por Aspose.PDF para .NET para crear diseños de encabezados o pies de página más complejos y personalizados.

#### P: ¿Puedo eliminar o borrar los elementos en línea del encabezado si es necesario?

 R: Sí, puede eliminar o borrar los elementos en línea modificando el contenido del`HeaderFooter` objeto y eliminando los respectivos párrafos en línea.

#### P: ¿Cómo puedo aplicar párrafos en línea a páginas específicas del documento PDF?

 R: Para aplicar párrafos en línea a páginas específicas, puede crear párrafos separados`HeaderFooter` objetos para cada página y asígnalos usando el`Header` propiedad del respectivo`Aspose.Pdf.Page` objetos.