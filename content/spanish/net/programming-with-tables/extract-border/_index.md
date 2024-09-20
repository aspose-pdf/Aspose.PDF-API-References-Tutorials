---
title: Extraer borde en archivo PDF
linktitle: Extraer borde en archivo PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a extraer bordes de un archivo PDF y guardarlos como imagen con Aspose.PDF para .NET. Guía paso a paso con ejemplos de código y consejos para lograr el éxito.
type: docs
weight: 80
url: /es/net/programming-with-tables/extract-border/
---
## Introducción

Al trabajar con archivos PDF, extraer elementos específicos, como bordes o rutas gráficas, puede parecer una tarea abrumadora. Pero con Aspose.PDF para .NET, puede extraer fácilmente bordes o formas de un archivo PDF y guardarlos como una imagen. En este tutorial, profundizaremos en el proceso de extracción de un borde de un PDF y su guardado como una imagen PNG. ¡Prepárese para tomar el control del contenido gráfico de su PDF!

## Prerrequisitos

Antes de sumergirnos en el código, asegúrese de tener todo configurado:

1.  Aspose.PDF para .NET: Si aún no ha instalado la biblioteca Aspose.PDF, puede[Descárgalo aquí](https://releases.aspose.com/pdf/net/)También necesitarás aplicar la licencia, ya sea a través de la prueba gratuita o una licencia comprada.
2. Configuración de IDE: configure un proyecto de C# en Visual Studio o cualquier otro IDE de .NET. Asegúrese de haber agregado las referencias necesarias a la biblioteca Aspose.PDF.
3. Archivo PDF de entrada: tenga listo un archivo PDF del cual extraerá los bordes. Este tutorial hará referencia a un archivo llamado`input.pdf`.

## Importación de paquetes necesarios

Comencemos importando los espacios de nombres necesarios. Estos paquetes proporcionan las herramientas necesarias para manipular el contenido del PDF.

```csharp
using System.IO;
using System;
using System.Drawing.Drawing2D;
using System.Drawing.Imaging;
using System.Collections;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
```

Ahora que cubrimos los conceptos básicos, pasemos a la guía paso a paso donde desglosaremos cada parte del código para explicarlo en detalle.


## Paso 1: Cargar el documento PDF

El primer paso es cargar el documento PDF que contiene el borde que desea extraer. Piense en ello como si estuviera abriendo un libro antes de comenzar a leer: ¡necesita acceder al contenido!

 Comenzaremos especificando el directorio donde se almacena su archivo PDF y cargaremos el documento usando el`Aspose.Pdf.Document` clase.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
```

 Este código carga el`input.pdf` archivo del directorio especificado. Asegúrese de que la ruta del archivo sea correcta o podría aparecer un error de archivo no encontrado.

## Paso 2: Configuración de gráficos y mapas de bits

Antes de comenzar a extraer, debemos crear un lienzo en el que dibujar. En el mundo de .NET, esto significa configurar un mapa de bits y objetos gráficos. El mapa de bits representa la imagen y el objeto gráfico nos permitirá dibujar formas, como bordes, extraídos del PDF.

```csharp
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);
```

He aquí un desglose:
- Creamos una imagen de mapa de bits del tamaño de la primera página del PDF.
- GraphicsPath se utiliza para definir formas (en este caso, bordes).
- La matriz define cómo se transformarán los gráficos; necesitamos una matriz de inversión porque PDF y .NET tienen diferentes sistemas de coordenadas.

## Paso 3: Procesamiento del contenido del PDF


El archivo PDF es una serie de comandos de dibujo, y necesitamos procesar cada uno de estos comandos para identificar y extraer la información del borde.

```csharp
foreach (Operator op in doc.Pages[1].Contents)
{
    // Procesar comandos como guardar/restaurar estado, dibujar líneas, rellenar formas, etc.
}
```

El código recorre en bucle cada operador de dibujo en el flujo de contenido del PDF. Cada operador puede representar una línea, un rectángulo u otra instrucción gráfica.

## Paso 4: Manejo de operadores PDF

Cada operador del archivo PDF controla una acción. Para extraer el borde, necesitamos identificar comandos como "mover a", "línea a" y "dibujar rectángulo". Los siguientes operadores controlan estas acciones:

- MoveTo: Mueve el cursor a un punto de inicio.
- LineTo: dibuja una línea desde el punto actual hasta un nuevo punto.
- Re: Dibuja un rectángulo (esto podría ser parte del borde).

```csharp
Aspose.Pdf.Operators.MoveTo opMoveTo = op as Aspose.Pdf.Operators.MoveTo;
Aspose.Pdf.Operators.LineTo opLineTo = op as Aspose.Pdf.Operators.LineTo;
Aspose.Pdf.Operators.Re opRe = op as Aspose.Pdf.Operators.Re;

if (opMoveTo != null)
{
    lastPoint = new System.Drawing.PointF((float)opMoveTo.X, (float)opMoveTo.Y);
}
else if (opLineTo != null)
{
    System.Drawing.PointF linePoint = new System.Drawing.PointF((float)opLineTo.X, (float)opLineTo.Y);
    graphicsPath.AddLine(lastPoint, linePoint);
    lastPoint = linePoint;
}
else if (opRe != null)
{
    System.Drawing.RectangleF re = new System.Drawing.RectangleF((float)opRe.X, (float)opRe.Y, (float)opRe.Width, (float)opRe.Height);
    graphicsPath.AddRectangle(re);
}
```

En este paso:
- Capturamos los puntos de cada línea o forma dibujada.
- Para rectángulos (`opRe` ), los agregamos directamente a la`graphicsPath`, que usaremos más adelante para dibujar el borde.

## Paso 5: Dibujar el borde

Una vez que hemos identificado las líneas y los rectángulos que forman el borde, debemos dibujarlos en el objeto Bitmap. Aquí es donde entra en juego el objeto Graphics.

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
    gr.SmoothingMode = SmoothingMode.HighQuality;
    gr.DrawPath(new System.Drawing.Pen(strokeColor), graphicsPath);
}
```

- Creamos un objeto gráfico basado en el mapa de bits.
- SmoothingMode.HighQuality garantiza que obtengamos una imagen agradable y suave.
- Por último, utilizamos DrawPath para dibujar el borde.

## Paso 6: Guardar el borde extraído

Ahora que hemos extraído el borde, es momento de guardarlo como archivo de imagen. Esto guardará el borde como PNG.

```csharp
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);
```

- El mapa de bits se guarda como una imagen PNG.
- Ahora puedes abrir esta imagen para ver el borde extraído.

## Conclusión

Al principio, extraer bordes de un archivo PDF con Aspose.PDF para .NET puede parecer complicado, pero una vez que lo desglosas, se vuelve sencillo. Si comprendes los operadores de dibujo de un PDF y utilizas las potentes bibliotecas de .NET, puedes manipular y extraer contenido gráfico de manera eficiente. ¡Esta guía te brinda una base sólida para comenzar a manipular archivos PDF!

## Preguntas frecuentes

### ¿Cómo puedo manejar varias páginas en el PDF?  
 Puede recorrer cada página del documento iterando sobre ella`doc.Pages` En lugar de codificar de forma rígida`doc.Pages[1]`.

### ¿Puedo extraer otros elementos, como texto, utilizando el mismo enfoque?  
Sí, Aspose.PDF proporciona API enriquecidas para extraer texto, imágenes y otro contenido de archivos PDF.

### ¿Cómo solicito una licencia para evitar limitaciones?  
 Puede[solicitar una licencia](https://purchase.aspose.com/temporary-license/) cargándolo a través del`License` clase proporcionada por Aspose.

### ¿Qué pasa si mi PDF no tiene bordes?  
Si el PDF no contiene bordes visibles, es posible que el proceso de extracción de gráficos no dé ningún resultado. Asegúrese de que el contenido del PDF incluya bordes dibujables.

### ¿Puedo guardar la salida en formatos distintos a PNG?  
 Sí, simplemente cambia el`ImageFormat.Png` a otro formato compatible como`ImageFormat.Jpeg`.