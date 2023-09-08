---
title: Agregar objeto de línea en un archivo PDF
linktitle: Agregar objeto de línea en un archivo PDF
second_title: Aspose.PDF para referencia de API .NET
description: Aprenda cómo agregar un objeto de línea personalizado en un archivo PDF usando Aspose.PDF para .NET.
type: docs
weight: 30
url: /es/net/programming-with-graphs/add-line-object/
---
En este tutorial, lo guiaremos a través del siguiente código fuente de C# paso a paso para agregar un objeto de línea usando Aspose.PDF para .NET.

Asegúrese de haber instalado la biblioteca Aspose.PDF y configurar su entorno de desarrollo antes de comenzar. También tener conocimientos básicos de programación en C#.

## Paso 1: Configuración del directorio de documentos

En el código fuente proporcionado, debe especificar el directorio donde desea guardar el archivo PDF resultante. Cambie la variable "dataDir" al directorio deseado.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: crear una instancia de documento y agregar una página

Creamos una instancia de la clase Documento y agregamos una página a este documento.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Paso 3: crear un objeto gráfico y agregarlo a la página

Creamos un objeto Graph con dimensiones específicas y lo agregamos a la colección de párrafos de la página.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(graph);
```

## Paso 4: crear un objeto de línea y agregarlo al gráfico

Creamos un objeto Línea con las coordenadas especificadas y lo agregamos a la colección de formas del gráfico.

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
graph.Shapes.Add(line);
```

## Paso 5: configuración de línea

Podemos especificar propiedades para la línea, como el tipo de guión y la fase del guión.

```csharp
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## Paso 6: guardar el archivo PDF

Finalmente, guardamos el archivo PDF resultante con el nombre "AddLineObject_out.pdf" en el directorio especificado.

```csharp
doc.Save(dataDir + "AddLineObject_out.pdf");
```

### Código fuente de muestra para Agregar objeto de línea usando Aspose.PDF para .NET 

```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crear instancia de documento
Document doc = new Document();
// Agregar página a colección de páginas de archivos PDF
Page page = doc.Pages.Add();
// Crear instancia de gráfico
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
// Agregar objeto gráfico a la colección de párrafos de la instancia de página
page.Paragraphs.Add(graph);
// Crear instancia de rectángulo
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
// Especificar el color de relleno para el objeto Gráfico
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
// Agregar un objeto rectangular a la colección de formas del objeto Graph
graph.Shapes.Add(line);
dataDir = dataDir + "AddLineObject_out.pdf";
// Guardar archivo PDF
doc.Save(dataDir);
Console.WriteLine("\nLine object added successfully to pdf.\nFile saved at " + dataDir);            

```

## Conclusión

En este tutorial, explicamos paso a paso cómo agregar un objeto de línea usando Aspose.PDF para .NET. Ahora puede utilizar este conocimiento para crear documentos PDF con líneas personalizadas en sus aplicaciones.

### Preguntas frecuentes para agregar un objeto de línea en un archivo PDF

#### P: ¿Cuál es el propósito de este tutorial?

R: Este tutorial tiene como objetivo guiarlo a través del proceso de agregar un objeto de línea usando Aspose.PDF para .NET para mejorar sus documentos PDF.

#### P: ¿Qué requisitos previos se requieren antes de comenzar?

R: Antes de comenzar, asegúrese de haber instalado la biblioteca Aspose.PDF y configurado su entorno de desarrollo. Además, se recomienda tener conocimientos básicos de programación en C#.

#### P: ¿Cómo especifico el directorio para guardar el archivo PDF?

R: En el código fuente proporcionado, puede modificar la variable "dataDir" para indicar el directorio donde desea guardar el archivo PDF resultante.

#### P: ¿Cuál es el propósito del objeto Graph?

R: El objeto Gráfico sirve como contenedor para elementos de dibujo. Se crea con dimensiones específicas y se agrega a la colección de párrafos de la página.

#### P: ¿Cómo puedo agregar un objeto de línea al documento PDF?

R: Para agregar un objeto de línea, cree una instancia de la clase Línea con coordenadas especificadas y agréguela a la colección de formas del gráfico.

#### P: ¿Puedo personalizar la apariencia de la línea?

R: Sí, puede personalizar la apariencia de la línea configurando propiedades como el tipo de guión y la fase del guión usando la propiedad GraphInfo del objeto Línea.

#### P: ¿Cuál es el propósito de especificar la matriz de guiones y la fase de guiones?

R: Las propiedades de matriz de guiones y fase de guión le permiten crear líneas discontinuas o de puntos con patrones específicos.

#### P: ¿Cómo puedo guardar el archivo PDF después de agregar el objeto de línea?

 R: Después de agregar el objeto de línea, puede guardar el archivo PDF resultante usando el`doc.Save(dataDir + "AddLineObject_out.pdf");` línea en el código fuente proporcionado.

#### P: ¿Hay un código fuente de muestra disponible?

R: Sí, el tutorial incluye un código fuente de muestra al que puede consultar para implementar los pasos descritos.