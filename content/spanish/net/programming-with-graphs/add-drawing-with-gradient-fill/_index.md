---
title: Agregar dibujo con relleno degradado
linktitle: Agregar dibujo con relleno degradado
second_title: Aspose.PDF para referencia de API .NET
description: Aprenda cómo agregar un dibujo con relleno degradado con Aspose.PDF para .NET. Tutorial paso a paso para crear atractivos documentos PDF.
type: docs
weight: 20
url: /es/net/programming-with-graphs/add-drawing-with-gradient-fill/
---
En este tutorial, lo guiaremos a través del siguiente código fuente de C# paso a paso para agregar un dibujo con relleno degradado a la programación con gráficos usando Aspose.PDF para .NET.

Asegúrese de haber instalado la biblioteca Aspose.PDF y configurar su entorno de desarrollo antes de comenzar. También tener conocimientos básicos de programación en C#.

## Paso 1: Configuración del directorio de documentos

En el código fuente proporcionado, debe especificar el directorio donde desea guardar el archivo PDF resultante. Cambie la variable "dataDir" al directorio deseado.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: crear una instancia de un objeto de documento y agregar una página

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

## Paso 4: crear un objeto rectangular y agregarlo al gráfico

Creamos un objeto Rectángulo con dimensiones específicas y lo agregamos a la colección de formas del gráfico.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(0, 0, 300, 300);
graph.Shapes.Add(rect);
```

## Paso 5: Configurar el relleno degradado

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

## Paso 6: guardar el archivo PDF

Finalmente, guardamos el archivo PDF resultante con el nombre "AddDrawingWithGradientFill_out.pdf" en el directorio especificado.

```csharp
doc.Save(dataDir + "AddDrawingWithGradientFill_out.pdf");
```

### Código fuente de muestra para agregar dibujo con relleno degradado usando Aspose.PDF para .NET 

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

### Preguntas frecuentes

#### P: ¿Cuál es el propósito de este tutorial?

R: Este tutorial tiene como objetivo guiarlo a través del proceso de agregar un dibujo con relleno degradado a la programación con gráficos usando Aspose.PDF para .NET.

#### P: ¿Qué requisitos previos se requieren antes de comenzar?

R: Antes de comenzar, asegúrese de haber instalado la biblioteca Aspose.PDF y configurado su entorno de desarrollo. Además, se recomienda tener conocimientos básicos de programación en C#.

#### P: ¿Cómo especifico el directorio para guardar el archivo PDF?

R: En el código fuente proporcionado, puede cambiar el valor de la variable "dataDir" para indicar el directorio donde desea guardar el archivo PDF resultante.

#### P: ¿Cuál es el propósito del objeto Graph?

R: El objeto Gráfico sirve como contenedor para los elementos de dibujo. Se crea con dimensiones específicas y se agrega a la colección de párrafos de la página.

#### P: ¿Cómo puedo configurar el relleno degradado para una forma?

R: Para configurar el relleno degradado, puede configurar la propiedad FillColor de GraphInfo de una forma usando la clase GradientAxialShading. Esto le permite definir los puntos inicial y final del degradado y los colores entre los que realizar la transición.

#### P: ¿Puedo personalizar los colores y la dirección del relleno degradado?

R: Sí, puede personalizar los colores y la dirección del relleno degradado ajustando los objetos de color y especificando los puntos inicial y final de GradientAxialShading.

#### P: ¿Cuál es el paso final del tutorial?

R: El último paso consiste en guardar el archivo PDF resultante con el nombre "AddDrawingWithGradientFill_out.pdf" en el directorio especificado.

#### P: ¿Hay un código fuente de muestra disponible?

R: Sí, el tutorial proporciona un código fuente de muestra que puede utilizar como referencia para implementar los pasos descritos.

#### P: ¿Puedo aplicar relleno degradado a otras formas además de los rectángulos?

R: Sí, también puedes aplicar relleno degradado a otras formas. El proceso implica configurar la propiedad FillColor de GraphInfo de la forma usando la clase GradientAxialShading.