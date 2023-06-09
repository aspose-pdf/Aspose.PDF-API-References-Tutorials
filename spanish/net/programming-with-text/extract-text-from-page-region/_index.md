---
title: Extraer texto de la región de la página
linktitle: Extraer texto de la región de la página
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a extraer texto de una región específica en una página de un documento PDF usando Aspose.PDF para .NET.
type: docs
weight: 190
url: /es/net/programming-with-text/extract-text-from-page-region/
---

Este tutorial lo guiará a través del proceso de extracción de texto de una región específica en una página de un documento PDF usando Aspose.PDF para .NET. El código fuente de C# proporcionado demuestra los pasos necesarios.

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

## Paso 6: Obtener el texto extraído
 Accede al texto extraído de la`TextAbsorber` objeto.

```csharp
string extractedText = absorb.Text;
```

## Paso 7: Guarda el texto extraído
 Crear un`TextWriter` y abra el archivo donde desea guardar el texto extraído. Escriba el texto extraído en el archivo y cierre la transmisión.

```csharp
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
tw.WriteLine(extractedText);
tw. Close();
```

### Ejemplo de código fuente para Extraer texto de la región de la página usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
// Crear objeto TextAbsorber para extraer texto
TextAbsorber absorber = new TextAbsorber();
absorber.TextSearchOptions.LimitToPageBounds = true;
absorber.TextSearchOptions.Rectangle = new Aspose.Pdf.Rectangle(100, 200, 250, 350);
// Aceptar el absorbedor para la primera página
pdfDocument.Pages[1].Accept(absorber);
// Obtener el texto extraído
string extractedText = absorber.Text;
// Crea un escritor y abre el archivo.
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
// Escribir una línea de texto en el archivo.
tw.WriteLine(extractedText);
// Cierra la corriente
tw.Close();
```

## Conclusión
Ha extraído con éxito texto de una región específica en una página de un documento PDF utilizando Aspose.PDF para .NET. El texto extraído se ha guardado en el archivo de salida especificado.