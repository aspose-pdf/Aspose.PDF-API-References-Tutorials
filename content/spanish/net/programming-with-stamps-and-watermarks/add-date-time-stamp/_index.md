---
title: Agregar sello de fecha y hora en archivo PDF
linktitle: Agregar sello de fecha y hora en archivo PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a agregar una marca de fecha y hora a sus archivos PDF con Aspose.PDF para .NET con esta guía paso a paso. Perfecta para mejorar la autenticidad de los documentos.
type: docs
weight: 10
url: /es/net/programming-with-stamps-and-watermarks/add-date-time-stamp/
---
## Introducción

Cuando se trata de gestionar documentos, especialmente archivos PDF, añadir una marca de fecha y hora puede ser un cambio radical. Ya sea que trabajes con documentos legales, informes de proyectos o facturas, una marca de tiempo no solo añade autenticidad, sino que también proporciona un registro claro de cuándo se creó o modificó el documento. En esta guía, te guiaremos a través del proceso de añadir una marca de fecha y hora a un archivo PDF utilizando la biblioteca Aspose.PDF para .NET. 

Este artículo está diseñado para ser sencillo y fácil de seguir, por lo que incluso si eres nuevo en programación o en la biblioteca Aspose.PDF, podrás implementar esta función con confianza. ¡Vamos a profundizar!

## Prerrequisitos

Antes de comenzar, hay algunos requisitos previos que debes tener en cuenta:

1. Visual Studio: asegúrate de tener Visual Studio instalado en tu equipo. Aquí es donde escribirás y ejecutarás tu código.
2. Aspose.PDF para .NET: Debe descargar e instalar la biblioteca Aspose.PDF. Puede encontrar la última versión[aquí](https://releases.aspose.com/pdf/net/).
3. Conocimientos básicos de C#: La familiaridad con la programación en C# te ayudará a comprender mejor los ejemplos, pero no te preocupes si recién estás comenzando; te explicaremos todo paso a paso.
4.  Un archivo PDF: tenga listo un archivo PDF de muestra. Para nuestro ejemplo, usaremos un archivo llamado`AddTextStamp.pdf`.

Una vez que tenga estos requisitos previos, ¡estará listo para comenzar a agregar marcas de fecha y hora a sus archivos PDF!

## Importar paquetes

Para comenzar, debe importar los espacios de nombres necesarios en su proyecto de C#. A continuación, le indicamos cómo hacerlo:

### Crear un nuevo proyecto

1. Abrir Visual Studio: inicie su aplicación de Visual Studio.
2. Crear un nuevo proyecto: seleccione “Crear un nuevo proyecto” en la pantalla de inicio.
3. Elegir aplicación de consola: seleccione “Aplicación de consola (.NET Framework)” de la lista de plantillas de proyecto.
4.  Nombre su proyecto: Déle un nombre a su proyecto, por ejemplo,`PDFDateTimeStamp`.

### Añadir referencia de Aspose.PDF

1. Haga clic derecho en Referencias: en el Explorador de soluciones, haga clic derecho en la carpeta “Referencias” de su proyecto.
2. Seleccionar “Agregar referencia”: Elija “Agregar referencia” en el menú contextual.
3. Busque Aspose.PDF: navegue hasta la ubicación donde descargó Aspose.PDF y selecciónelo. Haga clic en “Aceptar” para agregarlo a su proyecto.

### Importar espacios de nombres requeridos

 En la parte superior de tu`Program.cs` archivo, debe importar los siguientes espacios de nombres:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
using Aspose.Pdf.Annotations;
```

Ahora que tenemos todo configurado, desglosemos el proceso de agregar una marca de fecha y hora a un archivo PDF en pasos claros y manejables.

## Paso 1: Establezca el directorio del documento

En primer lugar, debe especificar el directorio en el que se encuentra el archivo PDF. Esto es fundamental porque el código buscará el PDF en este directorio.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Reemplazar con su ruta actual
```

 Asegúrese de reemplazar`YOUR DOCUMENT DIRECTORY` con la ruta real a su archivo PDF.

## Paso 2: Abra el documento PDF

A continuación, abrirá el documento PDF donde desea agregar la marca de tiempo. 

```csharp
// Abrir documento
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

 Esta línea de código inicializa el`Document` clase y carga su archivo PDF en el`pdfDocument` objeto.

## Paso 3: Crear la marca de fecha y hora

Ahora es el momento de generar la marca de fecha y hora. La formatearás para que se muestre de una manera específica. 

```csharp
string annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt ");
```

 Aquí,`DateTime.Now` obtiene la fecha y hora actuales, y`ToString` formatéelo al formato que desee.

## Paso 4: Crea un sello de texto

Con la cadena de fecha y hora lista, ahora puedes crear un sello de texto que se agregará a tu PDF.

```csharp
// Crear sello de texto
TextStamp textStamp = new TextStamp(annotationText);
```

 Esta línea crea una nueva instancia de`TextStamp` utilizando la cadena de fecha y hora formateada.

## Paso 5: Establecer las propiedades del sello

Puedes personalizar la apariencia y la posición del sello. Aquí te mostramos cómo configurar sus propiedades:

```csharp
// Establecer propiedades del sello
textStamp.BottomMargin = 10;
textStamp.RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;
```

En este paso, establecemos los márgenes y alineamos el sello con la esquina inferior derecha de la página PDF.

## Paso 6: Añade el sello al PDF

Ahora es el momento de agregar el sello de texto a su documento PDF. 

```csharp
// Añadir sello a la colección de sellos
pdfDocument.Pages[1].AddStamp(textStamp);
```

Esta línea agrega el sello a la primera página del PDF. Puede cambiar el número de página si desea colocarlo en una página diferente.

## Paso 7: Crear una anotación de texto libre (opcional)

Si desea agregar una anotación al sello, puede crear una`FreeTextAnnotation` como sigue:

```csharp
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 6, System.Drawing.Color.Black);
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(0, 0, 0, 0), default_appearance);
textAnnotation.Name = "Stamp";
textAnnotation.Accept(new AnnotationSelector(textAnnotation));
textAnnotation.Contents = textStamp.Value;
```

Este paso opcional crea una anotación de texto libre que puede proporcionar contexto o información adicional sobre el sello.

## Paso 8: Configurar el borde de anotación

Si deseas personalizar el borde de tu anotación, también puedes hacerlo:

```csharp
Border border = new Border(textAnnotation);
border.Width = 0;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(0, 0, 0, 0);
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
```

Este fragmento de código establece el ancho del borde en 0, haciéndolo invisible, y agrega la anotación al PDF.

## Paso 9: Guarde el documento PDF

Por último, debes guardar el documento PDF modificado. 

```csharp
dataDir = dataDir + "AddDateTimeStamp_out.pdf"; // Especifique el nombre del archivo de salida
pdfDocument.Save(dataDir);
Console.WriteLine("\nDate time stamp added successfully.\nFile saved at " + dataDir);
```

Esta línea guarda el PDF con la marca de tiempo agregada en un nuevo archivo. Puede consultar el directorio especificado para ver el resultado.

## Conclusión

¡Felicitaciones! Ha agregado con éxito una marca de fecha y hora a un archivo PDF con Aspose.PDF para .NET. Esta función simple pero efectiva puede mejorar sus documentos, haciéndolos más profesionales y brindando un registro claro de cuándo fueron creados o modificados. 

## Preguntas frecuentes

### ¿Puedo personalizar el formato de fecha en la marca de tiempo?
 Sí, puedes modificar el`ToString`Método para cambiar el formato de fecha según su preferencia.

### ¿Aspose.PDF es de uso gratuito?
 Aspose.PDF ofrece una versión de prueba gratuita, pero para obtener todas las funciones, es necesario adquirir una licencia. Puede obtener una licencia temporal[aquí](https://purchase.aspose.com/temporary-license/).

### ¿Puedo agregar varias marcas de tiempo a un PDF?
 ¡Por supuesto! Puedes crear varios`TextStamp` instancias y agregarlas a diferentes páginas o posiciones en el PDF.

### ¿Qué pasa si no tengo Visual Studio?
Puede utilizar cualquier IDE o editor de texto de C#, pero para ejecutar y depurar su proyecto, se recomienda Visual Studio.

### ¿Dónde puedo encontrar más ejemplos del uso de Aspose.PDF?
 Puede explorar más ejemplos y tutoriales en el[Documentación Aspose.PDF](https://reference.aspose.com/pdf/net/).