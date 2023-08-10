---
title: Crear rectángulo relleno
linktitle: Crear rectángulo relleno
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a crear un rectángulo relleno con Aspose.PDF para .NET. Guía paso a paso para personalizar el color de relleno.
type: docs
weight: 50
url: /es/net/programming-with-graphs/create-filled-rectangle/
---
En este tutorial, lo guiaremos a través del siguiente código fuente de C# paso a paso para crear un rectángulo relleno usando Aspose.PDF para .NET.

Asegúrese de haber instalado la biblioteca Aspose.PDF y configure su entorno de desarrollo antes de comenzar. También tener conocimientos básicos de programación en C#.

## Paso 1: Configuración del directorio de documentos

En el código fuente provisto, debe especificar el directorio donde desea guardar el archivo PDF resultante. Cambie la variable "dataDir" al directorio deseado.

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

## Paso 4: cree un objeto rectangular y agréguelo al gráfico

Creamos un objeto Rectangle con las dimensiones especificadas y lo agregamos a la colección de formas del gráfico.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
graph.Shapes.Add(rect);
```

## Paso 5: Configuración del color de relleno

Podemos especificar el color de relleno para el rectángulo usando la propiedad FillColor del objeto GraphInfo.

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
```

## Paso 6: Guardar el archivo PDF resultante

Finalmente, guardamos el archivo PDF resultante con el nombre "CreateFilledRectangle_out.pdf" en el directorio especificado.

```csharp
doc.Save(dataDir + "CreateFilledRectangle_out.pdf");
```

### Ejemplo de código fuente para crear un rectángulo relleno con Aspose.PDF para .NET 

```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crear instancia de documento
Document doc = new Document();
// Agregar página a la colección de páginas del archivo PDF
Page page = doc.Pages.Add();
// Crear instancia de gráfico
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
// Agregar objeto de gráfico a la colección de párrafos de instancia de página
page.Paragraphs.Add(graph);
// Crear instancia de Rectángulo
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
// Especifique el color de relleno para el objeto Gráfico
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
// Agregue un objeto rectangular a la colección de formas del objeto Graph
graph.Shapes.Add(rect);
dataDir = dataDir + "CreateFilledRectangle_out.pdf";
// Guardar archivo PDF
doc.Save(dataDir);
Console.WriteLine("\nFilled rectangle object created successfully.\nFile saved at " + dataDir);            

```

## Conclusión

En este tutorial, explicamos cómo crear un rectángulo relleno usando Aspose.PDF para .NET. Ahora puede utilizar este conocimiento para crear formas geométricas con colores de relleno personalizados en sus archivos PDF.

## Preguntas frecuentes

#### P: ¿Cuál es el propósito de este tutorial?

R: El propósito de este tutorial es guiarlo a través del proceso de creación de un rectángulo relleno usando Aspose.PDF para .NET, permitiéndole agregar formas geométricas personalizadas con colores de relleno a sus archivos PDF.

#### P: ¿Qué requisitos previos se requieren antes de comenzar?

R: Antes de comenzar, asegúrese de haber instalado la biblioteca Aspose.PDF y configurar su entorno de desarrollo. Además, se recomienda tener conocimientos básicos de programación en C#.

#### P: ¿Cómo especifico el directorio para guardar el archivo PDF?

R: En el código fuente proporcionado, puede modificar la variable "dataDir" para indicar el directorio donde desea guardar el archivo PDF resultante.

#### P: ¿Cuál es el propósito del objeto Graph?

R: El objeto Graph actúa como un contenedor para los elementos de dibujo. Se crea con dimensiones específicas y se agrega a la colección de párrafos de la página.

#### P: ¿Cómo puedo agregar un rectángulo relleno al documento PDF?

R: Para agregar un rectángulo relleno, cree una instancia de la clase Rectangle con las dimensiones y el color de relleno especificados, y agréguela a la colección de formas del gráfico.

#### P: ¿Puedo personalizar las dimensiones y el color de relleno del rectángulo?

 R: Sí, puede personalizar las dimensiones y el color de relleno del rectángulo modificando los parámetros pasados al`Aspose.Pdf.Drawing.Rectangle` constructor y configurando la propiedad FillColor.

#### P: ¿Cómo guardo el archivo PDF resultante después de crear el rectángulo relleno?

 R: Después de crear el rectángulo relleno, puede guardar el archivo PDF resultante usando el`doc.Save(dataDir + "CreateFilledRectangle_out.pdf");` línea en el código fuente proporcionado.