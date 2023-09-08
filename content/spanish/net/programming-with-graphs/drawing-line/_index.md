---
title: Línea de dibujo
linktitle: Línea de dibujo
second_title: Aspose.PDF para referencia de API .NET
description: Aprenda a dibujar una línea a lo largo de una página usando Aspose.PDF para .NET. Guía paso a paso para crear líneas personalizadas.
type: docs
weight: 80
url: /es/net/programming-with-graphs/drawing-line/
---
En este tutorial, lo guiaremos a través del siguiente código fuente de C# paso a paso para dibujar una línea usando Aspose.PDF para .NET.

Asegúrese de haber instalado la biblioteca Aspose.PDF y configurar su entorno de desarrollo antes de comenzar. También tener conocimientos básicos de programación en C#.

## Paso 1: Configuración del directorio de documentos

En el código fuente proporcionado, debe especificar el directorio donde desea guardar el archivo PDF resultante. Cambie la variable "dataDir" al directorio deseado.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: crear una instancia de documento y agregar una página

Creamos una instancia de la clase Documento y agregamos una página a este documento.

```csharp
Document pDoc = new Document();
Page pg = pDoc.Pages.Add();
```

## Paso 3: configurar los márgenes de la página

Establecemos los márgenes de la página en 0 en todos los lados.

```csharp
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
```

## Paso 4: crear un objeto gráfico y la primera línea

Creamos un objeto Graph con dimensiones iguales a las de la página y dibujamos la primera línea que va desde la esquina inferior izquierda hasta la esquina superior derecha de la página.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width, (float)pg.PageInfo.Height);
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect. URY });
graph.Shapes.Add(line);
```

## Paso 5: dibujar la segunda línea

Dibujamos la segunda línea que va desde la esquina superior izquierda hasta la esquina inferior derecha de la página.

```csharp
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect. LLX });
graph.Shapes.Add(line2);
```

## Paso 6: agregar el objeto gráfico a la página

Agregamos el objeto Graph a la colección de párrafos de la página.

```csharp
pg.Paragraphs.Add(graph);
```

## Paso 7: guardar el archivo PDF resultante

Finalmente, guardamos el archivo PDF resultante con el nombre "DrawingLine_out.pdf" en el directorio especificado.

```csharp
pDoc.Save(dataDir + "DrawingLine_out.pdf");
```

### Código fuente de muestra para Drawing Line usando Aspose.PDF para .NET 

```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crear instancia de documento
Document pDoc = new Document();
// Agregar página a colección de páginas de documentos PDF
Page pg = pDoc.Pages.Add();
// Establecer el margen de página en todos los lados como 0
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
// Cree un objeto Gráfico con ancho y alto iguales a las dimensiones de la página
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width , (float)pg.PageInfo.Height);
// Cree un objeto de primera línea desde la esquina inferior izquierda hasta la esquina superior derecha de la página
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect.URY });
// Agregar línea a la colección de formas del objeto Graph
graph.Shapes.Add(line);
// Dibuje una línea desde la esquina superior izquierda de la página hasta la esquina inferior derecha de la página
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect.LLX });
// Agregar línea a la colección de formas del objeto Graph
graph.Shapes.Add(line2);
// Agregar objeto Graph a la colección de párrafos de la página
pg.Paragraphs.Add(graph);
dataDir = dataDir + "DrawingLine_out.pdf";
// Guardar archivo PDF
pDoc.Save(dataDir);
Console.WriteLine("\nLine drawn successfully across the page.\nFile saved at " + dataDir);            

```

## Conclusión

En este tutorial, explicamos cómo dibujar una línea usando Aspose.PDF para .NET. Ahora puedes utilizar este conocimiento para crear formas geométricas con líneas personalizadas en tus archivos PDF.

### Preguntas frecuentes

#### P: ¿Cuál es el propósito de este tutorial?

R: El propósito de este tutorial es guiarlo a través del proceso de dibujar líneas usando Aspose.PDF para .NET. Aprenderá cómo crear líneas en una página PDF y personalizar su apariencia.

#### P: ¿Qué requisitos previos se requieren antes de comenzar?

R: Antes de comenzar, asegúrese de haber instalado la biblioteca Aspose.PDF y configurado su entorno de desarrollo. También se recomiendan conocimientos básicos de programación en C#.

#### P: ¿Cómo especifico el directorio para guardar el archivo PDF?

R: Modifique la variable "dataDir" en el código fuente proporcionado para indicar el directorio donde desea guardar el archivo PDF resultante.

#### P: ¿Cómo creo líneas en una página PDF?

R: El tutorial demuestra cómo crear un objeto Gráfico con las dimensiones de la página y luego agregarle objetos Línea. Modifique las coordenadas y propiedades de los objetos Línea para crear las líneas deseadas.

#### P: ¿Puedo personalizar la apariencia de las líneas?

R: Sí, puedes personalizar la apariencia de las líneas modificando las propiedades de los objetos Línea. Esto incluye cambiar sus coordenadas, color, grosor y otros atributos gráficos.

#### P: ¿Cómo guardo el documento PDF después de dibujar las líneas?

R: Después de agregar el objeto Gráfico con objetos Línea a la página, puede guardar el documento PDF resultante usando el`pDoc.Save(dataDir + "DrawingLine_out.pdf");` línea en el código fuente proporcionado.

#### P: ¿Puedo dibujar líneas con diferentes ángulos y orientaciones?

R: Sí, puedes dibujar líneas con diferentes ángulos y orientaciones ajustando las coordenadas y propiedades de los objetos Línea dentro del Gráfico.