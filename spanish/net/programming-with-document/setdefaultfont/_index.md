---
title: Establecer fuente predeterminada
linktitle: Establecer fuente predeterminada
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a configurar la fuente predeterminada para un documento PDF usando Aspose.PDF para .NET con esta guía paso a paso.
type: docs
weight: 280
url: /es/net/programming-with-document/setdefaultfont/
---
Si está trabajando con documentos PDF en .NET, es posible que encuentre problemas en los que la fuente utilizada en el PDF no esté disponible en el sistema donde se está viendo o imprimiendo. Esto puede resultar en que el texto aparezca incorrectamente o no aparezca en absoluto. Aspose.PDF para .NET ofrece una solución a este problema al permitirle establecer una fuente predeterminada para el documento. En este ejemplo, cómo configurar la fuente predeterminada usando Aspose.PDF para .NET.

## Paso 1: establezca la ruta al directorio del documento

necesitamos establecer la ruta al directorio donde se encuentra nuestro documento PDF. Guardaremos esta ruta en una variable llamada "dataDir".

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Cargue el documento PDF

 Comenzaremos cargando un documento PDF existente al que le faltan fuentes. En este ejemplo, supondremos que el documento PDF se encuentra en el directorio especificado por el`dataDir` variable.

```csharp
string documentName = dataDir + "input.pdf";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
    // el código va aquí
}
```

## Paso 3: establece la fuente predeterminada

 A continuación, estableceremos la fuente predeterminada para el documento PDF usando el`PdfSaveOptions`clase. En este ejemplo, estableceremos la fuente predeterminada en "Arial".

```csharp
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.DefaultFontName = "Arial";
```

## Paso 4: Guarde el documento actualizado

Finalmente, guardaremos el documento actualizado en un archivo nuevo. En este ejemplo, guardaremos el documento actualizado en un archivo llamado "output_out.pdf" en el mismo directorio que el archivo de entrada.

```csharp
document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
```

### Ejemplo de código fuente para establecer la fuente predeterminada usando Aspose.PDF para .NET

```csharp
	
	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Cargue un documento PDF existente al que le falta la fuente
	string documentName = dataDir + "input.pdf";
	string newName = "Arial";
	using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
	using (Document document = new Document(fs))
	{
		PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
		// Especificar nombre de fuente predeterminado
		pdfSaveOptions.DefaultFontName = newName;
		document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
	}
	
```
