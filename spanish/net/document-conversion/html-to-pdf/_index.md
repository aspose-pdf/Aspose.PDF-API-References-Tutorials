---
title: HTML a PDF
linktitle: HTML a PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Guía paso a paso para convertir HTML a PDF utilizando Aspose.PDF para .NET.
type: docs
weight: 50
url: /es/net/document-conversion/html-to-pdf/
---

En este tutorial, lo guiaremos a través del proceso de conversión de un archivo HTML a PDF usando Aspose.PDF para .NET. HTML (HyperText Markup Language) es un lenguaje de marcado utilizado para estructurar y presentar contenido web. Siguiendo los pasos a continuación, podrá convertir archivos HTML a formato PDF.

## requisitos previos
Antes de comenzar, asegúrese de cumplir con los siguientes requisitos previos:

- Conocimientos básicos del lenguaje de programación C#.
- Biblioteca Aspose.PDF para .NET instalada en su sistema.
- Un entorno de desarrollo como Visual Studio.

## Paso 1: Cargar el archivo HTML
En este paso, cargaremos el archivo HTML usando Aspose.PDF para .NET. Siga el código a continuación:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

HtmlLoadOptions options = new HtmlLoadOptions();
options.CustomLoaderOfExternalResources = new LoadOptions.ResourceLoadingStrategy(SamePictureLoader);

Document pdfDocument = new Document(dataDir + "HTMLToPDF.html", options);
```

 Asegúrese de reemplazar`"YOUR DOCUMENTS DIRECTORY"` con el directorio real donde se encuentra su archivo HTML.

## Paso 2: Opciones de carga de HTML
Ahora que hemos cargado el archivo HTML, podemos especificar opciones de carga específicas. Usa el siguiente código:

```csharp
options.CustomLoaderOfExternalResources = new LoadOptions.ResourceLoadingStrategy(SamePictureLoader);
```

El código anterior le dice a Aspose.PDF que use una estrategia de carga personalizada para recursos externos, como imágenes. Puede personalizar esta política para satisfacer sus necesidades.

## Paso 3: conversión de HTML a PDF
Después de cargar el archivo HTML y especificar las opciones de carga, podemos proceder con la conversión a PDF. Usa el siguiente código:

```csharp
pdfDocument.Save("HTMLToPDF_out.pdf");
```

### Código fuente de ejemplo para HTML a PDF usando Aspose.Words para .NET

```csharp
try
{
	
	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	HtmlLoadOptions options = new HtmlLoadOptions();
	options.CustomLoaderOfExternalResources = new LoadOptions.ResourceLoadingStrategy(SamePictureLoader);

	Document pdfDocument = new Document(dataDir + "HTMLToPDF.html", options);
	pdfDocument.Save("HTMLToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusión
En este tutorial, cubrimos el proceso paso a paso. paso de convertir un archivo HTML a PDF usando Aspose.PDF para .NET. Siguiendo las instrucciones descritas anteriormente, ahora debería poder convertir archivos HTML a formato PDF. Esta característica puede ser útil cuando necesita generar documentos PDF a partir de contenido HTML.

