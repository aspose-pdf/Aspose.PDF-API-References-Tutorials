---
title: Buscar texto y dibujar rectángulo
linktitle: Buscar texto y dibujar rectángulo
second_title: Aspose.PDF para referencia de API .NET
description: Aprenda a buscar texto en un PDF, dibujar rectángulos alrededor del texto encontrado y guardar el documento modificado usando Aspose.PDF para .NET.
type: docs
weight: 460
url: /es/net/programming-with-text/search-text-and-draw-rectangle/
---
Este tutorial explica cómo usar Aspose.PDF para .NET para buscar texto específico en un documento PDF, dibujar un rectángulo alrededor del texto encontrado y guardar el documento modificado. El código fuente de C# proporcionado demuestra el proceso paso a paso.

## Requisitos previos

Antes de continuar con el tutorial, asegúrese de tener lo siguiente:

- Conocimientos básicos del lenguaje de programación C#.
- Aspose.PDF para la biblioteca .NET instalada. Puede obtenerlo del sitio web de Aspose o utilizar NuGet para instalarlo en su proyecto.

## Paso 1: configurar el proyecto

Comience creando un nuevo proyecto C# en su entorno de desarrollo integrado (IDE) preferido y agregue una referencia a la biblioteca Aspose.PDF para .NET.

## Paso 2: importar los espacios de nombres necesarios

Agregue las siguientes directivas de uso al principio de su archivo C# para importar los espacios de nombres requeridos:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
```

## Paso 3: establezca la ruta al directorio de documentos

 Establezca la ruta a su directorio de documentos usando el`dataDir` variable:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

## Paso 4: cargue el documento PDF

 Cargue el documento PDF usando el`Document` clase:

```csharp
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 Reemplazar`"SearchAndGetTextFromAll.pdf"` con el nombre real de su archivo PDF.

## Paso 5: crear un TextFragmentAbsorber

 Crear un`TextFragmentAbsorber` objeto para encontrar todas las instancias de la frase de búsqueda de entrada:

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

 Reemplazar`@"[\S]+"` con el patrón de expresión regular que desee.

## Paso 6: habilite la búsqueda de expresiones regulares

 Habilite la búsqueda de expresiones regulares configurando el`TextSearchOptions` propiedad del absorbente:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

## Paso 7: buscar en todas las páginas

Acepta el absorbente para todas las páginas del documento:

```csharp
document.Pages.Accept(textAbsorber);
```

## Paso 8: dibuja un rectángulo alrededor del texto encontrado

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

## Paso 9: guarde el documento modificado

Guarde el documento modificado:

```csharp
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
```

 Asegúrate de reemplazar`"SearchTextAndDrawRectangle_out.pdf"` con el nombre del archivo de salida deseado.

### Código fuente de muestra para buscar texto y dibujar rectángulo usando Aspose.PDF para .NET 
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

¡Felicidades! Ha aprendido con éxito cómo buscar texto específico en un documento PDF, dibujar un rectángulo alrededor del texto encontrado y guardar el documento modificado usando Aspose.PDF para .NET. Este tutorial proporciona una guía paso a paso, desde la configuración del proyecto hasta la realización de las acciones necesarias. Ahora puede incorporar este código en sus propios proyectos de C# para manipular texto y dibujar rectángulos en archivos PDF.

### Preguntas frecuentes

#### P: ¿Cuál es el propósito del tutorial "Buscar texto y dibujar rectángulo"?

R: El tutorial "Buscar texto y dibujar rectángulo" tiene como objetivo guiar a los usuarios a través del proceso de uso de la biblioteca Aspose.PDF para .NET para buscar texto específico dentro de un documento PDF, dibujar rectángulos alrededor de los segmentos de texto encontrados y guardar el texto modificado. documento. El tutorial proporciona instrucciones detalladas y ejemplos de código C# para ilustrar cada paso del proceso.

#### P: ¿Cómo ayuda este tutorial a dibujar rectángulos alrededor de un texto específico en un documento PDF?

R: Este tutorial proporciona una guía completa sobre cómo ubicar y dibujar rectángulos alrededor de segmentos de texto específicos dentro de un documento PDF. Demuestra el proceso de configurar un proyecto, cargar un documento PDF, habilitar la búsqueda de expresiones regulares, dibujar rectángulos alrededor de segmentos de texto encontrados y guardar el PDF modificado.

#### P: ¿Qué requisitos previos se requieren para seguir este tutorial?

R: Antes de comenzar el tutorial, debes tener un conocimiento básico del lenguaje de programación C#. Además, debe tener instalada la biblioteca Aspose.PDF para .NET. Puede obtenerlo del sitio web de Aspose o instalarlo en su proyecto usando NuGet.

#### P: ¿Cómo configuro mi proyecto para seguir este tutorial?

R: Comience creando un nuevo proyecto de C# en su entorno de desarrollo integrado (IDE) preferido. Luego, agregue una referencia a la biblioteca Aspose.PDF para .NET a su proyecto. Esto le permitirá utilizar la funcionalidad de la biblioteca para manipular documentos PDF.

#### P: ¿Puedo dibujar rectángulos alrededor de un texto específico usando este tutorial?

R: Sí, el tutorial se centra en dibujar rectángulos alrededor de segmentos de texto específicos dentro de un documento PDF. Demuestra cómo ubicar el texto deseado usando expresiones regulares, crear rectángulos alrededor de los segmentos de texto identificados y guardar el PDF modificado.

#### P: ¿Cómo puedo especificar el texto que quiero buscar y dibujar rectángulos alrededor de él?

 R: Para especificar el texto que desea buscar y dibujar rectángulos alrededor, cree un`TextFragmentAbsorber` objeto y establecer su patrón usando el`Text` parámetro. Reemplazar el patrón predeterminado`@"[\S]+"` en el código del tutorial con el patrón de expresión regular que desee.

#### P: ¿Cómo habilito la búsqueda de texto con expresiones regulares?

 R: La búsqueda de expresiones regulares se habilita creando un`TextSearchOptions` objeto y estableciendo su valor en`true` . Asigne este objeto al`TextSearchOptions` propiedad de la`TextFragmentAbsorber` instancia. Esto garantiza que se utilice el patrón de expresión regular durante la búsqueda de texto.

#### P: ¿Cómo dibujo rectángulos alrededor del texto encontrado?

 R: Después de identificar los segmentos de texto usando el`TextFragmentAbsorber` , el tutorial proporciona un bucle para recorrer estos segmentos. Para cada segmento de texto, el tutorial demuestra cómo crear un rectángulo alrededor de él usando el`DrawBox` método y especificar la apariencia del rectángulo.

#### P: ¿Cuáles son los pasos para guardar el PDF modificado con rectángulos dibujados?

R: Después de dibujar rectángulos alrededor de los segmentos de texto deseados, use el`Document` clase`Save` Método para guardar el documento modificado. El código de muestra del tutorial muestra cómo guardar el PDF editado y mostrar un mensaje de éxito.

#### P: ¿Puedo personalizar la apariencia de los rectángulos dibujados?

 R: Sí, puedes personalizar la apariencia de los rectángulos dibujados. En el código de muestra del tutorial, el`DrawBox` El método se utiliza para crear rectángulos. Puede modificar propiedades como el color, el estilo y el grosor para personalizar la apariencia de los rectángulos dibujados.