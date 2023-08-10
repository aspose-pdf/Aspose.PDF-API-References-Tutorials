---
title: Longitud del guión
linktitle: Longitud del guión
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a configurar la longitud de los guiones con Aspose.PDF para .NET. Guía paso a paso para personalizar patrones de guiones.
type: docs
weight: 70
url: /es/net/programming-with-graphs/dash-length/
---
En este tutorial, lo guiaremos a través del siguiente código fuente de C# paso a paso para establecer la longitud de los guiones usando Aspose.PDF para .NET.

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
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(canvas);
```

## Paso 4: Creación de un objeto de línea y configuración

Creamos un objeto Línea con las coordenadas especificadas y configuramos el color y la longitud de los guiones.

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## Paso 5: agregar la línea al objeto gráfico

Agregamos la línea a la colección de formas del objeto Graph.

```csharp
canvas.Shapes.Add(line);
```

## Paso 6: Guardar el archivo PDF resultante

Finalmente, guardamos el archivo PDF resultante con el nombre "DashLength_out.pdf" en el directorio especificado.

```csharp
doc.Save(dataDir + "DashLength_out.pdf");
```

### Ejemplo de código fuente para Dash Length usando Aspose.PDF para .NET 

```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instanciar instancia de documento
Document doc = new Document();
// Agregar página a la colección de páginas del objeto Documento
Page page = doc.Pages.Add();
// Crear objeto de dibujo con ciertas dimensiones
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Agregar objeto de dibujo a la colección de párrafos de instancia de página
page.Paragraphs.Add(canvas);
// Crear objeto de línea
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
// Establecer color para el objeto Línea
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
// Especifique una matriz de guiones para el objeto de línea
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
// Establecer la fase del guión para la instancia de Línea
line.GraphInfo.DashPhase = 1;
// Agregar línea a la colección de formas del objeto de dibujo
canvas.Shapes.Add(line);
dataDir = dataDir + "DashLength_out.pdf";
// Guardar documento PDF
doc.Save(dataDir);
Console.WriteLine("\nLength dashed successfully in black and white.\nFile saved at " + dataDir);            

```

## Conclusión

En este tutorial, explicamos cómo configurar la longitud de los guiones usando Aspose.PDF para .NET. Ahora puede usar este conocimiento para crear líneas con patrones de guiones personalizados en sus archivos PDF.

## preguntas frecuentes

#### P: ¿Cuál es el propósito de este tutorial?

R: El propósito de este tutorial es guiarlo a través del proceso de configuración de la longitud de los guiones para las líneas usando Aspose.PDF para .NET. Aprenderá a crear líneas con patrones de guiones personalizados en sus archivos PDF.

#### P: ¿Qué requisitos previos se requieren antes de comenzar?

R: Antes de comenzar, asegúrese de haber instalado la biblioteca Aspose.PDF y configurar su entorno de desarrollo. También se recomienda una comprensión básica de la programación en C#.

#### P: ¿Cómo especifico el directorio para guardar el archivo PDF?

R: Modifique la variable "dataDir" en el código fuente provisto para indicar el directorio donde desea guardar el archivo PDF resultante.

#### P: ¿Cómo creo una línea con patrones de guiones personalizados?

 R: El tutorial muestra la creación de un objeto Línea y la configuración de su color, matriz de guiones y fase de guiones mediante el`GraphInfo` objeto. Modifique estos ajustes para lograr el patrón de guiones deseado.

#### P: ¿Puedo personalizar el color de la línea?

 R: Sí, puede personalizar el color de la línea configurando el`Color` propiedad de la`GraphInfo` objeto asociado a la Línea.

#### P: ¿Cómo guardo el documento PDF después de configurar la longitud del guión?

 R: Después de configurar el objeto Línea con el patrón de guiones deseado, puede guardar el documento PDF resultante usando el`doc.Save(dataDir + "DashLength_out.pdf");` línea en el código fuente proporcionado.