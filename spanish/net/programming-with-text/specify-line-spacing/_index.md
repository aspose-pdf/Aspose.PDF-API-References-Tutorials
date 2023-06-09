---
title: Especificar interlineado
linktitle: Especificar interlineado
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a especificar el espacio entre líneas en un documento PDF con Aspose.PDF para .NET.
type: docs
weight: 510
url: /es/net/programming-with-text/specify-line-spacing/
---

Este tutorial explica cómo especificar el espacio entre líneas en un documento PDF utilizando Aspose.PDF para .NET. El código fuente de C# proporcionado demuestra el proceso paso a paso.

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
using System.IO;
```

## Paso 3: establezca la ruta al directorio del documento

 Establezca la ruta a su directorio de documentos usando el`dataDir` variable:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

## Paso 4: Cargue el archivo PDF de entrada

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

## Paso 7: Cargue el archivo de fuente (opcional)

 Si desea utilizar una fuente específica para el texto, cargue el archivo de fuente TrueType en un`FileStream` objeto:

```csharp
string fontFile = dataDir + "HPSimplified.TTF";
using (FileStream fontStream = File.OpenRead(fontFile))
{
    textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
}
```

 Reemplazar`"HPSimplified.TTF"`con el nombre de archivo de fuente real.

## Paso 8: especifique la posición del texto y el espacio entre líneas

 Establezca la posición para el fragmento de texto y asigne el`TextFormattingOptions` hacia`TextState.FormattingOptions` propiedad:

```csharp
textFragment.Position = new Position(100, 600);
textFragment.TextState.FormattingOptions = formattingOptions;
```

## Paso 9: Agrega el texto al documento

 Agregue el fragmento de texto al documento, ya sea anexándolo a un`TextBuilder` o directamente a una página`Paragraphs` recopilación:

```csharp
var page = doc.Pages.Add();
page.Paragraphs.Add(textFragment);
```

## Paso 10: Guarde el documento PDF resultante

Guarde el documento PDF modificado:

```csharp
dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
doc.Save(dataDir);
```

 Asegúrese de reemplazar`"SpecifyLineSpacing_out.pdf"` con el nombre de archivo de salida deseado.

### Ejemplo de código fuente para Especificar espaciado entre líneas usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string fontFile = dataDir + "HPSimplified.TTF";
// Cargar archivo PDF de entrada
Document doc = new Document();
//Crear TextFormattingOptions con LineSpacingMode.FullSize
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
// Crear un objeto generador de texto para la primera página del documento
//TextBuilder textBuilder = new TextBuilder(doc.Pages[1]);
// Crear fragmento de texto con cadena de muestra
TextFragment textFragment = new TextFragment("Hello world");
if (fontFile != "")
{
	// Cargue la fuente TrueType en el objeto de flujo
	using (FileStream fontStream = System.IO.File.OpenRead(fontFile))
	{
		// Establecer el nombre de la fuente para la cadena de texto
		textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
		// Especificar la posición del fragmento de texto
		textFragment.Position = new Position(100, 600);
		//Establezca TextFormattingOptions del fragmento actual en predefinido (que apunta a LineSpacingMode.FullSize)
		textFragment.TextState.FormattingOptions = formattingOptions;
		// Agregue el texto a TextBuilder para que pueda colocarse sobre el archivo PDF
		//textBuilder.AppendText(fragmento de texto);
		var page = doc.Pages.Add();
		page.Paragraphs.Add(textFragment);
	}
	dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
	// Guardar el documento PDF resultante
	doc.Save(dataDir);
}
```

## Conclusión

¡Felicidades! Ha aprendido con éxito cómo especificar el espacio entre líneas en un documento PDF utilizando Aspose.PDF para .NET. Este tutorial proporcionó una guía paso a paso, desde configurar el proyecto hasta guardar el documento modificado. Ahora puede incorporar este código en sus propios proyectos de C# para personalizar el espacio entre líneas del texto en archivos PDF.