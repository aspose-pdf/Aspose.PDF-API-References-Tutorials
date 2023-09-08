---
title: MHT a PDF
linktitle: MHT a PDF
second_title: Aspose.PDF para referencia de API .NET
description: Guía paso a paso para convertir MHT a PDF usando Aspose.PDF para .NET.
type: docs
weight: 70
url: /es/net/document-conversion/mht-to-pdf/
---
En este tutorial, lo guiaremos a través del proceso de convertir un archivo MHT a PDF usando Aspose.PDF para .NET. MHT (MIME HTML) es un formato utilizado para guardar una página web completa, incluidas imágenes y contenido asociado. Siguiendo los pasos a continuación, podrá convertir archivos MHT a formato PDF.

## Requisitos previos
Antes de comenzar, asegúrese de cumplir con los siguientes requisitos previos:

- Conocimientos básicos del lenguaje de programación C#.
- Biblioteca Aspose.PDF para .NET instalada en su sistema.
- Un entorno de desarrollo como Visual Studio.

## Paso 1: cargar el archivo MHT
En este paso cargaremos el archivo MHT usando Aspose.PDF para .NET. Siga el código a continuación:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

MhtLoadOptions options = new MhtLoadOptions();

// Cargar el documento
Document document = new Document(dataDir + "test.mht", options);
```

 Asegúrate de reemplazar`"YOUR DOCUMENTS DIRECTORY"` con el directorio real donde se encuentra su archivo MHT.

## Paso 2: conversión de MHT a PDF
Después de cargar el archivo MHT, podemos proceder con la conversión a PDF. Utilice el siguiente código:

```csharp
// Guarde el resultado como un documento PDF
document.Save(dataDir + "MHTToPDF_out.pdf");
```

 El código anterior convierte el archivo MHT a formato PDF y lo guarda como el nombre del archivo.`"MHTToPDF_out.pdf"`.

### Código fuente de ejemplo para MHT a PDF usando Aspose.PDF para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
MhtLoadOptions options = new MhtLoadOptions();
// Cargar documento
Document document = new Document(dataDir  + "test.mht", options);
// Guarde el resultado como documento PDF
document.Save(dataDir + "MHTToPDF_out.pdf");
```

## Conclusión
En este tutorial, cubrimos el proceso paso a paso de convertir un archivo MHT a PDF usando Aspose.PDF para .NET. Si sigue las instrucciones descritas anteriormente, ahora debería poder convertir archivos MHT a formato PDF. Esta función puede resultar útil cuando necesita convertir páginas web completas en documentos PDF.

### Preguntas frecuentes

#### P: ¿Aspose.PDF para .NET admite la conversión de archivos MHT con imágenes incrustadas a PDF?

R: Sí, Aspose.PDF para .NET admite la conversión de archivos MHT con imágenes incrustadas a PDF. La biblioteca puede manejar el contenido completo de la página web, incluidas imágenes y recursos asociados, y convertirlo en un documento PDF.

#### P: ¿Puedo personalizar la salida del PDF durante el proceso de conversión de MHT a PDF?

R: Sí, Aspose.PDF para .NET proporciona varias opciones para personalizar la salida del PDF durante el proceso de conversión de MHT a PDF. Puede establecer propiedades como el tamaño de página, la orientación, los márgenes y más para controlar la apariencia del documento PDF resultante.

#### P: ¿Aspose.PDF para .NET conserva los hipervínculos y el formato del archivo MHT original en la salida PDF?

R: Sí, Aspose.PDF para .NET conserva los hipervínculos y el formato del archivo MHT original en la salida PDF. La biblioteca garantiza que el PDF convertido conserve el mismo diseño y contenido que el archivo MHT de origen.

#### P: ¿Puedo convertir varios archivos MHT en documentos PDF separados usando Aspose.PDF para .NET?

R: Sí, puede convertir varios archivos MHT en documentos PDF separados utilizando Aspose.PDF para .NET. Simplemente cargue cada archivo MHT y guárdelo como un documento PDF independiente con un nombre de archivo único.