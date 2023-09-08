---
title: Iniciar sesión digitalmente en un archivo PDF
linktitle: Iniciar sesión digitalmente en un archivo PDF
second_title: Aspose.PDF para referencia de API .NET
description: Aprenda a iniciar sesión digitalmente en un archivo PDF con Aspose.PDF para .NET.
type: docs
weight: 40
url: /es/net/programming-with-security-and-signatures/digitally-sign/
---
En este tutorial, lo guiaremos a través del proceso de firma digital en un archivo PDF usando Aspose.PDF para .NET. La firma digital garantiza la autenticidad e integridad del documento, añadiendo una huella electrónica única.

## Paso 1: requisitos previos

Antes de comenzar, asegúrese de tener los siguientes requisitos previos:

- Conocimientos básicos del lenguaje de programación C#.
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

## Paso 3: firma digital

El primer paso es firmar digitalmente el archivo PDF. El código proporcionado muestra cómo crear una firma digital con Aspose.PDF para .NET.

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

### Código fuente de muestra para firmar digitalmente usando Aspose.PDF para .NET 
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
			PKCS7 pkcs = new PKCS7(pbxFile, "WebSales"); // Utilice objetos PKCS7/PKCS7Detached
			DocMDPSignature docMdpSignature = new DocMDPSignature(pkcs, DocMDPAccessPermissions.FillingInForms);
			System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
			// Establecer apariencia de firma
			signature.SignatureAppearance = dataDir + @"aspose-logo.jpg";
			// Crea cualquiera de los tres tipos de firma
			signature.Certify(1, "Signature Reason", "Contact", "Location", true, rect, docMdpSignature);
			// Guardar el archivo PDF de salida
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
				if (signature.VerifySigned(sigNames[0] as string)) // Verificar el primero
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

¡Enhorabuena! Ha realizado con éxito una firma digital en un archivo PDF utilizando Aspose.PDF para .NET. Este tutorial cubrió el proceso paso a paso, desde agregar la firma digital hasta verificar su validez. Ahora puede utilizar esta función para proteger sus archivos PDF con firmas digitales.

### Preguntas frecuentes

#### P: ¿Cuál es el propósito de este tutorial?

R: Este tutorial lo guía a través del proceso de firma digital de un archivo PDF usando Aspose.PDF para .NET. Las firmas digitales añaden una huella digital electrónica para garantizar la autenticidad e integridad del documento.

#### P: ¿Qué requisitos previos se requieren antes de comenzar?

R: Antes de comenzar, asegúrese de tener conocimientos básicos del lenguaje de programación C#, tener instalado Visual Studio y tener instalada la biblioteca Aspose.PDF para .NET.

#### P: ¿Cómo configuro el entorno de desarrollo?

R: Siga los pasos proporcionados para configurar su entorno de desarrollo, incluida la creación de un nuevo proyecto de C# en Visual Studio y la importación de los espacios de nombres necesarios.

#### P: ¿Cómo agrego una firma digital a un archivo PDF?

 R: El código de muestra proporcionado demuestra cómo cargar un archivo PDF, crear una firma digital, especificar la apariencia y guardar el archivo PDF firmado. La firma digital se añade mediante el`Certify` método de la`PdfFileSignature` objeto.

#### P: ¿Cómo verifico la validez de una firma digital?

R: Después de agregar la firma digital, puede usar el código de muestra para verificar la validez de la firma. Comprueba si la firma está certificada y tiene permisos de acceso específicos.

####  P: ¿Qué significa el`PKCS7` object represent?

 R: El`PKCS7` El objeto se utiliza para proporcionar la funcionalidad criptográfica para firmas digitales. Se utiliza para crear la firma digital en el código de muestra proporcionado.

#### P: ¿Puedo personalizar la apariencia de la firma digital?

 R: Sí, puede personalizar la apariencia de la firma digital especificando la ruta a una imagen en el`SignatureAppearance` propiedad de la`PdfFileSignature` objeto.

#### P: ¿Qué pasa si la firma no es válida?

R: Si la firma no es válida, el proceso de verificación fallará y las acciones correspondientes dentro del bloque del código de verificación no se ejecutarán.

#### P: ¿Cómo puedo garantizar la seguridad de mis firmas digitales?

R: Las firmas digitales son seguras por diseño y utilizan técnicas criptográficas para garantizar la autenticidad y la integridad. Asegúrese de mantener segura su clave privada y siga las mejores prácticas para el manejo de firmas digitales.

#### P: ¿Puedo agregar varias firmas digitales a un PDF?

 R: Sí, puede agregar varias firmas digitales a un archivo PDF usando el`PdfFileSignature` objetos`Sign` o`Certify` métodos. Cada firma tendrá su propia apariencia y configuración.