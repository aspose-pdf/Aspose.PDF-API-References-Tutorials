---
title: Representación de símbolos reemplazables
linktitle: Representación de símbolos reemplazables
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a representar símbolos reemplazables en un documento PDF utilizando Aspose.PDF para .NET.
type: docs
weight: 310
url: /es/net/programming-with-text/rendering-replaceable-symbols/
---

En este tutorial, explicaremos cómo representar símbolos reemplazables en un documento PDF utilizando la biblioteca Aspose.PDF para .NET. Pasaremos por el proceso paso a paso de crear un PDF, agregar un fragmento de texto con marcadores de nueva línea, configurar las propiedades del texto, colocar el texto y guardar el PDF usando el código fuente de C# provisto.

## requisitos previos

Antes de comenzar, asegúrese de tener lo siguiente:

- La biblioteca Aspose.PDF para .NET instalada.
- Conocimientos básicos de programación en C#.

## Paso 1: configurar el directorio de documentos

 Primero, debe establecer la ruta al directorio donde desea guardar el archivo PDF generado. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el`dataDir` variable con la ruta a su directorio deseado.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Cree un documento PDF y una página

 A continuación, creamos un nuevo documento PDF y le agregamos una página usando el`Document` clase y`Page` clase de la biblioteca Aspose.PDF.

```csharp
Aspose.Pdf.Document pdfApplicationDoc = new Aspose.Pdf.Document();
Aspose.Pdf.Page applicationFirstPage = (Aspose.Pdf.Page)pdfApplicationDoc.Pages.Add();
```

## Paso 3: Agregar fragmento de texto con marcadores de nueva línea

 Creamos un`TextFragment` objeto y establecer su texto para incluir marcadores de nueva línea (`Environment.NewLine`) para representar varias líneas de texto.

```csharp
Aspose.Pdf.Text.TextFragment textFragment = new Aspose.Pdf.Text.TextFragment("Applicant Name: " + Environment.NewLine + " Joe Smoe");
```

## Paso 4: establecer las propiedades del fragmento de texto

Podemos establecer varias propiedades para el fragmento de texto si lo desea, como el tamaño de fuente, la fuente, el color de fondo y el color de primer plano.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
```

## Paso 5: Crear párrafo de texto y posición

 Creamos un`TextParagraph` agregar el fragmento de texto al párrafo y establecer la posición del párrafo en la página.

```csharp
TextParagraph par = new TextParagraph();
par.AppendLine(textFragment);
par.Position = new Aspose.Pdf.Text.Position(100, 600);
```

## Paso 6: agregue un párrafo de texto a la página

 Creamos un`TextBuilder`objeto con la página y agregue el párrafo de texto al generador de texto.

```csharp
TextBuilder textBuilder = new TextBuilder(applicationFirstPage);
textBuilder.AppendParagraph(par);
```

## Paso 7: Guarde el documento PDF

Finalmente, guardamos el documento PDF en el archivo de salida especificado.

```csharp
dataDir = dataDir + "RenderingReplaceableSymbols_out.pdf";
pdfApplicationDoc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols rendered successfully during PDF creation.\nFile saved at " + dataDir);
```

### Ejemplo de código fuente para renderizar símbolos reemplazables usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document pdfApplicationDoc = new Aspose.Pdf.Document();
Aspose.Pdf.Page applicationFirstPage = (Aspose.Pdf.Page)pdfApplicationDoc.Pages.Add();
// Inicialice el nuevo TextFragment con texto que contenga los marcadores de nueva línea requeridos
Aspose.Pdf.Text.TextFragment textFragment = new Aspose.Pdf.Text.TextFragment("Applicant Name: " + Environment.NewLine + " Joe Smoe");
// Establezca las propiedades del fragmento de texto si es necesario
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// Crear objeto TextParagraph
TextParagraph par = new TextParagraph();
// Agregar nuevo TextFragment al párrafo
par.AppendLine(textFragment);
// Establecer la posición del párrafo
par.Position = new Aspose.Pdf.Text.Position(100, 600);
// Crear objeto TextBuilder
TextBuilder textBuilder = new TextBuilder(applicationFirstPage);
// Agregue TextParagraph usando TextBuilder
textBuilder.AppendParagraph(par);
dataDir = dataDir + "RenderingReplaceableSymbols_out.pdf";
pdfApplicationDoc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols render successfully duing pdf creation.\nFile saved at " + dataDir);
```

## Conclusión

En este tutorial, aprendió cómo representar símbolos reemplazables en un documento PDF utilizando la biblioteca Aspose.PDF para .NET. Siguiendo la guía paso a paso y ejecutando el código C# provisto, puede crear un PDF, agregar texto con marcadores de nueva línea, establecer propiedades de texto, colocar el texto en la página y guardar el PDF.