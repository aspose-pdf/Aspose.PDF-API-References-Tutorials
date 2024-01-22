---
title: Firmar digitalmente con marca de tiempo en un archivo PDF
linktitle: Firmar digitalmente con marca de tiempo en un archivo PDF
second_title: Aspose.PDF para referencia de API .NET
description: Aprenda a realizar una firma digital con marca de tiempo en un archivo PDF usando Aspose.PDF para .NET.
type: docs
weight: 50
url: /es/net/programming-with-security-and-signatures/digitally-sign-with-time-stamp/
---
En este tutorial, lo guiaremos a través del proceso de firma digital en un archivo PDF con marca de tiempo usando Aspose.PDF para .NET. La firma digital con sello de tiempo garantiza la autenticidad e integridad del documento, al agregar una huella electrónica con sello de tiempo.

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
```

## Paso 3: Firma digital con marca de tiempo

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

### Código fuente de muestra para firmar digitalmente con marca de tiempo usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pfxFile = "";
using (Document document = new Document(dataDir + @"DigitallySign.pdf"))
{
	using (PdfFileSignature signature = new PdfFileSignature(document))
	{
		PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
		TimestampSettings timestampSettings = new TimestampSettings("https:\\your_timestamp_settings", "user:password"); // Se puede omitir usuario/contraseña
		pkcs.TimestampSettings = timestampSettings;
		System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
		// Crea cualquiera de los tres tipos de firma
		signature.Sign(1, "Signature Reason", "Contact", "Location", true, rect, pkcs);
		// Guardar el archivo PDF de salida
		signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
	}
}
```

## Conclusión

¡Enhorabuena! Ha realizado con éxito una firma digital con marca de tiempo en un archivo PDF utilizando Aspose.PDF para .NET. Este tutorial cubrió el proceso paso a paso desde la creación de la firma hasta guardar el archivo PDF actualizado. Ahora puede utilizar esta función para agregar firmas digitales con marca de tiempo a sus archivos PDF.

### Preguntas frecuentes sobre la firma digital con marca de tiempo en un archivo PDF

#### P: ¿Cuál es el propósito de firmar digitalmente con una marca de tiempo?

R: La firma digital con marca de tiempo agrega una huella digital electrónica con una marca de tiempo a un archivo PDF, lo que garantiza la autenticidad e integridad del documento en un momento específico.

#### P: ¿Qué requisitos previos se necesitan para comenzar este tutorial?

R: Antes de comenzar, asegúrese de tener conocimientos básicos del lenguaje de programación C#, tener instalado Visual Studio y tener instalada la biblioteca Aspose.PDF para .NET.

#### P: ¿Cómo puedo configurar mi entorno de desarrollo?

R: Siga los pasos proporcionados para configurar su entorno de desarrollo, incluida la creación de un nuevo proyecto de C# en Visual Studio y la importación de los espacios de nombres necesarios.

#### P: ¿Cómo agrego una firma digital con marca de tiempo a un PDF?

R: El código de muestra proporcionado demuestra cómo cargar un archivo PDF, crear una firma digital con una marca de tiempo usando un archivo PFX (clave privada) y una configuración de marca de tiempo especificada, agregar la firma al archivo PDF y guardar el archivo actualizado.

#### P: ¿Qué es un archivo PFX y por qué se utiliza en el ejemplo?

R: Un archivo PFX (formato de intercambio personal) contiene una clave privada y un certificado. Se utiliza aquí para proporcionar funcionalidad criptográfica para firmas digitales. Asegúrese de reemplazar el marcador de posición con su archivo PFX y contraseña.

#### P: ¿Qué son las configuraciones de marca de tiempo?

R: TimestampSettings define la configuración del servidor de marca de tiempo utilizado para agregar la marca de tiempo electrónica a la firma. Incluye la URL del servidor de marca de tiempo y credenciales de usuario opcionales.

#### P: ¿Puedo utilizar un servidor de marca de tiempo distinto al del ejemplo?
 R: Sí, puedes utilizar cualquier servidor de marca de tiempo compatible. Reemplace la URL y, si es necesario, proporcione las credenciales de usuario adecuadas en el`TimestampSettings` objeto.

#### P: ¿Cuál es el propósito de especificar el rectángulo de firma?

R: El rectángulo de firma define la posición y las dimensiones de la apariencia de la firma digital en la página PDF. Ajuste estos valores para colocar la firma como desee.

#### P: ¿Qué sucede si el servidor de marca de tiempo no está disponible durante la firma?

R: Si el servidor de marca de tiempo no está disponible durante la firma, el proceso puede fallar o tardar más. Asegúrese de que su servidor de marca de tiempo sea confiable y accesible.

#### P: ¿Cómo puedo verificar la presencia de una marca de tiempo en el PDF firmado?

 R: Puede examinar el PDF firmado utilizando el código de muestra proporcionado. El`TimestampSettings` que utilizó durante la firma debe estar disponible en los detalles de la firma.

#### P: ¿Son legalmente vinculantes las firmas digitales con marcas de tiempo?

R: Las firmas digitales con marcas de tiempo tienen valor legal en muchas jurisdicciones y a menudo se consideran más confiables que las simples firmas digitales. Consulte a expertos legales en su jurisdicción para conocer las regulaciones específicas.

#### P: ¿Puedo agregar varias firmas digitales con marcas de tiempo a un PDF?

R: Sí, puede agregar varias firmas digitales con marcas de tiempo a un archivo PDF llamando al proceso de creación de firma varias veces. Cada firma tendrá su propia marca de tiempo.