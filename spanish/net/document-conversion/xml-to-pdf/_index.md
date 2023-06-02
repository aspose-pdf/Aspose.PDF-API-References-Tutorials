---
title: XML a PDF
linktitle: XML a PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Guía paso a paso para convertir archivos XML a PDF utilizando Aspose.PDF para .NET.
type: docs
weight: 330
url: /es/net/document-conversion/xml-to-pdf/
---

En este tutorial, lo guiaremos a través de cómo convertir un archivo XML a PDF utilizando la biblioteca Aspose.PDF para .NET paso a paso. Detallaremos el código fuente de C# provisto y le mostraremos cómo implementarlo en sus propios proyectos. Al final de este tutorial, podrá convertir fácilmente archivos XML a documentos PDF.

## Paso 1: establecer el directorio de documentos
```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```
 Reemplazar`"YOUR DOCUMENTS DIRECTORY"` con la ruta donde desea guardar el archivo PDF generado.

## Paso 2: crear una instancia de un objeto de documento
```csharp
Document doc = new Document();
```
Cree una instancia del objeto Documento.

## Paso 3: vincular el archivo XML de origen
```csharp
doc.BindXml(dataDir + "sample.xml");
```
Vincula el archivo XML de origen al documento.

## Paso 4: obtenga la referencia del objeto de la página desde XML
```csharp
Page page = (Page)doc.GetObjectById("mainSection");
```
Obtenga la referencia del objeto de página del XML usando su ID.

## Paso 5: obtenga la referencia del segmento de texto del XML
```csharp
TextSegment segment = (TextSegment)doc.GetObjectById("boldHtml");
segment = (TextSegment)doc.GetObjectById("strongHtml");
```
Obtenga referencias de segmentos de texto de XML usando sus ID. Puede agregar más segmentos según sea necesario.

## Paso 6: Guarde el archivo PDF resultante
```csharp
doc.Save(dataDir + "XMLToPDF_out.pdf");
```
Guarde el archivo PDF resultante en el directorio especificado.

### Código fuente de ejemplo para XML a PDF usando Aspose.Words para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instanciar objeto de documento
Document doc = new Document();
// Vincular archivo XML de origen
doc.BindXml( dataDir + "sample.xml");
// Obtenga la referencia del objeto de la página desde XML
Page page = (Page)doc.GetObjectById("mainSection");
// Obtenga la referencia del primer TextSegment con ID boldHtml
TextSegment segment = (TextSegment)doc.GetObjectById("boldHtml");
// Obtenga la referencia del segundo TextSegment con ID strongHtml
segment = (TextSegment)doc.GetObjectById("strongHtml");
// Guardar el archivo PDF resultante
doc.Save(dataDir + "XMLToPDF_out.pdf");
```

## Conclusión
En este tutorial, aprendimos cómo convertir un archivo XML a PDF utilizando la biblioteca Aspose.PDF para .NET. Hemos detallado el código fuente de C# provisto y explicado cada paso del proceso de conversión. Siguiendo estas instrucciones, puede integrar fácilmente la función de conversión de XML a PDF en sus propias aplicaciones .NET.