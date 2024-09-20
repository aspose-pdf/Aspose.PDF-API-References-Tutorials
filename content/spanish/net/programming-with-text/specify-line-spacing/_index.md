---
title: Especificar el interlineado en un archivo PDF
linktitle: Especificar el interlineado en un archivo PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a especificar el interlineado en un PDF con Aspose.PDF para .NET con esta guía paso a paso. Perfecta para desarrolladores que buscan un formato de texto preciso.
type: docs
weight: 510
url: /es/net/programming-with-text/specify-line-spacing/
---
## Introducción

¿Alguna vez ha tenido problemas para controlar el interlineado en un archivo PDF? Quizás haya tenido texto que parece demasiado abarrotado o que simplemente no se ve tan pulido como le gustaría. En este tutorial, le mostraremos cómo puede especificar fácilmente el interlineado en un PDF utilizando Aspose.PDF para .NET. Utilizaremos una guía sencilla, paso a paso, para llevarlo de un PDF en blanco a uno que incluya interlineado personalizado. Esto es perfecto si necesita precisión en el diseño del texto para documentos como informes, facturas o certificados.

## Prerrequisitos

Antes de pasar al código, asegurémonos de que tienes todo lo que necesitas:

1.  Aspose.PDF para .NET instalado. Si no lo tienes, descárgalo desde[Página de descarga de Aspose.PDF](https://releases.aspose.com/pdf/net/).
2. Un entorno de desarrollo .NET (como Visual Studio).
3. Un archivo de fuente TrueType (`.ttf` ) que usaremos en el ejemplo. Puedes usar cualquier fuente, pero para esta guía, usaremos la`HPSimplified.TTF` fuente.
4. Conocimientos básicos de C# y manipulación de PDF.

Si está listo, pasemos a importar los paquetes necesarios.

## Importar paquetes

En su proyecto de C#, deberá importar los espacios de nombres Aspose.PDF para trabajar con las funcionalidades de PDF. A continuación, le indicamos cómo hacerlo:

```csharp
using Aspose.Pdf.Text;
using System.IO;
```

Estos espacios de nombres le permiten crear y manipular documentos PDF, así como trabajar con formato de texto y opciones de fuente.

Lo dividiremos en pasos breves para que puedas seguirlo fácilmente. Cada paso se centrará en una parte clave del proceso, desde la configuración del PDF hasta la especificación del interlineado.

## Paso 1: Configure su proyecto y defina el directorio del documento

Lo primero que debemos hacer es definir dónde se encuentran nuestros archivos. Esto ayuda al programa a saber dónde encontrar la fuente y dónde guardar el PDF resultante.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string fontFile = dataDir + "HPSimplified.TTF";
```

 En este paso, reemplazarás`"YOUR DOCUMENT DIRECTORY"` con la ruta real donde almacenas tus archivos. Aquí es donde colocarás tu archivo de fuente (`HPSimplified.TTF`) y donde se guardará el PDF.

## Paso 2: Cargue un documento PDF

Ahora, necesitamos crear un nuevo documento PDF. Para esta guía, comenzaremos con un documento en blanco, pero también puedes cargar un PDF existente si es necesario.

```csharp
Document doc = new Document();
```

Esto crea un nuevo documento PDF vacío. Fácil, ¿verdad?

## Paso 3: Establecer las opciones de formato de texto

 Aquí es donde ocurre la magia. Especificaremos el modo de interlineado para el texto que queremos agregar al PDF. Aspose.PDF nos brinda varias opciones, pero en esta guía, usaremos`LineSpacingMode.FullSize`, lo que garantiza que se respete plenamente el espacio entre líneas.

```csharp
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
```

 Este código establece el modo de interlineado en`FullSize` , lo que garantiza que el texto se mostrará con el espaciado adecuado. Hay otras opciones como`Proportional` Si desea diferentes comportamientos de espaciado, pero por ahora, sigamos con`FullSize`.

## Paso 4: Crear un fragmento de texto

Ahora vamos a crear el texto real que se colocará en el PDF. Este texto respetará el interlineado que hemos definido.

```csharp
TextFragment textFragment = new TextFragment("Hello world");
```

 Hemos creado un fragmento de texto con la cadena`"Hello world"`Por supuesto, puedes personalizar este texto como quieras.

## Paso 5: Cargar y aplicar una fuente personalizada

Para que el texto se destaque, cargaremos una fuente TrueType personalizada desde un archivo. Este paso es opcional, pero puede agregar un toque profesional a sus archivos PDF.

```csharp
if (fontFile != "")
{
    using (FileStream fontStream = System.IO.File.OpenRead(fontFile))
    {
        textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
```

Aquí cargamos el archivo de fuente y lo aplicamos al fragmento de texto. Si la ruta del archivo es válida, se utiliza la fuente. De lo contrario, se aplica la fuente predeterminada.

## Paso 6: Establecer la posición y el formato del texto

A continuación, debemos posicionar el texto en el PDF. También aplicaremos las opciones de formato que creamos anteriormente.

```csharp
textFragment.Position = new Position(100, 600);
textFragment.TextState.FormattingOptions = formattingOptions;
```

 El`Position` El método establece las coordenadas en las que aparecerá el texto en la página (en este caso, 100 unidades desde la izquierda y 600 unidades desde la parte inferior). Aquí se aplican las opciones de formato, incluido el modo de interlineado.

## Paso 7: Agregar texto a la página PDF

Ahora que nuestro texto está formateado y posicionado, es momento de agregarlo al documento PDF.

```csharp
var page = doc.Pages.Add();
page.Paragraphs.Add(textFragment);
```

Este código crea una nueva página en el documento PDF y le agrega el fragmento de texto.

## Paso 8: Guarda el PDF

¡Hemos llegado al paso final! Ahora que todo está configurado, guardemos el PDF.

```csharp
dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
doc.Save(dataDir);
```

Esto guarda el PDF con el espacio entre líneas especificado y ¡su archivo estará listo!

## Conclusión

¡Y eso es todo! Acabas de crear un documento PDF con interlineado personalizado utilizando Aspose.PDF para .NET. Es una herramienta poderosa que te permite controlar cada aspecto de tus archivos PDF, y este es solo un ejemplo de lo que puedes lograr. Desde la ubicación del texto hasta el formato, las posibilidades son infinitas.

Si desea profundizar en la manipulación de archivos PDF, Aspose.PDF ofrece una gran cantidad de funciones para explorar. ¡No dude en experimentar y superar los límites de lo que puede hacer con sus documentos!

## Preguntas frecuentes

### ¿Puedo ajustar el interlineado a otros modos?  
 Sí, puedes utilizar otros modos como`Proportional` o`Fixed` dependiendo de sus necesidades.

### ¿Es posible cargar fuentes desde el sistema en lugar de un archivo?  
 Sí, puedes cargar fuentes instaladas en el sistema usando el`FontRepository`.

### ¿Puedo utilizar Aspose.PDF para .NET con otros formatos de archivo?  
¡Por supuesto! Aspose.PDF para .NET admite una variedad de formatos, como XML, HTML y más.

### ¿Necesito una licencia para usar Aspose.PDF para .NET?  
Sí, para una funcionalidad completa, necesitará una licencia, que puede obtener[aquí](https://purchase.aspose.com/buy).

### ¿Cómo configuro el interlineado para varios párrafos?  
 Puedes aplicar`TextFormattingOptions` A cada uno`TextFragment` o`TextParagraph` para controlar el espaciado de varias líneas o párrafos.