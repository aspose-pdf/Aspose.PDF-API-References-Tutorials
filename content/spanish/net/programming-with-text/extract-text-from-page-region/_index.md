---
title: Extraer texto de la región de la página en un archivo PDF
linktitle: Extraer texto de la región de la página en un archivo PDF
second_title: Aspose.PDF para referencia de API .NET
description: Aprenda a extraer texto de una región específica en una página en un archivo PDF usando Aspose.PDF para .NET.
type: docs
weight: 190
url: /es/net/programming-with-text/extract-text-from-page-region/
---
Este tutorial lo guiará a través del proceso de extracción de texto de una región específica en una página en un archivo PDF usando Aspose.PDF para .NET. El código fuente de C# proporcionado demuestra los pasos necesarios.

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

## Paso 5: extraer texto de una región de página
 Crear un`TextAbsorber` objeto para extraer texto del documento. Configurar el`TextSearchOptions` para limitar la búsqueda a una región de página específica definida por un rectángulo.

```csharp
TextAbsorber absorb = new TextAbsorber();
absorb.TextSearchOptions.LimitToPageBounds = true;
absorb.TextSearchOptions.Rectangle = new Aspose.Pdf.Rectangle(100, 200, 250, 350);
pdfDocument.Pages[1].Accept(absorb);
```

## Paso 6: obtenga el texto extraído
 Accede al texto extraído del`TextAbsorber` objeto.

```csharp
string extractedText = absorb.Text;
```

## Paso 7: guarde el texto extraído
 Crear un`TextWriter` y abra el archivo donde desea guardar el texto extraído. Escriba el texto extraído en el archivo y cierre la transmisión.

```csharp
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
tw.WriteLine(extractedText);
tw. Close();
```

### Código fuente de muestra para extraer texto de la región de la página usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
// Crear objeto TextAbsorber para extraer texto
TextAbsorber absorber = new TextAbsorber();
absorber.TextSearchOptions.LimitToPageBounds = true;
absorber.TextSearchOptions.Rectangle = new Aspose.Pdf.Rectangle(100, 200, 250, 350);
// Aceptar el absorbente para la primera página.
pdfDocument.Pages[1].Accept(absorber);
// Obtener el texto extraído
string extractedText = absorber.Text;
// Crea un escritor y abre el archivo.
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
// Escribe una línea de texto en el archivo.
tw.WriteLine(extractedText);
// Cerrar la transmisión
tw.Close();
```

## Conclusión
Ha extraído con éxito texto de una región específica en una página de un documento PDF utilizando Aspose.PDF para .NET. El texto extraído se ha guardado en el archivo de salida especificado.

### Preguntas frecuentes

#### P: ¿Cuál es el propósito de este tutorial?

R: Este tutorial tiene como objetivo guiarlo a través del proceso de extracción de texto de una región específica en una página en un archivo PDF usando Aspose.PDF para .NET. El código fuente de C# adjunto proporciona instrucciones paso a paso para realizar esta tarea.

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

#### P: ¿Cómo extraigo texto de una región de página específica?

 R: El paso 5 implica crear un`TextAbsorber`objeto para extraer texto del documento PDF. Luego configurará el`TextSearchOptions` para definir una región rectangular específica en la página usando coordenadas.

#### P: ¿Cómo accedo al texto extraído?

 R: El paso 6 le guía para acceder al texto extraído del`TextAbsorber` objeto.

#### P: ¿Cómo guardo el texto extraído en un archivo?

 R: En el paso 7, creará un`TextWriter`, abra el archivo donde desea guardar el texto extraído, escriba el texto extraído en el archivo y luego cierre la secuencia.

#### P: ¿Cuál es la conclusión clave de este tutorial?

R: Al seguir este tutorial, habrá aprendido cómo extraer texto de una región específica en una página de un documento PDF usando Aspose.PDF para .NET. El texto extraído se ha guardado en un archivo de salida específico, lo que le permite apuntar y analizar con precisión el contenido textual deseado.