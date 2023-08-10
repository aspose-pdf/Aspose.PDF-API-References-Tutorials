---
title: Firmar con tarjeta inteligente utilizando el campo de firma
linktitle: Firmar con tarjeta inteligente utilizando el campo de firma
second_title: Referencia de API de Aspose.PDF para .NET
description: Firme sus archivos PDF de forma segura con una tarjeta inteligente utilizando Aspose.PDF para .NET.
type: docs
weight: 120
url: /es/net/programming-with-security-and-signatures/sign-with-smart-card-using-signature-field/
---
La firma digital con una tarjeta inteligente es una forma segura de firmar archivos PDF. Con Aspose.PDF para .NET, puede firmar fácilmente un archivo PDF utilizando un campo de firma y una tarjeta inteligente siguiendo el siguiente código fuente:

## Paso 1: importa las bibliotecas requeridas

Antes de comenzar, debe importar las bibliotecas necesarias para su proyecto de C#. Aquí están las directivas de importación necesarias:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## Paso 2: establecer la ruta a la carpeta de documentos

 En este paso, debe especificar la ruta a la carpeta que contiene el archivo PDF que desea firmar. Reemplazar`"YOUR DOCUMENTS DIRECTORY"`en el siguiente código con la ruta real a su carpeta de documentos:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 3: Copie y abra el documento PDF

Ahora copiaremos y abriremos el documento PDF a firmar utilizando el siguiente código:

```csharp
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);

using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
     using (Document doc = new Document(fs))
     {
         // Crear un campo de firma
         SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));

         // Seleccione el certificado en la tienda
         X509Store store = new X509Store(StoreLocation.CurrentUser);
         store.Open(OpenFlags.ReadOnly);
         X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
        
         // Crear una firma externa con la información necesaria
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

## Paso 4: Verificar firma

 Finalmente, verificamos la firma del archivo PDF firmado usando el`PdfFileSignature` clase. Obtenemos los nombres de las firmas y los verificamos uno por uno. Si una firma falla en la verificación, se lanza una excepción. Aquí está el código correspondiente:

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

### Ejemplo de código fuente para Firmar con tarjeta inteligente usando el campo de firma usando Aspose.PDF para .NET 
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
		// Eligió manualmente el certificado en la tienda
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

¡Felicidades! Ahora tiene una guía paso a paso para firmar un archivo PDF con una tarjeta inteligente utilizando un campo de firma con Aspose.PDF para .NET. Puede usar este código para agregar firmas digitales seguras a sus documentos PDF.

Asegúrese de consultar la documentación oficial de Aspose.PDF para obtener más información sobre las funciones avanzadas de gestión de certificados y firma digital.

### Preguntas frecuentes

#### P: ¿Cuál es el beneficio de usar un campo de firma para la firma digital con una tarjeta inteligente?

R: El uso de un campo de firma para la firma digital con una tarjeta inteligente proporciona un área designada dentro del PDF donde se aplica la firma. Esto mejora la claridad del documento y asegura la autenticidad de la firma.

#### P: ¿Cómo facilita la biblioteca Aspose.PDF para .NET la firma digital basada en tarjetas inteligentes con un campo de firma?

R: Aspose.PDF para .NET simplifica el proceso de crear un campo de firma, seleccionar un certificado de tarjeta inteligente y aplicar una firma digital a un área específica dentro del documento PDF.

#### P: ¿Por qué es importante seleccionar un certificado específico para la firma basada en tarjetas inteligentes?

R: La selección de un certificado específico le permite identificar de manera única al firmante y garantizar la integridad de la firma. Esto ayuda a establecer la confianza y el cumplimiento de los estándares de firma digital.

#### P: ¿Cómo maneja el código fuente proporcionado el proceso de firma basado en tarjeta inteligente con un campo de firma?

R: El código fuente demuestra cómo crear un campo de firma, seleccionar un certificado de tarjeta inteligente y aplicar una firma digital con información de firma específica. También muestra cómo verificar la validez de la firma.

#### P: ¿Puedo personalizar la apariencia del campo de la firma?

R: Sí, puede personalizar la apariencia del campo de firma, como su tamaño, posición y representación visual, para alinearlo con el diseño de su documento.

#### P: ¿Qué sucede si una firma falla en la verificación durante el paso de verificación?

R: Si una firma falla en la verificación, se genera una excepción que indica que la firma no es válida. Esto garantiza que solo se acepten firmas válidas y confiables.

#### P: ¿Puedo aplicar múltiples campos de firma y firmas basadas en tarjetas inteligentes a un solo documento PDF?

R: Absolutamente, puede aplicar múltiples campos de firma y firmas basadas en tarjetas inteligentes a diferentes áreas del mismo documento PDF, lo que brinda múltiples capas de seguridad.

#### P: ¿Cómo mejora el proceso general de firma de documentos el uso de un campo de firma?

R: El uso de un campo de firma agiliza el proceso de firma de documentos, ya que guía al firmante a colocar su firma en un área designada, lo que hace que el proceso de firma sea más organizado y fácil de usar.

#### P: ¿Existe alguna limitación en el uso de campos de firma con la firma basada en tarjeta inteligente?

R: No existen limitaciones inherentes al uso de campos de firma con la firma basada en tarjeta inteligente. Sin embargo, es importante asegurarse de que la ubicación del campo de firma elegido no oculte el contenido importante del documento.

#### P: ¿Dónde puedo encontrar más asistencia o soporte para implementar la firma basada en tarjeta inteligente con un campo de firma?

R: Para obtener orientación y soporte adicionales, puede consultar la documentación oficial de Aspose.PDF y los foros de la comunidad, que ofrecen información y soluciones valiosas para implementar firmas digitales seguras.