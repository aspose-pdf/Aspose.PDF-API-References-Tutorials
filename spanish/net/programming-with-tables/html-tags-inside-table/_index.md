---
title: Etiquetas HTML dentro de la tabla
linktitle: Etiquetas HTML dentro de la tabla
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a usar etiquetas HTML dentro de una tabla en un documento PDF con Aspose.PDF para .NET.
type: docs
weight: 100
url: /es/net/programming-with-tables/html-tags-inside-table/
---

En este tutorial, aprenderemos a usar etiquetas HTML dentro de una tabla en un documento PDF usando Aspose.PDF para .NET. Explicaremos el código fuente en C# paso a paso. Al final de este tutorial, sabrá cómo insertar contenido HTML en una tabla en un documento PDF. ¡Empecemos!

## Paso 1: Configuración del entorno
Asegúrese de haber configurado su entorno de desarrollo C# con Aspose.PDF para .NET. Agregue la referencia a la biblioteca e importe los espacios de nombres necesarios.

## Paso 2: crear datos de tabla
Creamos un DataTable que contiene una columna de "datos" de tipo String. Luego agregamos filas a este DataTable usando contenido HTML.

```csharp
DataTable dt = new DataTable("Employee");
dt.Columns.Add("data", System.Type.GetType("System.String"));

DataRow dr = dt.NewRow();
dr[0] = "<li>Department of Emergency Medicine: 3400 Spruce Street Ground Silverstein Bldg Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt. NewRow();
dr[0] = "<li>Penn Observation Medicine Service: 3400 Spruce Street Ground Floor Donner Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt. NewRow();
dr[0] = "<li>UPHS/Presbyterian - Dept. of Emergency Medicine: 51 N. 39th Street . Philadelphia PA 19104-2640</li>";
dt.Rows.Add(dr);
```

## Paso 3: Creación del documento y la tabla
Creamos un nuevo documento PDF y agregamos una página en este documento. A continuación, inicializamos una instancia de la clase Table y establecemos las propiedades de la tabla.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tableProvider = new Aspose.Pdf.Table();
tableProvider. ColumnWidths = "400 50";
tableProvider.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
tableProvider.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 2.5F;
margin. Left = 2.5F;
margin. Bottom = 1.0F;
tableProvider. DefaultCellPadding = margin;
```

## Paso 4: Importación de datos a la tabla
Importamos los datos de DataTable a la tabla usando el método "ImportDataTable". Especificamos parámetros de método para indicar qué rango de filas y columnas de DataTable se debe importar.

```csharp
tableProvider.ImportDataTable(dt, false, 0, 0, 3, 1, true);
```

## Paso 5: agregar la tabla al documento
Añadimos la tabla a la página del documento.

```csharp
doc.Pages[1].Paragraphs.Add(tableProvider);
```

## Etapa 6: Guardar el documento
Guardamos el documento PDF con la tabla que contiene contenido HTML.

```csharp
doc.Save(dataDir + "HTMLInsideTableCell_out.pdf");
```

### Ejemplo de código fuente para etiquetas HTML dentro de la tabla usando Aspose.PDF para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

DataTable dt = new DataTable("Employee");
dt.Columns.Add("data", System.Type.GetType("System.String"));

DataRow dr = dt.NewRow();
dr[0] = "<li>Department of Emergency Medicine: 3400 Spruce Street Ground Silverstein Bldg Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = "<li>Penn Observation Medicine Service: 3400 Spruce Street Ground Floor Donner Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = "<li>UPHS/Presbyterian - Dept. of Emergency Medicine: 51 N. 39th Street . Philadelphia PA 19104-2640</li>";
dt.Rows.Add(dr);

Document doc = new Document();
doc.Pages.Add();
// Inicializa una nueva instancia de la tabla.
Aspose.Pdf.Table tableProvider = new Aspose.Pdf.Table();
//Establecer anchos de columna de la tabla
tableProvider.ColumnWidths = "400 50 ";
// Establezca el color del borde de la tabla como LightGray
tableProvider.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Establecer el borde de las celdas de la tabla
tableProvider.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 2.5F;
margin.Left = 2.5F;
margin.Bottom = 1.0F;
tableProvider.DefaultCellPadding = margin;

tableProvider.ImportDataTable(dt, false, 0, 0, 3, 1, true);

doc.Pages[1].Paragraphs.Add(tableProvider);
doc.Save(dataDir + "HTMLInsideTableCell_out.pdf");
```

## Conclusión
En este tutorial, aprendimos a usar etiquetas HTML dentro de una tabla en un documento PDF usando Aspose.PDF para .NET. Puede usar esta guía paso a paso para insertar contenido HTML en las celdas de una tabla en un documento PDF usando C#.