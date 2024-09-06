---
title: Firmar digitalmente con sello de tiempo en archivo PDF
linktitle: Firmar digitalmente con sello de tiempo en archivo PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a realizar una firma digital con sello de tiempo en un archivo PDF usando Aspose.PDF para .NET.
type: docs
weight: 50
url: /es/net/programming-with-security-and-signatures/digitally-sign-with-time-stamp/
---
En este tutorial, le guiaremos a través del proceso de firma digital de un archivo PDF con sello de tiempo utilizando Aspose.PDF para .NET. La firma digital con sello de tiempo garantiza la autenticidad e integridad del documento, al agregar una huella electrónica con sello de tiempo.

## Paso 1: Requisitos previos

Antes de comenzar, asegúrese de tener los siguientes requisitos previos:

- Conocimientos básicos del lenguaje de programación C#
- Instalación de Visual Studio en su máquina
- Biblioteca Aspose.PDF para .NET instalada

## Paso 2: Configuración del entorno

Para comenzar, siga estos pasos para configurar su entorno de desarrollo:

1. Abra Visual Studio y cree un nuevo proyecto C#.
2. Importe los espacios de nombres necesarios en su archivo de código:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
```

## Paso 3: Firma digital con sello de tiempo

El primer paso es realizar la firma digital con marca de tiempo en el archivo PDF. El código proporcionado muestra cómo lograr esta firma con Aspose.PDF para .NET.

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

### Código fuente de muestra para firmar digitalmente con sello de tiempo utilizando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pfxFile = "";
using (Document document = new Document(dataDir + @"DigitallySign.pdf"))
{
	using (PdfFileSignature signature = new PdfFileSignature(document))
	{
		PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
		TimestampSettings timestampSettings = new TimestampSettings("https:\\your_timestamp_settings", "user:password"); // Se puede omitir el usuario y la contraseña
		pkcs.TimestampSettings = timestampSettings;
		System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
		// Crea cualquiera de los tres tipos de firma
		signature.Sign(1, "Signature Reason", "Contact", "Location", true, rect, pkcs);
		// Guardar archivo PDF de salida
		signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
	}
}
```

## Conclusión

¡Felicitaciones! Ha realizado con éxito una firma digital con marca de tiempo en un archivo PDF utilizando Aspose.PDF para .NET. Este tutorial cubrió el proceso paso a paso desde la creación de la firma hasta el guardado del archivo PDF actualizado. Ahora puede usar esta función para agregar firmas digitales con marca de tiempo a sus archivos PDF.

### Preguntas frecuentes sobre la firma digital con sello de tiempo en archivo PDF

#### P: ¿Cuál es el propósito de firmar digitalmente con una marca de tiempo?

R: La firma digital con marca de tiempo agrega una huella electrónica con marca de tiempo a un archivo PDF, lo que garantiza la autenticidad e integridad del documento en un momento específico.

#### P: ¿Qué requisitos previos se necesitan para comenzar este tutorial?

R: Antes de comenzar, asegúrese de tener un conocimiento básico del lenguaje de programación C#, tener instalado Visual Studio y tener instalada la biblioteca Aspose.PDF para .NET.

#### P: ¿Cómo puedo configurar mi entorno de desarrollo?

R: Siga los pasos proporcionados para configurar su entorno de desarrollo, incluida la creación de un nuevo proyecto de C# en Visual Studio y la importación de los espacios de nombres necesarios.

#### P: ¿Cómo puedo agregar una firma digital con marca de tiempo a un PDF?

R: El código de muestra proporcionado demuestra cómo cargar un archivo PDF, crear una firma digital con una marca de tiempo utilizando un archivo PFX (clave privada) y configuraciones de marca de tiempo especificadas, agregar la firma al archivo PDF y guardar el archivo actualizado.

#### P: ¿Qué es un archivo PFX y por qué se utiliza en el ejemplo?

R: Un archivo PFX (formato de intercambio personal) contiene una clave privada y un certificado. Se utiliza aquí para proporcionar funcionalidad criptográfica para firmas digitales. Asegúrese de reemplazar el marcador de posición con su archivo PFX y contraseña.

#### P: ¿Qué son las configuraciones de marca de tiempo?

A: TimestampSettings define la configuración del servidor de marca de tiempo que se utiliza para agregar la marca de tiempo electrónica a la firma. Incluye la URL del servidor de marca de tiempo y las credenciales de usuario opcionales.

#### P: ¿Puedo utilizar un servidor de marca de tiempo distinto al del ejemplo?
 R: Sí, puede utilizar cualquier servidor de marca de tiempo compatible. Reemplace la URL y, si es necesario, proporcione las credenciales de usuario adecuadas en el campo`TimestampSettings` objeto.

#### P: ¿Cuál es el propósito de especificar el rectángulo de firma?

A: El rectángulo de firma define la posición y las dimensiones de la apariencia de la firma digital en la página PDF. Ajuste estos valores para colocar la firma como desee.

#### P: ¿Qué sucede si el servidor de marca de tiempo no está disponible durante la firma?

A: Si el servidor de marca de tiempo no está disponible durante la firma, el proceso puede fallar o demorar más. Asegúrese de que su servidor de marca de tiempo sea confiable y accesible.

#### P: ¿Cómo puedo verificar la presencia de una marca de tiempo en el PDF firmado?

 A: Puede examinar el PDF firmado utilizando el código de muestra proporcionado.`TimestampSettings` La información que utilizó durante la firma debe estar disponible en los detalles de la firma.

#### P: ¿Las firmas digitales con marcas de tiempo son legalmente vinculantes?

R: Las firmas digitales con sellos de tiempo tienen valor legal en muchas jurisdicciones y suelen considerarse más confiables que las firmas digitales simples. Consulte a los expertos legales de su jurisdicción para conocer las regulaciones específicas.

#### P: ¿Puedo agregar varias firmas digitales con marcas de tiempo a un PDF?

R: Sí, puedes agregar varias firmas digitales con marcas de tiempo a un archivo PDF llamando al proceso de creación de firmas varias veces. Cada firma tendrá su propia marca de tiempo.