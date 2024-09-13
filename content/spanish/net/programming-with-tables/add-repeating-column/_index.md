---
title: Agregar columna repetida en documento PDF
linktitle: Agregar columna repetida en documento PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a agregar una columna repetida en un documento PDF usando Aspose.PDF para .NET.
type: docs
weight: 20
url: /es/net/programming-with-tables/add-repeating-column/
---
En este tutorial, aprenderemos a agregar una columna repetida en un documento PDF usando Aspose.PDF para .NET. Explicaremos el código fuente en C# paso a paso. Al final de este tutorial, sabrá cómo crear una tabla con una columna repetida en un documento PDF. ¡Comencemos!

## Paso 1: Configuración del entorno
En primer lugar, asegúrese de haber configurado su entorno de desarrollo de C# con Aspose.PDF para .NET. Agregue la referencia a la biblioteca e importe los espacios de nombres necesarios.

## Paso 2: Creación del documento PDF
En este paso, creamos un nuevo documento PDF.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

Hemos creado un documento PDF vacío donde podemos añadir contenido.

## Paso 3: Creación de las tablas
En este paso creamos una tabla principal (`outerTable`) y una tabla anidada (`mytable`) que se repetirá en la columna.

```csharp
Table outerTable = new Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;

Table mytable = new Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;
```

Especificamos propiedades de tabla como el ancho de columna y el modo de salto de tabla anidada.

## Paso 4: Agregar las tablas al documento
Ahora agregamos las tablas creadas al documento PDF.

```csharp
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
page.Paragraphs.Add(mytable);
```

Primero agregamos la tabla principal (`outerTable`) al documento PDF. A continuación, agregamos la tabla anidada (`mytable` ) como un párrafo en una celda de la tabla principal. También especificamos el número de columnas repetidas para`mytable` (en este ejemplo, 5 columnas).

## Paso 5: Agregar encabezados y líneas
Ahora agregamos los encabezados y filas a la tabla.

```csharp
Row headerRow = mytable.Rows.Add();
headerRow.Cells.Add("header 1");
headerRow.Cells.Add("header 2");
headerRow.Cells.Add("header 3");
// ...
//Añade otros encabezados aquí

for (int RowCounter = 0; RowCounter <= 5; RowCounter++)
{
     Row row1 = mytable.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
     // ...
     // Añade las otras columnas aquí
}
```

Primero agregamos los encabezados a la primera fila de la tabla (`headerRow`). Luego, agregamos las filas de datos de un bucle. En este ejemplo, agregamos 6 filas de datos.

## Paso 6: Guardar el documento PDF
Finalmente, guardamos el documento PDF en el archivo especificado.

```csharp
string outFile = dataDir + "AddRepeatingColumn_out.pdf";
doc.Save(outFile);
```

Asegúrese de especificar el directorio y el nombre de archivo correctos para guardar el archivo PDF de salida.

### Código fuente de ejemplo para agregar una columna repetida usando Aspose.PDF para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

string outFile = dataDir + "AddRepeatingColumn_out.pdf";
// Crear un nuevo documento
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();

// Crear una instancia de una tabla externa que ocupe toda la página
Aspose.Pdf.Table outerTable = new Aspose.Pdf.Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;

// Cree una instancia de un objeto de tabla que se anidará dentro de outerTable y que se dividirá dentro de la misma página
Aspose.Pdf.Table mytable = new Aspose.Pdf.Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;

// Añade la tabla externa a los párrafos de la página
// Agregar mytable a outerTable
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
page.Paragraphs.Add(mytable);

// Agregar fila de encabezado
Aspose.Pdf.Row row = mytable.Rows.Add();
row.Cells.Add("header 1");
row.Cells.Add("header 2");
row.Cells.Add("header 3");
row.Cells.Add("header 4");
row.Cells.Add("header 5");
row.Cells.Add("header 6");
row.Cells.Add("header 7");
row.Cells.Add("header 11");
row.Cells.Add("header 12");
row.Cells.Add("header 13");
row.Cells.Add("header 14");
row.Cells.Add("header 15");
row.Cells.Add("header 16");
row.Cells.Add("header 17");

for (int RowCounter = 0; RowCounter <= 5; RowCounter++)

{
	// Crea filas en la tabla y luego celdas en las filas.
	Aspose.Pdf.Row row1 = mytable.Rows.Add();
	row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 4");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 5");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 6");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 7");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 11");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 12");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 13");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 14");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 15");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 16");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 17");
}
doc.Save(outFile);
```

## Conclusión
En este tutorial, aprendimos a agregar una columna repetida en un documento PDF con Aspose.PDF para .NET. Puede usar esta guía paso a paso para crear tablas con columnas repetidas en sus propios proyectos de C#.

### Preguntas frecuentes sobre cómo agregar columnas repetidas en un documento PDF

#### P: ¿Puedo personalizar la cantidad de columnas repetidas en la tabla anidada?

 R: Sí, puede personalizar la cantidad de columnas repetidas en la tabla anidada. En el ejemplo proporcionado, configuramos`mytable.RepeatingColumnsCount = 5;`, lo que significa que habrá 5 columnas repetidas. Puedes cambiar este valor por cualquier número que desees.

#### P: ¿Es posible agregar más filas a la tabla anidada de forma dinámica?

R: Sí, puedes agregar dinámicamente más filas a la tabla anidada de la misma manera que se muestra en el tutorial. Puedes usar bucles o cualquier otra lógica para agregar filas en función de tus datos.

#### P: ¿Puedo aplicar estilos y formatos a la tabla y sus celdas?

R: Sí, puede aplicar estilos y formatos a la tabla y sus celdas mediante Aspose.PDF para .NET. La biblioteca proporciona varias propiedades y métodos para personalizar la apariencia de la tabla y su contenido.

#### P: ¿Aspose.PDF para .NET es compatible con .NET Core?

R: Sí, Aspose.PDF para .NET es compatible con .NET Core. Puede usarlo tanto en aplicaciones .NET Framework como .NET Core.

#### P: ¿Puedo utilizar este enfoque para agregar columnas repetidas en un documento PDF existente?

R: Sí, puede utilizar este método para agregar columnas repetidas en un documento PDF existente. Simplemente cargue el documento existente mediante Aspose.PDF para .NET y siga los mismos pasos para crear y agregar la columna repetida.