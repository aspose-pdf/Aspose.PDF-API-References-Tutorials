---
title: Establecer metadatos XMP
linktitle: Establecer metadatos XMP
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a configurar XMPMetadata en archivos PDF usando Aspose.PDF para .NET. Siga esta guía paso a paso.
type: docs
weight: 330
url: /es/net/programming-with-document/setxmpmetadata/
---
En este artículo, proporcionaremos una guía paso a paso sobre cómo usar Aspose.PDF para .NET para configurar metadatos XMP en un archivo PDF. Proporcionaremos un código fuente de ejemplo completo al final del artículo.

## Paso 1: establezca la ruta al directorio del documento

Antes de comenzar, debemos establecer la ruta al directorio donde se encuentra nuestro documento PDF. Guardaremos esta ruta en una variable llamada "dataDir".

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Asegúrese de reemplazar`YOUR DOCUMENT DIRECTORY` con la ruta real a su archivo PDF.

## Paso 2: Abra el archivo PDF

El primer paso es abrir el archivo PDF para el que desea configurar los metadatos XMP. Para hacer esto, deberá crear una nueva`Document` objeto y pase la ruta a su archivo PDF.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Abrir documento
Document pdfDocument = new Document(dataDir + "SetXMPMetadata.pdf");
```

## Paso 3: Establecer propiedades de metadatos XMP

Ahora que tiene su archivo PDF abierto, puede comenzar a configurar las propiedades de los metadatos XMP. Las propiedades que establezca dependerán de sus necesidades específicas, pero aquí hay algunas propiedades comunes que quizás desee establecer:

- `xmp:CreateDate`: La fecha de creación del archivo PDF.
- `xmp:Nickname`: Un apodo o alias para el archivo PDF.
- `xmp:CustomProperty`: una propiedad personalizada con un valor que especifique.

 Para establecer estas propiedades, puede utilizar el`Metadata` propiedad de la`Document` objeto. Aquí hay un ejemplo:

```csharp
// Establecer propiedades
pdfDocument.Metadata["xmp:CreateDate"] = DateTime.Now;
pdfDocument.Metadata["xmp:Nickname"] = "Nickname";
pdfDocument.Metadata["xmp:CustomProperty"] = "Custom Value";
```

En este tutorial, estableceremos la fecha de creación en la fecha y hora actuales, el apodo en "Apodo" y una propiedad personalizada en "Valor personalizado". Puede reemplazar estos valores por los suyos propios.

## Paso 4: Guarde el archivo PDF

 Después de configurar las propiedades de los metadatos XMP, debe guardar el archivo PDF. Para ello, puede utilizar el`Save` metodo de la`Document` objeto y pase la ruta donde desea guardar el archivo PDF actualizado.

```csharp
dataDir = dataDir + "SetXMPMetadata_out.pdf";
//Guardar documento
pdfDocument.Save(dataDir);
```

### Ejemplo de código fuente para establecer XMPMetadata usando Aspose.PDF para .NET

Aquí está el código fuente de ejemplo completo para configurar XMPMetadata usando Aspose.PDF para .NET:

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Abrir documento
	Document pdfDocument = new Document(dataDir + "SetXMPMetadata.pdf");

	// Establecer propiedades
	pdfDocument.Metadata["xmp:CreateDate"] = DateTime.Now;
	pdfDocument.Metadata["xmp:Nickname"] = "Nickname";
	pdfDocument.Metadata["xmp:CustomProperty"] = "Custom Value";

	dataDir = dataDir + "SetXMPMetadata_out.pdf";
	//Guardar documento
	pdfDocument.Save(dataDir);
	
	Console.WriteLine("\nXMP metadata in a pdf file setup successfully.\nFile saved at " + dataDir);

```
