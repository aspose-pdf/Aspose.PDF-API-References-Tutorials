---
title: Extraer texto completo en archivo PDF
linktitle: Extraer texto de todo un archivo PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a extraer todo el texto de un archivo PDF usando Aspose.PDF para .NET.
type: docs
weight: 180
url: /es/net/programming-with-text/extract-text-all/
---
Este tutorial lo guiará a través del proceso de extracción de todo el texto de un archivo PDF con Aspose.PDF para .NET. El código fuente de C# proporcionado muestra los pasos necesarios.

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
using System.IO;
```

## Paso 3: Establezca el directorio del documento
 En el código, localiza la línea que dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` y reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta al directorio donde se almacenan sus documentos.

## Paso 4: Abra el documento PDF
 Abra un documento PDF existente utilizando el`Document`constructor y pasando la ruta al archivo PDF de entrada.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
```

## Paso 5: Extraer todo el texto
 Crear un`TextAbsorber`Objeto para extraer texto del documento. Luego, acepta el absorbedor para todas las páginas.

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
```

## Paso 6: Obtener el texto extraído
 Acceda al texto extraído de la`TextAbsorber` objeto.

```csharp
string extractedText = textAbsorber.Text;
```

## Paso 7: Guarda el texto extraído
 Crear un`TextWriter` y abre el archivo donde quieres guardar el texto extraído. Escribe el texto extraído en el archivo y cierra la secuencia.

```csharp
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
tw.WriteLine(extractedText);
tw. Close();
```

### Código fuente de muestra para extraer todo el texto con Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
// Crear un objeto TextAbsorber para extraer texto
TextAbsorber textAbsorber = new TextAbsorber();
// Acepta el absorbedor para todas las páginas.
pdfDocument.Pages.Accept(textAbsorber);
// Obtener el texto extraído
string extractedText = textAbsorber.Text;
// Crea un escritor y abre el archivo.
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
// Escribe una línea de texto en el archivo
tw.WriteLine(extractedText);
// Cerrar la transmisión
tw.Close();
```

## Conclusión
Ha extraído correctamente todo el texto de un documento PDF con Aspose.PDF para .NET. El texto extraído se ha guardado en el archivo de salida especificado.

### Preguntas frecuentes

#### P: ¿Cuál es el propósito de este tutorial?

A: Este tutorial sirve como guía para ayudarlo a extraer todo el texto de un archivo PDF mediante Aspose.PDF para .NET. El código fuente de C# adjunto proporciona instrucciones paso a paso para lograr esta tarea.

#### P: ¿Qué espacios de nombres debo importar?

R: En el archivo de código donde desea extraer texto, incluya las siguientes directivas using al comienzo del archivo:

```csharp
using Aspose.Pdf;
using System.IO;
```

#### P: ¿Cómo especifico el directorio del documento?

 A: Localiza la linea`string dataDir = "YOUR DOCUMENT DIRECTORY";` en el código y reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

#### P: ¿Cómo abro un documento PDF existente?

 A: En el paso 4, abrirá un documento PDF existente utilizando el`Document` constructor y proporcionar la ruta al archivo PDF de entrada.

#### P: ¿Cómo extraigo todo el texto del documento?

 A: El paso 5 implica crear un`TextAbsorber` Objeto para extraer texto del documento PDF. Luego, aceptará el absorbedor para todas las páginas.

#### P: ¿Cómo puedo acceder al texto extraído?

 A: El paso 6 lo guía para acceder al texto extraído de la`TextAbsorber` objeto.

#### P: ¿Cómo guardo el texto extraído en un archivo?

 A: En el paso 7, crearás un`TextWriter`, abra el archivo donde desea guardar el texto extraído, escriba el texto extraído en el archivo y luego cierre la secuencia.

#### P: ¿Cuál es la conclusión clave de este tutorial?

R: Al seguir este tutorial, aprendió a extraer todo el texto de un documento PDF con Aspose.PDF para .NET. El texto extraído se guardó en un archivo de salida específico, lo que le permitió analizar y manipular el contenido textual del documento.