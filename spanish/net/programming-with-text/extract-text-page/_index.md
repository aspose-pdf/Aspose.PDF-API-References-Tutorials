---
title: Extraer página de texto
linktitle: Extraer página de texto
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a extraer texto de una página específica de un documento PDF utilizando Aspose.PDF para .NET.
type: docs
weight: 200
url: /es/net/programming-with-text/extract-text-page/
---

Este tutorial lo guiará a través del proceso de extracción de texto de una página específica de un documento PDF utilizando Aspose.PDF para .NET. El código fuente de C# proporcionado demuestra los pasos necesarios.

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
using System.IO;
```

## Paso 3: establecer el directorio de documentos
 En el código, busque la línea que dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` y reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta al directorio donde se almacenan sus documentos.

## Paso 4: Abra el documento PDF
 Abra un documento PDF existente usando el`Document` constructor y pasando la ruta al archivo PDF de entrada.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## Paso 5: extrae texto de una página específica
 Crear un`TextAbsorber` objeto para extraer texto del documento. Acepte el absorbedor de la página deseada accediendo a él a través del`Pages` colección de la`pdfDocument`.

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages[1].Accept(textAbsorber);
```

## Paso 6: Obtener el texto extraído
 Accede al texto extraído de la`TextAbsorber` objeto.

```csharp
string extractedText = textAbsorber.Text;
```

## Paso 7: Guarda el texto extraído
 Crear un`TextWriter` y abra el archivo donde desea guardar el texto extraído. Escriba el texto extraído en el archivo y cierre la secuencia.

```csharp
dataDir = dataDir + "extracted-text_out.txt";
TextWriter tw = new StreamWriter(dataDir);
tw.WriteLine(extractedText);
tw. Close();
```

### Ejemplo de código fuente para Extraer página de texto usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
// Crear objeto TextAbsorber para extraer texto
TextAbsorber textAbsorber = new TextAbsorber();
//Aceptar el absorbedor para una página en particular
pdfDocument.Pages[1].Accept(textAbsorber);
// Obtener el texto extraído
string extractedText = textAbsorber.Text;
dataDir = dataDir + "extracted-text_out.txt";
// Crea un escritor y abre el archivo.
TextWriter tw = new StreamWriter(dataDir);
// Escribir una línea de texto en el archivo.
tw.WriteLine(extractedText);
// Cierra la corriente
tw.Close();
Console.WriteLine("\nText extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

## Conclusión
Ha extraído correctamente el texto de una página específica de un documento PDF utilizando Aspose.PDF para .NET. El texto extraído se ha guardado en el archivo de salida especificado.