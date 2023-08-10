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

### Código fuente de ejemplo para MHT a PDF usando Aspose.PDF para .NET

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

### Preguntas frecuentes

#### P: ¿Aspose.PDF para .NET admite la conversión de archivos MHT con imágenes incrustadas a PDF?

R: Sí, Aspose.PDF para .NET admite la conversión de archivos MHT con imágenes incrustadas a PDF. La biblioteca puede manejar el contenido completo de la página web, incluidas las imágenes y los recursos asociados, y convertirlo en un documento PDF.

#### P: ¿Puedo personalizar la salida de PDF durante el proceso de conversión de MHT a PDF?

R: Sí, Aspose.PDF para .NET ofrece varias opciones para personalizar la salida de PDF durante el proceso de conversión de MHT a PDF. Puede establecer propiedades como el tamaño de página, la orientación, los márgenes y más para controlar la apariencia del documento PDF resultante.

#### P: ¿Aspose.PDF para .NET conserva los hipervínculos y el formato del archivo MHT original en la salida PDF?

R: Sí, Aspose.PDF para .NET conserva los hipervínculos y el formato del archivo MHT original en la salida PDF. La biblioteca garantiza que el PDF convertido conserve el mismo diseño y contenido que el archivo MHT de origen.

#### P: ¿Puedo convertir varios archivos MHT en documentos PDF separados usando Aspose.PDF para .NET?

R: Sí, puede convertir varios archivos MHT en documentos PDF independientes mediante Aspose.PDF para .NET. Simplemente cargue cada archivo MHT y guárdelo como un documento PDF separado con un nombre de archivo único.