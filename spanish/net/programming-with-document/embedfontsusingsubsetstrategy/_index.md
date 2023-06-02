---
title: Incrustar fuentes usando la estrategia de subconjunto
linktitle: Incrustar fuentes usando la estrategia de subconjunto
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a incrustar fuentes en un archivo PDF con Subset Strategy usando Aspose.PDF para .NET. Optimice el tamaño de su PDF incrustando solo los caracteres necesarios.
type: docs
weight: 130
url: /es/net/programming-with-document/embedfontsusingsubsetstrategy/
---

En este tutorial, analizaremos cómo incrustar fuentes en un archivo PDF con una estrategia de subconjunto utilizando Aspose.PDF para .NET. Aspose.PDF para .NET es una potente biblioteca que permite a los desarrolladores crear, editar y manipular documentos PDF mediante programación. Incrustar fuentes en un archivo PDF es un paso importante para garantizar que el documento se muestre correctamente en diferentes dispositivos, independientemente de si las fuentes requeridas están instaladas en esos dispositivos o no.

## Paso 1: Cree una nueva aplicación de consola C#
Para comenzar, cree una nueva aplicación de consola C# en Visual Studio. Puedes nombrarlo como quieras. Una vez que se crea el proyecto, debe agregar una referencia a la biblioteca Aspose.PDF para .NET.

## Paso 2: Importe el espacio de nombres Aspose.PDF
Agregue la siguiente línea de código en la parte superior de su archivo C# para importar el espacio de nombres Aspose.PDF:

```csharp
using Aspose.Pdf;
```

## Paso 3: Cargue un archivo PDF existente
Para incrustar fuentes en un archivo PDF existente, debe cargar ese archivo usando la clase Documento. El siguiente código demuestra cómo cargar un archivo PDF existente:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Cargar un archivo PDF existente
Document doc = new Document(dataDir + "input.pdf");
```

## Paso 4: incrustar fuentes con estrategia de subconjunto
Aspose.PDF para .NET proporciona dos estrategias para incrustar fuentes: SubsetAllFonts y SubsetEmbeddedFontsOnly.

La estrategia SubsetAllFonts incrustará todas las fuentes en el documento como un subconjunto. Un subconjunto es una parte de la fuente que contiene solo los caracteres utilizados en el documento. Esta estrategia es útil para reducir el tamaño del archivo del documento PDF.

La estrategia SubsetEmbeddedFontsOnly incrustará solo el subconjunto de fuentes que ya están incrustadas en el documento. Si una fuente no está incrustada, no se verá afectada por esta estrategia.

El siguiente código demuestra cómo incrustar fuentes en un archivo PDF con una estrategia de subconjunto:

```csharp
// Todas las fuentes se incrustarán como subconjunto en el documento en el caso de SubsetAllFonts.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetAllFonts);

// El subconjunto de fuentes se incrustará para las fuentes totalmente incrustadas, pero las fuentes que no estén incrustadas en el documento no se verán afectadas.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetEmbeddedFontsOnly);
```

## Paso 5: Guarde el documento PDF
Una vez que haya incrustado todas las fuentes en el archivo PDF con una estrategia de subconjunto, debe guardar el documento. El siguiente código muestra cómo guardar el archivo PDF:

```csharp
doc.Save(dataDir + "Output_out.pdf");
```

### Código fuente de ejemplo para incrustar fuentes con estrategia de subconjunto utilizando Aspose.PDF para .NET. 

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
// Todas las fuentes se incrustarán como subconjunto en el documento en el caso de SubsetAllFonts.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetAllFonts);
// El subconjunto de fuentes se incrustará para las fuentes totalmente incrustadas, pero las fuentes que no estén incrustadas en el documento no se verán afectadas.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetEmbeddedFontsOnly);
doc.Save(dataDir + "Output_out.pdf");
```

## Conclusión
En este artículo, hemos discutido cómo incrustar fuentes en un archivo PDF con una estrategia de subconjunto usando Aspose.PDF para .NET. Aspose.PDF para .NET proporciona una API simple y fácil de usar para trabajar con documentos PDF, lo que incluye agregar e incrustar fuentes con diferentes estrategias. Incrustar fuentes en un archivo PDF es un paso importante para garantizar que el documento se muestre correctamente en diferentes dispositivos, y la estrategia de subconjuntos es una función útil para reducir el tamaño del archivo del documento PDF.

