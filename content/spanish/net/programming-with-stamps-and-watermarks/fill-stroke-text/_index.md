---
title: Rellenar texto de trazo en un archivo PDF
linktitle: Rellenar texto de trazo en un archivo PDF
second_title: Aspose.PDF para referencia de API .NET
description: Aprenda cómo completar y delinear fácilmente texto en un archivo PDF con Aspose.PDF para .NET.
type: docs
weight: 90
url: /es/net/programming-with-stamps-and-watermarks/fill-stroke-text/
---
En este tutorial, le explicaremos paso a paso cómo rellenar y delinear texto en un archivo PDF utilizando Aspose.PDF para .NET. Le mostraremos cómo utilizar el código fuente C# proporcionado para aplicar colores de relleno y contorno al texto del archivo PDF.

## Paso 1: configurar el entorno

Antes de comenzar, asegúrese de tener lo siguiente:

- Un entorno de desarrollo .NET instalado.
- La biblioteca Aspose.PDF para .NET descargada y referenciada en su proyecto.

## Paso 2: crear el objeto TextState

El primer paso es crear un objeto TextState para pasar las propiedades avanzadas. Así es cómo:

```csharp
// Cree un objeto TextState para transferir propiedades avanzadas
TextState ts = new TextState();

// Establecer color de contorno
ts.StrokingColor = Color.Gray;

// Definir el modo de representación del texto.
ts.RenderingMode = TextRenderingMode.StrokeText;
```

El código anterior crea un nuevo objeto TextState y establece el color del contorno y cómo se representa el texto.

## Paso 3: cargar el documento PDF

Ahora que el objeto TextState está listo, podemos cargar el documento PDF donde queremos aplicar el relleno y el contorno del texto. Así es cómo:

```csharp
// Cargue el documento PDF como entrada
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
```

El código anterior carga el documento PDF existente utilizando la clase PdfFileStamp de la biblioteca Aspose.PDF.Facades.

## Paso 4: agregar relleno y trazo al texto

Ahora que el documento PDF está cargado, podemos agregar el relleno y el contorno al texto. Así es cómo:

```csharp
// Crear un sello (Stamp) con el texto y las propiedades definidas
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

// Añadir el sello al documento.
fileStamp.AddStamp(stamp);
```

El código anterior crea un sello con el texto especificado y las propiedades de Relleno y Trazo definidas.

## Paso 5: guarde el documento de salida

Una vez añadido el sello de texto, podremos guardar el documento PDF modificado. Así es cómo:

```csharp
// Guardar el documento modificado
fileStamp.Save(dataDir + "output_out.pdf");
fileStamp.Close();
```

El código anterior guarda el documento PDF editado en el directorio especificado.

### Código fuente de muestra para rellenar texto con trazo usando Aspose.PDF para .NET 
```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Cree un objeto TextState para transferir propiedades avanzadas
TextState ts = new TextState();

// Establecer color para el trazo
ts.StrokingColor = Color.Gray;

// Establecer el modo de representación de texto
ts.RenderingMode = TextRenderingMode.StrokeText;

// Cargar un documento PDF de entrada
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

¡Enhorabuena! Ha aprendido a rellenar y delinear texto en un documento PDF utilizando Aspose.PDF para .NET. Ahora puedes aplicar este conocimiento para personalizar los colores de relleno y contorno en tus documentos PDF.

### Preguntas frecuentes para rellenar texto de trazo en un archivo PDF

#### P: ¿Qué significa completar y delinear texto en un documento PDF y cuándo podría necesitar hacerlo?

R: Rellenar y delinear texto en un documento PDF implica aplicar colores al interior de los caracteres del texto (relleno) y a los bordes alrededor del texto (contorno). Esto se puede utilizar para mejorar la apariencia visual del texto, crear énfasis o resaltar contenido específico dentro del PDF.

#### P: ¿Cómo logra el código fuente C# proporcionado completar y delinear el texto en un archivo PDF?

 R: El código fuente proporcionado demuestra cómo crear un`TextState` objeto para definir propiedades de texto avanzadas, como el color del contorno y el modo de representación. Luego usa Aspose.PDF.Facades para cargar un documento PDF existente, crear un sello que contiene el texto con propiedades de relleno y trazo especificadas y agregar el sello al documento.

####  P: ¿Cuál es el propósito de la`TextState` object in the code?

 R: El`TextState`El objeto se utiliza para definir propiedades avanzadas del texto, incluido el color del contorno del texto (trazo) y el modo de representación. Le permite personalizar cómo aparece el texto en términos de trazo y relleno.

#### P: ¿Puedo aplicar diferentes colores de relleno y contorno a diferentes partes del mismo texto?

 R: Sí, puedes modificar el código para crear diferentes`TextState` objetos con distintos colores de relleno y contorno y aplicarlos a partes específicas del texto usando separado`Stamp` objetos.

#### P: ¿Puedo aplicar colores de relleno y contorno al texto que ya está presente en el documento PDF?

 R: Sí, puede utilizar principios similares para aplicar colores de relleno y contorno al texto existente en el documento PDF seleccionando los objetos de texto apropiados y agregándolos como sellos con el nombre deseado.`TextState` propiedades.

#### P: ¿Cómo puedo ajustar la opacidad y la combinación del texto relleno y delineado?

 R: El código proporcionado le permite configurar las propiedades de opacidad y fusión del sello usando el`Opacity` y`BlendingSpace`propiedades, respectivamente. Puede ajustar estos valores para lograr el efecto visual deseado.

#### P: ¿Cómo puedo aplicar diferentes colores de relleno y contorno a varios sellos dentro del mismo documento PDF?

 R: Puedes crear múltiples`TextState` objetos con diferentes colores de relleno y contorno, y luego crear separados`Stamp` objetos para cada conjunto de texto con distintos colores. Agregue estos sellos al mismo documento PDF usando el`PdfFileStamp` clase.

#### P: ¿Puedo utilizar fuentes distintas a Arial para el texto delineado y relleno?

 R: Sí, puede cambiar la fuente modificando el parámetro de nombre de fuente en el`FormattedText` constructor al crear el sello. Puede utilizar cualquier fuente disponible en su sistema.

#### P: ¿Cómo puedo modificar el ángulo de rotación del texto delineado y relleno?

 R: El código proporcionado le permite configurar el ángulo de rotación del sello usando el`Rotation` propiedad. Puede ajustar esta propiedad para especificar el ángulo de rotación deseado para el texto.

#### P: ¿Cómo puedo controlar la posición y el tamaño del texto delineado y relleno en la página?

R: Puedes usar el`SetOrigin` método de la`Stamp` objeto para establecer las coordenadas X e Y de la posición del sello en la página. Además, puede ajustar el tamaño de fuente en el`FormattedText` constructor para controlar el tamaño del texto.