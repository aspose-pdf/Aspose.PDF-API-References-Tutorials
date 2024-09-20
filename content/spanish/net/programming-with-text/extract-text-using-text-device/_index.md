---
title: Extraer texto usando un dispositivo de texto
linktitle: Extraer texto usando un dispositivo de texto
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a extraer texto de un documento PDF utilizando el dispositivo de texto en Aspose.PDF para .NET.
type: docs
weight: 210
url: /es/net/programming-with-text/extract-text-using-text-device/
---
## Introducción

Extraer texto de un PDF puede ser complicado, especialmente cuando se trata de documentos que tienen varios formatos, fuentes incrustadas o diseños complejos. Pero con Aspose.PDF para .NET, este proceso se vuelve muy fácil. Ya sea que desee convertir páginas de un PDF en texto sin formato para un análisis posterior o simplemente necesite extraer secciones específicas, Aspose.PDF lo tiene cubierto. En este tutorial, desglosaremos paso a paso cómo extraer texto de un PDF utilizando la clase TextDevice en Aspose.PDF. También proporcionaremos explicaciones claras, para que pueda aplicar los mismos métodos a sus propios proyectos con facilidad.

## Prerrequisitos

Antes de comenzar con el código, asegúrate de tener todo listo para seguir. Esto es lo que necesitarás:

1.  Aspose.PDF para .NET: Descargue la última versión desde[Página de descarga de Aspose.PDF para .NET](https://releases.aspose.com/pdf/net/).
2. Entorno de desarrollo: Visual Studio o cualquier otro entorno de desarrollo de C#.
3. .NET Framework: asegúrese de que su proyecto tenga como objetivo .NET Framework 4.x o superior.
4. Archivo PDF de entrada: un archivo PDF que utilizará para la extracción de texto. Colóquelo en un directorio de su equipo (lo llamaremos`YOUR DOCUMENT DIRECTORY`).

## Importar paquetes

En la parte superior de su código, deberá importar los espacios de nombres necesarios para trabajar con Aspose.PDF:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Devices;
using System;
using System.Text;
```

## Paso 1: Cargue su documento PDF

 Antes de extraer el texto, debemos cargar el documento PDF en la memoria. En este paso, abrirá su PDF con Aspose.PDF.`Document` clase. Esto le permitirá acceder a todas las páginas y contenidos dentro del archivo.

```csharp
// Define la ruta a tu documento PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Cargar el documento PDF
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 Aquí estamos usando`Document pdfDocument = new Document(dataDir + "input.pdf");` para cargar el PDF.`dataDir` La variable contiene la ruta del directorio de su archivo PDF. Esto nos dará acceso a todo el documento, lo que nos permitirá recorrer las páginas y extraer contenido.

## Paso 2: Configurar un generador de cadenas para el almacenamiento de texto

 Ahora que el documento está cargado, necesitamos una forma de almacenar el texto extraído. Para ello, utilizaremos un`StringBuilder` que permite una concatenación eficiente de cadenas.

```csharp
// StringBuilder para almacenar el texto extraído
StringBuilder builder = new StringBuilder();
```

 Inicializamos un`StringBuilder`instancia, que recopilará el texto extraído de cada página. Es una forma más eficiente de manejar cadenas grandes en comparación con la concatenación de cadenas normal en un bucle.

## Paso 3: Recorrer las páginas del PDF

 A continuación, recorreremos cada página del documento PDF para extraer el texto. Procesaremos cada página individualmente utilizando el`TextDevice` clase, que es responsable de convertir el contenido PDF a formato de texto.

```csharp
// Recorrer todas las páginas del PDF
foreach (Page pdfPage in pdfDocument.Pages)
{
    // Procesar cada página para la extracción de texto
}
```

Este bucle recorre cada página del PDF (`pdfDocument.Pages` ). Para cada página, extraeremos el texto y lo agregaremos a nuestra`StringBuilder`.

## Paso 4: Extraer texto de cada página

 Ahora, configuramos el proceso de extracción de texto para cada página. Aquí, crearemos un`TextDevice` objeto y utilizarlo para procesar las páginas PDF.`TextDevice` extrae texto sin formato o formateado según las opciones de extracción que configuremos.

```csharp
using (MemoryStream textStream = new MemoryStream())
{
    // Crear un dispositivo de texto para la extracción de texto
    TextDevice textDevice = new TextDevice();
    
    // Establezca las opciones de extracción de texto en modo 'Puro'
    TextExtractionOptions textExtOptions = new TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
    textDevice.ExtractionOptions = textExtOptions;

    //Extraer texto de la página actual y guardarlo en el flujo de memoria
    textDevice.Process(pdfPage, textStream);

    // Convertir flujo de memoria a texto
    string extractedText = Encoding.Unicode.GetString(textStream.ToArray());

    // Añade el texto extraído al StringBuilder
    builder.Append(extractedText);
}
```

- `TextDevice textDevice = new TextDevice();` : El`TextDevice` La clase se utiliza para extraer texto del PDF.
- `TextExtractionOptions textExtOptions = new TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);` : Esta opción extrae el texto sin formato sin conservar ningún formato, como fuentes o posiciones. También puede utilizar`TextFormattingMode.Raw` Si necesita más control sobre el formato.
- `textDevice.Process(pdfPage, textStream);` :Esto procesa cada página del PDF y almacena el texto extraído en un`MemoryStream`.
-  Finalmente, convertimos el texto del`MemoryStream` a una cadena y añádela a la`StringBuilder`.

## Paso 5: Guardar el texto extraído en un archivo

 Después de procesar todas las páginas, el texto se almacena en el`StringBuilder`El último paso es guardar este texto extraído en un archivo.

```csharp
// Definir la ruta de salida para el archivo de texto
dataDir = dataDir + "input_Text_Extracted_out.txt";

// Guardar el texto extraído en un archivo
File.WriteAllText(dataDir, builder.ToString());

Console.WriteLine("\nText extracted successfully from PDF document.\nFile saved at " + dataDir);
```

- `File.WriteAllText(dataDir, builder.ToString());` :Esto escribe todo el contenido del`StringBuilder` en un archivo de texto.
- La ruta del archivo de salida se establece agregando un nombre de archivo (`"input_Text_Extracted_out.txt"` ) hacia`dataDir` camino.

## Conclusión

Extraer texto de un PDF con Aspose.PDF para .NET es un proceso sencillo y eficaz. Si sigue los pasos que se describen en esta guía, podrá abrir fácilmente documentos PDF, recorrer las páginas y extraer texto en un archivo de texto. Esto resulta especialmente útil para procesar grandes volúmenes de datos PDF, realizar análisis de texto o convertir documentos para su posterior manipulación.

Con Aspose.PDF, no se limita a la extracción de texto: puede gestionar anotaciones, manipular imágenes o incluso convertir archivos PDF a otros formatos como HTML o Word. La flexibilidad y la potencia de esta biblioteca la convierten en una herramienta invaluable para la gestión de archivos PDF en aplicaciones .NET.

## Preguntas frecuentes

### ¿Puede Aspose.PDF extraer texto de archivos PDF basados en imágenes?
No, Aspose.PDF está diseñado para extraer texto de archivos PDF basados en contenido. Para archivos PDF basados en imágenes, se necesita tecnología OCR.

### ¿Aspose.PDF conserva el formato al extraer texto?
De forma predeterminada, el texto se extrae sin formato, pero puedes ajustar las opciones de extracción si deseas conservar algún formato.

### ¿Puedo extraer texto de un rango de páginas específico?
Sí, puedes modificar el código para que recorra un rango específico de páginas en lugar de todas las páginas.

### ¿Cuáles son los modos de extracción de texto en Aspose.PDF?
Aspose.PDF ofrece dos modos: Raw y Pure. El modo Raw intenta conservar el diseño original, mientras que el modo Pure extrae solo el texto sin formato.

### ¿Aspose.PDF para .NET es compatible con .NET Core?
Sí, Aspose.PDF para .NET es totalmente compatible con .NET Core y .NET Framework.