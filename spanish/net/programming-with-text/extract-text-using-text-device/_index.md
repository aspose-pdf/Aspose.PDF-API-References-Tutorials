---
title: Extraer texto usando un dispositivo de texto
linktitle: Extraer texto usando un dispositivo de texto
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a extraer texto de un documento PDF utilizando el dispositivo de texto en Aspose.PDF para .NET.
type: docs
weight: 210
url: /es/net/programming-with-text/extract-text-using-text-device/
---

Este tutorial lo guiará a través del proceso de extracción de texto de un documento PDF utilizando el dispositivo de texto en Aspose.PDF para .NET. El código fuente de C# proporcionado demuestra los pasos necesarios.

## Requisitos
Antes de comenzar, asegúrese de tener lo siguiente:

- Visual Studio o cualquier otro compilador de C# instalado en su máquina.
- Aspose.PDF para la biblioteca .NET. Puede descargarlo del sitio web oficial de Aspose o usar un administrador de paquetes como NuGet para instalarlo.

## Paso 1: configurar el proyecto
1. Cree un nuevo proyecto de C# en su entorno de desarrollo preferido.
2. Agregue una referencia a la biblioteca Aspose.PDF para .NET.

## Paso 2: importa los espacios de nombres requeridos
En el archivo de código donde desea extraer el texto, agregue las siguientes directivas using en la parte superior del archivo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

## Paso 3: establecer el directorio de documentos
 En el código, busque la línea que dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` y reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta al directorio donde se almacenan sus documentos.

## Paso 4: Abra el documento PDF
 Abra un documento PDF existente usando el`Document` constructor y pasando la ruta al archivo PDF de entrada.

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## Paso 5: extraiga texto usando el dispositivo de texto
 Crear un`StringBuilder` objeto para contener el texto extraído. Iterar a través de cada página del documento y utilizar un`TextDevice` para extraer el texto de cada página.

```csharp
StringBuilder builder = new StringBuilder();
string extractedText = "";
foreach(Page pdfPage in pdfDocument.Pages)
{
using (MemoryStream textStream = new MemoryStream())
{
TextDevice textDevice = new TextDevice();
TextExtractionOptions textExtOptions = new TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
textDevice.ExtractionOptions = textExtOptions;
textDevice.Process(pdfPage, textStream);
textStream. Close();
extractedText = Encoding.Unicode.GetString(textStream.ToArray());
}
builder. Append(extractedText);
}
```

## Paso 6: Guarda el texto extraído
 Especifique la ruta del archivo de salida y guarde el texto extraído en un archivo de texto usando el`File.WriteAllText` método.

```csharp
dataDir = dataDir + "input_Text_Extracted_out.txt";
File.WriteAllText(dataDir, builder.ToString());
```

### Ejemplo de código fuente para Extraer texto usando un dispositivo de texto usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document( dataDir + "input.pdf");
System.Text.StringBuilder builder = new System.Text.StringBuilder();
// Cadena para contener el texto extraído
string extractedText = "";
foreach (Page pdfPage in pdfDocument.Pages)
{
	using (MemoryStream textStream = new MemoryStream())
	{
		// Crear dispositivo de texto
		TextDevice textDevice = new TextDevice();
		// Establecer opciones de extracción de texto: establecer el modo de extracción de texto (sin formato o puro)
		TextExtractionOptions textExtOptions = new
		TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
		textDevice.ExtractionOptions = textExtOptions;
		// Convierta una página en particular y guarde el texto en la secuencia
		textDevice.Process(pdfPage, textStream);
		// Convierta una página en particular y guarde el texto en la secuencia
		textDevice.Process(pdfDocument.Pages[1], textStream);
		// Cerrar flujo de memoria
		textStream.Close();
		// Obtener texto del flujo de memoria
		extractedText = Encoding.Unicode.GetString(textStream.ToArray());
	}
	builder.Append(extractedText);
}
dataDir = dataDir + "input_Text_Extracted_out.txt";
// Guarde el texto extraído en un archivo de texto
File.WriteAllText(dataDir, builder.ToString());
Console.WriteLine("\nText extracted successfully using text device from page of PDF Document.\nFile saved at " + dataDir);
```

## Conclusión
Ha extraído con éxito el texto de un documento PDF utilizando el dispositivo de texto en Aspose.PDF para .NET. El texto extraído se ha guardado en el archivo de salida especificado.