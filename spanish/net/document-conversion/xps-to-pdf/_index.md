---
title: XPS a PDF
linktitle: XPS a PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Guía paso a paso para convertir archivos XPS a PDF con Aspose.PDF para .NET.
type: docs
weight: 350
url: /es/net/document-conversion/xps-to-pdf/
---

En este tutorial, lo guiaremos a través de cómo convertir un archivo XPS a PDF utilizando la biblioteca Aspose.PDF para .NET paso a paso. Detallaremos el código fuente de C# provisto y le mostraremos cómo implementarlo en sus propios proyectos. Al final de este tutorial, podrá convertir fácilmente archivos XPS a documentos PDF.

## Paso 1: establecer el directorio de documentos
```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```
 Reemplazar`"YOUR DOCUMENTS DIRECTORY"` con la ruta donde guardó sus archivos.

## Paso 2: Cree una instancia del objeto LoadOptions mediante las opciones de carga de XPS
```csharp
Aspose.Pdf.LoadOptions options = new XpsLoadOptions();
```
Cree una instancia del objeto LoadOptions mediante las opciones de carga de XPS.

## Paso 3: crear el objeto de documento
```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "XPSToPDF.xps", options);
```
Cree un objeto Documento especificando el archivo XPS de entrada y las opciones de carga.

## Paso 4: Guarde el documento PDF resultante
```csharp
document.Save(dataDir + "XPSToPDF_out.pdf");
```
Guarde el documento PDF resultante en el directorio especificado.

### Código fuente de ejemplo para XPS a PDF usando Aspose.Words para .NET

```csharp
try
{
	
	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Crear una instancia del objeto LoadOption usando la opción de carga XPS
	Aspose.Pdf.LoadOptions options = new XpsLoadOptions();

	// Crear objeto de documento
	Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "XPSToPDF.xps", options);

	// Guarde el documento PDF resultante
	document.Save(dataDir + "XPSToPDF_out.pdf");
	
}
catch(Exception ex)
   
{
	Console.WriteLine(ex.Message);
}
```

## Conclusión
En este tutorial, aprendimos cómo convertir un archivo XPS a PDF usando la biblioteca Aspose.PDF para .NET. Siguiendo los pasos proporcionados, puede realizar fácilmente esta conversión en sus propias aplicaciones. Obtenga resultados precisos y profesionales al convertir archivos XPS a PDF.