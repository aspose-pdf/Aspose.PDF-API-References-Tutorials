---
title: Determinar el descanso de la mesa
linktitle: Determinar el descanso de la mesa
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a determinar los saltos de tabla en un documento PDF con Aspose.PDF para .NET.
type: docs
weight: 60
url: /es/net/programming-with-tables/determine-table-break/
---

En este tutorial, vamos a aprender cómo determinar los saltos de tabla en un documento PDF utilizando Aspose.PDF para .NET. Explicaremos el código fuente en C# paso a paso. Al final de este tutorial, sabrá cómo determinar si una tabla excede los márgenes de la página. ¡Empecemos!

## Paso 1: Configuración del entorno
Primero, asegúrese de haber configurado su entorno de desarrollo C# con Aspose.PDF para .NET. Agregue la referencia a la biblioteca e importe los espacios de nombres necesarios.

## Paso 2: Crear el documento PDF
 En este paso, creamos un nuevo`Document` objeto para representar el documento PDF.

```csharp
pdf-Document = new Document();
```

Este documento se utilizará para agregar secciones y tablas.

## Paso 3: agregar una sección y una tabla
Ahora vamos a agregar una sección a nuestro documento PDF y crear una tabla dentro de esta sección.

```csharp
Page page = pdf.Pages.Add();
Table table1 = new Table();
table1. Margin. Top = 300;
page.Paragraphs.Add(table1);
```

También especificamos un margen superior de 300 puntos para la tabla. Puede ajustar este valor según sus necesidades.

## Paso 4: Configuración de la mesa
En este paso, configuramos las propiedades de la tabla, como el ancho de las columnas y los bordes.

```csharp
table1. ColumnWidths = "100 100 100";
table1.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1F);
table1.Border = new BorderInfo(BorderSide.All, 1F);
```

Aquí definimos el ancho de las columnas de la tabla y los bordes de las celdas. Puede ajustar estos valores según sus preferencias.

## Paso 5: agregue filas y celdas a la tabla
Ahora crearemos filas y celdas en la tabla usando un bucle.

```csharp
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
     Row row1 = table1.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
```

Aquí creamos 17 filas en la tabla y agregamos tres celdas a cada fila. Puedes ajustar la hebilla según tus necesidades.

## Paso 6: Determinación de los descansos de la mesa
Ahora determinaremos si la tabla excede los márgenes de la página comparando la altura de la página con la altura total de los objetos en la tabla.

```csharp
float PageHeight = (float)pdf.PageInfo.Height;
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

if ((PageHeight - TotalObjectsHeight) <= 10)
     Console.WriteLine("The height of the page - Height of objects < 10, the table will be truncated");
```

Calculamos la altura de la página y la altura total de los objetos teniendo en cuenta los márgenes. Si la diferencia es 10 o menos, la tabla excede los márgenes de la página.

## Paso 7: Guardar el documento PDF
Finalmente, guardamos el documento PDF con los resultados.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
dataDir = dataDir + "DetermineTableBreak_out.pdf";
pdf.Save(dataDir);
Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

Asegúrese de especificar el directorio de documentos correcto. El archivo PDF resultante se guardará con los saltos de tabla determinados.

### Ejemplo de código fuente para Determinar salto de tabla usando Aspose.Words para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crear una instancia de una clase PDF de objeto
Document pdf = new Document();
// Agregar la sección a la colección de secciones del documento PDF
Aspose.Pdf.Page page = pdf.Pages.Add();
// Crear una instancia de un objeto de tabla
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table1.Margin.Top = 300;
// Agregue la tabla en la colección de párrafos de la sección deseada
page.Paragraphs.Add(table1);
// Establecer con anchos de columna de la tabla
table1.ColumnWidths = "100 100 100";
// Establecer borde de celda predeterminado usando el objeto BorderInfo
table1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// Establecer el borde de la tabla usando otro objeto BorderInfo personalizado
table1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// Cree el objeto MarginInfo y establezca sus márgenes izquierdo, inferior, derecho y superior
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Establezca el relleno de celda predeterminado en el objeto MarginInfo
table1.DefaultCellPadding = margin;
// Si aumentas el contador a 17, la mesa se romperá.
// Porque no se puede acomodar más en esta página
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
	// Crear filas en la tabla y luego celdas en las filas
	Aspose.Pdf.Row row1 = table1.Rows.Add();
	row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
// Obtener la información de la altura de la página
float PageHeight = (float)pdf.PageInfo.Height;
// Obtenga la información de altura total del margen superior e inferior de la página,
// Margen superior de la mesa y altura de la mesa.
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

// Mostrar la altura de la página, la altura de la tabla, el margen superior de la tabla y la parte superior de la página
// Y la información del margen inferior
Console.WriteLine("PDF document Height = " + pdf.PageInfo.Height.ToString() + "\nTop Margin Info = " + page.PageInfo.Margin.Top.ToString() + "\nBottom Margin Info = " + page.PageInfo.Margin.Bottom.ToString() + "\n\nTable-Top Margin Info = " + table1.Margin.Top.ToString() + "\nAverage Row Height = " + table1.Rows[0].MinRowHeight.ToString() + " \nTable height " + table1.GetHeight().ToString() + "\n ----------------------------------------" + "\nTotal Page Height =" + PageHeight.ToString() + "\nCummulative height including Table =" + TotalObjectsHeight.ToString());

//Compruebe si deducimos la suma del margen superior de la página + el margen inferior de la página
// + Margen superior de la mesa y altura de la mesa desde la altura de la página y su menor
// Que 10 (una fila promedio puede ser mayor que 10)
if ((PageHeight - TotalObjectsHeight) <= 10)
	// Si el valor es inferior a 10, muestra el mensaje.
	// Lo que demuestra que no se puede colocar otra fila y si agregamos nuevas
	// Fila, la mesa se romperá. Depende del valor de la altura de la fila.
	Console.WriteLine("Page Height - Objects Height < 10, so table will break");


dataDir = dataDir + "DetermineTableBreak_out.pdf";
// Guardar el documento pdf
pdf.Save(dataDir);

Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

## Conclusión
En este tutorial, aprendimos cómo determinar los saltos de tabla en un documento PDF usando Aspose.PDF para .NET. Puede utilizar esta guía paso a paso para comprobar si una tabla supera los márgenes de página en sus propios proyectos de C#.