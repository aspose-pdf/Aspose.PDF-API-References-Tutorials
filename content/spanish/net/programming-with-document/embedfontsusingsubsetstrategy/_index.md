---
title: Incrustar fuentes en archivos PDF con estrategia de subconjunto
linktitle: Incrustar fuentes con estrategia de subconjunto
second_title: Aspose.PDF para referencia de API .NET
description: Aprenda a incrustar fuentes en un archivo PDF con Subset Strategy usando Aspose.PDF para .NET. Optimice el tamaño de su PDF incorporando solo los caracteres necesarios.
type: docs
weight: 130
url: /es/net/programming-with-document/embedfontsusingsubsetstrategy/
---
En este tutorial, discutiremos cómo incrustar fuentes en un archivo PDF con una estrategia de subconjunto usando Aspose.PDF para .NET. Aspose.PDF para .NET es una poderosa biblioteca que permite a los desarrolladores crear, editar y manipular documentos PDF mediante programación. Incrustar fuentes en un archivo PDF es un paso importante para garantizar que el documento se muestre correctamente en diferentes dispositivos, independientemente de si las fuentes requeridas están instaladas en esos dispositivos o no.

## Paso 1: crear una nueva aplicación de consola C#
Para comenzar, cree una nueva aplicación de consola C# en Visual Studio. Puedes nombrarlo como quieras. Una vez creado el proyecto, debe agregar una referencia a la biblioteca Aspose.PDF para .NET.

## Paso 2: Importe el espacio de nombres Aspose.PDF
Agregue la siguiente línea de código en la parte superior de su archivo C# para importar el espacio de nombres Aspose.PDF:

```csharp
using Aspose.Pdf;
```

## Paso 3: cargue un archivo PDF existente
Para incrustar fuentes en un archivo PDF existente, debe cargar ese archivo usando la clase Documento. El siguiente código demuestra cómo cargar un archivo PDF existente:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Cargar un archivo PDF existente
Document doc = new Document(dataDir + "input.pdf");
```

## Paso 4: incrustar fuentes con estrategia de subconjunto
Aspose.PDF para .NET proporciona dos estrategias para la incrustación de fuentes: SubsetAllFonts y SubsetEmbeddedFontsOnly.

La estrategia SubsetAllFonts incrustará todas las fuentes del documento como un subconjunto. Un subconjunto es una parte de la fuente que contiene sólo los caracteres utilizados en el documento. Esta estrategia es útil para reducir el tamaño del archivo del documento PDF.

La estrategia SubsetEmbeddedFontsOnly incrustará solo el subconjunto de fuentes que ya están incrustadas en el documento. Si una fuente no está incrustada, esta estrategia no la afectará.

El siguiente código demuestra cómo incrustar fuentes en un archivo PDF con una estrategia de subconjunto:

```csharp
// Todas las fuentes se incrustarán como subconjunto en el documento en el caso de SubsetAllFonts.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetAllFonts);

// El subconjunto de fuentes se incrustará en el caso de las fuentes totalmente incrustadas, pero las fuentes que no estén incrustadas en el documento no se verán afectadas.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetEmbeddedFontsOnly);
```

## Paso 5: guarde el documento PDF
Una vez que haya incrustado todas las fuentes en el archivo PDF con una estrategia de subconjunto, deberá guardar el documento. El siguiente código demuestra cómo guardar el archivo PDF:

```csharp
doc.Save(dataDir + "Output_out.pdf");
```

### Código fuente de ejemplo para incrustar fuentes con estrategia de subconjunto usando Aspose.PDF para .NET. 

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
// Todas las fuentes se incrustarán como subconjunto en el documento en el caso de SubsetAllFonts.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetAllFonts);
// El subconjunto de fuentes se incrustará en el caso de las fuentes totalmente incrustadas, pero las fuentes que no estén incrustadas en el documento no se verán afectadas.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetEmbeddedFontsOnly);
doc.Save(dataDir + "Output_out.pdf");
```

## Conclusión
En este artículo, analizamos cómo incrustar fuentes en un archivo PDF con una estrategia de subconjunto usando Aspose.PDF para .NET. Aspose.PDF para .NET proporciona una API simple y fácil de usar para trabajar con documentos PDF, incluida la adición e incrustación de fuentes con diferentes estrategias. Incrustar fuentes en un archivo PDF es un paso importante para garantizar que el documento se muestre correctamente en diferentes dispositivos, y la estrategia de subconjunto es una característica útil para reducir el tamaño del archivo del documento PDF.

### Preguntas frecuentes sobre incrustar fuentes en archivos PDF con estrategia de subconjunto

#### P: ¿Cuál es una estrategia de subconjunto para incrustar fuentes en un archivo PDF?

R: Una estrategia de subconjunto para incrustar fuentes en un archivo PDF significa que solo se incrustará una parte de la fuente que contiene los caracteres utilizados en el documento. Esto ayuda a reducir el tamaño del archivo del documento PDF al eliminar datos de fuentes innecesarios.

#### P: ¿Cuál es la diferencia entre las estrategias SubsetAllFonts y SubsetEmbeddedFontsOnly?

 R: El`SubsetAllFonts`La estrategia incrustará todas las fuentes en el documento como un subconjunto, mientras que la`SubsetEmbeddedFontsOnly` La estrategia solo incrustará el subconjunto de fuentes que ya están incrustadas en el documento. La última estrategia no afectará a las fuentes que aún no estén incrustadas.

#### P: ¿Por qué es importante la incrustación de fuentes con una estrategia de subconjunto?

R: La incrustación de fuentes con una estrategia de subconjunto es importante para garantizar que el archivo PDF contenga los datos de fuente necesarios para mostrar el texto correctamente y, al mismo tiempo, mantener el tamaño del archivo más pequeño al incluir solo los caracteres utilizados en el documento.

#### P: ¿Puedo usar Aspose.PDF para .NET para incrustar fuentes con diferentes estrategias?

 R: Sí, Aspose.PDF para .NET proporciona varias estrategias para incrustar fuentes, incluyendo`SubsetAllFonts` y`SubsetEmbeddedFontsOnly`. Puede elegir la estrategia adecuada según sus necesidades.

#### P: ¿Aspose.PDF para .NET es una biblioteca confiable para trabajar con documentos PDF?

R: Sí, Aspose.PDF para .NET es una biblioteca poderosa y confiable para trabajar con documentos PDF. Proporciona amplias funciones para crear, editar y manipular archivos PDF en aplicaciones .NET.