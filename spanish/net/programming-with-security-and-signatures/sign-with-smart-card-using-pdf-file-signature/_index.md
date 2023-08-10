---
title: Firmar con tarjeta inteligente mediante firma de archivo PDF
linktitle: Firmar con tarjeta inteligente mediante firma de archivo PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Firme sus archivos PDF de forma segura con una tarjeta inteligente utilizando Aspose.PDF para .NET.
type: docs
weight: 110
url: /es/net/programming-with-security-and-signatures/sign-with-smart-card-using-pdf-file-signature/
---
La firma digital con una tarjeta inteligente es una forma segura de firmar archivos PDF. Con Aspose.PDF para .NET, puede firmar fácilmente un archivo PDF con una tarjeta inteligente siguiendo el siguiente código fuente:

## Paso 1: importa las bibliotecas requeridas

Antes de comenzar, debe importar las bibliotecas necesarias para su proyecto de C#. Aquí están las directivas de importación necesarias:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## Paso 2: establecer la ruta a la carpeta de documentos

 En este paso, debe especificar la ruta a la carpeta que contiene el archivo PDF que desea firmar. Reemplazar`"YOUR DOCUMENTS DIRECTORY"`en el siguiente código con la ruta real a su carpeta de documentos:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 3: Cargue el documento PDF

Ahora cargaremos el documento PDF a firmar utilizando el siguiente código:

```csharp
Document doc = new Document(dataDir + "blank.pdf");
```

## Paso 4: Realizar la firma con la tarjeta inteligente

 En este paso realizaremos la firma con la tarjeta inteligente utilizando el`PdfFileSignature` clase de la`Facades`biblioteca. Seleccionamos el certificado de tarjeta inteligente del almacén de certificados de Windows y especificamos la información de firma necesaria. Aquí está el código correspondiente:

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature())
{
     pdfSign.BindPdf(doc);

     // Seleccione el certificado en la tienda
     X509Store store = new X509Store(StoreLocation.CurrentUser);
     store.Open(OpenFlags.ReadOnly);
     X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
     ExternalSignature externalSignature = new ExternalSignature(sel[0]);

     pdfSign.SignatureAppearance = dataDir + "demo.png";
     pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
     pdfSign.Save(dataDir + "externalSignature2.pdf");
}
```

## Paso 5: Verificar firma

 Finalmente, verificamos la firma del archivo PDF firmado usando el`PdfFileSignature` clase. Obtenemos los nombres de las firmas y los verificamos uno por uno. Si una firma falla en la verificación, se lanza una excepción. Aquí está el código correspondiente:

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature2.pdf")))
{
     IList<string> sigNames = pdfSign. GetSignNames();
     for (int index = 0; index <= sigNames.Count - 1; index++)
     {
         if (!pdfSign.VerifySigned(sigNames[index]) || !pdfSign.VerifySignature(sigNames[index]))
         {
             throw new ApplicationException("Unverified");
         }
     }
}
```

### Ejemplo de código fuente para Firmar con tarjeta inteligente mediante la firma de archivos PDF mediante Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "blank.pdf");
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature())
{
	pdfSign.BindPdf(doc);
	// Firmar con selección de certificado en el almacén de certificados de Windows
	System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
	store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
	// Eligió manualmente el certificado en la tienda
	System.Security.Cryptography.X509Certificates.X509Certificate2Collection sel = System.Security.Cryptography.X509Certificates.X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, System.Security.Cryptography.X509Certificates.X509SelectionFlag.SingleSelection);
	Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0]);
	pdfSign.SignatureAppearance = dataDir + "demo.png";
	pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
	pdfSign.Save(dataDir + "externalSignature2.pdf");
}
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature(new Document(dataDir + "externalSignature2.pdf")))
{
	IList<string> sigNames = pdfSign.GetSignNames();
	for (int index = 0; index <= sigNames.Count - 1; index++)
	{
		if (!pdfSign.VerifySigned(sigNames[index]) || !pdfSign.VerifySignature(sigNames[index]))
		{
			throw new ApplicationException("Not verified");
		}
	}
}
```

## Conclusión

¡Felicidades! Ahora tiene una guía paso a paso para firmar un archivo PDF con una tarjeta inteligente utilizando Aspose.PDF para .NET. Puede usar este código para agregar firmas digitales seguras a sus documentos PDF.

Asegúrese de consultar la documentación oficial de Aspose.PDF para obtener más información sobre las funciones avanzadas de gestión de certificados y firma digital.

### Preguntas frecuentes

#### P: ¿Por qué debo considerar firmar archivos PDF con una tarjeta inteligente?

R: La firma de archivos PDF con una tarjeta inteligente mejora la seguridad al garantizar la autenticidad e integridad del documento. Las firmas basadas en tarjetas inteligentes brindan un mayor nivel de confianza y cumplimiento.

#### P: ¿Cómo funciona la firma digital basada en tarjetas inteligentes?

R: La firma digital basada en tarjetas inteligentes implica el uso de una clave criptográfica almacenada en una tarjeta inteligente para crear una firma digital única. Esta firma se adjunta al archivo PDF, lo que permite a los destinatarios verificar el origen y la integridad del documento.

#### P: ¿Cuál es el papel de Aspose.PDF para .NET en la firma basada en tarjetas inteligentes?

R: Aspose.PDF para .NET proporciona un conjunto integral de herramientas y bibliotecas para facilitar la firma digital de archivos PDF basada en tarjetas inteligentes. Simplifica el proceso y garantiza la firma segura de documentos.

#### P: ¿Puedo elegir un certificado de tarjeta inteligente específico para firmar?

R: Sí, puede seleccionar un certificado de tarjeta inteligente específico del almacén de certificados de Windows para firmar. Aspose.PDF para .NET le permite integrar sin problemas la selección de certificados en su aplicación.

#### P: ¿Cómo maneja el código fuente provisto la firma basada en tarjetas inteligentes?

R: El código fuente muestra cómo vincular un documento PDF, seleccionar un certificado de tarjeta inteligente, especificar la información de firma y crear una firma digital. También muestra cómo verificar la validez de la firma.

#### P: ¿Puedo aplicar varias firmas usando tarjetas inteligentes en un solo archivo PDF?

R: Absolutamente, puede aplicar múltiples firmas basadas en tarjetas inteligentes a un solo archivo PDF. Cada firma es única y contribuye a la seguridad general del documento.

#### P: ¿Qué pasa si una firma falla en la verificación durante el paso de verificación?

R: Si una firma falla en la verificación, se genera una excepción que indica que la firma no es válida. Esto garantiza que solo se acepten firmas válidas y confiables.

#### P: ¿La firma basada en tarjetas inteligentes es compatible con todos los tipos de documentos PDF?

R: Sí, la firma basada en tarjetas inteligentes es compatible con todo tipo de documentos PDF. Puede aplicar firmas digitales a varios tipos de archivos PDF, incluidos formularios, informes y más.

#### P: ¿Cómo puedo obtener más información sobre la firma digital avanzada y la gestión de certificados?

R: Explore la documentación oficial de Aspose.PDF para obtener información detallada sobre las funciones avanzadas de firma digital, la gestión de certificados y las mejores prácticas para garantizar la seguridad de los documentos.

#### P: ¿Dónde puedo encontrar más asistencia o soporte para implementar la firma basada en tarjetas inteligentes?

R: Para obtener orientación y asistencia adicionales, comuníquese con los foros de la comunidad de Aspose.PDF o consulte la documentación para obtener información completa sobre la firma basada en tarjetas inteligentes.