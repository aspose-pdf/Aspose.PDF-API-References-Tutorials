---
title: Rebaja a PDF
linktitle: Rebaja a PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Guía paso a paso para convertir Markdown a PDF utilizando Aspose.PDF para .NET.
type: docs
weight: 60
url: /es/net/document-conversion/markdown-to-pdf/
---

En este tutorial, lo guiaremos a través del proceso de conversión de un archivo Markdown a PDF usando Aspose.PDF para .NET. Markdown es un lenguaje de marcado ligero que se utiliza para formatear texto sin formato de forma estructurada. Siguiendo los pasos a continuación, podrá convertir archivos Markdown a formato PDF.

## requisitos previos
Antes de comenzar, asegúrese de cumplir con los siguientes requisitos previos:

- Conocimientos básicos del lenguaje de programación C#.
- Biblioteca Aspose.PDF para .NET instalada en su sistema.
- Un entorno de desarrollo como Visual Studio.

## Paso 1: cargando el archivo Markdown
En este paso, cargaremos el archivo Markdown usando Aspose.PDF para .NET. Siga el código a continuación:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Abrir documento de Markdown
Document doc = new Document(dataDir + "sample.md", new MdLoadOptions());
```

 Asegúrese de reemplazar`"YOUR DOCUMENTS DIRECTORY"`con el directorio real donde se encuentra su archivo Markdown.

## Paso 2: Conversión de Markdown a PDF
Después de cargar el archivo Markdown, podemos proceder con la conversión a PDF. Usa el siguiente código:

```csharp
// Guarda el documento en formato PDF
doc.Save(dataDir + "MarkdownToPDF.pdf");
```

 El código anterior convierte el archivo Markdown a formato PDF y lo guarda como el nombre del archivo`"MarkdownToPDF.pdf"`.

### Código fuente de ejemplo para Markdown a PDF usando Aspose.Words para .NET


```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento de Markdown
Document doc = new Document(dataDir + "sample.md", new MdLoadOptions());
// Guardar documento en formato PDF
doc.Save(dataDir + "MarkdownToPDF.pdf");
```

## Conclusión
En este tutorial, cubrimos el proceso paso a paso de convertir un archivo Markdown a PDF usando Aspose.PDF para .NET. Siguiendo las instrucciones descritas anteriormente, ahora debería poder convertir archivos Markdown a formato PDF. Esta característica puede ser útil cuando necesita generar documentos PDF a partir del contenido de Markdown.