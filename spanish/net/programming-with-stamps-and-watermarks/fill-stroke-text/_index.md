---
title: Rellenar texto de trazo en archivo PDF
linktitle: Rellenar texto de trazo en archivo PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a rellenar y delinear fácilmente texto en un archivo PDF con Aspose.PDF para .NET.
type: docs
weight: 90
url: /es/net/programming-with-stamps-and-watermarks/fill-stroke-text/
---
En este tutorial, lo guiaremos paso a paso sobre cómo completar y delinear texto en un archivo PDF usando Aspose.PDF para .NET. Le mostraremos cómo utilizar el código fuente de C# proporcionado para aplicar colores de relleno y contorno al texto del archivo PDF.

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

¡Felicidades! Ha aprendido a rellenar y delinear texto en un documento PDF utilizando Aspose.PDF para .NET. Ahora puede aplicar este conocimiento para personalizar los colores de relleno y contorno en sus documentos PDF.

### Preguntas frecuentes sobre texto de trazo de relleno en archivo PDF

#### P: ¿Qué significa rellenar y delinear texto en un documento PDF y cuándo podría necesitar hacerlo?

R: Rellenar y delinear texto en un documento PDF implica aplicar colores al interior de los caracteres de texto (relleno) y a los bordes alrededor del texto (delineado). Esto se puede usar para mejorar la apariencia visual del texto, crear énfasis o resaltar contenido específico dentro del PDF.

#### P: ¿Cómo logra el código fuente de C# proporcionado completar y delinear texto en un archivo PDF?

 R: El código fuente proporcionado demuestra cómo crear un`TextState` objeto para definir propiedades de texto avanzadas, como el color del contorno y el modo de representación. A continuación, utiliza Aspose.PDF.Facades para cargar un documento PDF existente, crear un sello que contenga el texto con las propiedades de relleno y trazo especificadas y agregar el sello al documento.

####  P: ¿Cuál es el propósito de la`TextState` object in the code?

 R: El`TextState`El objeto se utiliza para definir propiedades de texto avanzadas, incluido el color del contorno del texto (trazo) y el modo de representación. Le permite personalizar cómo aparece el texto en términos de trazo y relleno.

#### P: ¿Puedo aplicar diferentes colores de relleno y contorno a diferentes partes del mismo texto?

 R: Sí, puede modificar el código para crear diferentes`TextState` objetos con distintos colores de relleno y de contorno y aplicarlos a partes específicas del texto utilizando distintos`Stamp` objetos.

#### P: ¿Puedo aplicar colores de relleno y contorno al texto que ya está presente en el documento PDF?

 R: Sí, puede usar principios similares para aplicar colores de relleno y contorno al texto existente en el documento PDF seleccionando los objetos de texto apropiados y agregándolos como sellos con el color deseado.`TextState` propiedades.

#### P: ¿Cómo puedo ajustar la opacidad y la combinación del texto relleno y delineado?

 R: El código provisto le permite establecer la opacidad y las propiedades de fusión del sello usando el`Opacity` y`BlendingSpace`propiedades, respectivamente. Puede ajustar estos valores para lograr el efecto visual deseado.

#### P: ¿Cómo puedo aplicar diferentes colores de relleno y contorno a varios sellos dentro del mismo documento PDF?

 R: Puede crear múltiples`TextState` objetos con diferentes colores de relleno y contorno y, a continuación, cree`Stamp` objetos para cada conjunto de texto con distintos colores. Agregue estos sellos al mismo documento PDF usando el`PdfFileStamp` clase.

#### P: ¿Puedo usar fuentes que no sean Arial para el texto delineado y relleno?

 R: Sí, puede cambiar la fuente modificando el parámetro de nombre de fuente en el`FormattedText` constructor al crear el sello. Puede utilizar cualquier fuente disponible en su sistema.

#### P: ¿Cómo puedo modificar el ángulo de rotación del texto delineado y relleno?

 R: El código provisto le permite establecer el ángulo de rotación del sello usando el`Rotation` propiedad. Puede ajustar esta propiedad para especificar el ángulo de rotación deseado para el texto.

#### P: ¿Cómo puedo controlar la posición y el tamaño del texto delineado y relleno en la página?

R: Puede utilizar el`SetOrigin` metodo de la`Stamp` objeto para establecer las coordenadas X e Y de la posición del sello en la página. Además, puede ajustar el tamaño de fuente en el`FormattedText` constructor para controlar el tamaño del texto.