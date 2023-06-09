---
title: Buscar texto y agregar hipervínculo
linktitle: Buscar texto y agregar hipervínculo
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a buscar texto en un PDF, agregue hipervínculos al texto encontrado y guarde el documento modificado con Aspose.PDF para .NET.
type: docs
weight: 450
url: /es/net/programming-with-text/search-text-and-add-hyperlink/
---

Este tutorial explica cómo usar Aspose.PDF para .NET para buscar texto específico en un documento PDF, agregar un hipervínculo al texto encontrado y guardar el documento modificado. El código fuente de C# proporcionado demuestra el proceso paso a paso.

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
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Text;
```

## Paso 3: establezca la ruta al directorio del documento

 Establezca la ruta a su directorio de documentos usando el`dataDir` variable:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

## Paso 4: Crea un TextFragmentAbsorber

 Crear un`TextFragmentAbsorber` objeto para encontrar todas las instancias de la frase de búsqueda de entrada:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
```

 Reemplazar`"\\d{4}-\\d{4}"` con el patrón de expresión regular deseado.

## Paso 5: habilite la búsqueda de expresiones regulares

Habilite la búsqueda de expresiones regulares configurando el`TextSearchOptions` propiedad del absorbente:

```csharp
absorber.TextSearchOptions = new TextSearchOptions(true);
```

## Paso 6: Abra y encuaderne el documento PDF

 Crear un`PdfContentEditor` objeto y vincúlelo al archivo PDF de origen:

```csharp
PdfContentEditor editor = new PdfContentEditor();
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
```

 Reemplazar`"SearchRegularExpressionPage.pdf"` con el nombre real de su archivo PDF.

## Paso 7: Acepte el absorbedor para la página

Acepte el absorbedor para la página deseada del documento:

```csharp
editor.Document.Pages[1].Accept(absorber);
```

 Reemplazar`1` con el número de página deseado.

## Paso 8: agregue hipervínculos al texto encontrado

Recorra los fragmentos de texto recuperados y agrégueles hipervínculos:

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
    // Crea un rectángulo basado en la posición del fragmento de texto
    System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
        (int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
        (int)Math.Round(textFragment.Rectangle.Height + 1));
    // Agregar un enlace web al rectángulo
    editor.CreateWebLink(rect, "http://www.aspose.com", 1, System.Drawing.Color.Blue);
}
```

 Reemplazar`"http://www.aspose.com"` con la URL del hipervínculo deseado.

## Paso 9: Guarde y cierre el documento modificado

Guarde el documento modificado y cierre el editor:

```csharp
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

 Asegúrese de reemplazar`"SearchTextAndAddHyperlink_out.pdf"` con el nombre de archivo de salida deseado.

### Ejemplo de código fuente para buscar texto y agregar hipervínculo usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Cree un objeto absorbente para encontrar todas las instancias de la frase de búsqueda de entrada
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
// Habilitar la búsqueda de expresiones regulares
absorber.TextSearchOptions = new TextSearchOptions(true);
// Abrir documento
PdfContentEditor editor = new PdfContentEditor();
//Enlazar archivo PDF de origen
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
// Aceptar el absorbedor para la página.
editor.Document.Pages[1].Accept(absorber);
int[] dashArray = { };
String[] LEArray = { };
System.Drawing.Color blue = System.Drawing.Color.Blue;
// Bucle a través de los fragmentos
foreach (TextFragment textFragment in absorber.TextFragments)
{
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
		(int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
		(int)Math.Round(textFragment.Rectangle.Height + 1));
	Enum[] actionName = new Enum[2] { Aspose.Pdf.Annotations.PredefinedAction.Document_AttachFile, Aspose.Pdf.Annotations.PredefinedAction.Document_ExtractPages };
	editor.CreateWebLink(rect, "http:// Www.aspose.com", 1, azul, actionName);
	editor.CreateLine(rect, "", (float)textFragment.Rectangle.LLX + 1, (float)textFragment.Rectangle.LLY - 1,
		(float)textFragment.Rectangle.URX, (float)textFragment.Rectangle.LLY - 1, 1, 1, blue, "S", dashArray, LEArray);
}
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

## Conclusión

¡Felicidades! Ha aprendido con éxito cómo buscar texto específico en un documento PDF, agregar hipervínculos al texto encontrado y guardar el documento modificado usando Aspose.PDF para .NET. Este tutorial proporcionó una guía paso a paso, desde la configuración del proyecto hasta la realización de las acciones requeridas. Ahora puede incorporar este código en sus propios proyectos de C# para manipular texto y agregar hipervínculos en archivos PDF.