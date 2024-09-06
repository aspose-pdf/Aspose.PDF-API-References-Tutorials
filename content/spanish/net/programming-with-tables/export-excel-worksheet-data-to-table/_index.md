---
title: Exportar datos de una hoja de cálculo de Excel a una tabla
linktitle: Exportar datos de una hoja de cálculo de Excel a una tabla
second_title: Referencia de API de Aspose.PDF para .NET
description: Exportar datos de una hoja de Excel a una tabla PDF usando Aspose.PDF para .NET.
type: docs
weight: 70
url: /es/net/programming-with-tables/export-excel-worksheet-data-to-table/
---
En este tutorial, aprenderemos a exportar datos desde una hoja de cálculo de Excel y a crear una tabla en un documento PDF utilizando la biblioteca Aspose.PDF para .NET. Repasaremos el código fuente paso a paso y explicaremos cada sección en detalle. Al finalizar este tutorial, podrá generar archivos PDF con tablas que contengan datos de hojas de cálculo de Excel. ¡Comencemos!

## Requisitos
Antes de comenzar, asegúrese de tener lo siguiente:

- Conocimientos básicos del lenguaje de programación C#
- Visual Studio instalado en su máquina
- Se agregó la biblioteca Aspose.PDF para .NET a su proyecto

## Paso 1: Configuración del entorno
Para comenzar, cree un nuevo proyecto de C# en Visual Studio. Agregue la referencia a la biblioteca Aspose.PDF para .NET haciendo clic con el botón derecho en su proyecto en el Explorador de soluciones, seleccionando "Administrar paquetes NuGet" y buscando "Aspose.PDF". Instale el paquete y estará listo.

## Paso 2: Cargar la hoja de cálculo de Excel
En el primer paso de nuestro código, definimos la ruta al directorio que contiene el documento de Excel. Reemplace "YOUR DOCUMENT DIRECTORY" con la ruta del directorio real donde se encuentra su archivo de Excel.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
```

Aquí, utilizamos la biblioteca Aspose.Cells para cargar el libro de Excel. Asegúrate de reemplazar "newBook1.xlsx" con el nombre de tu archivo de Excel.

## Paso 3: Acceder a la hoja de trabajo
 A continuación, necesitamos acceder a la primera hoja de cálculo del archivo Excel. Para ello, utilizamos el comando`Worksheets` colección de la`Workbook` objeto.

```csharp
// Acceder a la primera hoja de cálculo del archivo Excel
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
```

 Si su archivo de Excel contiene varias hojas de cálculo, puede cambiar el valor del índice`[0]` para acceder a una hoja de trabajo diferente.

## Paso 4: Exportación de datos a DataTable
 Ahora, exportaremos el contenido de la hoja de cálculo de Excel a una`DataTable` objeto. Especificamos el rango de celdas a exportar utilizando el`ExportDataTable` método.

```csharp
// Exportar el contenido de 7 filas y 2 columnas a partir de la primera celda a DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);
```

En este ejemplo, exportamos todas las filas y columnas desde la primera celda (0, 0) hasta la última celda de la hoja de cálculo. Establezca el rango apropiado según sus requisitos.

## Paso 5: Creación de un documento PDF
Ahora, crearemos un nuevo documento PDF utilizando la biblioteca Aspose.PDF.

```csharp
// Crear una instancia de Documento
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

Esto crea un documento PDF vacío donde podemos agregar contenido.

## Paso 6: Agregar una página y una tabla
Para mostrar los datos en formato de tabla, necesitamos agregar una página y una tabla al documento PDF.

```csharp
// Crear una página en la instancia del documento
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// Crear un objeto de tabla
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Agregue el objeto Tabla en la colección de párrafos de la sección
sec1.Paragraphs.Add(tab1);
```

Aquí, creamos una nueva página y un objeto de tabla. Luego, agregamos la tabla a la colección de párrafos de la página.

## Paso 7: Configuración de las propiedades de la tabla
Antes de importar los datos, necesitamos configurar algunas propiedades de la tabla, como el ancho de las columnas y los bordes de las celdas predeterminados.

```csharp
// Establecer el ancho de las columnas de la tabla
tab1.ColumnWidths = "40 100 100";

// Establecer el borde de celda predeterminado de la tabla utilizando el objeto BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

En este ejemplo, configuramos los anchos de las columnas en 40, 100 y 100 unidades. Ajuste los valores en función de sus datos. También configuramos el borde de celda predeterminado para que se muestren bordes en todos los lados de cada celda.

## Paso 8: Importar datos a la tabla
 Ahora, importaremos los datos del`DataTable` objeto en la tabla usando el`ImportDataTable` método.

```csharp
// Importar datos al objeto Tabla desde la DataTable creada anteriormente
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
```

 Aquí, especificamos el rango de filas y columnas que se importarán. En este ejemplo, importamos todas las filas y columnas de la`dataTable` objeto.

## Paso 9: Dar formato a la tabla
Para mejorar la apariencia de la tabla, podemos aplicar formato a celdas o filas específicas. En este paso, formatearemos la primera fila y las filas alternas de la tabla.

```csharp
// Consigue la primera fila de la tabla.
Aspose.Pdf.Row row1 = tab1.Rows[0];

// Formatear la primera fila
foreach(Aspose.Pdf.Cell curCell in row1.Cells)
{
     // Establecer el color de fondo de las celdas de la primera fila
     curCell.BackgroundColor = Color.Blue;// Establecer la cara de las celdas en la primera fila
     curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
    
     // Establecer el color de fuente de las celdas de la primera fila
     curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
    
     // Establecer la alineación del texto para las celdas de la primera fila
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

Aquí, iteramos a través de las celdas de la primera fila y configuramos el color de fondo, el tipo de fuente, el color de la fuente y la alineación del texto. Luego, iteramos a través de todas las celdas de las filas alternas y configuramos el color de fondo y el color del texto.

## Paso 10: Guardar el documento PDF
Finalmente, guardamos el documento PDF en la ubicación especificada.

```csharp
// Guardar el PDF
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta del directorio y el nombre de archivo deseados para el archivo PDF de salida.

### Código fuente de ejemplo para exportar datos de una hoja de cálculo de Excel a una tabla utilizando Aspose.PDF para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
// Acceder a la primera hoja de cálculo del archivo Excel
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
// Exportar el contenido de 7 filas y 2 columnas a partir de la primera celda a DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);

// Crear una instancia de documento
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
// Crear una página en la instancia del documento
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// Crear un objeto de tabla
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Agregue el objeto Tabla en la colección de párrafos de la sección
sec1.Paragraphs.Add(tab1);

// Establezca el ancho de las columnas de la tabla. Necesitamos especificar el recuento de columnas manualmente.
// Como la hoja de cálculo de Excel actual tiene tres columnas, estamos especificando el mismo recuento.
tab1.ColumnWidths = "40 100 100";

// Establecer el borde de celda predeterminado de la tabla utilizando el objeto BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Importar datos al objeto Tabla desde la DataTable creada anteriormente
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
// Consigue la primera fila de la tabla.
Aspose.Pdf.Row row1 = tab1.Rows[0];

// Recorrer todas las celdas de la primera fila y establecer su color de fondo en azul.
foreach (Aspose.Pdf.Cell curCell in row1.Cells)
{
	// Establece el fondo de todas las celdas de la primera fila de la tabla.
	curCell.BackgroundColor = Color.Blue;
	// Establezca el tipo de fuente para las celdas de la primera fila de la tabla.
	curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
	// Establezca el color de fuente de todas las celdas de la primera fila de la tabla.
	curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
	// Establezca la alineación del texto de las celdas de la primera fila como Centro.
	curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
	// Recorrer todas las celdas de la primera fila y establecer su color de fondo en azul.
	foreach (Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
	{
		// Establezca el color de fondo de todas las celdas excepto las de la primera fila.
		curCell.BackgroundColor = Color.Gray;
		// Establezca el color del texto de todas las celdas excepto la primera fila.
		curCell.DefaultCellTextState.ForegroundColor = Color.White;
	}
}

// Guardar el PDF
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

## Conclusión
En este tutorial, aprendimos a exportar datos de una hoja de cálculo de Excel a una tabla PDF mediante la biblioteca Aspose.PDF para .NET. Cubrimos el proceso paso a paso de cargar la hoja de cálculo de Excel, crear un documento PDF, agregar una tabla, importar datos y formatear la tabla. Ahora puede generar archivos PDF con tablas que contienen datos de Excel mediante programación.

### Preguntas frecuentes

#### P: ¿Cuál es el propósito de exportar datos de una hoja de cálculo de Excel a una tabla PDF?

A: Exportar datos de una hoja de cálculo de Excel a una tabla PDF le permite presentar los datos en un formato estructurado y organizado. Le permite generar archivos PDF con tablas que contienen datos de hojas de cálculo de Excel, lo que facilita compartir y conservar la información en un formato de documento portátil.

#### P: ¿Puedo personalizar la apariencia de la tabla PDF?

R: Sí, puede personalizar la apariencia de la tabla PDF utilizando varias propiedades proporcionadas por Aspose.PDF para .NET. En el código fuente C# proporcionado, puede modificar el ancho de las columnas, los bordes de las celdas, la alineación del texto, el estilo de fuente y más para adaptarlo a sus requisitos específicos.

#### P: ¿Cómo manejo archivos de Excel con múltiples hojas de cálculo?

 A: En el código C# proporcionado, accedimos a la primera hoja de cálculo en el archivo Excel usando el índice`[0]` Si su archivo de Excel contiene varias hojas de cálculo, puede acceder a ellas modificando el valor del índice en consecuencia, como`[1]` para la segunda hoja de trabajo o`[2]` para la tercera hoja de trabajo.

#### P: ¿Puedo aplicar diferentes formatos a filas o celdas específicas en la tabla PDF?

R: Sí, puede aplicar un formato diferente a filas o celdas específicas en la tabla PDF. En el código fuente de C# proporcionado, demostramos cómo formatear la primera fila y las filas alternas de manera diferente cambiando el color de fondo, el estilo de fuente y el color de fuente. Puede aplicar técnicas de formato similares a cualquier fila o celda específica según sea necesario.

#### P: ¿Aspose.PDF para .NET es la única biblioteca que permite exportar datos de Excel a una tabla PDF?

R: Aspose.PDF para .NET es una potente biblioteca para trabajar con documentos PDF en aplicaciones .NET. Si bien puede haber otras bibliotecas disponibles, Aspose.PDF para .NET ofrece una amplia gama de funciones y capacidades para generar, manipular y exportar archivos PDF con tablas a partir de datos de Excel, lo que lo convierte en una opción popular para dichas tareas.