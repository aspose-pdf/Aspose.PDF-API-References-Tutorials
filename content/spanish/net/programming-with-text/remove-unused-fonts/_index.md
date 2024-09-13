---
title: Eliminar fuentes no utilizadas en un archivo PDF
linktitle: Eliminar fuentes no utilizadas en un archivo PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a eliminar fuentes no utilizadas en un archivo PDF usando Aspose.PDF para .NET.
type: docs
weight: 300
url: /es/net/programming-with-text/remove-unused-fonts/
---
En este tutorial, explicaremos cómo eliminar fuentes no utilizadas en un archivo PDF mediante la biblioteca Aspose.PDF para .NET. Repasaremos el proceso paso a paso de cargar un PDF, identificar y eliminar fuentes no utilizadas y guardar el PDF actualizado mediante el código fuente de C# proporcionado.

## Requisitos

Antes de comenzar, asegúrese de tener lo siguiente:

- La biblioteca Aspose.PDF para .NET instalada.
- Un conocimiento básico de programación en C#.

## Paso 1: Configurar el directorio de documentos

 Primero, debes establecer la ruta al directorio donde se encuentran tus archivos PDF. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el`dataDir` variable con la ruta a sus archivos PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Cargue el PDF de origen

 A continuación, cargamos el documento PDF de origen utilizando el`Document` clase de la biblioteca Aspose.PDF.

```csharp
Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
```

## Paso 3: Identificar y eliminar fuentes no utilizadas

 Creamos una`TextFragmentAbsorber` objeto con el`TextEditOptions` conjunto de parámetros a`TextEditOptions.FontReplace.RemoveUnusedFonts` Esta opción nos permite identificar y eliminar fuentes no utilizadas en el documento PDF. Luego, iteramos a través de todas las`TextFragments` y configure la fuente a la fuente deseada.

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

### Código fuente de muestra para eliminar fuentes no utilizadas con Aspose.PDF para .NET 
```csharp
try
{
	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Cargar archivo PDF de origen
	Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	doc.Pages.Accept(absorber);
	// Iterar a través de todos los fragmentos de texto
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

En este tutorial, aprendió a eliminar fuentes no utilizadas de un documento PDF mediante la biblioteca Aspose.PDF para .NET. Si sigue la guía paso a paso y ejecuta el código C# proporcionado, podrá cargar un PDF, identificar y eliminar fuentes no utilizadas y guardar el PDF actualizado.

### Preguntas frecuentes

#### P: ¿Cuál es el propósito del tutorial "Eliminar fuentes no utilizadas en un archivo PDF"?

R: El tutorial "Eliminar fuentes no utilizadas en un archivo PDF" explica cómo utilizar la biblioteca Aspose.PDF para .NET para eliminar fuentes no utilizadas de un documento PDF. El tutorial lo guía a través del proceso de carga de un PDF, identificación y eliminación de fuentes no utilizadas y guardado del PDF actualizado.

#### P: ¿Por qué querría eliminar fuentes no utilizadas de un documento PDF?

R: Quitar las fuentes no utilizadas de un documento PDF puede ayudar a reducir el tamaño del archivo y optimizar el documento para un mejor rendimiento. Esto resulta especialmente útil cuando se trabaja con archivos PDF que contienen fuentes incrustadas que en realidad no se utilizan en el contenido del documento.

#### P: ¿Cómo configuro el directorio de documentos?

A: Para configurar el directorio de documentos:

1.  Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el`dataDir` variable con la ruta al directorio donde se encuentran sus archivos PDF.

#### P: ¿Cómo puedo eliminar fuentes no utilizadas de un documento PDF usando la biblioteca Aspose.PDF?

R: El tutorial le guiará a través del proceso paso a paso:

1.  Abra el documento PDF utilizando el`Document` clase.
2.  Crear un`TextFragmentAbsorber` objeto con`TextEditOptions` empezar a`FontReplace.RemoveUnusedFonts`.
3. Acepte el absorbedor para identificar y eliminar fuentes no utilizadas del PDF.
4.  Iterar a través de todo`TextFragments` y configure la fuente a la fuente deseada.
5. Guarde el documento PDF actualizado.

####  P: ¿Cuál es el propósito de la`TextEditOptions.FontReplace.RemoveUnusedFonts` parameter?

 A: El`TextEditOptions.FontReplace.RemoveUnusedFonts` El parámetro instruye al`TextFragmentAbsorber`para identificar y eliminar fuentes no utilizadas del documento PDF.

#### P: ¿Puedo reemplazar fuentes no utilizadas con una fuente de mi elección?

R: Sí, puedes modificar el código para reemplazar las fuentes no utilizadas por una fuente de tu elección. En el código de muestra proporcionado, se utiliza la fuente "Arial, Bold" como reemplazo.

#### P: ¿Cómo funciona el`TextFragmentAbsorber` work to remove unused fonts?

 A: El`TextFragmentAbsorber` está configurado con el`TextEditOptions.FontReplace.RemoveUnusedFonts` parámetro, que identifica las fuentes no utilizadas dentro de los fragmentos de texto del PDF. Después de la absorción, puede iterar a través de la`TextFragments` y configurar sus fuentes como las fuentes de reemplazo deseadas.

#### P: ¿Cuál es el resultado esperado de la ejecución del código proporcionado?

R: Si sigue el tutorial y ejecuta el código C# proporcionado, eliminará las fuentes no utilizadas del documento PDF de entrada y guardará la versión actualizada como archivo PDF de salida.

#### P: ¿Puedo modificar el código para eliminar fuentes solo de páginas o áreas específicas?

R: El código proporcionado se centra en eliminar fuentes no utilizadas de todo el documento PDF. Si desea eliminar fuentes de páginas o regiones específicas, deberá modificar el enfoque y utilizar una lógica más compleja para identificar fuentes no utilizadas en esas áreas.