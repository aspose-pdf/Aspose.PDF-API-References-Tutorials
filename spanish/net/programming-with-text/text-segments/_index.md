---
title: Segmentos de texto
linktitle: Segmentos de texto
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a buscar segmentos de texto específicos dentro de un documento PDF utilizando expresiones regulares en Aspose.PDF para .NET.
type: docs
weight: 540
url: /es/net/programming-with-text/text-segments/
---

Este tutorial explica cómo buscar segmentos de texto específicos dentro de un documento PDF utilizando Aspose.PDF para .NET. El código fuente de C# proporcionado demuestra diferentes escenarios usando expresiones regulares.

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
```

## Paso 3: use TextFragmentAbsorber para la búsqueda de texto

 Crear un`TextFragmentAbsorber`objeto para buscar segmentos de texto específicos usando expresiones regulares:

```csharp
TextFragmentAbsorber textFragmentAbsorber;
```

## Paso 4: Realice búsquedas de texto con expresiones regulares

Realice búsquedas de texto basadas en diferentes escenarios utilizando expresiones regulares. Aquí están algunos ejemplos:

- Para buscar una coincidencia exacta de palabras: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"\bWord\b", new TextSearchOptions(true));
```

- Para buscar una cadena en mayúsculas o minúsculas: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber("(?i)Line", new TextSearchOptions(true));
```

- Para buscar todas las cadenas dentro del documento PDF: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

- Para buscar texto después de una cadena específica hasta un salto de línea: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"(?i)the ((.)*)");
```

- Para buscar texto después de una coincidencia de expresiones regulares: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"(?<=word).*");
```

- Para buscar hipervínculos/URL dentro del documento PDF: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"(http|ftp|https):\/\/([\w\-_]+(?:(?:\.[\w\-_]+)+))([\w\-\.,@?^=%&amp;:/~\+#]*[\w\-\@?^=%&amp;/~\+#])?");
```

Reemplace las expresiones regulares con los patrones de búsqueda que desee.

## Paso 5: Realiza la búsqueda y procesa los resultados

 Realice la búsqueda utilizando el creado`TextFragmentAbsorber` objetar y procesar los resultados según sus requisitos.

### Ejemplo de código fuente para segmentos de texto usando Aspose.PDF para .NET 
```csharp
TextFragmentAbsorber textFragmentAbsorber;
// Para buscar coincidencias exactas de una palabra, puede considerar usar una expresión regular.
textFragmentAbsorber = new TextFragmentAbsorber(@"\bWord\b", new TextSearchOptions(true));
//Para buscar una cadena en mayúsculas o minúsculas, puede considerar usar una expresión regular.
textFragmentAbsorber = new TextFragmentAbsorber("(?i)Line", new TextSearchOptions(true));
// Para buscar todas las cadenas (analizar todas las cadenas) dentro del documento PDF, intente usar la siguiente expresión regular.
textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
// Encuentre la coincidencia de la cadena de búsqueda y obtenga cualquier cosa después de la cadena hasta el salto de línea.
textFragmentAbsorber = new TextFragmentAbsorber(@"(?i)the ((.)*)");
// Utilice la siguiente expresión regular para encontrar el texto que sigue a la coincidencia de expresiones regulares.
textFragmentAbsorber = new TextFragmentAbsorber(@"(?<=word).*");
// Para buscar hipervínculos/URL dentro del documento PDF, intente utilizar la siguiente expresión regular.
textFragmentAbsorber = new TextFragmentAbsorber(@"(http|ftp|https):\/\/([\w\-_]+(?:(?:\.[\w\-_]+)+))([\w\-\.,@?^=%&amp;:/~\+#]*[\w\-\@?^=%&amp;/~\+#])?");
```


## Conclusión

¡Felicidades! Ha aprendido con éxito cómo buscar segmentos de texto específicos dentro de un documento PDF utilizando Aspose.PDF para .NET. Este tutorial proporcionó ejemplos de diferentes escenarios de búsqueda usando expresiones regulares. Ahora puede incorporar este código en sus propios proyectos de C# para buscar y procesar segmentos de texto en archivos PDF.