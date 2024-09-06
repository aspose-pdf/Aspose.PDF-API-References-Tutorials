---
title: Sellos de número de página en archivo PDF
linktitle: Sellos de número de página en archivo PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a agregar sellos de número de página en un archivo PDF con Aspose.PDF para .NET.
type: docs
weight: 160
url: /es/net/programming-with-stamps-and-watermarks/page-number-stamps/
---
En este tutorial, le mostraremos paso a paso cómo agregar sellos de número de página en un archivo PDF con Aspose.PDF para .NET. Usaremos el código fuente de C# proporcionado para abrir un documento PDF existente, crear un sello de número de página, configurar sus propiedades y agregarlo a una página específica en el archivo PDF.

## Paso 1: Configuración del entorno

Antes de comenzar, asegúrese de tener lo siguiente:

- Un entorno de desarrollo .NET instalado.
- La biblioteca Aspose.PDF para .NET descargada y referenciada en su proyecto.

## Paso 2: Cargar el documento PDF existente

El primer paso es cargar el documento PDF existente en el proyecto. A continuación, le indicamos cómo hacerlo:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Abrir el documento PDF existente
Document pdfDocument = new Document(dataDir + "PageNumberStamp.pdf");
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real al directorio donde se encuentra su documento PDF.

## Paso 3: Creación y configuración del sello de numeración de páginas

Ahora que el documento PDF está cargado, podemos crear un buffer de numeración de páginas y configurarlo según nuestras necesidades. A continuación, le indicamos cómo:

```csharp
// Crear un buffer de números de página
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// Define si el buffer está en segundo plano o no
pageNumberStamp.Background = false;

// Formato del buffer de numeración de páginas
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;

// Margen inferior del buffer de numeración de páginas
pageNumberStamp.BottomMargin = 10;

// Alineación horizontal del buffer de numeración de páginas
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;

// Número inicial de numeración de página
pageNumberStamp.StartingNumber = 1;

// Establecer las propiedades del texto del búfer del número de página
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;
```

El código anterior crea un sello de número de página con propiedades como formato de número de página, margen inferior, alineación horizontal, número inicial y propiedades de texto.

## Paso 4: Agregar el sello de número de página a una página específica

Una vez configurado el sello de número de página, podemos agregarlo a una página específica del documento PDF. A continuación, le indicamos cómo:

```csharp
// Añade el buffer de número de página a una página específica
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
```

El código anterior agrega el número de página a la primera página del documento PDF. Puede cambiar el número de página según sea necesario.

## Paso 5: Guardar el documento PDF modificado

Una vez que se agrega el sello de número de página al documento PDF, podemos guardar el documento PDF modificado. A continuación, le indicamos cómo hacerlo:

```csharp
// Guardar el documento PDF modificado
pdfDocument.Save(dataDir + "PageNumberStamp_out.pdf");
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real al directorio donde desea guardar el documento PDF editado.

### Código fuente de muestra para sellos de números de página utilizando Aspose.PDF para .NET 
```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Abrir documento
Document pdfDocument = new Document(dataDir+ "PageNumberStamp.pdf");

// Crear sello de número de página
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// Si el sello es de fondo
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

// Añadir sello a una página específica
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
dataDir = dataDir + "PageNumberStamp_out.pdf";

// Guardar documento de salida
pdfDocument.Save(dataDir);
Console.WriteLine("\nPage number stamp added successfully.\nFile saved at " + dataDir);

```

## Conclusión

¡Felicitaciones! Aprendió a agregar números de página a un documento PDF con Aspose.PDF para .NET. Ahora puede personalizar sus documentos PDF agregando números de página claros e informativos.

### Preguntas frecuentes sobre los sellos de números de página en archivos PDF

#### P: ¿Qué es un sello de número de página y cómo se utiliza para agregar números de página a un archivo PDF?

A: Un sello de número de página es una función de Aspose.PDF que le permite agregar números de página dinámicos a páginas específicas de un documento PDF. En este tutorial, esto se logra creando un objeto PageNumberStamp, configurando sus propiedades y agregándolo a una página designada.

#### P: ¿Cómo logra el código fuente C# proporcionado agregar sellos de número de página a un archivo PDF?

A: El código demuestra cómo cargar un documento PDF existente, crear un PageNumberStamp, configurar varias propiedades (como formato, fuente, alineación, etc.) y luego agregar el sello a una página específica. El sello calcula automáticamente el recuento total de páginas e inserta los números de página correctos.

#### P: ¿Puedo personalizar la apariencia del número de página, como el estilo de fuente, el color y el tamaño?

R: Por supuesto, puede personalizar la apariencia del sello del número de página ajustando propiedades como fuente, tamaño de fuente, estilo de fuente (negrita, cursiva, etc.) y color del texto.

#### P: ¿Es posible agregar sellos de número de página a varias páginas dentro de un documento PDF?

R: Sí, puede agregar sellos de número de página a varias páginas creando varios objetos PageNumberStamp y agregando cada uno a las páginas deseadas.

#### P: ¿Puedo elegir si el sello del número de página aparece como parte del contenido de la página o como un elemento de fondo?

 R: Sí, puede controlar si el sello del número de página aparece como parte del contenido de la página o como un elemento de fondo configurando la`Background` propiedad de PageNumberStamp.

#### P: ¿Cómo especifico el formato del número de página, incluido el recuento total de páginas?

 A: El código utiliza el`Format`Propiedad de PageNumberStamp para especificar el formato del número de página. La macro "# of" se utiliza para representar el recuento total de páginas.

#### P: ¿Qué sucede si agrego el mismo sello de número de página a varias páginas?

R: Si se agrega la misma instancia de PageNumberStamp a varias páginas, se mostrarán los números de página correctos para cada página. El sello ajusta automáticamente el número de página y el recuento total de páginas.

#### P: ¿Puedo agregar sellos de número de página a las secciones de encabezado o pie de página de un documento PDF?

R: Si bien los PageNumberStamps normalmente se agregan directamente al contenido de la página, puedes usar FloatingBox u otras técnicas para posicionarlos en secciones de encabezado o pie de página.

#### P: ¿Cómo especifico la posición del sello del número de página en la página?

 A: El`BottomMargin` y`HorizontalAlignment` Las propiedades de PageNumberStamp le permiten controlar la posición del sello dentro de la página.

#### P: ¿Qué pasa si quiero comenzar a numerar páginas desde un número diferente al 1?

 A: Puedes configurar el`StartingNumber`propiedad de PageNumberStamp para especificar el número de página inicial.