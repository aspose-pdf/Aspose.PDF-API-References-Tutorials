---
title: Crear rectángulo con color alfa
linktitle: Crear rectángulo con color alfa
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a crear un rectángulo con color transparente usando Aspose.PDF para .NET. Guía paso a paso para personalizar la transparencia.
type: docs
weight: 60
url: /es/net/programming-with-graphs/create-rectangle-with-alpha-color/
---

En este tutorial, lo guiaremos a través del siguiente código fuente de C# paso a paso para crear un rectángulo con color alfa usando Aspose.PDF para .NET.

Asegúrese de haber instalado la biblioteca Aspose.PDF y configure su entorno de desarrollo antes de comenzar. También tener conocimientos básicos de programación en C#.

## Paso 1: Configuración del directorio de documentos

En el código fuente provisto, debe especificar el directorio donde desea guardar el archivo PDF resultante. Cambie la variable "dataDir" al directorio deseado.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: instanciar un objeto de documento y agregar una página

Creamos una instancia de la clase Documento y agregamos una página a este documento.

```csharp
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Paso 3: crear un objeto gráfico y un rectángulo

Creamos un objeto Graph con dimensiones específicas y un rectángulo con dimensiones específicas.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
```

## Paso 4: Configuración del color alfa para el rectángulo

Podemos especificar un color alfa para el rectángulo utilizando el método FromArgb de la clase System.Drawing.Color.

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
```

## Paso 5: agregar el rectángulo al objeto gráfico

Agregamos el rectángulo a la colección de formas del objeto Graph.

```csharp
canvas.Shapes.Add(rect);
```

## Paso 6: crear un segundo rectángulo con un color alfa diferente

Creamos un segundo rectángulo con dimensiones específicas y otro color alfa.

```csharp
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
```

## Paso 7: agregar el objeto gráfico a la página

Agregamos el objeto Graph a la colección Paragraph del objeto Page.

```csharp
page.Paragraphs.Add(canvas);
```

## Paso 8: Guardar el archivo PDF resultante

Finalmente, guardamos el archivo PDF resultante con el nombre "CreateRectangleWithAlphaColor_out.pdf" en el directorio especificado.

```csharp
doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");
```

### Ejemplo de código fuente para Create Rectangle With Alpha Color usando Aspose.Words para .NET 

```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instanciar instancia de documento
Document doc = new Document();
// Agregar página a la colección de páginas del archivo PDF
Aspose.Pdf.Page page = doc.Pages.Add();
// Crear instancia de gráfico
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Crear un objeto rectangular con dimensiones específicas
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
// Establezca el color de relleno del gráfico desde la estructura System.Drawing.Color desde un valor ARGB de 32 bits
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
// Agregue un objeto de rectángulo a la colección de formas de la instancia de Graph
canvas.Shapes.Add(rect);
// Crear segundo objeto de rectángulo
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
// Agregar instancia de gráfico a la colección de párrafos del objeto de página
page.Paragraphs.Add(canvas);
dataDir = dataDir + "CreateRectangleWithAlphaColor_out.pdf";
// Guardar archivo PDF
doc.Save(dataDir);
Console.WriteLine("\nRectangle object created successfully with alpha color.\nFile saved at " + dataDir);            

```

## Conclusión

En este tutorial, explicamos cómo crear un rectángulo con color alfa usando Aspose.PDF para .NET. Ahora puede utilizar este conocimiento para crear formas geométricas con colores transparentes en sus archivos PDF.
