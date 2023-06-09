---
title: EPUB a PDF
linktitle: EPUB a PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Guía paso a paso para convertir EPUB a PDF utilizando Aspose.PDF para .NET.
type: docs
weight: 30
url: /es/net/document-conversion/epub-to-pdf/
---

En este tutorial, lo guiaremos a través del proceso de conversión de un archivo EPUB a PDF utilizando la biblioteca Aspose.PDF para .NET. EPUB (publicación electrónica) es un formato ampliamente utilizado para libros electrónicos, mientras que PDF (formato de documento portátil) es un estándar de intercambio de documentos. Siguiendo los pasos que se detallan a continuación, podrá convertir archivos EPUB a formato PDF sin esfuerzo.

## requisitos previos
Antes de comenzar, asegúrese de cumplir con los siguientes requisitos previos:

- Conocimientos básicos del lenguaje de programación C#.
- Biblioteca Aspose.PDF para .NET instalada en su sistema.
- Un entorno de desarrollo como Visual Studio.

## Paso 1: Cargue el archivo EPUB
En este paso, cargaremos el archivo EPUB usando Aspose.PDF para .NET. Siga el código a continuación:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Crea una instancia del objeto LoadOption usando la opción de carga EPUB
EpubLoadOptions epubload = new EpubLoadOptions();

// Crear un objeto de documento
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document(dataDir + "EPUBToPDF.epub", epubload);
```

 Asegúrese de reemplazar`"YOUR DOCUMENTS DIRECTORY"` con el directorio real donde se encuentra su archivo EPUB.

## Paso 2: conversión de EPUB a PDF
Ahora que hemos subido el archivo EPUB, podemos proceder con la conversión a PDF. Usa el siguiente código:

```csharp
// Guarde el documento PDF resultante
pdf. Save(dataDir + "EPUBToPDF_out.pdf");
```

 El código anterior convierte el archivo EP EPUB cargado en formato PDF y lo guarda como nombre de archivo`"EPUBToPDF_out.pdf"`. Asegúrese de proporcionar la ruta y el nombre de archivo correctos para el archivo PDF de salida.


 Reemplazar`"YOUR DOCUMENTS DIRECTORY"` con el directorio deseado donde desea guardar el archivo PDF de salida.

### Código fuente de ejemplo para EPUB a PDF usando Aspose.PDF para .NET

```csharp
try
{
	
	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Crear una instancia del objeto LoadOption usando la opción de carga EPUB
	EpubLoadOptions epubload = new EpubLoadOptions();

	// Crear objeto de documento
	Aspose.Pdf.Document pdf = new Aspose.Pdf.Document(dataDir + "EPUBToPDF.epub", epubload);

	// Guarde el documento PDF resultante
	pdf.Save(dataDir + "EPUBToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}

```

## Conclusión
En este tutorial, cubrimos el proceso paso a paso de convertir un archivo EPUB a PDF utilizando la biblioteca Aspose.PDF para .NET. Siguiendo las instrucciones descritas anteriormente, ahora debería poder convertir archivos EPUB a formato PDF sin esfuerzo. Esta conversión abre posibilidades para compartir, imprimir y archivar sus documentos.

