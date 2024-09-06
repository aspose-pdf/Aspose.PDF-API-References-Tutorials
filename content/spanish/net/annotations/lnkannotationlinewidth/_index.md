---
title: Ancho de línea de anotación lnk
linktitle: Ancho de línea de anotación lnk
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a configurar el ancho de línea de anotación de tinta en un PDF con Aspose.PDF para .NET. Este tutorial detallado lo guía paso a paso para garantizar un resultado de alta calidad.
type: docs
weight: 110
url: /es/net/annotations/lnkannotationlinewidth/
---
## Introducción

Al trabajar con documentos PDF, agregar anotaciones puede ser una forma eficaz de resaltar información o agregar elementos interactivos a sus archivos. Una de esas anotaciones es la Anotación de Tinta, que le permite dibujar líneas de forma libre en su PDF. Pero, ¿qué sucede si necesita personalizar la apariencia de estas líneas, en particular el ancho de línea? En este tutorial, lo guiaremos a través del proceso de configuración del ancho de línea de anotación de tinta utilizando Aspose.PDF para .NET.

## Prerrequisitos

Antes de sumergirnos en el código, asegurémonos de tener todo configurado para seguir este tutorial sin problemas:

1.  Aspose.PDF para .NET: Asegúrese de tener instalada la biblioteca Aspose.PDF para .NET. Puede descargarla desde[página de descarga](https://releases.aspose.com/pdf/net/) o instálelo a través del Administrador de paquetes NuGet en Visual Studio.
2. Entorno de desarrollo: este tutorial asume que está trabajando en un entorno de desarrollo .NET como Visual Studio.
3. Conocimientos básicos de C#: una comprensión básica de C# le ayudará a seguir los pasos de codificación.
4. Documento PDF: utilice un documento PDF existente o cree uno nuevo para este tutorial.

## Importación de los espacios de nombres necesarios

Antes de comenzar a codificar, asegúrese de importar los espacios de nombres necesarios en su proyecto:

```csharp
using System.IO;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using System;
using System.Collections;
using System.Collections.Generic;
```

Estos espacios de nombres proporcionan las clases y los métodos necesarios para manipular documentos PDF, trabajar con anotaciones y manejar elementos gráficos.

Ahora que tenemos nuestros requisitos previos establecidos, desglosemos el proceso de configuración del ancho de línea de anotación de tinta en pasos claros y manejables.

## Paso 1: Inicializar el documento PDF

Primero, necesitamos crear o abrir un documento PDF. En este tutorial, crearemos un nuevo documento PDF desde cero.

```csharp
// Inicializar el documento PDF
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Especifique el directorio de su documento
Document doc = new Document();
doc.Pages.Add(); // Agregar una página en blanco al documento
```

 Aquí estamos inicializando un nuevo`Document` objeto, que representa nuestro archivo PDF. Luego agregamos una página en blanco a este documento para trabajar con ella.

## Paso 2: Crea la anotación de tinta

continuación, crearemos la anotación de tinta propiamente dicha, lo que implica definir los puntos que forman los trazos de tinta.

```csharp
// Crear la anotación de tinta
IList<Point[]> inkList = new List<Point[]>();
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = Color.Red;
lineInfo.LineWidth = 2;
```

 En este paso definimos el`LineInfo` objeto, que contiene las coordenadas de los trazos de tinta, su visibilidad, color y ancho de línea inicial.`VerticeCoordinate` La matriz contiene las coordenadas X e Y de cada punto del trazo.

## Paso 3: Convertir coordenadas en puntos

Ahora, necesitamos convertir estas coordenadas en puntos que puedan usarse mediante la anotación de tinta.

```csharp
// Convertir coordenadas en puntos
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
    gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}

inkList.Add(gesture);
```

 Este bucle procesa la matriz de coordenadas, convirtiendo cada par de coordenadas en una`Point` objeto, que luego se agrega a nuestro`inkList`.

## Paso 4: Agregue la anotación de tinta a la página PDF

Con los puntos listos, ahora podemos crear la anotación de tinta y agregarla a la página PDF.

```csharp
// Agregar la anotación de tinta a la página PDF
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
a1.Subject = "Test";
a1.Title = "Title";
a1.Color = Aspose.Pdf.Color.FromRgb(Color.Green);
```

 En este paso, inicializamos un`InkAnnotation`objeto, especificando la página, un rectángulo delimitador y nuestra lista de puntos. También establecemos el tema, el título y el color de la anotación.

## Paso 5: Personaliza el borde de la anotación

Para personalizar aún más la apariencia de nuestra anotación, modificaremos sus propiedades de borde.

```csharp
// Personalizar el borde de la anotación
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
doc.Pages[1].Annotations.Add(a1);
```

 Aquí creamos un`Border` Objeto para nuestra anotación, estableciendo su ancho, efecto, patrón de trazos y estilo. Este paso garantiza que la anotación se destaque visualmente en la página PDF.

## Paso 6: Guarde el documento PDF

Finalmente, después de realizar todos los cambios necesarios, es el momento de guardar el documento.

```csharp
// Guardar el documento PDF
dataDir = dataDir + "lnkAnnotationLineWidth_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nInk annotation line width setup successfully.\nFile saved at " + dataDir);
```

 Este código guarda el documento PDF modificado con la anotación de tinta en el directorio especificado.`Console.WriteLine` La declaración confirma la ejecución exitosa del código.

## Conclusión

¡Felicitaciones! Ha creado y personalizado con éxito una anotación manuscrita en un documento PDF con Aspose.PDF para .NET. Este tutorial cubrió todo el proceso, desde la inicialización del documento hasta el guardado del archivo final. Con este conocimiento, puede explorar más a fondo las amplias capacidades de Aspose.PDF para .NET y aplicar técnicas similares a otros tipos de anotaciones o manipulaciones de PDF.

## Preguntas frecuentes

### ¿Puedo utilizar diferentes colores para diferentes partes de la anotación de tinta?  
 Sí, puedes crear varios`InkAnnotation` objetos con diferentes colores y agregarlos a la misma o diferentes páginas de su PDF.

### ¿Cómo cambio el ancho de línea dinámicamente?  
 Puedes ajustar el`LineWidth` propiedad de la`LineInfo` objeto antes de convertir las coordenadas en puntos.

### ¿Es posible hacer que la anotación de tinta sea transparente?  
 Sí, puedes modificar el`Opacity` propiedad de la`InkAnnotation` objeto para hacerlo transparente.

### ¿Puedo agregar múltiples anotaciones de tinta a la misma página?  
¡Por supuesto! Puedes agregar tantas anotaciones con tinta como quieras a una sola página repitiendo el proceso.

### ¿Cómo elimino una anotación de tinta de un PDF?  
 Puedes eliminar una anotación usando el`doc.Pages[1].Annotations.Delete(a1)` método, donde`a1` es su objeto de anotación.