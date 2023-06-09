---
title: Agregar diferentes encabezados
linktitle: Agregar diferentes encabezados
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a agregar fácilmente diferentes encabezados a cada página de sus documentos PDF con Aspose.PDF para .NET.
type: docs
weight: 30
url: /es/net/programming-with-stamps-and-watermarks/adding-different-headers/
---
En este tutorial, lo guiaremos paso a paso sobre cómo agregar diferentes encabezados a un documento PDF utilizando Aspose.PDF para .NET. Le mostraremos cómo utilizar el código fuente de C# proporcionado para agregar encabezados personalizados a cada página del documento PDF.

## Paso 1: Configuración del entorno

Antes de comenzar, asegúrese de tener lo siguiente:

- Un entorno de desarrollo .NET instalado.
- La biblioteca Aspose.PDF para .NET descargada y referenciada en su proyecto.

## Paso 2: Cargar el documento PDF

El primer paso es cargar el documento PDF existente en su proyecto. Así es cómo:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Abre el documento fuente
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "AddingDifferentHeaders.pdf");
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real al directorio donde se encuentra su documento PDF.

## Paso 3: Creación de búferes de encabezado

Ahora que ha cargado el documento PDF, puede crear los sellos de encabezado para agregar. Así es cómo:

```csharp
// Crear tres búferes de encabezado
Aspose.Pdf.TextStamp stamp1 = new Aspose.Pdf.TextStamp("Header 1");
Aspose.Pdf.TextStamp stamp2 = new Aspose.Pdf.TextStamp("Header 2");
Aspose.Pdf.TextStamp stamp3 = new Aspose.Pdf.TextStamp("Header 3");
```

El código anterior crea tres nuevos búferes de encabezado que contienen el texto especificado.

## Paso 4: Configuración de las propiedades del búfer de encabezado

Antes de agregar los sellos de encabezado al documento PDF, puede configurar diferentes propiedades para cada sello, como alineación, tamaño, color, etc. Así es como se hace:

```csharp
// Configurar el primer búfer de encabezado
stamp1.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
stamp1.TextState.FontStyle = FontStyles.Bold;
stamp1.TextState.ForegroundColor = Color.Red;
stamp1.TextState.FontSize = 14;

// Configuración del segundo búfer de cabecera
stamp2.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
stamp2.Zoom = 10;

// Configurar el búfer del tercer encabezado
stamp3.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp3.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
stamp3.RotateAngle = 35;
stamp3.TextState.BackgroundColor = Color.Pink;
stamp3.TextState.Font = FontRepository.FindFont("Verdana");
```

Puede ajustar estas propiedades según sea necesario para cada búfer de encabezado.

## Paso 5: agregue sellos de encabezado a PDF

Ahora que los sellos de encabezado están listos, puede agregarlos a cada página específica del documento PDF. Así es cómo:

```csharp
// Agregue búferes de encabezado a páginas específicas
doc.Pages[1].AddStamp(stamp1);
doc.Pages[2].AddStamp(stamp2);
doc.Pages[3].AddStamp(stamp3);
```

El código anterior agrega cada sello de encabezado a la página correspondiente del documento PDF.

## Paso 6: Guarde el documento de salida

Una vez que haya agregado los sellos de encabezado, puede guardar el documento PDF editado. Así es cómo:

```csharp
// Guardar el documento actualizado
doc.Save(dataDir);
```

El código anterior guarda el documento PDF editado en el directorio especificado.

### Ejemplo de código fuente para agregar diferentes encabezados usando Aspose.PDF para .NET 
```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Documento de código abierto
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "AddingDifferentHeaders.pdf");

// Crea tres sellos
Aspose.Pdf.TextStamp stamp1 = new Aspose.Pdf.TextStamp("Header 1");
Aspose.Pdf.TextStamp stamp2 = new Aspose.Pdf.TextStamp("Header 2");
Aspose.Pdf.TextStamp stamp3 = new Aspose.Pdf.TextStamp("Header 3");

//Establezca la alineación del sello (coloque el sello en la parte superior de la página, centrado horizontalmente)
stamp1.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;

// Especifique el estilo de fuente como Negrita
stamp1.TextState.FontStyle = FontStyles.Bold;

// Establecer la información de color de primer plano del texto como rojo
stamp1.TextState.ForegroundColor = Color.Red;

// Especifique el tamaño de fuente como 14
stamp1.TextState.FontSize = 14;

// Ahora necesitamos establecer la alineación vertical del segundo objeto de sello como Superior
stamp2.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;

// Establezca la información de alineación horizontal para el sello como Alineado al centro
stamp2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;

// Establecer el factor de zoom para el objeto de sello
stamp2.Zoom = 10;

// Establecer el formato del tercer objeto de sello
// Especifique la información de alineación vertical para el objeto de sello como SUPERIOR
stamp3.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;

// Establezca la información de alineación horizontal para el objeto de sello como Alineado al centro
stamp3.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;

// Establecer el ángulo de rotación para el objeto de sello
stamp3.RotateAngle = 35;

// Establecer rosa como color de fondo para el sello
stamp3.TextState.BackgroundColor = Color.Pink;

// Cambie la información de la fuente para el sello a Verdana
stamp3.TextState.Font = FontRepository.FindFont("Verdana");

// Se agrega el primer sello en la primera página;
doc.Pages[1].AddStamp(stamp1);

// Se agrega el segundo sello en la segunda página;
doc.Pages[2].AddStamp(stamp2);

// Se agrega el tercer sello en la tercera página.
doc.Pages[3].AddStamp(stamp3);
dataDir = dataDir + "multiheader_out.pdf";

// Guardar el documento actualizado
doc.Save(dataDir);
Console.WriteLine("\nDifferent headers added successfully.\nFile saved at " + dataDir);

```

## Conclusión

¡Felicidades! Ha aprendido a agregar diferentes encabezados a cada página de un documento PDF usando Aspose.PDF para .NET. Ahora puede aplicar este conocimiento a sus propios proyectos para personalizar los encabezados de sus documentos PDF.
