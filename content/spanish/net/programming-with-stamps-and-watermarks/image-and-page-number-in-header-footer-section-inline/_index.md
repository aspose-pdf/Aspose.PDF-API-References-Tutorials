---
title: Imagen y número de página en la sección de encabezado y pie de página en línea
linktitle: Imagen y número de página en la sección de encabezado y pie de página en línea
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a agregar una imagen y un número de página en línea en la sección de encabezado de un PDF usando Aspose.PDF para .NET con esta guía paso a paso.
type: docs
weight: 120
url: /es/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section-inline/
---
## Introducción

Aspose.PDF para .NET es una herramienta potente que ofrece amplias capacidades para manipular y generar archivos PDF. Ya sea que necesite agregar imágenes, personalizar encabezados y pies de página o administrar texto, Aspose.PDF lo ayudará. En este tutorial, exploraremos cómo agregar una imagen y un número de página en línea en el encabezado o pie de página de un documento PDF. Profundicemos en el proceso paso a paso.

## Prerrequisitos

Antes de pasar al código, asegurémonos de que tienes todo en su lugar para seguir:

-  Aspose.PDF para .NET: Descargue la última versión desde[Página de descarga de PDF de Aspose](https://releases.aspose.com/pdf/net/).
- Entorno de desarrollo: necesitará un IDE de C# como Visual Studio.
-  Licencia: Si aún no tienes una licencia, puedes obtener una[Licencia temporal aquí](https://purchase.aspose.com/temporary-license/) o compre uno completo en[Tienda Aspose](https://purchase.aspose.com/buy).

Ahora que tienes los requisitos previos listos, comencemos.

## Importar paquetes

Antes de comenzar a codificar, asegúrese de importar los espacios de nombres necesarios:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Estos paquetes le permiten trabajar con archivos PDF y manipulación de texto.

## Paso 1: Configurar el directorio de documentos

Lo primero que debemos hacer es definir la ruta del directorio donde se guardará nuestro archivo PDF. Esta ruta puede personalizarse para la carpeta de su proyecto o cualquier ubicación de su equipo.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Esta variable contiene la ubicación donde se almacenará su documento. Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta actual.

## Paso 2: Crear una instancia del documento PDF

 En este paso, creamos una nueva instancia del`Aspose.Pdf.Document` objeto. Este objeto servirá como columna vertebral de su archivo PDF.

```csharp
// Instanciar un objeto Documento llamando a su constructor vacío
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

Aquí, estamos creando un archivo PDF en blanco que luego podemos completar con contenido.

## Paso 3: Agregar una página al PDF

Tu PDF necesita al menos una página en la que puedas agregar encabezados, pies de página y contenido. Agreguemos una página en blanco a nuestro documento.

```csharp
// Crear una página en el objeto Pdf
Aspose.Pdf.Page page = pdf1.Pages.Add();
```

 llamando`pdf1.Pages.Add()`se agrega una nueva página al documento, lista para personalizar el encabezado y el pie de página.

## Paso 4: Crear y configurar el encabezado

Ahora es el momento de crear el encabezado del documento. Aquí es donde agregaremos el texto, la imagen y el número de página.

```csharp
// Crear la sección de encabezado del documento
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();
// Establecer el encabezado para el archivo PDF
page.Header = header;
```

 Creamos una`HeaderFooter` objeto y asignarlo a la`Header` propiedad de la página, garantizando que cualquier cosa que agreguemos al encabezado aparecerá en la parte superior de la página.

## Paso 5: Agregar texto en línea al encabezado

 Agregar texto es tan sencillo como crear un`TextFragment` y especificar sus propiedades. Agreguemos un texto de color a nuestro encabezado.

```csharp
// Crear un objeto de texto
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a Robust component by");
// Especifica el color
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;
```

 En este paso, creamos un`TextFragment` con el contenido "Aspose.Pdf es un componente robusto de" y establezca su color en azul.`IsInLineParagraph` La propiedad garantiza que el texto esté en línea, lo que significa que aparecerá en la misma línea que los otros elementos (como la imagen y el texto adicional).

## Paso 6: Insertar una imagen en línea en el encabezado

Para que el encabezado sea visualmente atractivo, puedes agregar una imagen en línea con el texto. Puede ser el logotipo de tu empresa o cualquier otro gráfico.

```csharp
// Crea un objeto de imagen en la sección
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
// Establecer la ruta del archivo de imagen
image1.File = dataDir + "aspose-logo.jpg";
// Establecer el ancho de la imagen Información
image1.FixWidth = 50;
image1.FixHeight = 20;
// Indica que InlineParagraph de seg1 es una imagen.
image1.IsInLineParagraph = true;
```

 Aquí, agregamos una imagen al encabezado creando un`Image` objeto, estableciendo su ruta y ajustando el ancho y la altura.`IsInLineParagraph` asegura que la imagen esté alineada con el texto.

## Paso 7: Agregue texto adicional en línea para completar el encabezado

Agreguemos más texto para completar el encabezado en línea.

```csharp
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);
```

 En esta parte, creamos otro`TextFragment` con el contenido "Pty Ltd." y se establece su color en granate. Tanto los fragmentos de texto como la imagen se agregan al encabezado.

## Paso 8: Guarda el PDF

Una vez que hayas configurado el encabezado, es hora de guardar el PDF.

```csharp
// Guardar el PDF
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");
```

 El`Save` El método escribe el archivo PDF final en la ubicación especificada.

## Conclusión

¡Felicitaciones! Ha agregado con éxito una imagen y texto al encabezado de un documento PDF con Aspose.PDF para .NET. Este tutorial lo guió por los pasos esenciales, incluida la creación de un documento, la adición de páginas, la inserción de encabezados y la colocación de contenido en línea como texto e imágenes. Aspose.PDF le brinda una flexibilidad increíble para administrar sus archivos PDF, ya sea que esté manipulando encabezados, pies de página o contenido complejo. 

## Preguntas frecuentes

### ¿Puedo agregar también un número de página al encabezado?
 ¡Sí! Puedes agregar fácilmente un número de página usando el`TextFragment` Clase y formatéela según sea necesario. Simplemente insértela en la sección de encabezado como contenido en línea.

### ¿Cómo configuro una imagen de fondo en el encabezado?
 Puedes utilizar el`BackgroundImage` propiedad de la`HeaderFooter` Clase para establecer una imagen de fondo. Sin embargo, no se trata de contenido en línea y cubrirá toda el área del encabezado.

### ¿Es posible utilizar otros formatos de imagen además de JPEG?
¡Por supuesto! Aspose.PDF admite varios formatos de imagen, como PNG, BMP y GIF.

### ¿Puedo personalizar la fuente del texto del encabezado?
 Sí, puedes utilizar el`TextState`objeto para cambiar la fuente, el tamaño y el estilo del texto.

### ¿Necesito una licencia para usar Aspose.PDF para .NET?
 Sí, Aspose.PDF requiere una licencia para uso en producción, pero puedes comenzar con una[Prueba gratis aquí](https://releases.aspose.com/).