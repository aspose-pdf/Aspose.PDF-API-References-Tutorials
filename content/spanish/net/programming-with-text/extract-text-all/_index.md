---
title: Extraer texto todo en un archivo PDF
linktitle: Extraer texto todo en archivo PDF
second_title: Aspose.PDF para referencia de API .NET
description: Aprenda a extraer todo el texto en un archivo PDF usando Aspose.PDF para .NET.
type: docs
weight: 180
url: /es/net/programming-with-text/extract-text-all/
---
Este tutorial lo guiará a través del proceso de extracción de todo el texto en un archivo PDF usando Aspose.PDF para .NET. El código fuente de C# proporcionado demuestra los pasos necesarios.

## Requisitos
Antes de comenzar, asegúrese de tener lo siguiente:

- Visual Studio o cualquier otro compilador de C# instalado en su máquina.
- Aspose.PDF para la biblioteca .NET. Puede descargarlo del sitio web oficial de Aspose o utilizar un administrador de paquetes como NuGet para instalarlo.

## Paso 1: configurar el proyecto
1. Cree un nuevo proyecto de C# en su entorno de desarrollo preferido.
2. Agregue una referencia a la biblioteca Aspose.PDF para .NET.

## Paso 2: importar los espacios de nombres necesarios
En el archivo de código donde desea extraer texto, agregue lo siguiente usando directivas en la parte superior del archivo:

```csharp
using Aspose.Pdf;
using System.IO;
```

## Paso 3: configurar el directorio de documentos
 En el código, localice la línea que dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` y reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta al directorio donde están almacenados sus documentos.

## Paso 4: abre el documento PDF
 Abra un documento PDF existente usando el`Document`constructor y pasando la ruta al archivo PDF de entrada.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
```

## Paso 5: extrae todo el texto
 Crear un`TextAbsorber`objeto para extraer texto del documento. Luego, acepte el absorbente para todas las páginas.

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
```

## Paso 6: obtenga el texto extraído
 Accede al texto extraído del`TextAbsorber` objeto.

```csharp
string extractedText = textAbsorber.Text;
```

## Paso 7: guarde el texto extraído
 Crear un`TextWriter` y abra el archivo donde desea guardar el texto extraído. Escriba el texto extraído en el archivo y cierre la transmisión.

```csharp
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
tw.WriteLine(extractedText);
tw. Close();
```

### Código fuente de muestra para Extraer texto todo usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
// Crear objeto TextAbsorber para extraer texto
TextAbsorber textAbsorber = new TextAbsorber();
// Aceptar el absorbente para todas las páginas.
pdfDocument.Pages.Accept(textAbsorber);
// Obtener el texto extraído
string extractedText = textAbsorber.Text;
// Crea un escritor y abre el archivo.
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
// Escribe una línea de texto en el archivo.
tw.WriteLine(extractedText);
// Cerrar la transmisión
tw.Close();
```

## Conclusión
Ha extraído con éxito todo el texto de un documento PDF utilizando Aspose.PDF para .NET. El texto extraído se ha guardado en el archivo de salida especificado.

### Preguntas frecuentes

#### P: ¿Cuál es el propósito de este tutorial?

R: Este tutorial sirve como guía para ayudarle a extraer todo el texto de un archivo PDF usando Aspose.PDF para .NET. El código fuente de C# adjunto proporciona instrucciones paso a paso para realizar esta tarea.

#### P: ¿Qué espacios de nombres debo importar?

R: En el archivo de código donde desea extraer texto, incluya las siguientes directivas de uso al principio del archivo:

```csharp
using Aspose.Pdf;
using System.IO;
```

#### P: ¿Cómo especifico el directorio de documentos?

 R: Localice la línea`string dataDir = "YOUR DOCUMENT DIRECTORY";` en el código y reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

#### P: ¿Cómo abro un documento PDF existente?

 R: En el Paso 4, abrirá un documento PDF existente usando el`Document` constructor y proporcionando la ruta al archivo PDF de entrada.

#### P: ¿Cómo extraigo todo el texto del documento?

 R: El paso 5 implica crear un`TextAbsorber` objeto para extraer texto del documento PDF. Luego, tendrá el protector para todas las páginas.

#### P: ¿Cómo accedo al texto extraído?

 R: El paso 6 le guía para acceder al texto extraído del`TextAbsorber` objeto.

#### P: ¿Cómo guardo el texto extraído en un archivo?

 R: En el paso 7, creará un`TextWriter`, abra el archivo donde desea guardar el texto extraído, escriba el texto extraído en el archivo y luego cierre la secuencia.

#### P: ¿Cuál es la conclusión clave de este tutorial?

R: Al seguir este tutorial, habrá aprendido cómo extraer todo el texto de un documento PDF usando Aspose.PDF para .NET. El texto extraído se ha guardado en un archivo de salida específico, lo que le permite analizar y manipular el contenido textual del documento.