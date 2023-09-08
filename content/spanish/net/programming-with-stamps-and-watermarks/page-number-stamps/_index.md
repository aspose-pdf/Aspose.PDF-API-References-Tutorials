---
title: Sellos de número de página en archivo PDF
linktitle: Sellos de número de página en archivo PDF
second_title: Aspose.PDF para referencia de API .NET
description: Aprenda a agregar sellos de números de página en un archivo PDF con Aspose.PDF para .NET.
type: docs
weight: 160
url: /es/net/programming-with-stamps-and-watermarks/page-number-stamps/
---
En este tutorial, lo guiaremos paso a paso sobre cómo agregar sellos de números de página en un archivo PDF usando Aspose.PDF para .NET. Usaremos el código fuente de C# proporcionado para abrir un documento PDF existente, crear un sello de número de página, establecer sus propiedades y agregarlo a una página específica del archivo PDF.

## Paso 1: configurar el entorno

Antes de comenzar, asegúrese de tener lo siguiente:

- Un entorno de desarrollo .NET instalado.
- La biblioteca Aspose.PDF para .NET descargada y referenciada en su proyecto.

## Paso 2: cargar el documento PDF existente

El primer paso es cargar el documento PDF existente en su proyecto. Así es cómo:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Abra el documento PDF existente
Document pdfDocument = new Document(dataDir + "PageNumberStamp.pdf");
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real al directorio donde se encuentra su documento PDF.

## Paso 3: Crear y configurar el sello de numeración de páginas

Ahora que el documento PDF está cargado, podemos crear un búfer de numeración de páginas y configurarlo según nuestras necesidades. Así es cómo:

```csharp
// Crear un búfer de número de página
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// Definir si el buffer está en segundo plano o no
pageNumberStamp.Background = false;

// Formato del búfer de numeración de páginas
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;

// Margen inferior del búfer de numeración de páginas
pageNumberStamp.BottomMargin = 10;

// Alineación horizontal del búfer de numeración de páginas
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;

// Número de inicio de la numeración de páginas.
pageNumberStamp.StartingNumber = 1;

// Establecer propiedades de texto del búfer de número de página
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;
```

El código anterior crea un sello de número de página con propiedades como formato de número de página, margen inferior, alineación horizontal, número inicial y propiedades de texto.

## Paso 4: agregar el sello del número de página a una página específica

Una vez configurado el sello del número de página, podemos agregarlo a una página específica del documento PDF. Así es cómo:

```csharp
// Agregue el búfer de número de página a una página específica
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
```

El código anterior agrega el sello del número de página a la primera página del documento PDF. Puede cambiar el número de página según sea necesario.

## Paso 5: Guardar el documento PDF modificado

Una vez que se agrega el sello del número de página al documento PDF, podemos guardar el documento PDF modificado. Así es cómo:

```csharp
// Guarde el documento PDF modificado
pdfDocument.Save(dataDir + "PageNumberStamp_out.pdf");
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real al directorio donde desea guardar el documento PDF editado.

### Código fuente de muestra para sellos de números de página usando Aspose.PDF para .NET 
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

// Agregar sello a una página en particular
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
dataDir = dataDir + "PageNumberStamp_out.pdf";

// Guardar documento de salida
pdfDocument.Save(dataDir);
Console.WriteLine("\nPage number stamp added successfully.\nFile saved at " + dataDir);

```

## Conclusión

¡Enhorabuena! Ha aprendido cómo agregar sellos de números de página a un documento PDF usando Aspose.PDF para .NET. Ahora puede personalizar sus documentos PDF agregando números de página claros e informativos.

### Preguntas frecuentes sobre sellos de números de página en archivos PDF

#### P: ¿Qué es un sello de número de página y cómo se utiliza para agregar números de página a un archivo PDF?

R: Un sello de número de página es una función de Aspose.PDF que le permite agregar números de página dinámicos a páginas específicas de un documento PDF. En este tutorial, esto se logra creando un objeto PageNumberStamp, configurando sus propiedades y agregándolo a una página designada.

#### P: ¿Cómo logra el código fuente C# proporcionado agregar sellos de números de página a un archivo PDF?

R: El código demuestra cómo cargar un documento PDF existente, crear un PageNumberStamp, establecer varias propiedades (como formato, fuente, alineación, etc.) y luego agregar el sello a una página específica. El sello calcula automáticamente el recuento total de páginas e inserta los números de página correctos.

#### P: ¿Puedo personalizar la apariencia del número de página, como el estilo, el color y el tamaño de la fuente?

R: Por supuesto, puedes personalizar la apariencia del sello del número de página ajustando propiedades como fuente, tamaño de fuente, estilo de fuente (negrita, cursiva, etc.) y color del texto.

#### P: ¿Es posible agregar sellos de números de página a varias páginas dentro de un documento PDF?

R: Sí, puede agregar sellos de números de página a varias páginas creando varios objetos PageNumberStamp y agregando cada uno a las páginas deseadas.

#### P: ¿Puedo elegir si el sello del número de página aparece como parte del contenido de la página o como elemento de fondo?

 R: Sí, puedes controlar si el sello del número de página aparece como parte del contenido de la página o como elemento de fondo configurando el`Background` propiedad de PageNumberStamp.

#### P: ¿Cómo especifico el formato del número de página, incluido el recuento total de páginas?

 R: El código utiliza el`Format`propiedad de PageNumberStamp para especificar el formato del número de página. La macro "# de" se utiliza para representar el recuento total de páginas.

#### P: ¿Qué sucede si agrego el mismo sello de número de página en varias páginas?

R: Agregar la misma instancia de PageNumberStamp a varias páginas mostrará los números de página correctos para cada página. El sello ajusta automáticamente el número de página y el recuento total de páginas.

#### P: ¿Puedo agregar sellos de números de página a las secciones de encabezado o pie de página de un documento PDF?

R: Si bien los PageNumberStamps generalmente se agregan directamente al contenido de la página, puedes usar FloatingBox u otras técnicas para colocarlos en las secciones de encabezado o pie de página.

#### P: ¿Cómo especifico la posición del sello del número de página en la página?

 R: El`BottomMargin` y`HorizontalAlignment` Las propiedades de PageNumberStamp le permiten controlar la posición del sello dentro de la página.

#### P: ¿Qué sucede si quiero comenzar a numerar las páginas desde un número diferente en lugar de 1?

 R: Puedes configurar el`StartingNumber`propiedad de PageNumberStamp para especificar el número de página inicial.