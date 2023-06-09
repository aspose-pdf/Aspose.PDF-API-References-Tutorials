---
title: Firmar digitalmente con sello de tiempo
linktitle: Firmar digitalmente con sello de tiempo
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a realizar una firma digital con marca de tiempo en un archivo PDF utilizando Aspose.PDF para .NET.
type: docs
weight: 50
url: /es/net/programming-with-security-and-signatures/digitally-sign-with-time-stamp/
---

En este tutorial, lo guiaremos a través del proceso de firma digital de un archivo PDF con marca de tiempo usando Aspose.PDF para .NET. La firma digital con sello de tiempo garantiza la autenticidad e integridad del documento, al agregar una huella digital con sello de tiempo.

## Paso 1: Requisitos previos

Antes de comenzar, asegúrese de tener los siguientes requisitos previos:

- Conocimientos básicos del lenguaje de programación C#
- Instalación de Visual Studio en su máquina
- Biblioteca Aspose.PDF para .NET instalada

## Paso 2: configuración del entorno

Para comenzar, siga estos pasos para configurar su entorno de desarrollo:

1. Abra Visual Studio y cree un nuevo proyecto de C#.
2. Importe los espacios de nombres requeridos en su archivo de código:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
```

## Paso 3: Firma digital con sello de tiempo

El primer paso es realizar la firma digital con sello de tiempo en el archivo PDF. El código proporcionado muestra cómo lograr esta firma con Aspose.PDF para .NET.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pfxFile = "";
using (Document document = new Document(dataDir + @"DigitallySign.pdf"))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
         TimestampSettings timestampSettings = new TimestampSettings("https:\\your_timestamp_settings", "user:password");
         pkcs. TimestampSettings = timestampSettings;
         System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
         signature.Sign(1, "Reason for signing", "Contact", "Location", true, rect, pkcs);
         signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
     }
}
```

Este código carga un archivo PDF, crea una firma digital con marca de tiempo utilizando un archivo PFX (clave privada) y los parámetros de marca de tiempo especificados. Luego, la firma se agrega al archivo PDF y se guarda con el sufijo "_afuera".

### Ejemplo de código fuente para Firmar digitalmente con marca de tiempo usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pfxFile = "";
using (Document document = new Document(dataDir + @"DigitallySign.pdf"))
{
	using (PdfFileSignature signature = new PdfFileSignature(document))
	{
		PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
		TimestampSettings timestampSettings = new TimestampSettings("https:\\your_timestamp_settings", "user:password"); // Se puede omitir el usuario/contraseña
		pkcs.TimestampSettings = timestampSettings;
		System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
		//Crea cualquiera de los tres tipos de firma
		signature.Sign(1, "Signature Reason", "Contact", "Location", true, rect, pkcs);
		// Guardar archivo PDF de salida
		signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
	}
}
```

## Conclusión

¡Felicidades! Ha realizado con éxito una firma digital con marca de tiempo en un archivo PDF usando Aspose.PDF para .NET. Este tutorial cubrió el proceso paso a paso desde la creación de la firma hasta el guardado del archivo PDF actualizado. Ahora puede usar esta función para agregar firmas digitales con marca de tiempo a sus archivos PDF.