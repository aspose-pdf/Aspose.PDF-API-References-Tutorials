---
title: Eliminar fuentes no utilizadas
linktitle: Eliminar fuentes no utilizadas
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a eliminar las fuentes no utilizadas de un documento PDF con Aspose.PDF para .NET.
type: docs
weight: 300
url: /es/net/programming-with-text/remove-unused-fonts/
---

En este tutorial, explicaremos cómo eliminar las fuentes no utilizadas de un documento PDF utilizando la biblioteca Aspose.PDF para .NET. Pasaremos por el proceso paso a paso de cargar un PDF, identificar y eliminar las fuentes no utilizadas y guardar el PDF actualizado usando el código fuente de C# proporcionado.

## Requisitos

Antes de comenzar, asegúrese de tener lo siguiente:

- La biblioteca Aspose.PDF para .NET instalada.
- Conocimientos básicos de programación en C#.

## Paso 1: configurar el directorio de documentos

 Primero, debe establecer la ruta al directorio donde se encuentran sus archivos PDF. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el`dataDir` variable con la ruta a sus archivos PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Cargue el PDF de origen

 A continuación, cargamos el documento PDF de origen usando el`Document` clase de la biblioteca Aspose.PDF.

```csharp
Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
```

## Paso 3: identifique y elimine las fuentes no utilizadas

 Creamos un`TextFragmentAbsorber` objeto con el`TextEditOptions` parámetro establecido en`TextEditOptions.FontReplace.RemoveUnusedFonts` . Esta opción nos permite identificar y eliminar fuentes no utilizadas en el documento PDF. Luego iteramos a través de todos los`TextFragments` y establezca la fuente en la fuente deseada.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
doc.Pages.Accept(absorb);

foreach(TextFragment textFragment in absorber.TextFragments)
{
     textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
}
```

## Paso 4: Guarde el PDF actualizado

Finalmente, guardamos el documento PDF actualizado en el archivo de salida especificado.

```csharp
dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nUnused fonts removed successfully from the PDF document.\nFile saved at " + dataDir);
```

### Ejemplo de código fuente para Eliminar fuentes no utilizadas usando Aspose.PDF para .NET 
```csharp
try
{
	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Cargar archivo PDF de origen
	Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	doc.Pages.Accept(absorber);
	// Iterar a través de todos los TextFragments
	foreach (TextFragment textFragment in absorber.TextFragments)
	{
		textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
	}
	dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
	// Guardar documento actualizado
	doc.Save(dataDir);
	Console.WriteLine("\nUnused fonts removed successfully from pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.");
}
```

## Conclusión

En este tutorial, aprendió cómo eliminar las fuentes no utilizadas de un documento PDF utilizando la biblioteca Aspose.PDF para .NET. Si sigue la guía paso a paso y ejecuta el código C# provisto, puede cargar un PDF, identificar y eliminar fuentes no utilizadas y guardar el PDF actualizado.