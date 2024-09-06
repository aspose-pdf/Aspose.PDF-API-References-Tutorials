---
title: Buscar texto y agregar hipervínculo
linktitle: Buscar texto y agregar hipervínculo
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a buscar texto en un PDF, agregar hipervínculos al texto encontrado y guardar el documento modificado usando Aspose.PDF para .NET.
type: docs
weight: 450
url: /es/net/programming-with-text/search-text-and-add-hyperlink/
---
Este tutorial explica cómo utilizar Aspose.PDF para .NET para buscar texto específico en un documento PDF, agregar un hipervínculo al texto encontrado y guardar el documento modificado. El código fuente de C# proporcionado muestra el proceso paso a paso.

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
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Text;
```

## Paso 3: Establezca la ruta al directorio del documento

 Establezca la ruta a su directorio de documentos utilizando el`dataDir` variable:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

## Paso 4: Crear un TextFragmentAbsorber

 Crear un`TextFragmentAbsorber` objeto para encontrar todas las instancias de la frase de búsqueda ingresada:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
```

 Reemplazar`"\\d{4}-\\d{4}"` con el patrón de expresión regular deseado.

## Paso 5: Habilitar la búsqueda de expresiones regulares

 Habilite la búsqueda de expresiones regulares configurando la`TextSearchOptions` Propiedad del absorbedor:

```csharp
absorber.TextSearchOptions = new TextSearchOptions(true);
```

## Paso 6: Abra y encuaderne el documento PDF

 Crear un`PdfContentEditor` objeto y vincularlo al archivo PDF de origen:

```csharp
PdfContentEditor editor = new PdfContentEditor();
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
```

 Reemplazar`"SearchRegularExpressionPage.pdf"` con el nombre real de su archivo PDF.

## Paso 7: Acepte el absorbente para la página.

Acepte el absorbedor para la página deseada del documento:

```csharp
editor.Document.Pages[1].Accept(absorber);
```

 Reemplazar`1` con el número de página deseado.

## Paso 8: Agregar hipervínculos al texto encontrado

Recorrer los fragmentos de texto recuperados y agregarles hipervínculos:

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
    // Crea un rectángulo basado en la posición del fragmento de texto.
    System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
        (int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
        (int)Math.Round(textFragment.Rectangle.Height + 1));
    //Añadir un enlace web al rectángulo
    editor.CreateWebLink(rect, "http://www.aspose.com", 1, Sistema.Dibujo.Color.Azul);
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

 Asegúrese de reemplazar`"SearchTextAndAddHyperlink_out.pdf"` con el nombre del archivo de salida deseado.

### Código fuente de muestra para buscar texto y agregar hipervínculos con Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crear un objeto absorbente para encontrar todas las instancias de la frase de búsqueda de entrada
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
// Habilitar la búsqueda de expresiones regulares
absorber.TextSearchOptions = new TextSearchOptions(true);
// Abrir documento
PdfContentEditor editor = new PdfContentEditor();
// Enlazar archivo PDF de origen
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
// Acepta el absorbedor para la página.
editor.Document.Pages[1].Accept(absorber);
int[] dashArray = { };
String[] LEArray = { };
System.Drawing.Color blue = System.Drawing.Color.Blue;
// Recorrer los fragmentos
foreach (TextFragment textFragment in absorber.TextFragments)
{
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
		(int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
		(int)Math.Round(textFragment.Rectangle.Height + 1));
	Enum[] actionName = new Enum[2] { Aspose.Pdf.Annotations.PredefinedAction.Document_AttachFile, Aspose.Pdf.Annotations.PredefinedAction.Document_ExtractPages };
	editor.CreateWebLink(rect, "http:// Www.aspose.com", 1, azul, nombreDeAcción);
	editor.CreateLine(rect, "", (float)textFragment.Rectangle.LLX + 1, (float)textFragment.Rectangle.LLY - 1,
		(float)textFragment.Rectangle.URX, (float)textFragment.Rectangle.LLY - 1, 1, 1, blue, "S", dashArray, LEArray);
}
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

## Conclusión

¡Felicitaciones! Aprendió a buscar texto específico en un documento PDF, agregar hipervínculos al texto encontrado y guardar el documento modificado utilizando Aspose.PDF para .NET. Este tutorial le proporcionó una guía paso a paso, desde la configuración del proyecto hasta la realización de las acciones necesarias. Ahora puede incorporar este código en sus propios proyectos de C# para manipular texto y agregar hipervínculos en archivos PDF.

### Preguntas frecuentes

#### P: ¿Cuál es el propósito del tutorial “Buscar texto y agregar hipervínculo”?

R: El tutorial "Buscar texto y agregar hipervínculo" tiene como objetivo demostrar cómo utilizar la biblioteca Aspose.PDF para .NET para buscar texto específico dentro de un documento PDF, agregar hipervínculos al texto encontrado y luego guardar el documento modificado. El tutorial proporciona una guía completa y ejemplos de código C# para ilustrar el proceso paso a paso.

#### P: ¿Cómo ayuda este tutorial a agregar hipervínculos a texto específico en un documento PDF?

A: Este tutorial le guiará a través del proceso de uso de la biblioteca Aspose.PDF para localizar texto específico en un documento PDF, aplicar un hipervínculo al texto identificado y guardar el PDF modificado. Abarca pasos esenciales como la configuración del proyecto, la carga del documento, la habilitación de la búsqueda de expresiones regulares y la adición de hipervínculos al texto encontrado.

#### P: ¿Qué requisitos previos se necesitan para seguir este tutorial?

R: Antes de comenzar, debe tener conocimientos básicos del lenguaje de programación C#. Además, debe tener instalada la biblioteca Aspose.PDF para .NET, que puede obtenerse desde el sitio web de Aspose o instalarse mediante NuGet en su proyecto.

#### P: ¿Cómo configuro mi proyecto para seguir este tutorial?

R: Comience por crear un nuevo proyecto de C# en su entorno de desarrollo integrado (IDE) preferido. Luego, agregue una referencia a la biblioteca Aspose.PDF para .NET, que le permitirá utilizar las capacidades de la biblioteca en su proyecto.

#### P: ¿Puedo agregar hipervínculos a un texto específico usando este tutorial?

R: Sí, este tutorial se centra específicamente en cómo agregar hipervínculos a texto específico en un documento PDF. Demuestra cómo buscar y extraer el texto deseado mediante expresiones regulares, crear hipervínculos asociados con los fragmentos de texto y guardar el PDF modificado.

#### P: ¿Cómo defino el texto que quiero buscar y agregarle un hipervínculo?

 A: Para especificar el texto que desea buscar y agregar un hipervínculo, cree un`TextFragmentAbsorber` objeto y establecer su patrón utilizando el`Text` parámetro. Reemplazar el patrón predeterminado`"\\d{4}-\\d{4}"` en el código del tutorial con el patrón de expresión regular deseado.

#### P: ¿Cómo puedo habilitar la búsqueda de expresiones regulares para texto?

 A: La búsqueda de expresiones regulares se habilita mediante la creación de una`TextSearchOptions` objeto y estableciendo su valor en`true` Asignar este objeto a la`TextSearchOptions` propiedad de la`TextFragmentAbsorber` instancia. Esto garantiza que el patrón de expresión regular se aplique durante la búsqueda de texto.

#### P: ¿Cómo puedo agregar hipervínculos al texto encontrado?

 A: Después de identificar los fragmentos de texto utilizando el`TextFragmentAbsorber` , el tutorial proporciona un bucle para iterar a través de estos fragmentos. Para cada fragmento de texto, el tutorial demuestra cómo establecer el color del texto en azul y crear un hipervínculo utilizando el`CreateWebLink` método.

#### P: ¿Cuáles son los pasos para guardar el PDF modificado con hipervínculos?

 A: Después de agregar hipervínculos a los fragmentos de texto deseados, utilice el`PdfContentEditor` Clase para guardar el documento modificado. El código de muestra del tutorial muestra cómo guardar el PDF editado, cerrar el editor y mostrar un mensaje de confirmación.