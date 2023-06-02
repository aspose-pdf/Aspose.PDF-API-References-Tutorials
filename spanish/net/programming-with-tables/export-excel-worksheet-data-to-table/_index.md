---
title: Exportar datos de la hoja de cálculo de Excel a la tabla
linktitle: Exportar datos de la hoja de cálculo de Excel a la tabla
second_title: Referencia de API de Aspose.PDF para .NET
description: Exporte datos de una hoja de Excel a una tabla PDF utilizando Aspose.PDF para .NET.
type: docs
weight: 70
url: /es/net/programming-with-tables/export-excel-worksheet-data-to-table/
---

En este tutorial, aprenderemos cómo exportar datos desde una hoja de cálculo de Excel y crear una tabla en un documento PDF utilizando la biblioteca Aspose.PDF para .NET. Revisaremos el código fuente paso a paso y explicaremos cada sección en detalle. Al final de este tutorial, podrá generar archivos PDF con tablas que contengan datos de hojas de cálculo de Excel. ¡Empecemos!

## Requisitos
Antes de comenzar, asegúrese de tener lo siguiente:

- Conocimientos básicos del lenguaje de programación C#
- Visual Studio instalado en su máquina
- Aspose.PDF para la biblioteca .NET agregada a su proyecto

## Paso 1: Configuración del entorno
Para comenzar, cree un nuevo proyecto de C# en Visual Studio. Agregue la referencia a la biblioteca Aspose.PDF para .NET haciendo clic con el botón derecho en su proyecto en el Explorador de soluciones, seleccionando "Administrar paquetes NuGet" y buscando "Aspose.PDF". Instale el paquete y estará listo para comenzar.

## Paso 2: cargar la hoja de cálculo de Excel
En el primer paso de nuestro código, definimos la ruta al directorio que contiene el documento de Excel. Reemplace "SU DIRECTORIO DE DOCUMENTOS" con la ruta del directorio real donde se encuentra su archivo de Excel.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
```

Aquí, usamos la biblioteca Aspose.Cells para cargar el libro de Excel. Asegúrese de reemplazar "nuevoLibro1.xlsx" con el nombre de su archivo de Excel.

## Paso 3: Acceso a la hoja de trabajo
 A continuación, debemos acceder a la primera hoja de trabajo en el archivo de Excel. Esto lo hacemos usando el`Worksheets` colección de la`Workbook` objeto.

```csharp
// Acceso a la primera hoja de trabajo en el archivo de Excel
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
```

 Si su archivo de Excel contiene varias hojas de trabajo, puede cambiar el valor del índice`[0]` para acceder a una hoja de trabajo diferente.

## Paso 4: exportar datos a DataTable
 Ahora, exportaremos el contenido de la hoja de cálculo de Excel a un`DataTable` objeto. Especificamos el rango de celdas a exportar usando el`ExportDataTable` método.

```csharp
// Exportación del contenido de 7 filas y 2 columnas a partir de la primera celda a DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);
```

En este ejemplo, exportamos todas las filas y columnas desde la primera celda (0, 0) hasta la última celda de la hoja de trabajo. Establezca el rango apropiado según sus requisitos.

## Paso 5: Creación de un documento PDF
Ahora, crearemos un nuevo documento PDF utilizando la biblioteca Aspose.PDF.

```csharp
//Instanciar una instancia de Documento
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

Esto crea un documento PDF vacío donde podemos agregar contenido.

## Paso 6: agregar una página y una tabla
Para mostrar los datos en formato de tabla, necesitamos agregar una página y una tabla al documento PDF.

```csharp
// Crear una página en la instancia del documento
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// Crear un objeto de tabla
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Agregue el objeto Table en la colección de párrafos de la sección.
sec1.Paragraphs.Add(tab1);
```

Aquí, creamos una nueva página y un objeto de tabla. Luego agregamos la tabla a la colección de párrafos de la página.

## Paso 7: Configuración de las propiedades de la tabla
Antes de importar los datos, debemos establecer algunas propiedades de la tabla, como el ancho de columna y los bordes de celda predeterminados.

```csharp
// Establecer anchos de columna de la tabla
tab1.ColumnWidths = "40 100 100";

// Establezca el borde de celda predeterminado de la tabla usando el objeto BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

En este ejemplo, establecemos los anchos de columna en 40, 100 y 100 unidades. Ajuste los valores en función de sus datos. También configuramos el borde de celda predeterminado para mostrar bordes en todos los lados de cada celda.

## Paso 8: Importación de datos a la tabla
Ahora, importaremos los datos de la`DataTable` objeto en la mesa usando el`ImportDataTable` método.

```csharp
// Importe datos al objeto Table desde el DataTable creado anteriormente
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
```

 Aquí, especificamos el rango de filas y columnas para importar. En este ejemplo, importamos todas las filas y columnas del`dataTable` objeto.

## Paso 9: Dar formato a la tabla
Para mejorar la apariencia de la tabla, podemos aplicar formato a celdas o filas específicas. En este paso, formatearemos la primera fila y las filas alternas de la tabla.

```csharp
// Obtener la primera fila de la tabla
Aspose.Pdf.Row row1 = tab1.Rows[0];

// Dar formato a la primera fila
foreach(Aspose.Pdf.Cell curCell in row1.Cells)
{
     // Establecer el color de fondo de las celdas en la primera fila
     curCell.BackgroundColor = Color.Blue;// Establecer la cara de las celdas en la primera fila
     curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
    
     // Establecer el color de fuente de las celdas en la primera fila
     curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
    
     // Establecer la alineación del texto para las celdas en la primera fila
     curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

// Formato de fila alternativo
for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
     foreach(Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
     {
         // Establecer el color de fondo de las celdas en filas alternas
         curCell.BackgroundColor = Color.Gray;
        
         // Establecer el color del texto de las celdas en filas alternas
         curCell.DefaultCellTextState.ForegroundColor = Color.White;
     }
}
```

Aquí, iteramos a través de las celdas en la primera fila y establecemos su color de fondo, fuente, color de fuente y alineación del texto. Luego, iteramos a través de todas las celdas en las filas alternativas y establecemos su fondo y color de texto.

## Paso 10: Guardar el documento PDF
Finalmente, guardamos el documento PDF en la ubicación especificada.

```csharp
// Guardar el PDF
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta del directorio y el nombre de archivo deseados para el archivo PDF de salida.

### Ejemplo de código fuente para exportar datos de hojas de cálculo de Excel a una tabla con Aspose.Words para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
// Acceso a la primera hoja de trabajo en el archivo de Excel
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
// Exportación del contenido de 7 filas y 2 columnas a partir de la primera celda a DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);

// Crear una instancia de documento
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
// Crear una página en la instancia del documento
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// Crear un objeto de tabla
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Agregue el objeto Table en la colección de párrafos de la sección.
sec1.Paragraphs.Add(tab1);

// Establecer anchos de columna de la tabla. Necesitamos especificar ColumnCount manualmente.
// Como la hoja de cálculo de Excel actual tiene tres columnas, estamos especificando el mismo recuento
tab1.ColumnWidths = "40 100 100";

// Establezca el borde de celda predeterminado de la tabla usando el objeto BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Importe datos al objeto Table desde el DataTable creado anteriormente
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
// Obtener la primera fila de la tabla
Aspose.Pdf.Row row1 = tab1.Rows[0];

// Iterar a través de todas las celdas en la primera fila y establecer su color de fondo en azul
foreach (Aspose.Pdf.Cell curCell in row1.Cells)
{
	// Establezca el fondo de todas las celdas en la primera fila de la tabla.
	curCell.BackgroundColor = Color.Blue;
	// Establezca el tipo de fuente para las celdas de la primera fila de la tabla.
	curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
	//Establezca el Color de fuente de todas las celdas en la primera fila de la tabla.
	curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
	// Establezca la alineación del texto para las celdas de la primera fila como Centro.
	curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
	// Iterar a través de todas las celdas en la primera fila y establecer su color de fondo en azul
	foreach (Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
	{
		// Establezca el color de fondo de todas las celdas excepto de la primera fila.
		curCell.BackgroundColor = Color.Gray;
		// Establezca el color del texto de todas las celdas excepto la primera fila.
		curCell.DefaultCellTextState.ForegroundColor = Color.White;
	}
}

// Guardar el PDF
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

## Conclusión
En este tutorial, aprendimos cómo exportar datos de una hoja de cálculo de Excel a una tabla PDF utilizando la biblioteca Aspose.PDF para .NET. Cubrimos el proceso paso a paso de cargar la hoja de cálculo de Excel, crear un documento PDF, agregar una tabla, importar datos y formatear la tabla. Ahora puede generar archivos PDF con tablas que contienen datos de Excel mediante programación.