---
title: Extraer texto resaltado
linktitle: Extraer texto resaltado
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a extraer texto resaltado usando Aspose.PDF para .NET con esta guía paso a paso.
type: docs
weight: 60
url: /es/net/annotations/extracthighlightedtext/
---
Para extraer texto resaltado de un documento PDF, puede usar Aspose.PDF para la API de .NET. Esta API proporciona una forma sencilla de recuperar todo el texto que se ha resaltado en un documento.

## Paso 1: Cargue el documento PDF

 El primer paso para extraer el texto resaltado de un documento PDF es cargar el documento mediante la API de Aspose.PDF para .NET. Puede hacer esto creando una nueva instancia del`Document` class y pasando la ruta al documento PDF como parámetro. 

```csharp
// La ruta al directorio de documentos.
string dataDir ="YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");
```

## Paso 2: recorrer todas las anotaciones

 El siguiente paso es recorrer todas las anotaciones en el documento PDF. Puedes hacer esto usando un`foreach` bucle, así:

```csharp
foreach (Annotation annotation in doc.Pages[1].Annotations)
{
	// El código va aquí
}
```

## Paso 3: filtrar las anotaciones de marcado de texto

 Dentro de`foreach` bucle, deberá filtrar todas las anotaciones que no sean anotaciones de marcado de texto. Puede hacerlo comprobando si la anotación es una instancia de la`TextMarkupAnnotation` clase.

```csharp
if (annotation is TextMarkupAnnotation)
{
	// El código va aquí
}
```

## Paso 4: recuperar fragmentos de texto resaltados

 Una vez que haya filtrado todas las anotaciones de marcado de texto, puede recuperar los fragmentos de texto resaltados para cada anotación. Puede hacerlo llamando al`GetMarkedTextFragments()` método en el`TextMarkupAnnotation` objeto.

```csharp
TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
```

## Paso 5: Mostrar el texto resaltado

 Finalmente, puede mostrar el texto resaltado al usuario. Puede hacer esto recorriendo cada`TextFragment` objeto en el`TextFragmentCollection` y llamando al`Text` propiedad.

```csharp
foreach (TextFragment tf in collection)
{
	Console.WriteLine(tf.Text);
}
```

### Ejemplo de código fuente para Extraer texto resaltado usando Aspose.PDF para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir ="YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");

	foreach (Annotation annotation in doc.Pages[1].Annotations)
	{
		if (annotation is TextMarkupAnnotation)
		{
			TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
			TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
			foreach (TextFragment tf in collection)
			{
				Console.WriteLine(tf.Text);
			}
		}
	}
```

