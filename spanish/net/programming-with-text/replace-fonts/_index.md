---
title: Reemplazar fuentes
linktitle: Reemplazar fuentes
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a reemplazar fuentes en un documento PDF usando Aspose.PDF para .NET.
type: docs
weight: 340
url: /es/net/programming-with-text/replace-fonts/
---

En este tutorial, explicaremos cómo reemplazar fuentes específicas en un documento PDF utilizando la biblioteca Aspose.PDF para .NET. Pasaremos por el proceso paso a paso de cargar un documento PDF, buscar fragmentos de texto, identificar las fuentes para reemplazar, reemplazar las fuentes y guardar el PDF modificado usando el código fuente de C# provisto.

## requisitos previos

Antes de comenzar, asegúrese de tener lo siguiente:

- La biblioteca Aspose.PDF para .NET instalada.
- Conocimientos básicos de programación en C#.

## Paso 1: configurar el directorio de documentos

 Primero, debe establecer la ruta al directorio donde tiene el archivo PDF de entrada. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el`dataDir` variable con la ruta a su archivo PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Cargue el documento PDF

 A continuación, cargamos el documento PDF usando el`Document` clase de la biblioteca Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
```

## Paso 3: Buscar y reemplazar fuentes

 Creamos un`TextFragmentAbsorber` objeto y configure la opción de edición para eliminar las fuentes no utilizadas. Luego, aceptamos el absorbedor de todas las páginas del documento PDF para buscar fragmentos de texto.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
pdfDocument.Pages.Accept(absorber);
```

## Paso 4: reemplazar fuentes

Recorremos todos los fragmentos de texto identificados por el absorbedor. Si el nombre de la fuente de un fragmento de texto coincide con la fuente que desea reemplazar, la reemplazamos con la nueva fuente.

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    if (textFragment.TextState.Font.FontName == "Arial,Bold")
    {
        textFragment.TextState.Font = FontRepository.FindFont("Arial");
    }
}
```

## Paso 5: Guarde el PDF modificado

Finalmente, guardamos el documento PDF modificado en el archivo de salida especificado.

```csharp
dataDir = dataDir + "ReplaceFonts_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nFonts replaced successfully in the PDF document.\nFile saved at " + dataDir);
```

### Ejemplo de código fuente para Reemplazar fuentes usando Aspose.PDF para .NET 
```csharp
try
{
	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Cargar archivo PDF de origen
	Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
	// Busque fragmentos de texto y configure la opción de edición como eliminar fuentes no utilizadas
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	// Aceptar el absorbedor para todas las páginas.
	pdfDocument.Pages.Accept(absorber);
	//Atraviesa todos los TextFragments
	foreach (TextFragment textFragment in absorber.TextFragments)
	{
		// Si el nombre de la fuente es ArialMT, reemplace el nombre de la fuente con Arial
		if (textFragment.TextState.Font.FontName == "Arial,Bold")
		{
			textFragment.TextState.Font = FontRepository.FindFont("Arial");
		}
	}
	dataDir = dataDir + "ReplaceFonts_out.pdf";
	// Guardar documento actualizado
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nFonts replaced successfully in pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.");
}
```

## Conclusión

En este tutorial, aprendió a reemplazar fuentes específicas en un documento PDF utilizando la biblioteca Aspose.PDF para .NET. Siguiendo la guía paso a paso y ejecutando el código C# provisto, puede cargar un documento PDF, buscar fragmentos de texto, identificar y reemplazar fuentes específicas y guardar el PDF modificado.