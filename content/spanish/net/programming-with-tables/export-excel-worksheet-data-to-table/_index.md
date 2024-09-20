---
title: Exportar datos de una hoja de cálculo de Excel a una tabla
linktitle: Exportar datos de una hoja de cálculo de Excel a una tabla
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a exportar datos de una hoja de cálculo de Excel a una tabla PDF con Aspose.PDF para .NET. Tutorial paso a paso con ejemplos de código, requisitos previos y consejos útiles.
type: docs
weight: 70
url: /es/net/programming-with-tables/export-excel-worksheet-data-to-table/
---
## Introducción

¿Alguna vez ha tenido que exportar datos de una hoja de cálculo de Excel a un archivo PDF, ordenados de forma ordenada en formato de tabla? Imagine tener un montón de datos en Excel, pero necesitar compartirlos como un PDF de aspecto profesional. Puede parecer complicado, ¿verdad? Pero con Aspose.PDF para .NET, puede convertir esta tarea en algo muy sencillo. En este tutorial, le guiaremos a través del proceso de exportación de datos de una hoja de cálculo de Excel a una tabla dentro de un documento PDF utilizando Aspose.PDF para .NET. Le guiaremos paso a paso, desglosando todo para que, incluso si es nuevo en esto, se sienta como un profesional al final.

## Prerrequisitos

Antes de sumergirnos en la codificación, configuremos algunas cosas:

1.  Biblioteca Aspose.PDF para .NET: asegúrese de tener instalada la última versión. Puede[Descárgalo aquí](https://releases.aspose.com/pdf/net/).
2.  Biblioteca Aspose.Cells para .NET: la necesitará para manejar operaciones de Excel. Descárguela desde[aquí](https://releases.aspose.com/cells/net/).
3. Entorno de desarrollo .NET: una herramienta como Visual Studio funcionará perfectamente para codificar.
4. Archivo Excel: Tenga listo un archivo Excel con los datos que desea exportar.

 Si no tiene las bibliotecas Aspose.PDF y Aspose.Cells, puede comenzar con una[prueba gratis](https://releases.aspose.com/).

## Importar paquetes

Para comenzar, asegúrese de haber instalado las bibliotecas Aspose.PDF y Aspose.Cells en su proyecto. Puede instalarlas mediante el Administrador de paquetes NuGet en Visual Studio.

A continuación se explica cómo importar los paquetes necesarios en su código C#:

```csharp
using System.Data;
using System.IO;
using System.Linq;
```

Ahora que se han establecido los requisitos previos, veamos el proceso de exportación de datos de una hoja de Excel a una tabla en un documento PDF.

## Paso 1: Cargue el libro de Excel

Para comenzar, debe cargar el libro de Excel en el programa. En este paso, utilizaremos Aspose.Cells para abrir el archivo de Excel.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Cargar el libro de Excel
Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
```

 Explicación: Aquí, especificamos la ruta del directorio donde se encuentra nuestro archivo de Excel y cargamos el libro de trabajo usando`Aspose.Cells.Workbook` Asegúrese de ajustar`"YOUR DOCUMENT DIRECTORY"` para señalar la ubicación de su archivo.

## Paso 2: Acceda a la primera hoja de trabajo

Después de cargar el libro de trabajo, necesitamos acceder a la primera hoja de trabajo donde están almacenados nuestros datos.

```csharp
// Acceder a la primera hoja de cálculo del archivo Excel
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
```

Explicación: Este paso es sencillo: tomamos la primera hoja de trabajo del libro, que contiene los datos que se van a exportar.

## Paso 3: Exportar datos a DataTable

Ahora, exportemos los datos de la hoja de Excel a un objeto DataTable, que actuará como intermediario para transferir los datos al PDF.

```csharp
// Exportar el contenido de 7 filas y 2 columnas a partir de la primera celda a DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);
```

 Explicación: El`ExportDataTable` El método extrae los datos a partir de la primera celda de la hoja de cálculo y abarca todas las filas y columnas. Estos datos se almacenan en una`DataTable` para uso posterior.

## Paso 4: Crear un nuevo documento PDF

A continuación, necesitamos crear un nuevo documento PDF utilizando Aspose.PDF.

```csharp
// Crear una instancia de Documento
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// Crear una página en la instancia del documento
Aspose.Pdf.Page page = pdfDocument.Pages.Add();
```

 Explicación: Aquí, inicializamos un nuevo`Aspose.Pdf.Document` agregarle una página. Esta página contendrá más adelante la tabla que estamos creando a partir de los datos de Excel.

## Paso 5: Crear un objeto de tabla en PDF

Pasemos a la creación de una tabla dentro del documento PDF.

```csharp
// Crear un objeto de tabla
Aspose.Pdf.Table table = new Aspose.Pdf.Table();

// Añade el objeto Tabla a la colección de párrafos de la página
page.Paragraphs.Add(table);
```

 Explicación: Creamos un`Aspose.Pdf.Table` objeto y agregarlo a la colección de párrafos de la página, lo que garantiza que la tabla se muestre en la página.

## Paso 6: Establezca el ancho y los bordes de las columnas

Las tablas en formato PDF necesitan anchos de columna definidos. También agregaremos bordes para que la tabla sea más legible.

```csharp
// Establecer el ancho de las columnas de la tabla
table.ColumnWidths = "40 100 100";

// Establecer el borde de celda predeterminado
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

 Explicación: Establecemos los anchos de las tres columnas y le damos a todas las celdas un borde predeterminado con un grosor de`0.1F`.

## Paso 7: Importar datos de DataTable a una tabla PDF

Ahora es el momento de importar los datos de DataTable a nuestra tabla PDF.

```csharp
// Importar datos al objeto Tabla desde DataTable
table.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
```

 Explicación: El`ImportDataTable`El método transfiere todos los datos del`DataTable` a la tabla PDF. Esto llena la tabla con los datos de su hoja de Excel.

## Paso 8: Dar estilo a la fila del encabezado

Vamos a darle estilo a la fila de encabezado de la tabla cambiando el color de fondo, la fuente y la alineación.

```csharp
// Obtener la primera fila de la tabla
Aspose.Pdf.Row headerRow = table.Rows[0];

// Establecer el estilo para la fila del encabezado
foreach (Aspose.Pdf.Cell cell in headerRow.Cells)
{
    cell.BackgroundColor = Color.Blue;
    cell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
    cell.DefaultCellTextState.ForegroundColor = Color.Yellow;
    cell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}
```

Explicación: Recorremos todas las celdas de la primera fila (encabezado) y establecemos su color de fondo en azul, el color del texto en amarillo y alineamos el texto al centro.

## Paso 9: Dale estilo a las filas restantes

Para diferenciar el encabezado y el resto de las filas, agreguemos un estilo diferente para las filas restantes.

```csharp
for (int i = 1; i <= dataTable.Rows.Count; i++)
{
    foreach (Aspose.Pdf.Cell cell in table.Rows[i].Cells)
    {
        cell.BackgroundColor = Color.Gray;
        cell.DefaultCellTextState.ForegroundColor = Color.White;
    }
}
```

Explicación: Para todas las filas excepto el encabezado, establecemos un fondo gris y un color de texto blanco.

## Paso 10: Guarde el documento PDF

Por último, guarde el documento PDF con la tabla.

```csharp
// Guardar el PDF
pdfDocument.Save(dataDir + "Exceldata_toPdf_table.pdf");
```

Explicación: Guardamos el PDF en el directorio especificado. ¡Listo! Tus datos de Excel ahora están dentro de una tabla PDF con un formato atractivo.

## Conclusión

¡Y ya está! En tan solo unos pasos, ha exportado datos de una hoja de cálculo de Excel a una tabla dentro de un PDF con Aspose.PDF para .NET. Al dividir el proceso y darle estilo a lo largo del camino, puede personalizar el resultado y asegurarse de que sus datos se vean limpios y profesionales. Así, la próxima vez que alguien le entregue un archivo de Excel y le pida un informe en PDF, sabrá exactamente qué hacer.

## Preguntas frecuentes

### ¿Puedo personalizar más la mesa?
¡Por supuesto! Puedes modificar colores, fuentes, alineación e incluso agregar bordes a celdas específicas.

### ¿Aspose.PDF para .NET es gratuito?
 Ofrece una prueba gratuita, pero para un uso prolongado, necesitará una licencia. Puede[Cómpralo aquí](https://purchase.aspose.com/buy).

### ¿Puedo exportar sólo filas y columnas específicas?
 Sí, puedes modificar los parámetros en el`ExportDataTable` Método para exportar rangos específicos.

### ¿Funciona esto con archivos grandes de Excel?
Sí, Aspose.Cells está diseñado para manejar archivos grandes de Excel de manera eficiente.

### ¿Cómo puedo agregar más páginas al PDF?
 Puedes utilizar`pdfDocument.Pages.Add()` para agregar tantas páginas como necesites.