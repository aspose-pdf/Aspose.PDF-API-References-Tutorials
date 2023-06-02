---
title: Agregar dibujo con relleno degradado
linktitle: Agregar dibujo con relleno degradado
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a agregar un dibujo con relleno degradado con Aspose.PDF para .NET. Tutorial paso a paso para crear atractivos documentos PDF.
type: docs
weight: 20
url: /es/net/programming-with-graphs/add-drawing-with-gradient-fill/
---
En este tutorial, lo guiaremos a través del siguiente código fuente de C# paso a paso para agregar un dibujo con relleno degradado a la programación con gráficos usando Aspose.PDF para .NET.

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
Page page = doc.Pages.Add();
```

## Paso 3: crear un objeto gráfico y agregarlo a la página

Creamos un objeto Graph con dimensiones específicas y lo agregamos a la colección de párrafos de la página.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 300);
page.Paragraphs.Add(graph);
```

## Paso 4: cree un objeto rectangular y agréguelo al gráfico

Creamos un objeto Rectangle con dimensiones específicas y lo agregamos a la colección de formas del gráfico.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(0, 0, 300, 300);
graph.Shapes.Add(rect);
```

## Paso 5: Configuración del relleno degradado

Configuramos el relleno degradado para el rectángulo usando la clase GradientAxialShading.

```csharp
rect.GraphInfo.FillColor = new Aspose.Pdf.Color
{
PatternColorSpace = new GradientAxialShading(Color.Red, Color.Blue)
{
Start = new Point(0, 0),
End = new Point(300, 300)
}
};
```

Esto crea un relleno degradado de rojo a azul, desde el punto (0, 0) hasta el punto (300, 300).

## Paso 6: Guardar el archivo PDF

Finalmente, guardamos el archivo PDF resultante con el nombre "AddDrawingWithGradientFill_out.pdf" en el directorio especificado.

```csharp
doc.Save(dataDir + "AddDrawingWithGradientFill_out.pdf");
```

### Ejemplo de código fuente para Agregar dibujo con relleno degradado usando Aspose.Words para .NET 

```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 300);
page.Paragraphs.Add(graph);
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(0, 0, 300, 300);
graph.Shapes.Add(rect);
rect.GraphInfo.FillColor = new Aspose.Pdf.Color
{
	PatternColorSpace = new GradientAxialShading(Color.Red, Color.Blue)
	{
		Start = new Point(0, 0),
		End = new Point(300, 300)
	}
};
doc.Save(dataDir + "AddDrawingWithGradientFill_out.pdf");

```
## Conclusión

En este tutorial hemos explicado paso a paso cómo añadir un dibujo con relleno degradado a la programación con gráficos usando Aspose.PDF para .NET. Ahora puede utilizar este conocimiento para crear atractivos documentos PDF con diseños personalizados y rellenos degradados.