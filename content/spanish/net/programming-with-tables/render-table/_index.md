---
title: Representar tabla en documento PDF
linktitle: Representar tabla en documento PDF
second_title: Aspose.PDF para referencia de API .NET
description: Aprenda cómo mostrar una tabla en un documento PDF usando Aspose.PDF para .NET.
type: docs
weight: 170
url: /es/net/programming-with-tables/render-table/
---
En este tutorial, lo guiaremos paso a paso para mostrar una tabla en un documento PDF usando Aspose.PDF para .NET. Explicaremos el código fuente de C# proporcionado y le mostraremos cómo implementarlo.

## Paso 1: crear el documento
Primero, crearemos un nuevo documento PDF:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Crear un nuevo documento
Document doc = new Document();
```

## Paso 2: Configurar los márgenes y la orientación de la página
A continuación, configuraremos los márgenes de la página y estableceremos la orientación en modo horizontal:

```csharp
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo. Left = 37;
marginInfo. Right = 37;
marginInfo. Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;
```

## Paso 3: crear la tabla y las columnas
Ahora creemos una tabla y establezcamos el ancho de las columnas:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "50 100";
```

## Paso 4: agregue filas y celdas a la tabla
continuación, agregaremos filas y celdas a la tabla usando un bucle:

```csharp
for (int i = 1; i <= 120; i++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row. FixedRowHeight = 15;
     Aspose.Pdf.Cell cell1 = row.Cells.Add();
     cell1.Paragraphs.Add(new TextFragment("Content 1"));
     Aspose.Pdf.Cell cell2 = row.Cells.Add();
     cell2.Paragraphs.Add(new TextFragment("HHHHH"));
}
```

## Paso 5: Agregar la tabla a la página
Ahora agreguemos la tabla a la página del documento:

```csharp
Page curPage = doc.Pages.Add();
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs. Add(table);
```

## Paso 6: Mostrar la tabla en una página nueva
A continuación, crearemos una nueva tabla y estableceremos la propiedad "IsInNewPage" en "true" para mostrar la tabla en una nueva página:

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table. ColumnWidths = "100 100";
for (int i = 1; i <= 10; i++)
{
     Aspose.Pdf.Row row = table1.Rows.Add();
     Aspose.Pdf.Cell cell1 = row.Cells.Add();
     cell1.Paragraphs.Add(new TextFragment("LAAAAAAA"));
     Aspose.Pdf.Cell cell2 = row.Cells.Add();
     cell2.Paragraphs.Add(new TextFragment("LAAGGGGGG"));
}
table1.IsInNewPage = true;
paragraphs. Add(table1);
```

## Paso 7: guardar PDF
Finalmente guardamos el documento PDF:

```csharp
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable displayed successfully on a page.\nFile saved at location: " + dataDir);
```

### Código fuente de ejemplo para Render Table usando Aspose.PDF para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo.Left = 37;
marginInfo.Right = 37;
marginInfo.Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table.ColumnWidths = "50 100";
// Página agregada.
Page curPage = doc.Pages.Add();
for (int i = 1; i <= 120; i++)
{
	Aspose.Pdf.Row row = table.Rows.Add();
	row.FixedRowHeight = 15;
	Aspose.Pdf.Cell cell1 = row.Cells.Add();
	cell1.Paragraphs.Add(new TextFragment("Content 1"));
	Aspose.Pdf.Cell cell2 = row.Cells.Add();
	cell2.Paragraphs.Add(new TextFragment("HHHHH"));
}
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs.Add(table);
/********************************************/
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table.ColumnWidths = "100 100";
for (int i = 1; i <= 10; i++)
{
	Aspose.Pdf.Row row = table1.Rows.Add();
	Aspose.Pdf.Cell cell1 = row.Cells.Add();
	cell1.Paragraphs.Add(new TextFragment("LAAAAAAA"));
	Aspose.Pdf.Cell cell2 = row.Cells.Add();
	cell2.Paragraphs.Add(new TextFragment("LAAGGGGGG"));
}
table1.IsInNewPage = true;
// Quiero mantener la tabla 1 en la página siguiente, por favor...
paragraphs.Add(table1);
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable render successfully on a page.\nFile saved at " + dataDir);
```

## Conclusión
¡Enhorabuena! Ahora ha aprendido cómo mostrar una tabla en un documento PDF usando Aspose.PDF para .NET. Esta guía paso a paso le mostró cómo crear un documento, configurar los márgenes y la orientación de la página, agregar una tabla y mostrar una tabla en una página nueva. Ahora puedes aplicar este conocimiento a tus propios proyectos.

### Preguntas frecuentes sobre la tabla de renderizado en un documento PDF

#### P: ¿Cómo puedo modificar la apariencia de la tabla, como cambiar los colores de las celdas o agregar bordes?

R: Para modificar la apariencia de la tabla, puede configurar varias propiedades de la`Aspose.Pdf.Table` y sus células. Por ejemplo, puede configurar el`BackgroundColor` propiedad de las celdas de cambiar su color de fondo. También puedes configurar el`Border` propiedad de la tabla o celdas individuales para agregar bordes. Además, puede personalizar la fuente, el color del texto y la alineación del contenido de la tabla modificando el`TextState` del`TextFragment` objetos agregados a las celdas.

#### P: ¿Puedo agregar encabezados o pies de página a la tabla?

R: Sí, puede agregar encabezados o pies de página a la tabla creando filas adicionales al principio o al final de la tabla y configurando el contenido apropiado en las celdas. Puede personalizar los encabezados o pies de página independientemente del resto del contenido de la tabla agregando diferentes estilos o contenido a estas filas específicas.

#### P: ¿Cómo puedo controlar la posición de la tabla en la página?

 R: Para controlar la posición de la tabla en la página, puede ajustar el`MarginInfo` del`PageInfo` objeto. El`MarginInfo`le permite configurar los márgenes izquierdo, derecho, superior e inferior de la página, lo que afecta el espacio disponible para la tabla. También puedes utilizar el`PositioningType` propiedad de la`Aspose.Pdf.Table` para controlar su alineación horizontal y vertical dentro del área de contenido de la página.

#### P: ¿Puedo exportar la tabla a diferentes formatos de archivo, como Excel o CSV?

R: Aspose.PDF para .NET está diseñado principalmente para trabajar con documentos PDF. Si bien puede exportar el documento PDF como una imagen o XPS, no admite directamente la exportación de tablas a formatos como Excel o CSV. Para exportar los datos de la tabla a diferentes formatos de archivo, es posible que necesite utilizar bibliotecas o métodos adicionales para convertir el contenido del PDF al formato deseado.

#### P: ¿Cómo puedo agregar hipervínculos a las celdas de la tabla?

 R: Para agregar hipervínculos a las celdas de la tabla, puede usar el`Aspose.Pdf.WebHyperlink` clase para crear un hipervínculo y luego agregarlo como un ancla al`TextFragment`dentro de la celda. Esto le permite asociar una URL o un enlace de destino con un texto o contenido específico dentro de la celda, creando hipervínculos en los que se puede hacer clic.