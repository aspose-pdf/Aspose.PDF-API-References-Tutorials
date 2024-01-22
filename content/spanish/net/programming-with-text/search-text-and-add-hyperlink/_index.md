---
title: Buscar texto y agregar hipervínculo
linktitle: Buscar texto y agregar hipervínculo
second_title: Aspose.PDF para referencia de API .NET
description: Aprenda a buscar texto en un PDF, agregar hipervínculos al texto encontrado y guardar el documento modificado usando Aspose.PDF para .NET.
type: docs
weight: 450
url: /es/net/programming-with-text/search-text-and-add-hyperlink/
---
Este tutorial explica cómo usar Aspose.PDF para .NET para buscar texto específico en un documento PDF, agregar un hipervínculo al texto encontrado y guardar el documento modificado. El código fuente de C# proporcionado demuestra el proceso paso a paso.

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
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Text;
```

## Paso 3: establezca la ruta al directorio de documentos

 Establezca la ruta a su directorio de documentos usando el`dataDir` variable:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

## Paso 4: crear un TextFragmentAbsorber

 Crear un`TextFragmentAbsorber` objeto para encontrar todas las instancias de la frase de búsqueda de entrada:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
```

 Reemplazar`"\\d{4}-\\d{4}"` con el patrón de expresión regular que desee.

## Paso 5: habilite la búsqueda de expresiones regulares

 Habilite la búsqueda de expresiones regulares configurando el`TextSearchOptions` propiedad del absorbente:

```csharp
absorber.TextSearchOptions = new TextSearchOptions(true);
```

## Paso 6: abra y vincule el documento PDF

 Crear un`PdfContentEditor` objeto y vincularlo al archivo PDF de origen:

```csharp
PdfContentEditor editor = new PdfContentEditor();
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
```

 Reemplazar`"SearchRegularExpressionPage.pdf"` con el nombre real de su archivo PDF.

## Paso 7: acepte el absorbente de la página

Acepte el absorbente para la página deseada del documento:

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
    // Crea un rectángulo basado en la posición del fragmento de texto.
    System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
        (int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
        (int)Math.Round(textFragment.Rectangle.Height + 1));
    //Agregue un enlace web al rectángulo
    editor.CreateWebLink(rect, "http://www.aspose.com", 1, Sistema.Dibujo.Color.Azul);
}
```

 Reemplazar`"http://www.aspose.com"` con la URL del hipervínculo deseada.

## Paso 9: guarde y cierre el documento modificado

Guarde el documento modificado y cierre el editor:

```csharp
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

 Asegúrate de reemplazar`"SearchTextAndAddHyperlink_out.pdf"` con el nombre del archivo de salida deseado.

### Código fuente de muestra para buscar texto y agregar hipervínculo usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Cree un objeto absorbente para encontrar todas las instancias de la frase de búsqueda de entrada.
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
// Habilitar la búsqueda de expresiones regulares
absorber.TextSearchOptions = new TextSearchOptions(true);
// Abrir documento
PdfContentEditor editor = new PdfContentEditor();
// Vincular archivo PDF de origen
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
// Aceptar el absorbente de la página.
editor.Document.Pages[1].Accept(absorber);
int[] dashArray = { };
String[] LEArray = { };
System.Drawing.Color blue = System.Drawing.Color.Blue;
// Recorre los fragmentos
foreach (TextFragment textFragment in absorber.TextFragments)
{
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
		(int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
		(int)Math.Round(textFragment.Rectangle.Height + 1));
	Enum[] actionName = new Enum[2] { Aspose.Pdf.Annotations.PredefinedAction.Document_AttachFile, Aspose.Pdf.Annotations.PredefinedAction.Document_ExtractPages };
	editor.CreateWebLink(rect, "http:// Www.aspose.com", 1, azul, nombreAcción);
	editor.CreateLine(rect, "", (float)textFragment.Rectangle.LLX + 1, (float)textFragment.Rectangle.LLY - 1,
		(float)textFragment.Rectangle.URX, (float)textFragment.Rectangle.LLY - 1, 1, 1, blue, "S", dashArray, LEArray);
}
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

## Conclusión

¡Felicidades! Ha aprendido con éxito cómo buscar texto específico en un documento PDF, agregar hipervínculos al texto encontrado y guardar el documento modificado usando Aspose.PDF para .NET. Este tutorial proporciona una guía paso a paso, desde la configuración del proyecto hasta la realización de las acciones necesarias. Ahora puede incorporar este código en sus propios proyectos de C# para manipular texto y agregar hipervínculos en archivos PDF.

### Preguntas frecuentes

#### P: ¿Cuál es el propósito del tutorial "Buscar texto y agregar hipervínculo"?

R: El tutorial "Buscar texto y agregar hipervínculo" tiene como objetivo demostrar cómo usar la biblioteca Aspose.PDF para .NET para buscar texto específico dentro de un documento PDF, agregar hipervínculos al texto encontrado y luego guardar el documento modificado. El tutorial proporciona una guía completa y ejemplos de código C# para ilustrar el proceso paso a paso.

#### P: ¿Cómo ayuda este tutorial a agregar hipervínculos a texto específico en un documento PDF?

R: Este tutorial lo guía a través del proceso de uso de la biblioteca Aspose.PDF para ubicar texto específico en un documento PDF, aplicar un hipervínculo al texto identificado y guardar el PDF modificado. Cubre pasos esenciales como configurar el proyecto, cargar el documento, habilitar la búsqueda de expresiones regulares y agregar hipervínculos al texto encontrado.

#### P: ¿Qué requisitos previos se necesitan para seguir este tutorial?

R: Antes de comenzar, debes tener un conocimiento básico del lenguaje de programación C#. Además, debe tener instalada la biblioteca Aspose.PDF para .NET, que puede obtenerse en el sitio web de Aspose o instalarse usando NuGet en su proyecto.

#### P: ¿Cómo configuro mi proyecto para seguir este tutorial?

R: Comience creando un nuevo proyecto de C# en su entorno de desarrollo integrado (IDE) preferido. Luego, agregue una referencia a la biblioteca Aspose.PDF para .NET, que le permitirá utilizar las capacidades de la biblioteca en su proyecto.

#### P: ¿Puedo agregar hipervínculos a texto específico usando este tutorial?

R: Sí, este tutorial se centra específicamente en agregar hipervínculos a texto específico en un documento PDF. Demuestra cómo encontrar y extraer el texto deseado usando expresiones regulares, crear hipervínculos asociados con los fragmentos de texto y guardar el PDF modificado.

#### P: ¿Cómo defino el texto que quiero buscar y al que agrego un hipervínculo?

 R: Para especificar el texto que desea buscar y agregarle un hipervínculo, cree un`TextFragmentAbsorber` objeto y establecer su patrón usando el`Text` parámetro. Reemplazar el patrón predeterminado`"\\d{4}-\\d{4}"` en el código del tutorial con el patrón de expresión regular que desee.

#### P: ¿Cómo puedo habilitar la búsqueda de texto con expresiones regulares?

 R: La búsqueda de expresiones regulares se habilita creando un`TextSearchOptions` objeto y estableciendo su valor en`true` . Asigne este objeto al`TextSearchOptions` propiedad de la`TextFragmentAbsorber` instancia. Esto garantiza que se aplique el patrón de expresión regular durante la búsqueda de texto.

#### P: ¿Cómo agrego hipervínculos al texto encontrado?

 R: Después de identificar los fragmentos de texto usando el`TextFragmentAbsorber` , el tutorial proporciona un bucle para recorrer estos fragmentos. Para cada fragmento de texto, el tutorial demuestra cómo configurar el color del texto en azul y crear un hipervínculo usando el`CreateWebLink` método.

#### P: ¿Cuáles son los pasos para guardar el PDF modificado con hipervínculos?

 R: Después de agregar hipervínculos a los fragmentos de texto deseados, use el`PdfContentEditor` clase para guardar el documento modificado. El código de muestra del tutorial muestra cómo guardar el PDF editado, cerrar el editor y mostrar un mensaje de éxito.