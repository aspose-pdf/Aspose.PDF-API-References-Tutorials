---
title: PDF a XML
linktitle: PDF a XML
second_title: Referencia de API de Aspose.PDF para .NET
description: Guía paso a paso para convertir PDF a XML utilizando Aspose.PDF para .NET.
type: docs
weight: 210
url: /es/net/document-conversion/pdf-to-xml/
---

En este tutorial, lo guiaremos a través del proceso de conversión de un archivo PDF a formato XML usando Aspose.PDF para .NET. XML (lenguaje de marcado extensible) es un formato de datos utilizado para almacenar e intercambiar información estructurada. Siguiendo los pasos a continuación, podrá convertir un archivo PDF a formato XML.

## requisitos previos
Antes de comenzar, asegúrese de cumplir con los siguientes requisitos previos:

- Conocimientos básicos del lenguaje de programación C#.
- Biblioteca Aspose.PDF para .NET instalada en su sistema.
- Un entorno de desarrollo como Visual Studio.

## Paso 1: Cargar el documento PDF
En este paso, cargaremos el archivo PDF de origen usando Aspose.PDF para .NET. Siga el código a continuación:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cargue el documento PDF
Document doc = new Document(dataDir + "input.pdf");
```

 Asegúrese de reemplazar`"YOUR DOCUMENTS DIRECTORY"` con el directorio real donde se encuentra su archivo PDF.

## Paso 2: guardar el archivo XML resultante
Ahora guardaremos el archivo PDF convertido en formato XML. Usa el siguiente código:

```csharp
// Guardar salida como XML
doc.Save(dataDir + "PDFToXML_out.xml", SaveFormat.MobiXml);
```

 El código anterior guarda el archivo PDF convertido en formato XML con el nombre de archivo`"PDFToXML_out.xml"`.

### Código fuente de ejemplo para PDF a XML utilizando Aspose.Words para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";            
// Cargar archivo PDF de origen
Document doc = new Document(dataDir + "input.pdf");
// Guardar salida en formato XML
doc.Save(dataDir + "PDFToXML_out.xml", SaveFormat.MobiXml);
```

## Conclusión
En este tutorial, cubrimos el proceso paso a paso de convertir un archivo PDF a XML usando Aspose.PDF para .NET. Siguiendo las instrucciones descritas anteriormente, ahora debería poder convertir un archivo PDF a formato XML. Esta función es útil cuando desea extraer contenido estructurado de un archivo PDF y procesarlo en un formato XML para su uso posterior.