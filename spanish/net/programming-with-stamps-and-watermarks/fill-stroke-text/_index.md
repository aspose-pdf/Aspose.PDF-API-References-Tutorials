---
title: Texto de trazo de relleno
linktitle: Texto de trazo de relleno
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a rellenar y delinear texto fácilmente en sus documentos PDF con Aspose.PDF para .NET.
type: docs
weight: 90
url: /es/net/programming-with-stamps-and-watermarks/fill-stroke-text/
---
En este tutorial, lo guiaremos paso a paso sobre cómo completar y delinear texto en un documento PDF usando Aspose.PDF para .NET. Le mostraremos cómo utilizar el código fuente de C# proporcionado para aplicar colores de relleno y contorno al texto del documento PDF.

## Paso 1: Configuración del entorno

Antes de comenzar, asegúrese de tener lo siguiente:

- Un entorno de desarrollo .NET instalado.
- La biblioteca Aspose.PDF para .NET descargada y referenciada en su proyecto.

## Paso 2: crear el objeto TextState

El primer paso es crear un objeto TextState para pasar las propiedades avanzadas. Así es cómo:

```csharp
// Crear objeto TextState para transferir propiedades avanzadas
TextState ts = new TextState();

// Establecer color de contorno
ts.StrokingColor = Color.Gray;

// Definir el modo de representación del texto
ts.RenderingMode = TextRenderingMode.StrokeText;
```

El código anterior crea un nuevo objeto TextState y establece el color del contorno y la forma en que se representa el texto.

## Paso 3: Cargar el documento PDF

Ahora que el objeto TextState está listo, podemos cargar el documento PDF donde queremos aplicar el relleno y el contorno del texto. Así es cómo:

```csharp
// Cargue el documento PDF como entrada
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
```

El código anterior carga el documento PDF existente utilizando la clase PdfFileStamp de la biblioteca Aspose.PDF.Facades.

## Paso 4: agregue relleno y trazo al texto

Ahora que el documento PDF está cargado, podemos agregar el relleno y el contorno al texto. Así es cómo:

```csharp
// Crear un sello (Sello) con el texto y las propiedades definidas
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// Vincular el objeto TextState
stamp.BindTextState(ts);

// Establecer origen X, Y
stamp.SetOrigin(100, 100);
stamp. Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp. IsBackground = false;

// Agregar el sello al documento
fileStamp.AddStamp(stamp);
```

El código anterior crea un sello con el texto especificado y las propiedades de relleno y trazo definidas.

## Paso 5: Guarde el documento de salida

Una vez que se agrega el sello de texto, podemos guardar el documento PDF modificado. Así es cómo:

```csharp
// Guardar el documento modificado
fileStamp.Save(dataDir + "output_out.pdf");
fileStamp.Close();
```

El código anterior guarda el documento PDF editado en el directorio especificado.

### Ejemplo de código fuente para Rellenar texto de trazo con Aspose.PDF para .NET 
```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crear objeto TextState para transferir propiedades avanzadas
TextState ts = new TextState();

// Establecer color para el trazo
ts.StrokingColor = Color.Gray;

// Establecer el modo de representación de texto
ts.RenderingMode = TextRenderingMode.StrokeText;

//Cargar un documento PDF de entrada
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// Vincular estado de texto
stamp.BindTextState(ts);

// Establecer origen X,Y
stamp.SetOrigin(100, 100);
stamp.Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp.IsBackground = false;

// Agregar sello
fileStamp.AddStamp(stamp);
fileStamp.Save(dataDir + "ouput_out.pdf");
fileStamp.Close();

```

## Conclusión

¡Felicidades! Ha aprendido a rellenar y delinear texto en un documento PDF utilizando Aspose.PDF para .NET. Ahora puede aplicar este conocimiento para personalizar los colores de relleno y contorno en sus documentos PDF.
