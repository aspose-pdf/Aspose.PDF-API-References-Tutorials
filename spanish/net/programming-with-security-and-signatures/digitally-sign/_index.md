---
title: Firmar digitalmente
linktitle: Firmar digitalmente
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a firmar digitalmente un archivo PDF con Aspose.PDF para .NET.
type: docs
weight: 40
url: /es/net/programming-with-security-and-signatures/digitally-sign/
---

En este tutorial, lo guiaremos a través del proceso de firma digital de un archivo PDF con Aspose.PDF para .NET. La firma digital garantiza la autenticidad e integridad del documento, al agregar una huella digital única.

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
using System.Collections.Generic;
```

## Paso 3: Firma digital

El primer paso es firmar digitalmente el archivo PDF. El código proporcionado muestra cómo hacer una firma digital con Aspose.PDF para .NET.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pbxFile = "";
string inFile = dataDir + @"DigitallySign.pdf";
string outFile = dataDir + @"DigitallySign_out.pdf";
using (Document document = new Document(inFile))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         PKCS7 pkcs = new PKCS7(pbxFile, "WebSales");
         DocMDPSignature docMdpSignature = new DocMDPSignature(pkcs, DocMDPAccessPermissions.FillingInForms);
         System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
         signature.SignatureAppearance = dataDir + @"aspose-logo.jpg";
         signature.Certify(1, "Reason for signing", "Contact", "Location", true, rect, docMdpSignature);
         signature.Save(outFile);
     }
}
```

Este código carga un archivo PDF, crea una firma digital con una apariencia específica y luego guarda el archivo PDF con la firma agregada.

## Paso 4: Verificación de firma

Después de agregar la firma digital, puede verificar si el archivo PDF contiene una firma válida.

```csharp
using(Document document = new Document(outFile))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         IList<string> sigNames = signature. GetSignNames();
         if (sigNames.Count > 0)
         {
             if (signature.VerifySigned(sigNames[0] as string))
             {
                 if (signature.IsCertified)
                 {
                     if (signature.GetAccessPermissions() == DocMDPAccessPermissions.FillingInForms)
                     {
                         // Hacer algo
                     }
                 }
             }
         }
     }
}
```

Este código verifica la primera firma del archivo PDF y realiza acciones adicionales si la firma está certificada y tiene permisos específicos.

### Ejemplo de código fuente para Digitally Sign usando Aspose.PDF para .NET 
```csharp
try
{
	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENTS DIRECTORY";
	string pbxFile = "";
	string inFile = dataDir + @"DigitallySign.pdf";
	string outFile = dataDir + @"DigitallySign_out.pdf";
	using (Document document = new Document(inFile))
	{
		using (PdfFileSignature signature = new PdfFileSignature(document))
		{
			PKCS7 pkcs = new PKCS7(pbxFile, "WebSales"); // Usar objetos PKCS7/PKCS7Detached
			DocMDPSignature docMdpSignature = new DocMDPSignature(pkcs, DocMDPAccessPermissions.FillingInForms);
			System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
			// Establecer la apariencia de la firma
			signature.SignatureAppearance = dataDir + @"aspose-logo.jpg";
			//Crea cualquiera de los tres tipos de firma
			signature.Certify(1, "Signature Reason", "Contact", "Location", true, rect, docMdpSignature);
			// Guardar archivo PDF de salida
			signature.Save(outFile);
		}
	}
	using (Document document = new Document(outFile))
	{
		using (PdfFileSignature signature = new PdfFileSignature(document))
		{
			IList<string> sigNames = signature.GetSignNames();
			if (sigNames.Count > 0) // ¿Alguna firma?
			{
				if (signature.VerifySigned(sigNames[0] as string)) // Verificar primero
				{
					if (signature.IsCertified) // ¿Certificado?
					{
						if (signature.GetAccessPermissions() == DocMDPAccessPermissions.FillingInForms) // Obtener permiso de acceso
						{
							// Hacer algo
						}
					}
				}
			}
		}
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusión

¡Felicidades! Ha realizado con éxito una firma digital en un archivo PDF utilizando Aspose.PDF para .NET. Este tutorial cubrió el proceso paso a paso, desde agregar la firma digital hasta verificar su validez. Ahora puede utilizar esta función para proteger sus archivos PDF con firmas digitales.