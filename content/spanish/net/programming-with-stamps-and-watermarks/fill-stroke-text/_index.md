---
title: Rellenar texto con trazo en archivo PDF
linktitle: Rellenar texto con trazo en archivo PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a rellenar texto con trazos en archivos PDF sin esfuerzo usando Aspose.PDF para .NET con esta guía paso a paso repleta de ejemplos prácticos.
type: docs
weight: 90
url: /es/net/programming-with-stamps-and-watermarks/fill-stroke-text/
---
## Introducción

¿Alguna vez ha deseado modificar un archivo PDF para que se destaque? Tal vez necesite agregar una marca de agua llamativa o un sello llamativo que haga que un documento importante sea inconfundiblemente suyo. Con Aspose.PDF para .NET, puede rellenar fácilmente el texto con trazos en un archivo PDF, agregando un toque artístico que llame la atención. En el tutorial de hoy, veremos el proceso para hacer exactamente eso: rellenar el texto con trazos en un PDF con C#. Al final, tendrá una sólida comprensión de cómo manipular archivos PDF como un profesional.

## Prerrequisitos

Antes de sumergirnos en la codificación, hay algunas cosas que necesitarás tener en cuenta para que este tutorial sea muy sencillo:

1. Visual Studio: asegúrese de tener Visual Studio instalado en su máquina, ya que escribiremos código C#.
2.  Biblioteca Aspose.PDF: asegúrese de haber descargado la biblioteca Aspose.PDF para .NET. Puede descargarla[aquí](https://releases.aspose.com/pdf/net/).
3. Conocimientos básicos de C#: La familiaridad con la programación en C# le ayudará a comprender el tutorial más fácilmente.
4. Archivo PDF de muestra: Necesitará un archivo PDF de muestra (`input.pdf`para realizar pruebas. Puedes crear uno simple o usar cualquier PDF que tengas.

Ahora que tenemos todo en su lugar, entremos en los detalles de cómo rellenar el texto del trazo en su archivo PDF.

## Importar paquetes

Para comenzar, necesitaremos importar los paquetes necesarios. A continuación, se incluye una breve descripción de las importaciones esenciales para nuestro proyecto:

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Estos paquetes nos permitirán utilizar las robustas funcionalidades de la biblioteca Aspose.PDF.

Dividamos la tarea principal en pasos claros. Si sigue estos pasos, podrá rellenar fácilmente texto con trazos en sus archivos PDF. 

## Paso 1: Configura tu entorno

En primer lugar, asegúrese de que todo esté configurado correctamente en su proyecto de Visual Studio. Cree un proyecto nuevo o elija uno existente. Si necesita ayuda, siga estos pasos:

1. Abra Visual Studio.
2. Cree un nuevo proyecto de C# (por ejemplo, aplicación de consola).
3. Haga clic derecho en el proyecto en el Explorador de soluciones y seleccione “Administrar paquetes NuGet”.
4.  Buscar`Aspose.PDF` e instalarlo.

## Paso 2: Defina su directorio de documentos

Todo viaje necesita un punto de partida, y en nuestro caso es el directorio de documentos donde residirán los archivos de entrada y salida. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real donde se encuentra su archivo PDF de entrada. 

## Paso 3: Crear el objeto TextState

Este paso es donde comienzas a definir las propiedades del texto que deseas agregar. 

```csharp
TextState ts = new TextState();
```

 El`TextState` El objeto contendrá las opciones de estilo para el texto del trazo.

## Paso 4: Establezca el color del trazo

A continuación, querrás definir el color del trazo de tu texto. 

```csharp
ts.StrokingColor = Color.Gray;
```

En este código, usamos un color gris para el trazo. ¡Siéntete libre de cambiar el color para adaptarlo a tus necesidades!

## Paso 5: Configurar el modo de renderizado

Para garantizar que el texto se muestre como se espera, configure el modo de representación:

```csharp
ts.RenderingMode = TextRenderingMode.StrokeText;
```

Esto le indica a la biblioteca Aspose que estamos trabajando con texto de trazo.

## Paso 6: Cargue el documento PDF de entrada

Ahora es el momento de cargar el archivo PDF que vas a modificar. 

```csharp
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
```

Asegúrese de que su PDF de entrada (`input.pdf`se encuentra en el directorio de documentos definido en los pasos anteriores.

## Paso 7: Crear un objeto de sello

A continuación, crea un sello que contendrá el texto del trazo. 

```csharp
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
```

Este sello se utilizará para superponer su texto en el PDF.

## Paso 8: Definir el texto a estampar

Necesitarás especificar qué texto quieres agregar al PDF:

```csharp
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));
```

Aquí, "PAGADO EN SU TOTALIDAD" es el texto que estamos agregando, junto con sus atributos de estilo. ¡Personalícelo según sus requisitos!

## Paso 9: Vincular el estado del texto

 Ahora, ata el`TextState` usted definió previamente el sello. 

```csharp
stamp.BindTextState(ts);
```

Este paso aplica todos los estilos como el color y el modo de representación a su texto.

## Paso 10: Establezca la posición del sello

Determina dónde aparecerá tu sello en el PDF:

```csharp
stamp.SetOrigin(100, 100);
```

 Los argumentos`(100, 100)` Indica las coordenadas X e Y (en puntos) del origen del texto. ¡Ajusta estos valores para posicionar el texto a la perfección!

## Paso 11: Configurar la opacidad y la rotación

Aquí puedes jugar con la apariencia de tu texto:

```csharp
stamp.Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
```

En este caso, un valor de opacidad y un ángulo de rotación de 45 grados le aportan un toque único al texto. No dude en modificar estos ajustes para obtener diferentes efectos.

## Paso 12: Añade el sello al PDF

Este es el paso crucial donde finalmente agregamos nuestro sello que incluye el texto del trazo al PDF:

```csharp
fileStamp.AddStamp(stamp);
```

¡Y así, tu texto estará listo para hacer una declaración!

## Paso 13: Guardar y cerrar el documento

Por último, guarde los cambios y asegúrese de que todo esté limpio correctamente. 

```csharp
fileStamp.Save(dataDir + "output_out.pdf");
fileStamp.Close();
```

 El archivo PDF recién modificado que contiene el texto del trazo se guardará como`output_out.pdf` en su directorio de documentos. 

## Conclusión

¡Y ya lo tienes! Siguiendo estos sencillos pasos, puedes rellenar fácilmente el texto con trazos de un archivo PDF con Aspose.PDF para .NET. Ya sea para documentos empresariales o proyectos personales, esta técnica te permite añadir un toque único a tus archivos PDF, haciéndolos destacar en cualquier pila de papeles.

## Preguntas frecuentes

### ¿Qué es Aspose.PDF para .NET?
Aspose.PDF para .NET es una biblioteca que permite a los desarrolladores crear, manipular y convertir archivos PDF mediante programación.

### ¿Puedo utilizar Aspose.PDF gratis?
Sí, Aspose ofrece una prueba gratuita. Puedes obtenerla[aquí](https://releases.aspose.com/).

### ¿Necesito pagar por una licencia?
 Si bien la biblioteca ofrece una prueba gratuita, también se puede comprar una licencia temporal en[Este enlace](https://purchase.aspose.com/temporary-license/).

### ¿Dónde puedo encontrar la documentación?
 Puedes acceder a la documentación completa[aquí](https://reference.aspose.com/pdf/net/).

### ¿Hay soporte disponible si tengo problemas?
 ¡Por supuesto! Puedes obtener ayuda en el foro de Aspose[aquí](https://forum.aspose.com/c/pdf/10).