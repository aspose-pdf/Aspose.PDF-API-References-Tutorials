---
title: Sellos de número de página
linktitle: Sellos de número de página
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a agregar sellos de número de página a un documento PDF con Aspose.PDF para .NET.
type: docs
weight: 160
url: /es/net/programming-with-stamps-and-watermarks/page-number-stamps/
---
En este tutorial, lo guiaremos paso a paso sobre cómo agregar sellos de números de página a un documento PDF utilizando Aspose.PDF para .NET. Usaremos el código fuente de C# provisto para abrir un documento PDF existente, crear un sello de número de página, establecer sus propiedades y agregarlo a una página específica en el documento PDF.

## Paso 1: Configuración del entorno

Antes de comenzar, asegúrese de tener lo siguiente:

- Un entorno de desarrollo .NET instalado.
- La biblioteca Aspose.PDF para .NET descargada y referenciada en su proyecto.

## Paso 2: Cargar el documento PDF existente

El primer paso es cargar el documento PDF existente en su proyecto. Así es cómo:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Abra el documento PDF existente
Document pdfDocument = new Document(dataDir + "PageNumberStamp.pdf");
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real al directorio donde se encuentra su documento PDF.

## Paso 3: Creación y configuración del sello de numeración de páginas

Ahora que el documento PDF está cargado, podemos crear un búfer de numeración de páginas y configurarlo según nuestras necesidades. Así es cómo:

```csharp
// Crear un búfer de número de página
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// Definir si el búfer está en segundo plano o no
pageNumberStamp.Background = false;

// Formato del búfer de numeración de páginas
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;

// Margen inferior del búfer de numeración de páginas
pageNumberStamp.BottomMargin = 10;

// Alineación horizontal del búfer de numeración de páginas
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;

// Número de inicio de la numeración de páginas
pageNumberStamp.StartingNumber = 1;

// Establecer las propiedades del texto del búfer del número de página
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;
```

El código anterior crea un sello de número de página con propiedades como formato de número de página, margen inferior, alineación horizontal, número inicial y propiedades de texto.

## Paso 4: agregar el sello de número de página a una página específica

Una vez configurado el sello de número de página, podemos agregarlo a una página específica del documento PDF. Así es cómo:

```csharp
// Agregue el búfer de número de página a una página específica
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
```

El código anterior agrega el sello de número de página a la primera página del documento PDF. Puede cambiar el número de página según sea necesario.

## Paso 5: Guardar el documento PDF modificado

Una vez que se agrega el sello del número de página al documento PDF, podemos guardar el documento PDF modificado. Así es cómo:

```csharp
// Guarde el documento PDF modificado
pdfDocument.Save(dataDir + "PageNumberStamp_out.pdf");
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real al directorio donde desea guardar el documento PDF editado.

### Ejemplo de código fuente para sellos de número de página usando Aspose.PDF para .NET 
```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Abrir documento
Document pdfDocument = new Document(dataDir+ "PageNumberStamp.pdf");

// Crear sello de número de página
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// Si el sello es fondo
pageNumberStamp.Background = false;
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;
pageNumberStamp.BottomMargin = 10;
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;
pageNumberStamp.StartingNumber = 1;

// Establecer propiedades de texto
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;

// Agregar sello a una página en particular
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
dataDir = dataDir + "PageNumberStamp_out.pdf";

// Guardar documento de salida
pdfDocument.Save(dataDir);
Console.WriteLine("\nPage number stamp added successfully.\nFile saved at " + dataDir);

```

## Conclusión

¡Felicidades! Aprendió a agregar sellos de número de página a un documento PDF usando Aspose.PDF para .NET. Ahora puede personalizar sus documentos PDF agregando números de página claros e informativos.
