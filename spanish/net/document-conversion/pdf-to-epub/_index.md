---
title: PDF a EPUB
linktitle: PDF a EPUB
second_title: Referencia de API de Aspose.PDF para .NET
description: Guía paso a paso para convertir PDF a EPUB usando Aspose.PDF para .NET.
type: docs
weight: 120
url: /es/net/document-conversion/pdf-to-epub/
---

En este tutorial, lo guiaremos a través del proceso de conversión de un archivo PDF a formato EPUB usando Aspose.PDF para .NET. El formato PDF se usa comúnmente para mostrar documentos, mientras que el formato EPUB está especialmente diseñado para libros electrónicos. Siguiendo los pasos a continuación, podrá convertir archivos PDF a formato EPUB.

## requisitos previos
Antes de comenzar, asegúrese de cumplir con los siguientes requisitos previos:

- Conocimientos básicos del lenguaje de programación C#.
- Biblioteca Aspose.PDF para .NET instalada en su sistema.
- Un entorno de desarrollo como Visual Studio.

## Paso 1: Cargar el documento PDF
En este paso, cargaremos el archivo PDF usando Aspose.PDF para .NET. Siga el código a continuación:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cargue el documento PDF
Document pdfDocument = new Document(dataDir + "PDFToEPUB.pdf");
```

 Asegúrese de reemplazar`"YOUR DOCUMENTS DIRECTORY"` con el directorio real donde se encuentra su archivo PDF.

## Paso 2: Crear una instancia de las opciones de guardado de EPUB
Después de cargar el documento PDF, instanciaremos las opciones de guardado para el formato EPUB. Usa el siguiente código:

```csharp
// Crear una instancia de las opciones de copia de seguridad de EPUB
EpubSaveOptions options = new EpubSaveOptions();
```

## Paso 3: Especificación del diseño del contenido
Ahora especificaremos el diseño de los contenidos del libro EPUB. Usa el siguiente código:

```csharp
// Especificación del diseño de los contenidos.
options.ContentRecognitionMode = EpubSaveOptions.RecognitionMode.Flow;
```

## Paso 4: Guardar el documento EPUB
Una vez que hemos configurado las opciones de guardado, ya podemos guardar el archivo EPUB resultante. Aquí está el último paso:

```csharp
// Guarde el documento EPUB
pdfDocument.Save(dataDir + "PDFToEPUB_out.epub", options);
```

 Reemplazar`"YOUR DOCUMENTS DIRECTORY"` con el directorio deseado donde desea guardar el archivo EPUB de salida.

### Código fuente de ejemplo para PDF a EPUB usando Aspose.Words para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Cargar documento PDF
Document pdfDocument = new Document(dataDir + "PDFToEPUB.pdf");

// Instancia las opciones de guardado de Epub
EpubSaveOptions options = new EpubSaveOptions();

// Especificar el diseño de los contenidos
options.ContentRecognitionMode = EpubSaveOptions.RecognitionMode.Flow;

// Guardar el documento ePUB
pdfDocument.Save(dataDir + "PDFToEPUB_out.epub", options);
```

## Conclusión
En este tutorial, hemos cubierto el proceso paso a paso de convertir un archivo PDF en formato EPUB usando Aspose.PDF para .NET. Siguiendo las instrucciones anteriores, puede convertir fácilmente archivos PDF a formato EPUB. Esta función es especialmente útil para convertir documentos PDF en libros electrónicos legibles en diferentes dispositivos.