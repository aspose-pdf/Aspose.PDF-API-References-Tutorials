---
title: PDFA a PDF
linktitle: PDFA a PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Guía paso a paso para convertir PDFA a PDF utilizando Aspose.PDF para .NET.
type: docs
weight: 100
url: /es/net/document-conversion/pdfa-to-pdf/
---

En este tutorial, lo guiaremos a través del proceso de conversión de un archivo PDFA (PDF/A) a formato PDF estándar usando Aspose.PDF para .NET. El formato PDFA es una versión específica del formato PDF que se utiliza para garantizar el archivo de documentos a largo plazo. Siguiendo los pasos a continuación, podrá convertir un archivo PDFA a formato PDF.

## requisitos previos
Antes de comenzar, asegúrese de cumplir con los siguientes requisitos previos:

- Conocimientos básicos del lenguaje de programación C#.
- Biblioteca Aspose.PDF para .NET instalada en su sistema.
- Un entorno de desarrollo como Visual Studio.

## Paso 1: Cargar el documento PDFA
En este paso, cargaremos el archivo PDFA de origen usando Aspose.PDF para .NET. Siga el código a continuación:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cargue el documento PDFA
Document doc = new Document(dataDir + "PDFAToPDF.pdf");
```

 Asegúrese de reemplazar`"YOUR DOCUMENTS DIRECTORY"` con el directorio real donde se encuentra su archivo PDFA.

## Paso 2: Eliminación de la información de cumplimiento de PDF/A
Ahora vamos a eliminar la información de cumplimiento de PDF/A del documento. Usa el siguiente código:

```csharp
// Eliminar información de cumplimiento de PDF/A
doc.RemovePdfaCompliance();
```

## Paso 3: Guardar el archivo PDF resultante
Finalmente, guardaremos el archivo PDFA convertido a formato PDF. Usa el siguiente código:

```csharp
// Guarde el documento actualizado en formato PDF
doc.Save(dataDir + "PDFAToPDF_out.pdf");
```

El código anterior guarda el archivo PDFA convertido a formato PDF con el nombre de archivo`"PDFAToPDF_out.pdf"`.

### Código fuente de ejemplo para PDFA a PDF usando Aspose.PDF para .NET


```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Abrir documento
Document doc = new Document(dataDir + "PDFAToPDF.pdf");

// Eliminar la información de cumplimiento de PDF/A
doc.RemovePdfaCompliance();
// Guardar documento actualizado
doc.Save(dataDir + "PDFAToPDF_out.pdf");
```

## Conclusión
En este tutorial, cubrimos el proceso paso a paso de convertir un archivo PDFA a formato PDF usando Aspose.PDF para .NET. Siguiendo las instrucciones descritas anteriormente, ahora debería poder convertir un archivo PDFA al formato PDF estándar. Esta característica es útil cuando desea eliminar las restricciones de cumplimiento de PDF/A de un documento para un uso más flexible.