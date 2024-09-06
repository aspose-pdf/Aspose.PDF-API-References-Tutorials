---
title: Buscar texto y dibujar rectángulo
linktitle: Buscar texto y dibujar rectángulo
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a buscar texto en un PDF, dibujar rectángulos alrededor del texto encontrado y guardar el documento modificado usando Aspose.PDF para .NET.
type: docs
weight: 460
url: /es/net/programming-with-text/search-text-and-draw-rectangle/
---
Este tutorial explica cómo utilizar Aspose.PDF para .NET para buscar texto específico en un documento PDF, dibujar un rectángulo alrededor del texto encontrado y guardar el documento modificado. El código fuente de C# proporcionado muestra el proceso paso a paso.

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
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
```

## Paso 3: Establezca la ruta al directorio del documento

 Establezca la ruta a su directorio de documentos utilizando el`dataDir` variable:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

## Paso 4: Cargue el documento PDF

 Cargue el documento PDF utilizando el`Document` clase:

```csharp
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 Reemplazar`"SearchAndGetTextFromAll.pdf"` con el nombre real de su archivo PDF.

## Paso 5: Crear un TextFragmentAbsorber

 Crear un`TextFragmentAbsorber` objeto para encontrar todas las instancias de la frase de búsqueda ingresada:

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

 Reemplazar`@"[\S]+"` con el patrón de expresión regular deseado.

## Paso 6: Habilitar la búsqueda de expresiones regulares

 Habilite la búsqueda de expresiones regulares configurando la`TextSearchOptions` Propiedad del absorbedor:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

## Paso 7: Buscar en todas las páginas

Aceptar el absorbedor para todas las páginas del documento:

```csharp
document.Pages.Accept(textAbsorber);
```

## Paso 8: Dibuje un rectángulo alrededor del texto encontrado

 Crear un`PdfContentEditor` objeto y recorra los fragmentos de texto recuperados, dibujando un rectángulo alrededor de cada segmento de texto:

```csharp
var editor = new PdfContentEditor(document);
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
    foreach (TextSegment textSegment in textFragment.Segments)
    {
        DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
    }
}
```

## Paso 9: Guarde el documento modificado

Guardar el documento modificado:

```csharp
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
```

 Asegúrese de reemplazar`"SearchTextAndDrawRectangle_out.pdf"` con el nombre del archivo de salida deseado.

### Código fuente de muestra para buscar texto y dibujar un rectángulo con Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
// Cree un objeto TextAbsorber para encontrar todas las frases que coincidan con la expresión regular
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
document.Pages.Accept(textAbsorber); 
var editor = new PdfContentEditor(document); 
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
			DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
	}
}
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
Console.WriteLine("\nRectangle drawn successfully on searched text.\nFile saved at " + dataDir);
```

## Conclusión

¡Felicitaciones! Aprendió a buscar texto específico en un documento PDF, dibujar un rectángulo alrededor del texto encontrado y guardar el documento modificado utilizando Aspose.PDF para .NET. Este tutorial proporcionó una guía paso a paso, desde la configuración del proyecto hasta la realización de las acciones necesarias. Ahora puede incorporar este código en sus propios proyectos de C# para manipular texto y dibujar rectángulos en archivos PDF.

### Preguntas frecuentes

#### P: ¿Cuál es el propósito del tutorial "Buscar texto y dibujar rectángulo"?

A: El tutorial "Buscar texto y dibujar rectángulos" tiene como objetivo guiar a los usuarios a través del proceso de uso de la biblioteca Aspose.PDF para .NET para buscar texto específico dentro de un documento PDF, dibujar rectángulos alrededor de los segmentos de texto encontrados y guardar el documento modificado. El tutorial proporciona instrucciones detalladas y ejemplos de código C# para ilustrar cada paso del proceso.

#### P: ¿Cómo ayuda este tutorial a dibujar rectángulos alrededor de un texto específico en un documento PDF?

A: Este tutorial ofrece una guía completa sobre cómo ubicar y dibujar rectángulos alrededor de segmentos de texto específicos dentro de un documento PDF. Demuestra el proceso de configuración de un proyecto, la carga de un documento PDF, la habilitación de la búsqueda de expresiones regulares, el dibujo de rectángulos alrededor de segmentos de texto encontrados y el guardado del PDF modificado.

#### P: ¿Qué requisitos previos se requieren para seguir este tutorial?

R: Antes de comenzar el tutorial, debe tener conocimientos básicos del lenguaje de programación C#. Además, debe tener instalada la biblioteca Aspose.PDF para .NET. Puede obtenerla del sitio web de Aspose o instalarla en su proyecto mediante NuGet.

#### P: ¿Cómo configuro mi proyecto para seguir este tutorial?

R: Comience por crear un nuevo proyecto de C# en su entorno de desarrollo integrado (IDE) preferido. Luego, agregue una referencia a la biblioteca Aspose.PDF para .NET a su proyecto. Esto le permitirá usar la funcionalidad de la biblioteca para manipular documentos PDF.

#### P: ¿Puedo dibujar rectángulos alrededor de un texto específico usando este tutorial?

R: Sí, el tutorial se centra en dibujar rectángulos alrededor de segmentos de texto específicos dentro de un documento PDF. Demuestra cómo ubicar el texto deseado mediante expresiones regulares, crear rectángulos alrededor de los segmentos de texto identificados y guardar el PDF modificado.

#### P: ¿Cómo puedo especificar el texto que quiero buscar y dibujar rectángulos alrededor?

 A: Para especificar el texto que desea buscar y dibujar rectángulos alrededor, cree un`TextFragmentAbsorber` objeto y establecer su patrón utilizando el`Text` parámetro. Reemplazar el patrón predeterminado`@"[\S]+"` en el código del tutorial con el patrón de expresión regular deseado.

#### P: ¿Cómo habilito la búsqueda de expresiones regulares para texto?

 A: La búsqueda de expresiones regulares se habilita mediante la creación de una`TextSearchOptions` objeto y estableciendo su valor en`true` Asignar este objeto a la`TextSearchOptions` propiedad de la`TextFragmentAbsorber` instancia. Esto garantiza que se utilice el patrón de expresión regular durante la búsqueda de texto.

#### P: ¿Cómo puedo dibujar rectángulos alrededor del texto encontrado?

 A: Después de identificar los segmentos de texto utilizando el`TextFragmentAbsorber` , el tutorial proporciona un bucle para iterar a través de estos segmentos. Para cada segmento de texto, el tutorial demuestra cómo crear un rectángulo a su alrededor utilizando el`DrawBox` método y especifica la apariencia del rectángulo.

#### P: ¿Cuáles son los pasos para guardar el PDF modificado con rectángulos dibujados?

A: Después de dibujar rectángulos alrededor de los segmentos de texto deseados, utilice el`Document` de la clase`Save` Método para guardar el documento modificado. El código de muestra del tutorial muestra cómo guardar el PDF editado y mostrar un mensaje de confirmación.

#### P: ¿Puedo personalizar la apariencia de los rectángulos dibujados?

 R: Sí, puedes personalizar la apariencia de los rectángulos dibujados. En el código de muestra del tutorial,`DrawBox` El método se utiliza para crear rectángulos. Puede modificar propiedades como el color, el estilo y el grosor para personalizar la apariencia de los rectángulos dibujados.