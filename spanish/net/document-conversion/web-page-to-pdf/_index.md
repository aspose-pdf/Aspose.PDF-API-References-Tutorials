---
title: Página web a PDF
linktitle: Página web a PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Guía paso a paso para convertir una página web a PDF usando Aspose.PDF para .NET.
type: docs
weight: 320
url: /es/net/document-conversion/web-page-to-pdf/
---

En este tutorial, lo guiaremos paso a paso sobre cómo convertir una página web a PDF utilizando la biblioteca Aspose.PDF para .NET. Explicaremos el código fuente de C# provisto y le mostraremos cómo implementarlo en sus propios proyectos. Al final de este tutorial, podrá convertir páginas web a documentos PDF sin esfuerzo.

## Introducción
La conversión de páginas web a formato PDF es un requisito común en muchas aplicaciones. Al convertir contenido web a PDF, puede conservar fácilmente el diseño, el formato y las imágenes de la página web original. Aspose.PDF para .NET es una poderosa biblioteca que le permite realizar esta conversión de manera eficiente y precisa.

## Requisitos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos en su lugar:
- Visual Studio instalado en su máquina
- Aspose.PDF para la biblioteca .NET (puede descargarlo del sitio web oficial de Aspose)
- Conocimientos básicos de programación en C#


## Paso 1: definir el directorio de documentos
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```
 Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta donde desea guardar el archivo PDF generado.

## Paso 2: crear una solicitud web
```csharp
WebRequest request = WebRequest.Create("https://en.wikipedia.org/wiki/Main_Page");
request.Credentials = CredentialCache.DefaultCredentials;
```
Cree un objeto de solicitud web y especifique la URL de la página web que desea convertir. Puede reemplazar la URL con cualquier página web que desee.

## Paso 3: obtenga la respuesta web
```csharp
HttpWebResponse response = (HttpWebResponse)request.GetResponse();
```
Envía la solicitud web y recupera la respuesta del servidor.

## Paso 4: Lea el contenido web
```csharp
Stream dataStream = response. GetResponseStream();
StreamReader reader = new StreamReader(dataStream);
string responseFromServer = reader.ReadToEnd();
reader. Close();
dataStream.Close();
response. Close();
```
 Lea el contenido de la página web utilizando un`StreamReader` y guárdelo en el`responseFromServer` variable.

## Paso 5: Convierte HTML a PDF
```csharp
MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));
HtmlLoadOptions options = new HtmlLoadOptions("https://en.wikipedia.org/wiki/");
Document pdfDocument = new Document(stream, options);
options.PageInfo.IsLandscape = true;
pdfDocument.Save(dataDir + "WebPageToPDF_out.pdf");
```
 Crear un`MemoryStream` objeto para cargar el contenido de la página web. Luego, crea una instancia de`HtmlLoadOptions` y pasar la URL base de la página web. A continuación, cree un`Document` objeto utilizando la secuencia cargada y las opciones de carga de HTML. Selecciona el`IsLandscape` propiedad a`true` si desea que el PDF esté en orientación horizontal. Finalmente, guarde el documento PDF en el directorio especificado

.

## Paso 6: Manejar excepciones
```csharp
catch (Exception ex)
{
Console.WriteLine(ex.Message);
}
```
Detecte cualquier excepción que pueda ocurrir durante el proceso de conversión y muestre el mensaje de error.

### Código fuente de ejemplo para página web a PDF usando Aspose.Words para .NET

```csharp
try
{
	
	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Cree una solicitud para la URL.
	WebRequest request = WebRequest.Create("https:// En.wikipedia.org/wiki/Main_Page");
	// Si lo requiere el servidor, configure las credenciales.
	request.Credentials = CredentialCache.DefaultCredentials;
	// Tiempo de espera en milisegundos antes de que se agote el tiempo de espera de la solicitud
	// Solicitud.Tiempo de espera = 100;

	// Obtén la respuesta.
	HttpWebResponse response = (HttpWebResponse)request.GetResponse();

	// Obtenga la transmisión que contiene el contenido devuelto por el servidor.
	Stream dataStream = response.GetResponseStream();
	// Abra la secuencia con un StreamReader para facilitar el acceso.
	StreamReader reader = new StreamReader(dataStream);
	// Lee el contenido.
	string responseFromServer = reader.ReadToEnd();
	reader.Close();
	dataStream.Close();
	response.Close();

	MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));
	HtmlLoadOptions options = new HtmlLoadOptions("https:// En.wikipedia.org/wiki/");


	// Cargar archivo HTML
	Document pdfDocument = new Document(stream, options);

	options.PageInfo.IsLandscape = true;

	// Guardar la salida como formato PDF
	pdfDocument.Save(dataDir + "WebPageToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusión
En este tutorial, hemos aprendido cómo convertir una página web a PDF utilizando la biblioteca Aspose.PDF para .NET. Revisamos la guía paso a paso que explica el código fuente de C# provisto. Siguiendo estas instrucciones, puede integrar fácilmente la funcionalidad de conversión de página web a PDF en sus propias aplicaciones .NET.