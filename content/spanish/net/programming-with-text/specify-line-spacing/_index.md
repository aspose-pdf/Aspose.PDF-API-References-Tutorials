---
title: Especificar el interlineado en un archivo PDF
linktitle: Especificar el interlineado en un archivo PDF
second_title: Aspose.PDF para referencia de API .NET
description: Aprenda a especificar el interlineado en un archivo PDF usando Aspose.PDF para .NET.
type: docs
weight: 510
url: /es/net/programming-with-text/specify-line-spacing/
---
Este tutorial explica cómo especificar el interlineado en un archivo PDF usando Aspose.PDF para .NET. El código fuente de C# proporcionado demuestra el proceso paso a paso.

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
using System.IO;
```

## Paso 3: establezca la ruta al directorio de documentos

 Establezca la ruta a su directorio de documentos usando el`dataDir` variable:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

## Paso 4: cargue el archivo PDF de entrada

 Cargue el archivo PDF de entrada usando el`Document` clase:

```csharp
Document doc = new Document();
```

## Paso 5: crear opciones de formato de texto

 Crear un`TextFormattingOptions` objeto y establezca el modo de interlineado en`FullSize`:

```csharp
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
```

## Paso 6: crea un fragmento de texto

 Crear un`TextFragment` objeto y especifique el contenido del texto:

```csharp
TextFragment textFragment = new TextFragment("Hello world");
```

## Paso 7: cargue el archivo de fuente (opcional)

 Si desea utilizar una fuente específica para el texto, cargue el archivo de fuente TrueType en un`FileStream` objeto:

```csharp
string fontFile = dataDir + "HPSimplified.TTF";
using (FileStream fontStream = File.OpenRead(fontFile))
{
    textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
}
```

 Reemplazar`"HPSimplified.TTF"` con el nombre del archivo de fuente real.

## Paso 8: especifique la posición del texto y el interlineado

 Establezca la posición del fragmento de texto y asigne el`TextFormattingOptions` hacia`TextState.FormattingOptions` propiedad:

```csharp
textFragment.Position = new Position(100, 600);
textFragment.TextState.FormattingOptions = formattingOptions;
```

## Paso 9: agregue el texto al documento

 Agregue el fragmento de texto al documento, ya sea agregándolo a un`TextBuilder` o directamente a una página`Paragraphs` recopilación:

```csharp
var page = doc.Pages.Add();
page.Paragraphs.Add(textFragment);
```

## Paso 10: guarde el documento PDF resultante

Guarde el documento PDF modificado:

```csharp
dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
doc.Save(dataDir);
```

 Asegúrate de reemplazar`"SpecifyLineSpacing_out.pdf"` con el nombre del archivo de salida deseado.

### Código fuente de muestra para especificar el interlineado usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string fontFile = dataDir + "HPSimplified.TTF";
// Cargar archivo PDF de entrada
Document doc = new Document();
//Crear TextFormattingOptions con LineSpacingMode.FullSize
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
// Crear un objeto de creación de texto para la primera página del documento
//TextBuilder textBuilder = nuevo TextBuilder(doc.Pages[1]);
// Crear fragmento de texto con cadena de muestra
TextFragment textFragment = new TextFragment("Hello world");
if (fontFile != "")
{
	// Cargue la fuente TrueType en el objeto de secuencia
	using (FileStream fontStream = System.IO.File.OpenRead(fontFile))
	{
		//Establecer el nombre de fuente para la cadena de texto
		textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
		// Especificar la posición del fragmento de texto
		textFragment.Position = new Position(100, 600);
		//Establezca TextFormattingOptions del fragmento actual en predefinido (que apunta a LineSpacingMode.FullSize)
		textFragment.TextState.FormattingOptions = formattingOptions;
		// Agregue el texto a TextBuilder para que pueda colocarse sobre el archivo PDF
		//textBuilder.AppendText(textFragment);
		var page = doc.Pages.Add();
		page.Paragraphs.Add(textFragment);
	}
	dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
	// Guarde el documento PDF resultante
	doc.Save(dataDir);
}
```

## Conclusión

¡Felicidades! Ha aprendido con éxito cómo especificar el interlineado en un documento PDF usando Aspose.PDF para .NET. Este tutorial proporciona una guía paso a paso, desde configurar el proyecto hasta guardar el documento modificado. Ahora puede incorporar este código en sus propios proyectos de C# para personalizar el interlineado del texto en archivos PDF.

### Preguntas frecuentes

#### P: ¿Cuál es el propósito del tutorial "Especificar el interlineado en un archivo PDF"?

R: El tutorial "Especificar el interlineado en un archivo PDF" tiene como objetivo guiar a los usuarios sobre cómo utilizar la biblioteca Aspose.PDF para .NET para personalizar el interlineado del texto dentro de un documento PDF. El tutorial proporciona instrucciones paso a paso y ejemplos de código C# para demostrar el proceso.

#### P: ¿Cómo ayuda este tutorial a especificar el interlineado dentro de un documento PDF?

R: Este tutorial ayuda a los usuarios a comprender cómo utilizar las capacidades de Aspose.PDF para .NET para especificar el interlineado del texto en un documento PDF. Siguiendo los pasos proporcionados y los ejemplos de código, los usuarios pueden ajustar el interlineado según sus preferencias.

#### P: ¿Qué requisitos previos se requieren para seguir este tutorial?

R: Antes de comenzar el tutorial, debes tener un conocimiento básico del lenguaje de programación C#. Además, debe tener instalada la biblioteca Aspose.PDF para .NET. Puede obtenerlo del sitio web de Aspose o instalarlo en su proyecto usando NuGet.

#### P: ¿Cómo configuro mi proyecto para seguir este tutorial?

R: Para comenzar, cree un nuevo proyecto de C# en su entorno de desarrollo integrado (IDE) preferido y agregue una referencia a la biblioteca Aspose.PDF para .NET. Esto le permite aprovechar las funciones de la biblioteca para trabajar con documentos PDF y personalizar el interlineado.

#### P: ¿Puedo utilizar este tutorial para especificar el interlineado para cualquier tipo de texto?

R: Sí, este tutorial proporciona instrucciones sobre cómo especificar el interlineado para cualquier contenido de texto dentro de un documento PDF usando Aspose.PDF para .NET. Puede utilizar los ejemplos de código proporcionados para ajustar el interlineado del texto según sus necesidades.

#### P: ¿Cómo especifico el modo de interlineado en el tutorial?

 R: El tutorial muestra cómo crear un`TextFormattingOptions` objeto y establecer su`LineSpacing` propiedad a`TextFormattingOptions.LineSpacingMode.FullSize`. Este modo especifica el interlineado completo para el contenido del texto.

#### P: ¿Cómo puedo cargar una fuente específica para el texto?

 R: Si desea utilizar una fuente específica para el contenido del texto, el tutorial proporciona orientación sobre cómo cargar un archivo de fuente TrueType en un`FileStream` objeto y configúrelo como fuente para el`TextFragment`. Esto le permite personalizar la fuente del texto junto con su interlineado.

#### P: ¿Cómo personalizo la posición del texto dentro del documento PDF?

 R: Para personalizar la posición del texto, cree un`TextFragment` objeto y establecer su`Position`propiedad a las coordenadas deseadas (X e Y). Esto le permite controlar dónde se coloca el texto dentro del documento PDF.

#### P: ¿Puedo aplicar estas modificaciones de interlineado a documentos PDF existentes?

 R: Sí, puede modificar el interlineado del texto en documentos PDF existentes. El tutorial muestra cómo crear un`TextFragment` con el espacio entre líneas y la posición especificados y luego agréguelo al archivo de una página.`Paragraphs` recopilación.