---
title: Extraer texto de columnas en un archivo PDF
linktitle: Extraer texto de columnas en un archivo PDF
second_title: Aspose.PDF para referencia de API .NET
description: Aprenda a extraer texto de columnas en un archivo PDF usando Aspose.PDF para .NET.
type: docs
weight: 150
url: /es/net/programming-with-text/extract-columns-text/
---
Este tutorial lo guiará a través del proceso de extracción de texto de columnas en un archivo PDF usando Aspose.PDF para .NET. El código fuente de C# proporcionado demuestra los pasos necesarios.

## Requisitos
Antes de comenzar, asegúrese de tener lo siguiente:

- Visual Studio o cualquier otro compilador de C# instalado en su máquina.
- Aspose.PDF para la biblioteca .NET. Puede descargarlo del sitio web oficial de Aspose o utilizar un administrador de paquetes como NuGet para instalarlo.

## Paso 1: configurar el proyecto
1. Cree un nuevo proyecto de C# en su entorno de desarrollo preferido.
2. Agregue una referencia a la biblioteca Aspose.PDF para .NET.

## Paso 2: importar los espacios de nombres necesarios
En el archivo de código donde desea extraer el texto de las columnas, agregue lo siguiente usando directivas en la parte superior del archivo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

## Paso 3: configurar el directorio de documentos
 En el código, localice la línea que dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` y reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta al directorio donde están almacenados sus documentos.

## Paso 4: abre el documento PDF
 Abra un documento PDF existente usando el`Document`constructor y pasando la ruta al archivo PDF de entrada.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## Paso 5: ajusta el tamaño de fuente
Reduzca el tamaño de fuente de los fragmentos de texto en un factor de 0,7 para mejorar la legibilidad y representar mejor el texto en columnas.

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
foreach(TextFragment tf in tfc)
{
     tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
```

## Paso 6: extraer texto de las columnas
 Guarde el documento PDF modificado en una secuencia de memoria y vuelva a cargarlo como un documento nuevo. Luego, utiliza el`TextAbsorber` clase para extraer texto de las columnas.

```csharp
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
textAbsorber.Visit(pdfDocument);
```

## Paso 7: guarde el texto extraído
Guarde el texto extraído en un archivo de texto en la ruta del archivo de salida especificada.

```csharp
dataDir = dataDir + "ExtractColumnsText_out.txt";
File.WriteAllText(dataDir, extractedText);
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

### Código fuente de muestra para extraer texto de columnas usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");                
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
foreach (TextFragment tf in tfc)
{
	// Es necesario reducir el tamaño de fuente al menos en un 70%.
	tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
textAbsorber.Visit(pdfDocument); 
dataDir = dataDir + "ExtractColumnsText_out.txt";
System.IO.File.WriteAllText(dataDir, extractedText);           
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

## Conclusión
Ha extraído con éxito el texto de las columnas de un documento PDF utilizando Aspose.PDF para .NET. El texto extraído se ha guardado en el archivo de salida especificado.

### Preguntas frecuentes

#### P: ¿Cuál es el propósito de este tutorial?

R: Este tutorial ofrece una guía paso a paso sobre cómo extraer columnas de texto de un archivo PDF usando Aspose.PDF para .NET. El código fuente C# adjunto proporciona una demostración práctica de los procedimientos necesarios.

#### P: ¿Qué espacios de nombres debo importar?

R: En el archivo de código donde desea extraer columnas de texto, incluya las siguientes directivas de uso al principio del archivo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

#### P: ¿Cómo especifico el directorio de documentos?

 R: Localice la línea`string dataDir = "YOUR DOCUMENT DIRECTORY";` en el código y reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

#### P: ¿Cómo abro un documento PDF existente?

 R: En el Paso 4, abrirá un documento PDF existente usando el`Document` constructor y proporcionando la ruta al archivo PDF de entrada.

#### P: ¿Por qué se ajusta el tamaño de fuente?

R: El paso 5 implica reducir el tamaño de fuente de los fragmentos de texto en un factor de 0,7. Este ajuste mejora la legibilidad y representa con mayor precisión el texto en columnas.

#### P: ¿Cómo extraigo texto de las columnas?

 R: El paso 6 consiste en guardar el documento PDF modificado en una secuencia de memoria, recargarlo como un documento nuevo y luego usar el`TextAbsorber` clase para extraer texto de las columnas.

#### P: ¿Cuál es el propósito de guardar el texto extraído?

R: En el paso 7, guardará el texto extraído en un archivo de texto en la ruta del archivo de salida especificada.

#### P: ¿Por qué reducir el tamaño de fuente antes de la extracción?

R: Reducir el tamaño de la fuente ayuda a garantizar que el texto extraído se alinee correctamente dentro de las columnas, lo que proporciona una representación más precisa del diseño original.

#### P: ¿Cuál es la conclusión clave de este tutorial?

R: Al seguir este tutorial, habrá adquirido los conocimientos y las habilidades necesarios para extraer columnas de texto de un documento PDF utilizando Aspose.PDF para .NET. El texto resultante se ha guardado en el archivo de salida especificado.