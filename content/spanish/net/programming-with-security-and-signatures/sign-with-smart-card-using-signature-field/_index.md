---
title: Firmar con tarjeta inteligente utilizando el campo de firma
linktitle: Firmar con tarjeta inteligente utilizando el campo de firma
second_title: Aspose.PDF para referencia de API .NET
description: Firme sus archivos PDF de forma segura con una tarjeta inteligente usando Aspose.PDF para .NET.
type: docs
weight: 120
url: /es/net/programming-with-security-and-signatures/sign-with-smart-card-using-signature-field/
---
La firma digital con una tarjeta inteligente es una forma segura de firmar archivos PDF. Con Aspose.PDF para .NET, puede firmar fácilmente un archivo PDF utilizando un campo de firma y una tarjeta inteligente siguiendo el siguiente código fuente:

## Paso 1: importar las bibliotecas necesarias

Antes de comenzar, debe importar las bibliotecas necesarias para su proyecto C#. Aquí están las directivas de importación necesarias:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## Paso 2: establezca la ruta a la carpeta de documentos

 En este paso, debe especificar la ruta a la carpeta que contiene el archivo PDF que desea firmar. Reemplazar`"YOUR DOCUMENTS DIRECTORY"`en el siguiente código con la ruta real a su carpeta de documentos:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 3: Copie y abra el documento PDF

Ahora copiaremos y abriremos el documento PDF a firmar usando el siguiente código:

```csharp
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);

using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
     using (Document doc = new Document(fs))
     {
         // Crear un campo de firma
         SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));

         // Seleccione el certificado en la tienda.
         X509Store store = new X509Store(StoreLocation.CurrentUser);
         store.Open(OpenFlags.ReadOnly);
         X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
        
         // Crea una firma externa con la información necesaria
         ExternalSignature externalSignature = new ExternalSignature(sel[0])
         {
             Authority = "Me",
             Reason = "Reason",
             ContactInfo = "Contact"
         };

         field1.PartialName = "sig1";
         doc.Form.Add(field1, 1);
         field1.Sign(externalSignature);
         doc.Save();
     }
}
```

## Paso 4: verificar la firma

 Finalmente, verificamos la firma del archivo PDF firmado utilizando el`PdfFileSignature` clase. Obtenemos los nombres de las firmas y los comprobamos uno por uno. Si una firma no pasa la verificación, se lanza una excepción. Aquí está el código correspondiente:

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature1.pdf")))
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

### Código fuente de muestra para firmar con tarjeta inteligente usando el campo de firma usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);
using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
	using (Document doc = new Document(fs))
	{
		SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));
		// Firmar con selección de certificado en el almacén de certificados de Windows
		System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
		store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
		// Elija manualmente el certificado en la tienda.
		System.Security.Cryptography.X509Certificates.X509Certificate2Collection sel = System.Security.Cryptography.X509Certificates.X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, System.Security.Cryptography.X509Certificates.X509SelectionFlag.SingleSelection);
		Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0])
		{
			Authority = "Me",
			Reason = "Reason",
			ContactInfo = "Contact"
		};
		field1.PartialName = "sig1";
		doc.Form.Add(field1, 1);
		field1.Sign(externalSignature);
		doc.Save();
	}
}
using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature1.pdf")))
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

¡Enhorabuena! Ahora tiene una guía paso a paso para firmar un archivo PDF con una tarjeta inteligente usando un campo de firma con Aspose.PDF para .NET. Puede utilizar este código para agregar firmas digitales seguras a sus documentos PDF.

Asegúrese de consultar la documentación oficial de Aspose.PDF para obtener más información sobre las funciones avanzadas de gestión de certificados y firma digital.

### Preguntas frecuentes

#### P: ¿Cuál es el beneficio de utilizar un campo de firma para la firma digital con una tarjeta inteligente?

R: El uso de un campo de firma para la firma digital con una tarjeta inteligente proporciona un área designada dentro del PDF donde se aplica la firma. Esto mejora la claridad del documento y garantiza la autenticidad de la firma.

#### P: ¿Cómo facilita la biblioteca Aspose.PDF para .NET la firma digital basada en tarjetas inteligentes con un campo de firma?

R: Aspose.PDF para .NET simplifica el proceso de crear un campo de firma, seleccionar un certificado de tarjeta inteligente y aplicar una firma digital a un área específica dentro del documento PDF.

#### P: ¿Por qué es importante seleccionar un certificado específico para la firma basada en tarjetas inteligentes?

R: Seleccionar un certificado específico le permite identificar de forma única al firmante y garantizar la integridad de la firma. Esto ayuda a establecer confianza y cumplimiento de los estándares de firma digital.

#### P: ¿Cómo maneja el código fuente proporcionado el proceso de firma basado en tarjeta inteligente con un campo de firma?

R: El código fuente muestra cómo crear un campo de firma, seleccionar un certificado de tarjeta inteligente y aplicar una firma digital con información de firma específica. También muestra cómo verificar la validez de la firma.

#### P: ¿Puedo personalizar la apariencia del campo de firma?

R: Sí, puede personalizar la apariencia del campo de firma, como su tamaño, posición y representación visual, para alinearlo con el diseño de su documento.

#### P: ¿Qué sucede si una firma no pasa la verificación durante el paso de verificación?

R: Si una firma no pasa la verificación, se genera una excepción que indica que la firma no es válida. Esto garantiza que solo se acepten firmas válidas y confiables.

#### P: ¿Puedo aplicar varios campos de firma y firmas basadas en tarjetas inteligentes a un único documento PDF?

R: Por supuesto, puede aplicar múltiples campos de firma y firmas basadas en tarjetas inteligentes a diferentes áreas del mismo documento PDF, proporcionando múltiples capas de seguridad.

#### P: ¿Cómo mejora el uso de un campo de firma el proceso general de firma de documentos?

R: El uso de un campo de firma agiliza el proceso de firma de documentos, ya que guía al firmante a colocar su firma en un área designada, lo que hace que el proceso de firma sea más organizado y fácil de usar.

#### P: ¿Existe alguna limitación en el uso de campos de firma con firma basada en tarjeta inteligente?

R: No existen limitaciones inherentes al uso de campos de firma con firma basada en tarjeta inteligente. Sin embargo, es importante asegurarse de que la ubicación del campo de firma elegida no oculte contenido importante del documento.

#### P: ¿Dónde puedo encontrar más ayuda o soporte para implementar la firma basada en tarjetas inteligentes con un campo de firma?

R: Para obtener orientación y soporte adicionales, puede consultar la documentación oficial de Aspose.PDF y los foros comunitarios, que ofrecen información y soluciones valiosas para implementar firmas digitales seguras.