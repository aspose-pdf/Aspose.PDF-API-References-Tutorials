---
title: Extraer texto resaltado en archivo PDF
linktitle: Extraer texto resaltado en archivo PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda cómo extraer texto resaltado en un archivo PDF usando Aspose.PDF para .NET con esta guía paso a paso.
type: docs
weight: 60
url: /es/net/annotations/extracthighlightedtext/
---
Para extraer el texto resaltado en un archivo PDF, puede usar Aspose.PDF para la API de .NET. Esta API proporciona una forma sencilla de recuperar todo el texto que se ha resaltado en un documento.

## Paso 1: Cargue el documento PDF

 El primer paso para extraer el texto resaltado en un archivo PDF es cargar el documento utilizando Aspose.PDF para la API de .NET. Puede hacer esto creando una nueva instancia del`Document` class y pasando la ruta al documento PDF como parámetro. 

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

## Conclusión

En este tutorial, exploramos cómo extraer texto resaltado de un documento PDF utilizando Aspose.PDF para .NET. Al seguir la guía paso a paso y usar el código fuente de C# proporcionado, los desarrolladores pueden extraer y administrar fácilmente el texto resaltado en sus documentos PDF.

### Preguntas frecuentes sobre la extracción de texto resaltado en un archivo PDF

#### P: ¿Qué son las anotaciones de marcado de texto en un documento PDF?

R: Las anotaciones de marcado de texto son anotaciones que resaltan o marcan texto específico en un documento PDF. Los ejemplos de anotaciones de marcado de texto incluyen resaltados, subrayados y tachados.

#### P: ¿Puedo extraer texto de otros tipos de anotaciones usando Aspose.PDF para .NET?

R: Sí, Aspose.PDF para .NET proporciona varios métodos para extraer texto de diferentes tipos de anotaciones, incluidas anotaciones de marcado de texto, anotaciones de texto libre y más.

#### P: ¿Aspose.PDF para .NET admite la extracción de texto de archivos PDF protegidos con contraseña?

R: Sí, Aspose.PDF para .NET admite la extracción de texto de archivos PDF protegidos con contraseña. Debe proporcionar la contraseña correcta al cargar el documento PDF utilizando el`Document` clase.

#### P: ¿Puedo filtrar el texto resaltado según otros criterios, como el color o el autor?

R: Sí, puede filtrar el texto resaltado según otros criterios, como el color, el autor o la fecha de creación. Aspose.PDF para .NET proporciona métodos para acceder y filtrar anotaciones en función de sus propiedades.

#### P: ¿Es posible guardar el texto resaltado extraído en un archivo separado?

R: Sí, puede guardar el texto resaltado extraído en un archivo separado o almacenarlo en una estructura de datos para su posterior procesamiento o análisis.
