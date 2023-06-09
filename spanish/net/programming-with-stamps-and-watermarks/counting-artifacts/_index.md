---
title: Contando artefactos
linktitle: Contando artefactos
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a contar fácilmente marcas de agua en sus documentos PDF con Aspose.PDF para .NET.
type: docs
weight: 60
url: /es/net/programming-with-stamps-and-watermarks/counting-artifacts/
---

En este tutorial, lo guiaremos paso a paso sobre cómo contar artefactos en un documento PDF utilizando Aspose.PDF para .NET. Le mostraremos cómo utilizar el código fuente de C# proporcionado para contar la cantidad de artefactos de "marca de agua" en una página específica del documento PDF.

## Paso 1: Configuración del entorno

Antes de comenzar, asegúrese de tener lo siguiente:

- Un entorno de desarrollo .NET instalado.
- La biblioteca Aspose.PDF para .NET descargada y referenciada en su proyecto.

## Paso 2: Cargar el documento PDF

El primer paso es cargar el documento PDF existente en su proyecto. Así es cómo:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Abre el documento
Document pdfDocument = new Document(dataDir + "watermark.pdf");
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real al directorio donde se encuentra su documento PDF.

## Paso 3: Cuente los artefactos

Ahora que ha cargado el documento PDF, puede contar los artefactos de tipo "marca de agua" en una página específica del documento. Así es cómo:

```csharp
// Inicializar el contador
int count = 0;

// Recorra todos los artefactos de la primera página
foreach(Artifact artifact in pdfDocument.Pages[1].Artifacts)
{
     // Si el subtipo de artefacto es "marca de agua", incremente el contador
     if (artifact.Subtype == Artifact.ArtifactSubtype.Watermark)
         count++;
}

// Mostrar el número de artefactos de tipo "marca de agua"
Console.WriteLine("The page contains " + count + " watermarks");
```

El código anterior recorre todos los artefactos en la primera página del documento PDF e incrementa el contador para cada artefacto de tipo "marca de agua" encontrado.

### Ejemplo de código fuente para contar artefactos usando Aspose.PDF para .NET 
```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Abrir documento
Document pdfDocument = new Document( dataDir +  "watermark.pdf");

int count = 0;
foreach (Artifact artifact in pdfDocument.Pages[1].Artifacts)
{
	// Si el tipo de artefacto es una marca de agua, aumente el contador
	if (artifact.Subtype == Artifact.ArtifactSubtype.Watermark) count++;
}
Console.WriteLine("Page contains " + count + " watermarks");

```

## Conclusión

¡Felicidades! Aprendió a contar artefactos de "marca de agua" en un documento PDF usando Aspose.PDF para .NET. Ahora puede usar este conocimiento para realizar análisis y procesamientos específicos en artefactos en sus documentos PDF.
