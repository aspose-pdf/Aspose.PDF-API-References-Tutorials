---
title: Eliminar todo el texto del PDF
linktitle: Eliminar todo el texto del PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a eliminar todo el texto de un documento PDF con Aspose.PDF para .NET.
type: docs
weight: 290
url: /es/net/programming-with-text/remove-all-text-from-pdf/
---

 En este tutorial, explicaremos cómo eliminar todo el texto de un documento PDF utilizando la biblioteca Aspose.PDF para .NET. Pasaremos por el proceso paso a paso de abrir un PDF, usando un`TextFragmentAbsorber` para eliminar todo el texto y guardar el PDF modificado con el código fuente de C# proporcionado.

## Requisitos

Antes de comenzar, asegúrese de tener lo siguiente:

- La biblioteca Aspose.PDF para .NET instalada.
- Conocimientos básicos de programación en C#.

## Paso 1: configurar el directorio de documentos

 Primero, debe establecer la ruta al directorio donde se encuentran sus archivos PDF. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el`dataDir` variable con la ruta a sus archivos PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Abra el documento PDF

 A continuación, abrimos el documento PDF usando el`Document` clase de la biblioteca Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
```

## Paso 3: eliminar todo el texto

 Inicializamos un`TextFragmentAbsorber` objeto y utilícelo para eliminar todo el texto absorbido del documento PDF.

```csharp
TextFragmentAbsorber absorb = new TextFragmentAbsorber();
absorb. RemoveAllText(pdfDocument);
```

## Paso 4: Guarde el PDF modificado

Finalmente, guardamos el documento PDF modificado en el archivo de salida especificado.

```csharp
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### Ejemplo de código fuente para Quitar todo el texto de PDF usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
// Iniciar TextFragmentAbsorber
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
// Eliminar todo el texto absorbido
absorber.RemoveAllText(pdfDocument);
// Guardar el documento
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

## Conclusión

En este tutorial, ha aprendido a eliminar todo el texto de un documento PDF utilizando la biblioteca Aspose.PDF para .NET. Siguiendo la guía paso a paso y ejecutando el código C# provisto, puede abrir un PDF, eliminar todo el texto usando un`TextFragmentAbsorber`y guarde el PDF modificado.