---
title: XML a PDFEstablecer ruta de imagen
linktitle: XML a PDFEstablecer ruta de imagen
second_title: Referencia de API de Aspose.PDF para .NET
description: Guía paso a paso para establecer la ruta de una imagen al convertir XML a PDF con Aspose.PDF para .NET.
type: docs
weight: 340
url: /es/net/document-conversion/xml-to-pdfset-image-path/
---

En este tutorial, lo guiaremos paso a paso sobre cómo configurar la ruta de una imagen al convertir un archivo XML a PDF utilizando la biblioteca Aspose.PDF para .NET. Detallaremos el código fuente de C# provisto y le mostraremos cómo implementarlo en sus propios proyectos. Al final de este tutorial, puede especificar fácilmente la ruta de una imagen al convertir XML a PDF.

## Paso 1: Establecer rutas de archivos
```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string inXml = dataDir + "input.xml";
string inFile = dataDir + "aspose-logo.jpg";
string outFile = dataDir + "output_out.pdf";
```
 Defina las rutas de los archivos XML de entrada, la imagen a utilizar y el archivo PDF de salida. Reemplazar`"YOUR DOCUMENTS DIRECTORY"` con la ruta donde guardó sus archivos.

## Paso 2: crear una instancia de un objeto de documento
```csharp
Document doc = new Document();
```
Cree una instancia del objeto Documento.

## Paso 3: vincular el archivo XML de origen
```csharp
doc. BindXml(inXml);
```
Vincula el archivo XML de origen al documento.

## Paso 4: establecer la ruta de la imagen
```csharp
Image image = (Image)doc.GetObjectById("testImg");
image.File = inFile;
```
Obtenga la referencia del objeto de imagen del XML usando su ID y establezca la ruta de la imagen que se usará.

## Paso 5: Guarde el archivo PDF resultante
```csharp
doc.Save(outFile);
```
Guarde el archivo PDF resultante en el directorio especificado.

### Código fuente de ejemplo para XML a PDF Establecer ruta de imagen usando Aspose.Words para .NET

```csharp
try
{
	
	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	string inXml = dataDir + "input.xml";
	string inFile = dataDir + "aspose-logo.jpg";
	string outFile = dataDir + "output_out.pdf";
	Document doc = new Document();
	doc.BindXml(inXml);
	Image image = (Image)doc.GetObjectById("testImg");
	image.File = inFile;
	doc.Save(outFile);
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusión
En este tutorial, aprendimos cómo configurar la ruta de una imagen al convertir XML a PDF usando la biblioteca Aspose.PDF para .NET. Siguiendo los pasos proporcionados, puede especificar fácilmente la ruta de la imagen en sus propias conversiones de XML a PDF.