---
title: Agregar objeto SVG
linktitle: Agregar objeto SVG
second_title: Referencia de API de Aspose.PDF para .NET
description: Agregue fácilmente objetos SVG a sus archivos PDF usando Aspose.PDF para .NET.
type: docs
weight: 30
url: /es/net/programming-with-tables/add-svg-object/
---

En este tutorial, aprenderemos cómo agregar un objeto SVG a un archivo PDF utilizando la biblioteca Aspose.PDF para .NET. SVG (Gráficos vectoriales escalables) es un formato popular para gráficos vectoriales que se puede escalar fácilmente sin perder calidad. Con Aspose.PDF, puede agregar objetos SVG a sus documentos PDF mediante programación.

## Requisitos

Antes de comenzar, asegúrese de tener lo siguiente:

- Visual Studio instalado
- Aspose.PDF para la biblioteca .NET instalada

## Paso 1: configurar el entorno

Primero, configuremos el entorno creando un nuevo proyecto de C# en Visual Studio. Abra Visual Studio y siga estos pasos:

1. Haga clic en "Archivo" > "Nuevo" > "Proyecto" para crear un nuevo proyecto.
2. Seleccione la plantilla "Aplicación de consola (.NET Framework)" o "Aplicación de consola (.NET Core)", según su configuración.
3. Elija un nombre y una ubicación adecuados para su proyecto, luego haga clic en "Crear".

## Paso 2: crear documentos y objetos de imagen

En este paso, crearemos los objetos necesarios para nuestro documento PDF e imagen SVG. Abra el archivo C# de su proyecto y agregue el siguiente código:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Objeto de documento instantáneo
Document doc = new Document();
// Crear una instancia de imagen
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
```

## Paso 3: establecer las propiedades de la imagen

A continuación, estableceremos las propiedades de nuestra imagen SVG. Especificaremos el tipo de archivo como SVG, la ruta al archivo SVG y las dimensiones de la imagen. Agregue el siguiente código después del paso anterior:

```csharp
// Establecer tipo de imagen como SVG
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// Ruta del archivo fuente
img.File = dataDir + "SVGToPDF.svg";
// Establecer ancho para instancia de imagen
img. FixWidth = 50;
// Establecer altura para instancia de imagen
img.FixHeight = 50;
```

## Paso 4: crear y configurar la tabla

Ahora, creemos un objeto de tabla y establezcamos los anchos de columna. Crearemos una tabla con dos columnas, cada una con un ancho de 100 unidades. Agrega el siguiente código:

```csharp
// Crear tabla de instancias
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Establecer el ancho de las celdas de la tabla
table. ColumnWidths = "100 100";
```

## Paso 5: Agregar celdas a la tabla

En este paso, agregaremos una fila y celdas a la tabla. Cada fila representa una fila horizontal en la tabla y las celdas se agregan a las filas. Agrega el siguiente código:

```csharp
// Cree un objeto de fila y agréguelo a la instancia de la tabla
Aspose.Pdf.Row row = table.Rows.Add();
// Cree un objeto de celda y agréguelo a la instancia de fila
Aspose.Pdf.Cell cell = row.Cells.Add();
```

## Paso 6: agregue texto e imagen a las celdas

A continuación, agreguemos texto y la imagen SVG a las celdas de la tabla. Agregaremos el texto "Primera celda" a la primera celda y la imagen SVG a la segunda celda. Agrega el siguiente código:

```csharp
// Agregar fragmento de texto a la colección de párrafos del objeto de celda
cell.Paragraphs.Add(new TextFragment("First cell"));
// Agregar otra celda al objeto de fila
cell = row. Cells. Add();
// Agregue una imagen SVG a la colección de párrafos de una instancia de celda agregada recientemente
cell.Paragraphs.Add(img);
```

## Paso 7: crear y agregar una página al documento

Ahora, creemos un objeto de página y agréguelo al documento. La tabla se agregará a la colección de párrafos de la página. Agrega el siguiente código:

```csharp
// Cree un objeto de página y agréguelo a la colección de páginas de la instancia del documento
Page page = doc.Pages.Add();
// Agregar tabla a la colección de párrafos del objeto de página
page.Paragraphs.Add(table);
```

## Paso 8: Guarde el archivo PDF

Finalmente, guardaremos el archivo PDF en la ubicación especificada. Agrega el siguiente código:

```csharp
dataDir = dataDir + "AddSVGObject_out.pdf";
// Guardar archivo PDF
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);
```

### Ejemplo de código fuente para agregar un objeto SVG usando Aspose.Words para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instanciar objeto de documento
Document doc = new Document();
// Crear una instancia de imagen
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
// Establecer tipo de imagen como SVG
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// Ruta del archivo fuente
img.File = dataDir + "SVGToPDF.svg";
// Establecer ancho para instancia de imagen
img.FixWidth = 50;
// Establecer altura para instancia de imagen
img.FixHeight = 50;
// Crear instancia de tabla
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Establecer el ancho de las celdas de la tabla
table.ColumnWidths = "100 100";
// Cree un objeto de fila y agréguelo a la instancia de la tabla
Aspose.Pdf.Row row = table.Rows.Add();
// Cree un objeto de celda y agréguelo a la instancia de fila
Aspose.Pdf.Cell cell = row.Cells.Add();
// Agregar fragmento de texto a la colección de párrafos del objeto de celda
cell.Paragraphs.Add(new TextFragment("First cell"));
// Agregar otra celda al objeto de fila
cell = row.Cells.Add();
// Agregue una imagen SVG a la colección de párrafos de una instancia de celda agregada recientemente
cell.Paragraphs.Add(img);
// Cree un objeto de página y agréguelo a la colección de páginas de la instancia del documento
Page page = doc.Pages.Add();
// Agregar tabla a la colección de párrafos del objeto de página
page.Paragraphs.Add(table);

dataDir = dataDir + "AddSVGObject_out.pdf";
// Guardar archivo PDF
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);            
```

## Conclusión

En este tutorial, hemos aprendido cómo agregar un objeto SVG a un archivo PDF utilizando la biblioteca Aspose.PDF para .NET. Cubrimos el proceso paso a paso de crear un documento, configurar el entorno, agregar una imagen SVG a una celda de tabla y guardar el archivo PDF. Ahora puede incorporar objetos SVG en sus documentos PDF mediante programación.