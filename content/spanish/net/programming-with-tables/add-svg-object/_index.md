---
title: Agregar objeto SVG en archivo PDF
linktitle: Agregar objeto SVG en archivo PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Agregue fácilmente objetos SVG en archivos PDF usando Aspose.PDF para .NET.
type: docs
weight: 30
url: /es/net/programming-with-tables/add-svg-object/
---
En este tutorial, aprenderemos a agregar un objeto SVG a un archivo PDF utilizando la biblioteca Aspose.PDF para .NET. SVG (Scalable Vector Graphics) es un formato popular para gráficos vectoriales que se puede escalar fácilmente sin perder calidad. Con Aspose.PDF, puede agregar objetos SVG a sus documentos PDF mediante programación.

## Requisitos

Antes de comenzar, asegúrese de tener lo siguiente:

- Visual Studio instalado
- Biblioteca Aspose.PDF para .NET instalada

## Paso 1: Configurar el entorno

En primer lugar, configuremos el entorno creando un nuevo proyecto de C# en Visual Studio. Abra Visual Studio y siga estos pasos:

1. Haga clic en “Archivo” > “Nuevo” > “Proyecto” para crear un nuevo proyecto.
2. Seleccione la plantilla “Aplicación de consola (.NET Framework)” o “Aplicación de consola (.NET Core)”, según su configuración.
3. Elija un nombre y una ubicación adecuados para su proyecto, luego haga clic en "Crear".

## Paso 2: Crear objetos de documento e imagen

En este paso, crearemos los objetos necesarios para nuestro documento PDF y la imagen SVG. Abra el archivo C# de su proyecto y agregue el siguiente código:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Objeto de documento instantáneo
Document doc = new Document();
// Crear una instancia de imagen
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
```

## Paso 3: Establecer las propiedades de la imagen

A continuación, configuraremos las propiedades de nuestra imagen SVG. Especificaremos el tipo de archivo como SVG, la ruta al archivo SVG y las dimensiones de la imagen. Agregue el siguiente código después del paso anterior:

```csharp
// Establecer el tipo de imagen como SVG
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// Ruta del archivo fuente
img.File = dataDir + "SVGToPDF.svg";
// Establecer el ancho para la instancia de imagen
img. FixWidth = 50;
// Establecer altura para la instancia de imagen
img.FixHeight = 50;
```

## Paso 4: Crear y configurar la tabla

Ahora, vamos a crear un objeto de tabla y a establecer el ancho de las columnas. Crearemos una tabla con dos columnas, cada una con un ancho de 100 unidades. Agregue el siguiente código:

```csharp
// Crear tabla de instancias
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Establecer el ancho de las celdas de la tabla
table. ColumnWidths = "100 100";
```

## Paso 5: Agregar celdas a la tabla

En este paso, agregaremos una fila y celdas a la tabla. Cada fila representa una fila horizontal en la tabla y las celdas se agregan a las filas. Agregue el siguiente código:

```csharp
//Crear un objeto de fila y agregarlo a la instancia de la tabla
Aspose.Pdf.Row row = table.Rows.Add();
// Crear un objeto de celda y agregarlo a la instancia de fila
Aspose.Pdf.Cell cell = row.Cells.Add();
```

## Paso 6: Agregar texto e imagen a las celdas

A continuación, agreguemos el texto y la imagen SVG a las celdas de la tabla. Agregaremos el texto "Primera celda" a la primera celda y la imagen SVG a la segunda celda. Agregue el siguiente código:

```csharp
// Agregar fragmento de texto a la colección de párrafos del objeto de celda
cell.Paragraphs.Add(new TextFragment("First cell"));
// Agregar otra celda al objeto de fila
cell = row. Cells. Add();
// Agregar imagen SVG a la colección de párrafos de la instancia de celda agregada recientemente
cell.Paragraphs.Add(img);
```

## Paso 7: Crear y agregar una página al documento

Ahora, vamos a crear un objeto de página y agregarlo al documento. La tabla se agregará a la colección de párrafos de la página. Agregue el siguiente código:

```csharp
// Crear un objeto de página y agregarlo a la colección de páginas de la instancia del documento
Page page = doc.Pages.Add();
// Agregar tabla a la colección de párrafos del objeto de página
page.Paragraphs.Add(table);
```

## Paso 8: Guarde el archivo PDF

Finalmente, guardaremos el archivo PDF en la ubicación indicada. Agregue el siguiente código:

```csharp
dataDir = dataDir + "AddSVGObject_out.pdf";
// Guardar archivo PDF
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);
```

### Código fuente de ejemplo para agregar un objeto SVG usando Aspose.PDF para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crear una instancia del objeto Documento
Document doc = new Document();
// Crear una instancia de imagen
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
// Establecer el tipo de imagen como SVG
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// Ruta del archivo fuente
img.File = dataDir + "SVGToPDF.svg";
// Establecer el ancho para la instancia de imagen
img.FixWidth = 50;
// Establecer altura para la instancia de imagen
img.FixHeight = 50;
// Crear una instancia de tabla
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Establecer el ancho de las celdas de la tabla
table.ColumnWidths = "100 100";
//Crear un objeto de fila y agregarlo a la instancia de la tabla
Aspose.Pdf.Row row = table.Rows.Add();
// Crear un objeto de celda y agregarlo a la instancia de fila
Aspose.Pdf.Cell cell = row.Cells.Add();
// Agregar fragmento de texto a la colección de párrafos del objeto de celda
cell.Paragraphs.Add(new TextFragment("First cell"));
// Agregar otra celda al objeto de fila
cell = row.Cells.Add();
// Agregar imagen SVG a la colección de párrafos de la instancia de celda agregada recientemente
cell.Paragraphs.Add(img);
// Crear un objeto de página y agregarlo a la colección de páginas de la instancia del documento
Page page = doc.Pages.Add();
// Agregar tabla a la colección de párrafos del objeto de página
page.Paragraphs.Add(table);

dataDir = dataDir + "AddSVGObject_out.pdf";
// Guardar archivo PDF
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);            
```

## Conclusión

En este tutorial, hemos aprendido a agregar un objeto SVG a un archivo PDF mediante la biblioteca Aspose.PDF para .NET. Hemos cubierto el proceso paso a paso de creación de un documento, configuración del entorno, adición de una imagen SVG a una celda de tabla y guardado del archivo PDF. Ahora puede incorporar objetos SVG a sus documentos PDF mediante programación.

### Preguntas frecuentes sobre cómo agregar un objeto SVG a un archivo PDF

#### P: ¿Puedo agregar varios objetos SVG al documento PDF?

 R: Sí, puedes agregar varios objetos SVG al documento PDF. Simplemente crea y configura objetos SVG adicionales.`Aspose.Pdf.Image` instancias para cada imagen SVG que desee agregar y luego agréguelas a las celdas de la tabla o párrafos deseados en el documento PDF.

#### P: ¿Cómo puedo ajustar el tamaño y la posición de la imagen SVG en la celda de la tabla?

 A: Para ajustar el tamaño y la posición de la imagen SVG en la celda de la tabla, puede modificar el`FixWidth` y`FixHeight` Propiedades de la`Aspose.Pdf.Image`instancia. También puedes utilizar otras propiedades como`HorizontalAlignment` y`VerticalAlignment` de la celda de la tabla para controlar el posicionamiento.

#### P: ¿Es posible agregar texto junto a la imagen SVG en la misma celda de la tabla?

 R: Sí, es posible agregar texto junto con la imagen SVG en la misma celda de la tabla. Puede utilizar el`cell.Paragraphs.Add(new TextFragment("Your Text Here"));` Método para agregar texto a la celda junto con la imagen SVG.

#### P: ¿Puedo agregar hipervínculos a la imagen SVG?

 R: Sí, puede agregar hipervínculos a la imagen SVG utilizando el`Hyperlink` propiedad de la`Aspose.Pdf.Image` Instancia. Establezca la URL del hipervínculo o la acción para que se pueda hacer clic en la imagen.

#### P: ¿Aspose.PDF para .NET es compatible con .NET Core 3.1 o versiones posteriores?

R: Sí, Aspose.PDF para .NET es compatible con .NET Core 3.1 y versiones posteriores. Puede usarlo tanto en aplicaciones .NET Framework como .NET Core.