---
title: Obtener dimensiones de página en formato PDF
linktitle: Obtener dimensiones de página en formato PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: En este tutorial, explicamos cómo obtener las dimensiones de una página PDF y realizar manipulaciones con Aspose.PDF para .NET. Se proporcionan pasos detallados para guiarlo a través del proceso.
type: docs
weight: 60
url: /es/net/programming-with-pdf-pages/get-dimensions/
---
## Introducción

¿Alguna vez ha tenido que manipular las dimensiones de página de un documento PDF? ¿Quizás ha querido cambiar el tamaño de una página o rotarla para que se ajuste a sus necesidades? Si es así, ¡está en el lugar correcto! En este tutorial, le mostraremos cómo recuperar y modificar las dimensiones de página de un PDF con Aspose.PDF para .NET. Tanto si es un principiante como un desarrollador experimentado, esta guía le resultará sencilla y fácil de seguir.

Aspose.PDF para .NET es una potente biblioteca que te permite crear, manipular y transformar archivos PDF sin esfuerzo. Es como tener una navaja suiza para archivos PDF: puedes ajustar cada pequeño detalle para que se ajuste a tus requisitos exactos. ¡Vamos a sumergirnos en el tema y a aprender a obtener y actualizar las dimensiones de las páginas PDF con esta increíble herramienta!

## Prerrequisitos

Antes de comenzar, necesitarás tener en cuenta algunas cosas para poder seguir este tutorial sin problemas:

1.  Aspose.PDF para .NET: Puede[Descargue la última versión aquí](https://releases.aspose.com/pdf/net/) Si no tienes licencia, ¡no te preocupes! Puedes solicitar una[prueba gratis](https://releases.aspose.com/) , o bien optar por una[licencia temporal](https://purchase.aspose.com/temporary-license/).
2. Visual Studio: el entorno de desarrollo que utilizarás para escribir y ejecutar el código.
3. Conocimientos básicos de C#: si bien mantendremos las cosas simples, cierta familiaridad con C# hará que el proceso sea más sencillo.
4. Archivo PDF con el que trabajar: tome cualquier archivo PDF de muestra o cree uno nuevo para probar.

## Importar paquetes

Para trabajar con Aspose.PDF para .NET, es necesario importar algunos espacios de nombres esenciales. Esto prepara el terreno para interactuar con documentos PDF. A continuación, le indicamos cómo hacerlo:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Estas importaciones garantizan que usted tenga acceso a las clases principales necesarias para manipular archivos PDF, particularmente para administrar páginas y recuperar sus dimensiones.

Ahora que tenemos todo en su lugar, dividamos el proceso en pasos fáciles de seguir.

## Paso 1: Defina la ruta del archivo y cargue el documento

El primer paso es especificar la ruta de acceso al documento PDF y cargarlo mediante Aspose.PDF. Esto le permitirá interactuar con las páginas del archivo PDF.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Abrir documento
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

En este paso, básicamente estás abriendo el archivo PDF en el que quieres trabajar. Si alguna vez abriste un libro en una página en particular, esto es bastante similar, pero en lugar de eso estás abriendo un documento PDF para acceder a sus páginas.

## Paso 2: Agregar una página en blanco si no existen páginas

¿Qué pasa si tu documento no tiene páginas? ¡No te preocupes! Podemos agregar una página en blanco al documento y trabajar con ella. A continuación, te indicamos cómo comprobar si existe una página y agregar una nueva si es necesario:

```csharp
// Agrega una página en blanco al documento PDF
Page page = pdfDocument.Pages.Count > 0 ? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
```

Esta línea de código comprueba si ya hay una página en el documento. Si es así, selecciona la primera página (`Pages[1]`) De lo contrario, crea una página en blanco y la agrega al PDF.

Piense en ello como abrir un cuaderno vacío y escribir en la primera página si no hay nada allí: fácil, ¿verdad?

## Paso 3: Obtenga información sobre la altura y el ancho de la página

 Ahora que tenemos una página con la que trabajar, recuperemos las dimensiones de la página. Usaremos el`GetPageRect()` Método para obtener la altura y el ancho.

```csharp
// Obtener información sobre la altura y el ancho de la página
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height.ToString());
```

 Aquí,`GetPageRect(true)` Devuelve un rectángulo que incluye la altura y el ancho de la página. Es como medir una hoja de papel con una regla. El resultado se mostrará en la consola y te indicará las dimensiones actuales de la página.

## Paso 4: Girar la página 90 grados

¿Quieres rotar la página? ¡No hay problema! Con una propiedad sencilla, puedes rotar la página 90 grados.

```csharp
// Girar la página en un ángulo de 90 grados
page.Rotate = Rotation.on90;
```

Este paso hace girar la página 90 grados en el sentido de las agujas del reloj. Imagina que estás girando una hoja impresa en tu escritorio: ¡ahora está en modo horizontal!

## Paso 5: Vuelva a verificar las dimensiones de la página después de la rotación

Después de girar la página, es buena idea volver a comprobar las dimensiones. ¿Por qué? Porque la rotación puede afectar la interpretación de la altura y el ancho.

```csharp
// Obtener información sobre la altura y el ancho de la página
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height.ToString());
```

Ahora, las dimensiones de la página se actualizarán según la nueva orientación. Es como girar una foto en el teléfono: de repente, el ancho se convierte en la altura y viceversa.


## Conclusión

¡Felicitaciones! Aprendió a recuperar y modificar las dimensiones de una página PDF con Aspose.PDF para .NET. A esta altura, debería poder cargar un PDF, verificar las dimensiones de la página e incluso rotarla si es necesario.

Manipular archivos PDF no tiene por qué ser complicado. Con Aspose.PDF, es tan sencillo como seguir unos pocos pasos y utilizar métodos intuitivos. Así, la próxima vez que necesites manipular las dimensiones de una página PDF, sabrás exactamente qué hacer.

## Preguntas frecuentes

### ¿Puedo girar la página en otros ángulos además de 90 grados?
 Sí, Aspose.PDF le permite rotar páginas 0, 90, 180 o 270 grados usando el`Rotation` propiedad.

### ¿Qué pasa si mi PDF no tiene páginas?
 Si su PDF no tiene páginas, puede agregar una página en blanco utilizando el`Pages.Add()` método, como se muestra en este tutorial.

### ¿Puedo manipular varias páginas a la vez?
Sí, puedes recorrer varias páginas y aplicar transformaciones, como cambiar el tamaño o rotarlas, a todas ellas.

### ¿Las dimensiones de la página afectan el contenido dentro del PDF?
Las dimensiones de la página solo cambian el tamaño del lienzo, no el contenido. Sin embargo, el cambio de tamaño puede alterar la forma en que aparece el contenido en la página.

### ¿Dónde puedo encontrar más información sobre Aspose.PDF para .NET?
 Puedes visitar el[documentación aquí](https://reference.aspose.com/pdf/net/) para obtener información más detallada y casos de uso avanzados.