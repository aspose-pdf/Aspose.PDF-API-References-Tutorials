---
title: MHT a PDF
linktitle: MHT a PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Guía paso a paso para convertir MHT a PDF usando Aspose.PDF para .NET.
type: docs
weight: 70
url: /es/net/document-conversion/mht-to-pdf/
---

En este tutorial, lo guiaremos a través del proceso de conversión de un archivo MHT a PDF usando Aspose.PDF para .NET. MHT (MIME HTML) es un formato que se utiliza para guardar una página web completa, incluidas las imágenes y el contenido asociado. Siguiendo los pasos a continuación, podrá convertir archivos MHT a formato PDF.

## requisitos previos
Antes de comenzar, asegúrese de cumplir con los siguientes requisitos previos:

- Conocimientos básicos del lenguaje de programación C#.
- Biblioteca Aspose.PDF para .NET instalada en su sistema.
- Un entorno de desarrollo como Visual Studio.

## Paso 1: cargando el archivo MHT
En este paso cargaremos el archivo MHT usando Aspose.PDF para .NET. Siga el código a continuación:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

MhtLoadOptions options = new MhtLoadOptions();

// Cargue el documento
Document document = new Document(dataDir + "test.mht", options);
```

 Asegúrese de reemplazar`"YOUR DOCUMENTS DIRECTORY"` con el directorio real donde se encuentra su archivo MHT.

## Paso 2: conversión de MHT a PDF
Después de cargar el archivo MHT, podemos proceder con la conversión a PDF. Usa el siguiente código:

```csharp
// Guarde la salida como un documento PDF
document.Save(dataDir + "MHTToPDF_out.pdf");
```

 El código anterior convierte el archivo MHT a formato PDF y lo guarda como el nombre del archivo`"MHTToPDF_out.pdf"`.

### Código fuente de ejemplo para MHT a PDF usando Aspose.Words para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
MhtLoadOptions options = new MhtLoadOptions();
// Cargar documento
Document document = new Document(dataDir  + "test.mht", options);
// Guarde la salida como documento PDF
document.Save(dataDir + "MHTToPDF_out.pdf");
```

## Conclusión
En este tutorial, cubrimos el proceso paso a paso de convertir un archivo MHT a PDF usando Aspose.PDF para .NET. Siguiendo las instrucciones descritas anteriormente, ahora debería poder convertir archivos MHT a formato PDF. Esta característica puede ser útil cuando necesita convertir páginas web completas en documentos PDF.