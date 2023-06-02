---
title: Dividir en páginas
linktitle: Dividir en páginas
second_title: Referencia de API de Aspose.PDF para .NET
description: Guía paso a paso para dividir un documento PDF en páginas individuales utilizando Aspose.PDF para .NET.
type: docs
weight: 140
url: /es/net/programming-with-pdf-pages/split-to-pages/
---
En este tutorial, lo guiaremos a través del proceso paso a paso para dividir un documento PDF en páginas individuales usando Aspose.PDF para .NET. Explicaremos el código fuente de C# incluido y le proporcionaremos una guía completa para ayudarlo a comprender e implementar esta función en sus propios proyectos. Al final de este tutorial, sabrá cómo dividir un documento PDF en varios archivos PDF, cada uno con una sola página.

## requisitos previos
Antes de comenzar, asegúrese de tener lo siguiente:

- Un conocimiento básico del lenguaje de programación C#
- Aspose.PDF para .NET instalado en su entorno de desarrollo

## Paso 1: Definir el directorio de documentos
Primero, debe establecer la ruta a su directorio de documentos. Aquí es donde se encuentra el documento PDF que desea dividir. Reemplace "SU DIRECTORIO DE DOCUMENTOS" con la ruta adecuada.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Abra el documento PDF
 Luego puede abrir el documento PDF para dividirlo usando el`Document` clase de Aspose.PDF. Asegúrese de especificar la ruta correcta del documento.

```csharp
Document pdfDocument = new Document(dataDir + "SplitToPages.pdf");
```

## Paso 3: Revisa las páginas y divídelas
Ahora puede recorrer todas las páginas del documento PDF usando un bucle. Para cada página, cree un nuevo documento y agregue esa página a este nuevo documento. Luego guarde el nuevo documento usando un nombre de archivo único para cada página.

```csharp
int pageCount = 1;
foreach(Page pdfPage in pdfDocument.Pages)
{
Document newDocument = newDocument();
newDocument.Pages.Add(pdfPage);
newDocument.Save(dataDir + "page_" + pageCount + "_out" + ".pdf");
pageCount++;
}
```

### Ejemplo de código fuente para Dividir en páginas usando Aspose.PDF para .NET 

```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "SplitToPages.pdf");
int pageCount = 1;
// Pasar por todas las páginas
foreach (Page pdfPage in pdfDocument.Pages)
{
	Document newDocument = new Document();
	newDocument.Pages.Add(pdfPage);
	newDocument.Save(dataDir + "page_" + pageCount + "_out" + ".pdf");
	pageCount++;
}

```

## Conclusión
En este tutorial, aprendimos a dividir un documento PDF en páginas individuales usando Aspose.PDF para .NET. Siguiendo esta guía paso a paso, puede dividir fácilmente un documento PDF en varios archivos PDF, cada uno con una sola página. Aspose.PDF ofrece una API potente y flexible para trabajar con documentos PDF en sus proyectos. Ahora puede utilizar esta función para realizar operaciones de división de documentos PDF según sus necesidades específicas.
