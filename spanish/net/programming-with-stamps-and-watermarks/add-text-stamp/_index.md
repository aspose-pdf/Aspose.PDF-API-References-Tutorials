---
title: Agregar sello de texto
linktitle: Agregar sello de texto
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a agregar fácilmente un sello de texto a sus documentos PDF con Aspose.PDF para .NET.
type: docs
weight: 50
url: /es/net/programming-with-stamps-and-watermarks/add-text-stamp/
---
En este tutorial, lo guiaremos paso a paso sobre cómo agregar un sello de texto a un documento PDF usando Aspose.PDF para .NET. Le mostraremos cómo usar el código fuente de C# provisto para agregar un sello de texto personalizado a una página específica del documento PDF.

## Paso 1: Configuración del entorno

Antes de comenzar, asegúrese de tener lo siguiente:

- Un entorno de desarrollo .NET instalado.
- La biblioteca Aspose.PDF para .NET descargada y referenciada en su proyecto.

## Paso 2: Cargar el documento PDF

El primer paso es cargar el documento PDF existente en su proyecto. Así es cómo:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Abre el documento
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real al directorio donde se encuentra su documento PDF.

## Paso 3: Crear el búfer de texto

Ahora que ha cargado el documento PDF, puede crear el sello de texto para agregar. Aquí está cómo hacerlo:

```csharp
// Crear el búfer de texto
TextStamp textStamp = new TextStamp("Example Stamp");
```

El código anterior crea un nuevo búfer de texto que contiene el texto especificado.

## Paso 4: Configuración de las propiedades del sello de texto

Antes de agregar el sello de texto al documento PDF, puede configurar varias propiedades del sello, como el fondo, la posición, la rotación, la fuente, el tamaño, etc. Así es como se hace:

```csharp
// Configurar las propiedades del búfer de texto
textStamp. Background = true;
textStamp. XIndent = 100;
textStamp. YIndent = 100;
textStamp.Rotate = Rotate.on90;
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Aqua);
```

Puede ajustar estas propiedades según sus necesidades.

## Paso 5: Agregar sello de texto a PDF

Ahora que el sello de texto está listo, puede agregarlo a una página específica del documento PDF. Así es cómo:

```csharp
// Agregar búfer de texto a una página específica
pdfDocument.Pages[1].AddStamp(textStamp);
```

El código anterior agrega el sello de texto a la primera página del documento PDF. Puede especificar otra página si es necesario.

## Paso 6: Guarde el documento de salida

Una vez que haya agregado el sello de texto, puede guardar el documento PDF editado. Así es cómo:

```csharp
// Guardar el documento de salida
pdfDocument.Save(dataDir);
```

El código anterior guarda el documento PDF modificado en el directorio especificado.

### Ejemplo de código fuente para Agregar sello de texto usando Aspose.PDF para .NET 
```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Abrir documento
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");

// Crear sello de texto
TextStamp textStamp = new TextStamp("Sample Stamp");

// Establecer si el sello es el fondo
textStamp.Background = true;

// Establecer origen
textStamp.XIndent = 100;
textStamp.YIndent = 100;

// Girar sello
textStamp.Rotate = Rotation.on90;

// Establecer propiedades de texto
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold;
textStamp.TextState.FontStyle = FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Aqua);

// Agregar sello a una página en particular
pdfDocument.Pages[1].AddStamp(textStamp);
dataDir = dataDir + "AddTextStamp_out.pdf";

// Guardar documento de salida
pdfDocument.Save(dataDir);
Console.WriteLine("\nText stamp added successfully.\nFile saved at " + dataDir);            

```

## Conclusión

¡Felicidades! Aprendió a agregar un sello de texto usando Aspose.PDF para .NET. Ahora puede aplicar este conocimiento a sus propios proyectos para agregar sellos de texto personalizados a documentos PDF.
