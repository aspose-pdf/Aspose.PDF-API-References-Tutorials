---
title: Proporcionar credenciales durante HTML a PDF
linktitle: Proporcionar credenciales durante HTML a PDF
second_title: Aspose.PDF para referencia de API .NET
description: Guía paso a paso para convertir HTML a PDF proporcionando credenciales con Aspose.PDF para .NET.
type: docs
weight: 240
url: /es/net/document-conversion/provide-credentials-during-html-to-pdf/
---
En este tutorial, lo guiaremos a través del proceso de convertir un archivo HTML a PDF mientras le proporcionamos credenciales al acceder a una URL segura usando Aspose.PDF para .NET. Si sigue los pasos a continuación, podrá convertir contenido HTML a PDF utilizando las credenciales adecuadas.

## Requisitos previos
Antes de comenzar, asegúrese de cumplir con los siguientes requisitos previos:

- Conocimientos básicos del lenguaje de programación C#.
- Biblioteca Aspose.PDF para .NET instalada en su sistema.
- Un entorno de desarrollo como Visual Studio.

## Paso 1: obtenga contenido HTML seguro
En este paso, recuperaremos contenido HTML seguro de una URL utilizando las credenciales adecuadas. Utilice el siguiente código:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cree una solicitud para la URL.
WebRequest request = WebRequest.Create("http://My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
// Si es necesario para el servidor, configure las credenciales.
request.Credentials = CredentialCache.DefaultCredentials;
// Obtenga la respuesta.
HttpWebResponse response = (HttpWebResponse)request.GetResponse();

// Obtenga la transmisión que contiene el contenido devuelto por el servidor.
Stream dataStream = response. GetResponseStream();
// Abra la transmisión usando un StreamReader para acceder fácilmente.
StreamReader reader = new StreamReader(dataStream);
// Lee el contenido.
string responseFromServer = reader.ReadToEnd();
reader. Close();
dataStream.Close();
response. Close();
```

 Asegúrate de reemplazar`"YOUR DOCUMENTS DIRECTORY"` con el directorio real donde desea guardar el archivo PDF resultante.

## Paso 2: convierta HTML a PDF proporcionando credenciales
Ahora cargaremos el contenido HTML recuperado y lo convertiremos a formato PDF mientras proporcionamos las credenciales adecuadas. Utilice el siguiente código:

```csharp
MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));

HtmlLoadOptions options = new HtmlLoadOptions("http://Mi.signchart.com/");
options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

// Cargue el archivo HTML
Document pdfDocument = new Document(stream, options);
```

## Paso 3: guardar el archivo PDF resultante
Finalmente, guardaremos el archivo PDF resultante. Utilice el siguiente código:

```csharp
// Guarde el archivo PDF resultante
pdfDocument.Save(dataDir + "ProvideCredentialsDuringHTMLToPDF_out.pdf");
```

 El código anterior guarda el archivo PDF resultante con el nombre de archivo`"ProvideCredentialsDuringHTMLToPDF_out.pdf"`.

### Código fuente de ejemplo para proporcionar credenciales durante HTML a PDF usando Aspose.PDF para .NET

```csharp
try
{
	
	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Cree una solicitud para la URL.
	WebRequest request = WebRequest.Create("http:// My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
	// Si el servidor lo requiere, configure las credenciales.
	request.Credentials = CredentialCache.DefaultCredentials;
	// Obtenga la respuesta.
	HttpWebResponse response = (HttpWebResponse)request.GetResponse();

	// Obtenga la transmisión que contiene el contenido devuelto por el servidor.
	Stream dataStream = response.GetResponseStream();
	// Abra la transmisión usando un StreamReader para acceder fácilmente.
	StreamReader reader = new StreamReader(dataStream);
	// Lee el contenido.
	string responseFromServer = reader.ReadToEnd();
	reader.Close();
	dataStream.Close();
	response.Close();

	MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));

	HtmlLoadOptions options = new HtmlLoadOptions("http:// Mi.signchart.com/");
	options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

	// Cargar archivo HTML
	Document pdfDocument = new Document(stream, options);
	// Guardar archivo resultante
	pdfDocument.Save("ProvideCredentialsDuringHTMLToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusión
En este tutorial, cubrimos el proceso paso a paso de convertir un archivo HTML a PDF mientras proporcionamos credenciales al acceder a una URL segura usando Aspose.PDF para .NET. Si sigue las instrucciones descritas anteriormente, podrá convertir con éxito contenido HTML a PDF proporcionando las credenciales correctas.

### Preguntas frecuentes

#### P: ¿Qué es Aspose.PDF para .NET?

R: Aspose.PDF para .NET es una biblioteca sólida que permite a los desarrolladores trabajar con documentos PDF en aplicaciones C#. Ofrece una amplia gama de funcionalidades, incluida la conversión de HTML a PDF.

#### P: ¿Cómo puedo recuperar contenido HTML seguro desde una URL?

 R: Para recuperar contenido HTML seguro de una URL, puede utilizar el`WebRequest` clase en C#. Asegúrese de configurar las credenciales apropiadas usando el`Credentials` propiedad.

#### P: ¿Cuáles son los requisitos previos para este tutorial?

R: Antes de continuar con el tutorial, asegúrese de tener los siguientes requisitos previos:

- Conocimientos básicos del lenguaje de programación C#.
- Biblioteca Aspose.PDF para .NET instalada en su sistema.
- Un entorno de desarrollo como Visual Studio.

#### P: ¿Cómo maneja Aspose.PDF para .NET los recursos externos al convertir HTML a PDF?

 R: Aspose.PDF para .NET proporciona la`HtmlLoadOptions`clase para manejar recursos externos durante la conversión de HTML a PDF. Puede configurar las credenciales de recursos externos utilizando el`ExternalResourcesCredentials` propiedad.

#### P: ¿Puedo personalizar el nombre del archivo PDF resultante?

 R: Sí, puede personalizar el nombre del archivo PDF resultante modificando el código que guarda el documento PDF. Simplemente cambie el nombre de archivo deseado en el`pdfDocument.Save()` método.