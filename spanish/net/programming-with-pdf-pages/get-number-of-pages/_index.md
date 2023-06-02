---
title: Obtener número de páginas
linktitle: Obtener número de páginas
second_title: Referencia de API de Aspose.PDF para .NET
description: Guía paso a paso para obtener el recuento de páginas de un PDF usando Aspose.PDF para .NET. Simple de implementar, ideal para sus proyectos.
type: docs
weight: 70
url: /es/net/programming-with-pdf-pages/get-number-of-pages/
---
En este tutorial, lo guiaremos a través del proceso paso a paso para obtener el recuento de páginas de un archivo PDF utilizando Aspose.PDF para .NET. Explicaremos el código fuente de C# incluido y le proporcionaremos una guía completa para ayudarlo a comprender e implementar esta característica en sus propios proyectos. Al final de este tutorial, sabrá cómo obtener el recuento de páginas de un archivo PDF utilizando Aspose.PDF para .NET.

## requisitos previos
Antes de comenzar, asegúrese de tener lo siguiente:

- Un conocimiento básico del lenguaje de programación C#
- Aspose.PDF para .NET instalado en su entorno de desarrollo

## Paso 1: Definir el directorio de documentos
Primero, debe establecer la ruta a su directorio de documentos. Esta es la ubicación de su archivo PDF para el que desea obtener el recuento de páginas. Reemplace "SU DIRECTORIO DE DOCUMENTOS" con la ruta adecuada.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Abra el documento PDF
 Luego puede abrir el archivo PDF usando el`Document` clase de Aspose.PDF. Asegúrese de especificar la ruta correcta al archivo PDF.

```csharp
Document pdfDocument = new Document(dataDir + "GetNumberofPages.pdf");
```

## Paso 3: Obtener el número de páginas
 Ahora puede obtener el número de páginas en el documento usando el`Count`propiedad del documento`s `Colección de páginas. Esto le dará el número total de páginas en el archivo PDF.

```csharp
System.Console.WriteLine("Number of pages: {0}", pdfDocument.Pages.Count);
```

### Ejemplo de código fuente para obtener el número de páginas usando Aspose.PDF para .NET 

```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "GetNumberofPages.pdf");
// Obtener recuento de páginas
System.Console.WriteLine("Page Count : {0}", pdfDocument.Pages.Count);

```

## Conclusión
En este tutorial, aprendimos cómo obtener el recuento de páginas de un archivo PDF usando Aspose.PDF para .NET. Siguiendo los pasos descritos anteriormente, puede implementar fácilmente esta funcionalidad en sus propios proyectos. Siéntase libre de explorar más la documentación de Aspose.PDF para descubrir otras características útiles para trabajar con archivos PDF.
