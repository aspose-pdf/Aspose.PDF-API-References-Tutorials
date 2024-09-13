---
title: Aplicar estilo de número en archivo PDF
linktitle: Aplicar estilo de número en archivo PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a aplicar diferentes estilos de números (números romanos, alfabéticos) a los encabezados de un PDF usando Aspose.PDF para .NET con esta guía paso a paso.
type: docs
weight: 10
url: /es/net/programming-with-headings/apply-number-style/
---
## Introducción

¿Alguna vez ha tenido que agregar listas numeradas a sus documentos PDF? Ya sea que esté formateando documentos legales, informes o presentaciones, los estilos de numeración adecuados son esenciales para organizar la información. Con Aspose.PDF para .NET, puede aplicar varios estilos de numeración a los encabezados de sus archivos PDF, creando documentos bien estructurados y profesionales. 

## Prerrequisitos

Antes de sumergirnos en la codificación, repasemos lo que necesitarás:

1. Aspose.PDF para .NET: Descargue la última versión de Aspose.PDF desde[aquí](https://releases.aspose.com/pdf/net/).
2. Entorno de desarrollo: asegúrese de tener Visual Studio o cualquier otro IDE compatible con .NET.
3. .NET Framework: asegúrese de tener instalado .NET Framework 4.0 o superior.
4.  Licencia: Puede utilizar una licencia temporal de[aquí](https://purchase.aspose.com/temporary-license/) o explorar el[prueba gratis](https://releases.aspose.com/) Opciones.

## Importar paquetes

Para comenzar, asegúrese de tener los siguientes espacios de nombres importados en su proyecto:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Paso 1: Configuración del documento

Comencemos por crear un nuevo documento PDF y configurar sus ajustes de página. Estableceremos el tamaño de página y los márgenes para controlar el diseño de nuestro contenido.

Explicación: En este paso, configuramos la estructura básica del PDF, que incluye la definición del tamaño de la página, la altura y los márgenes para un formato consistente.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDoc = new Document();

// Establecer las dimensiones y los márgenes de la página
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
```

Al hacer esto, su documento tendrá un tamaño de página estándar, equivalente a una página de 8,5 x 11 pulgadas, y un margen de 72 puntos (o 1 pulgada) en todos los lados.

## Paso 2: Agregar una página al PDF

continuación, agregaremos una nueva página al documento PDF donde posteriormente aplicaremos los estilos de numeración.

Explicación: ¡Todos los archivos PDF requieren páginas! Este paso agrega una página en blanco al PDF y configura sus márgenes para que coincidan con la configuración del documento.

```csharp
// Agregar una nueva página al documento PDF
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo.Width = 612.0;
pdfPage.PageInfo.Height = 792.0;
pdfPage.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfPage.PageInfo.Margin.Left = 72;
pdfPage.PageInfo.Margin.Right = 72;
pdfPage.PageInfo.Margin.Top = 72;
pdfPage.PageInfo.Margin.Bottom = 72;
```

## Paso 3: Crea un cuadro flotante

Un FloatingBox te permite colocar contenido (como texto o encabezados) dentro de un cuadro que se comporta independientemente del flujo de la página. Esto es útil cuando quieres tener un control total sobre el diseño de tu contenido.

Explicación: Aquí, estamos configurando un FloatingBox para contener los encabezados a los que se les aplicarán estilos numéricos.

```csharp
// Crear un FloatingBox para contenido estructurado
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox();
floatBox.Margin = pdfPage.PageInfo.Margin;
pdfPage.Paragraphs.Add(floatBox);
```

## Paso 4: Agrega el primer encabezado con números romanos

¡Ahora viene la parte emocionante! Agreguemos el primer encabezado con numeración en minúsculas romanas.

Explicación: Estamos aplicando el estilo NumberingStyle.NumeralsRomanLowercase al encabezado, que mostrará la numeración en números romanos (i, ii, iii, etc.).

```csharp
// Crea el primer encabezado con números romanos
Aspose.Pdf.Heading heading = new Aspose.Pdf.Heading(1);
heading.IsInList = true;
heading.StartNumber = 1;
heading.Text = "List 1";
heading.Style = NumberingStyle.NumeralsRomanLowercase;
heading.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading);
```

## Paso 5: Agregar un segundo encabezado con números romanos

Para fines demostrativos, agreguemos un segundo encabezado con números romanos, pero esta vez comenzaremos desde 13.

Explicación: La propiedad StartNumber le permite comenzar a numerar desde un número personalizado; en este caso, comenzamos desde 13.

```csharp
// Crea un segundo encabezado que comience con el número romano 13
Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
heading2.IsInList = true;
heading2.StartNumber = 13;
heading2.Text = "List 2";
heading2.Style = NumberingStyle.NumeralsRomanLowercase;
heading2.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading2);
```

## Paso 6: Agregar un encabezado con numeración alfabética

Para variar, vamos a añadir un tercer encabezado, pero esta vez utilizaremos numeración alfabética en minúsculas (a, b, c, etc.).

Explicación: Cambiar el estilo de numeración a Letras Minúsculas nos permite aplicar numeración alfabética a nuestros encabezados.

```csharp
// Crear un encabezado con numeración alfabética
Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2);
heading3.IsInList = true;
heading3.StartNumber = 1;
heading3.Text = "the value, as of the effective date of the plan, of property to be distributed under the plan on account of each allowed";
heading3.Style = NumberingStyle.LettersLowercase;
heading3.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading3);
```

## Paso 7: Guardar el PDF

Finalmente, después de aplicar todos los estilos de encabezados y números, guardemos el archivo PDF en el directorio deseado.

Explicación: Este paso guarda el archivo PDF que contiene todos los encabezados formateados con estilos de numeración aplicados.

```csharp
// Guardar el documento PDF
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumber style applied successfully in headings.\nFile saved at " + dataDir);
```

## Conclusión

¡Y ya está! Ha aplicado con éxito estilos de numeración (números romanos y alfabéticos) a los encabezados de un archivo PDF con Aspose.PDF para .NET. La flexibilidad que ofrece Aspose.PDF para controlar el diseño de la página, los estilos de numeración y la posición del contenido le ofrece un potente conjunto de herramientas para crear documentos PDF profesionales y bien organizados.

## Preguntas frecuentes

### ¿Puedo aplicar diferentes estilos de números al mismo documento PDF?  
Sí, Aspose.PDF para .NET le permite mezclar diferentes estilos de numeración, como números romanos, números arábigos y numeración alfabética dentro del mismo documento.

### ¿Cómo puedo personalizar el número inicial de los encabezados?  
 Puede establecer el número de inicio para cualquier encabezado utilizando el`StartNumber` propiedad.

### ¿Hay alguna forma de restablecer la secuencia de numeración?  
Sí, puede restablecer la numeración ajustando la`StartNumber` propiedad para cada encabezado.

### ¿Puedo aplicar estilo negrita o cursiva a los encabezados además de la numeración?  
 ¡Por supuesto! Puedes personalizar los estilos de encabezado modificando propiedades como fuente, tamaño, negrita y cursiva mediante el botón`TextState` objeto.

### ¿Cómo puedo obtener una licencia temporal para Aspose.PDF?  
 Puede obtener una licencia temporal en[aquí](https://purchase.aspose.com/temporary-license/) para probar Aspose.PDF sin restricciones.