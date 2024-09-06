---
title: Línea de dibujo
linktitle: Línea de dibujo
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a dibujar una línea a lo largo de una página con Aspose.PDF para .NET. Guía paso a paso para crear líneas personalizadas.
type: docs
weight: 80
url: /es/net/programming-with-graphs/drawing-line/
---
En este tutorial, lo guiaremos a través del siguiente código fuente de C# paso a paso para dibujar una línea usando Aspose.PDF para .NET.

Asegúrese de haber instalado la biblioteca Aspose.PDF y de haber configurado su entorno de desarrollo antes de comenzar. Además, debe tener conocimientos básicos de programación en C#.

## Paso 1: Configuración del directorio de documentos

En el código fuente proporcionado, debe especificar el directorio en el que desea guardar el archivo PDF resultante. Cambie la variable "dataDir" al directorio deseado.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Crear una instancia de documento y agregar una página

Creamos una instancia de la clase Document y agregamos una página a este documento.

```csharp
Document pDoc = new Document();
Page pg = pDoc.Pages.Add();
```

## Paso 3: Configuración de los márgenes de la página

Establecemos los márgenes de la página a 0 en todos los lados.

```csharp
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
```

## Paso 4: Creación de un objeto gráfico y la primera línea

Creamos un objeto Gráfico con dimensiones iguales a las de la página y dibujamos la primera línea que va desde la esquina inferior izquierda hasta la esquina superior derecha de la página.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width, (float)pg.PageInfo.Height);
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect. URY });
graph.Shapes.Add(line);
```

## Paso 5: Dibujar la segunda línea

Dibujamos la segunda línea que va desde la esquina superior izquierda hasta la esquina inferior derecha de la página.

```csharp
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect. LLX });
graph.Shapes.Add(line2);
```

## Paso 6: Agregar el objeto gráfico a la página

Agregamos el objeto Graph a la colección de párrafos de la página.

```csharp
pg.Paragraphs.Add(graph);
```

## Paso 7: Guardar el archivo PDF resultante

Finalmente, guardamos el archivo PDF resultante con el nombre "DrawingLine_out.pdf" en el directorio especificado.

```csharp
pDoc.Save(dataDir + "DrawingLine_out.pdf");
```

### Código fuente de muestra para dibujar líneas con Aspose.PDF para .NET 

```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crear instancia de documento
Document pDoc = new Document();
// Agregar página a la colección de páginas de un documento PDF
Page pg = pDoc.Pages.Add();
// Establecer el margen de página en todos los lados como 0
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
// Crear un objeto gráfico con ancho y alto iguales a las dimensiones de la página
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width , (float)pg.PageInfo.Height);
// Crear un objeto de primera línea comenzando desde la esquina inferior izquierda hasta la esquina superior derecha de la página
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect.URY });
// Agregar línea a la colección de formas del objeto Gráfico
graph.Shapes.Add(line);
// Dibuje una línea desde la esquina superior izquierda de la página hasta la esquina inferior derecha de la página.
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect.LLX });
// Agregar línea a la colección de formas del objeto Gráfico
graph.Shapes.Add(line2);
// Agregar objeto Gráfico a la colección de párrafos de la página
pg.Paragraphs.Add(graph);
dataDir = dataDir + "DrawingLine_out.pdf";
// Guardar archivo PDF
pDoc.Save(dataDir);
Console.WriteLine("\nLine drawn successfully across the page.\nFile saved at " + dataDir);            

```

## Conclusión

En este tutorial, explicamos cómo dibujar una línea con Aspose.PDF para .NET. Ahora puede utilizar este conocimiento para crear formas geométricas con líneas personalizadas en sus archivos PDF.

### Preguntas frecuentes

#### P: ¿Cuál es el propósito de este tutorial?

R: El objetivo de este tutorial es guiarlo a través del proceso de dibujo de líneas con Aspose.PDF para .NET. Aprenderá a crear líneas en una página PDF y a personalizar su apariencia.

#### P: ¿Qué requisitos previos se requieren antes de comenzar?

R: Antes de comenzar, asegúrese de haber instalado la biblioteca Aspose.PDF y de haber configurado su entorno de desarrollo. También se recomienda tener conocimientos básicos de programación en C#.

#### P: ¿Cómo especifico el directorio para guardar el archivo PDF?

A: Modifique la variable "dataDir" en el código fuente proporcionado para indicar el directorio donde desea guardar el archivo PDF resultante.

#### P: ¿Cómo creo líneas en una página PDF?

A: El tutorial muestra cómo crear un objeto Gráfico con las dimensiones de la página y luego agregarle objetos Línea. Modifique las coordenadas y propiedades de los objetos Línea para crear las líneas deseadas.

#### P: ¿Puedo personalizar la apariencia de las líneas?

R: Sí, puedes personalizar la apariencia de las líneas modificando las propiedades de los objetos Línea. Esto incluye cambiar sus coordenadas, color, grosor y otros atributos gráficos.

#### P: ¿Cómo guardo el documento PDF después de dibujar las líneas?

 A: Después de agregar el objeto Gráfico con objetos de Línea a la página, puede guardar el documento PDF resultante usando el`pDoc.Save(dataDir + "DrawingLine_out.pdf");` línea en el código fuente proporcionado.

#### P: ¿Puedo dibujar líneas con diferentes ángulos y orientaciones?

R: Sí, puede dibujar líneas con diferentes ángulos y orientaciones ajustando las coordenadas y propiedades de los objetos de Línea dentro del Gráfico.