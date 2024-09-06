---
title: Extraer texto usando un dispositivo de texto
linktitle: Extraer texto usando un dispositivo de texto
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a extraer texto de un documento PDF utilizando el dispositivo de texto en Aspose.PDF para .NET.
type: docs
weight: 210
url: /es/net/programming-with-text/extract-text-using-text-device/
---
Este tutorial lo guiará a través del proceso de extracción de texto de un documento PDF mediante el dispositivo de texto en Aspose.PDF para .NET. El código fuente de C# proporcionado demuestra los pasos necesarios.

## Requisitos
Antes de comenzar, asegúrese de tener lo siguiente:

- Visual Studio o cualquier otro compilador de C# instalado en su máquina.
- Biblioteca Aspose.PDF para .NET. Puede descargarla desde el sitio web oficial de Aspose o usar un administrador de paquetes como NuGet para instalarla.

## Paso 1: Configurar el proyecto
1. Cree un nuevo proyecto de C# en su entorno de desarrollo preferido.
2. Agregue una referencia a la biblioteca Aspose.PDF para .NET.

## Paso 2: Importar los espacios de nombres necesarios
En el archivo de código donde desea extraer texto, agregue las siguientes directivas using en la parte superior del archivo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

## Paso 3: Establezca el directorio del documento
 En el código, localiza la línea que dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` y reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta al directorio donde se almacenan sus documentos.

## Paso 4: Abra el documento PDF
 Abra un documento PDF existente utilizando el`Document` constructor y pasando la ruta al archivo PDF de entrada.

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## Paso 5: Extraer texto usando Text Device
 Crear un`StringBuilder` objeto para almacenar el texto extraído. Recorrer cada página del documento y utilizar un`TextDevice` para extraer el texto de cada página.

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
 Especifique la ruta del archivo de salida y guarde el texto extraído en un archivo de texto utilizando el`File.WriteAllText` método.

```csharp
dataDir = dataDir + "input_Text_Extracted_out.txt";
File.WriteAllText(dataDir, builder.ToString());
```

### Código fuente de muestra para extraer texto mediante un dispositivo de texto con Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document( dataDir + "input.pdf");
System.Text.StringBuilder builder = new System.Text.StringBuilder();
//Cadena para contener el texto extraído
string extractedText = "";
foreach (Page pdfPage in pdfDocument.Pages)
{
	using (MemoryStream textStream = new MemoryStream())
	{
		// Crear dispositivo de texto
		TextDevice textDevice = new TextDevice();
		// Establecer las opciones de extracción de texto: establecer el modo de extracción de texto (sin procesar o puro)
		TextExtractionOptions textExtOptions = new
		TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
		textDevice.ExtractionOptions = textExtOptions;
		// Convertir una página en particular y guardar el texto en la secuencia
		textDevice.Process(pdfPage, textStream);
		// Convertir una página en particular y guardar el texto en la secuencia
		textDevice.Process(pdfDocument.Pages[1], textStream);
		// Cerrar flujo de memoria
		textStream.Close();
		// Obtener texto del flujo de memoria
		extractedText = Encoding.Unicode.GetString(textStream.ToArray());
	}
	builder.Append(extractedText);
}
dataDir = dataDir + "input_Text_Extracted_out.txt";
// Guardar el texto extraído en un archivo de texto
File.WriteAllText(dataDir, builder.ToString());
Console.WriteLine("\nText extracted successfully using text device from page of PDF Document.\nFile saved at " + dataDir);
```

## Conclusión
Ha extraído correctamente el texto de un documento PDF mediante el dispositivo de texto de Aspose.PDF para .NET. El texto extraído se ha guardado en el archivo de salida especificado.

### Preguntas frecuentes

#### P: ¿Cuál es el propósito de este tutorial?

A: Este tutorial proporciona orientación sobre cómo extraer texto de un documento PDF mediante la función Dispositivo de texto en Aspose.PDF para .NET. El código fuente de C# adjunto muestra los pasos necesarios para realizar esta tarea.

#### P: ¿Qué espacios de nombres debo importar?

R: En el archivo de código donde planea extraer texto, incluya las siguientes directivas using al comienzo del archivo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

#### P: ¿Cómo especifico el directorio del documento?

 A: En el código, busque la línea que dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` y reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

#### P: ¿Cómo abro un documento PDF existente?

 A: En el paso 4, abrirá un documento PDF existente utilizando el`Document` constructor y proporcionar la ruta al archivo PDF de entrada.

#### P: ¿Cómo extraigo texto usando el dispositivo de texto?

 A: El paso 5 implica crear un`StringBuilder` objeto para almacenar el texto extraído. Luego, iterarás por cada página del documento y usarás un`TextDevice` junto con`TextExtractionOptions` para extraer texto de cada página.

#### P: ¿Cómo guardo el texto extraído en un archivo?

 A: En el paso 6, especificará la ruta del archivo de salida y utilizará el`File.WriteAllText`método para guardar el texto extraído en un archivo de texto.

#### P: ¿Cuál es la conclusión clave de este tutorial?

R: Al seguir este tutorial, aprendió a aprovechar la función Dispositivo de texto en Aspose.PDF para .NET para extraer texto de un documento PDF. El texto extraído se guardó en un archivo de salida específico, lo que le permitió manipular y utilizar el contenido extraído según sea necesario.