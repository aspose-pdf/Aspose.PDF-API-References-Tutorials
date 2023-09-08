---
title: Etiquetas HTML dentro de la tabla en un archivo PDF
linktitle: Etiquetas HTML dentro de la tabla en un archivo PDF
second_title: Aspose.PDF para referencia de API .NET
description: Aprenda a utilizar etiquetas HTML dentro de una tabla en un archivo PDF con Aspose.PDF para .NET.
type: docs
weight: 100
url: /es/net/programming-with-tables/html-tags-inside-table/
---
En este tutorial, aprenderemos cómo usar etiquetas HTML dentro de una tabla en un documento PDF usando Aspose.PDF para .NET. Explicaremos el código fuente en C# paso a paso. Al final de este tutorial, sabrá cómo insertar contenido HTML en una tabla en un documento PDF. ¡Empecemos!

## Paso 1: configurar el entorno
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

## Paso 3: crear el documento y la tabla
Creamos un nuevo documento PDF y agregamos una página en este documento. A continuación, inicializamos una instancia de la clase Tabla y configuramos las propiedades de la tabla.

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

## Paso 4: importar datos a la tabla
Importamos los datos del DataTable a la tabla usando el método "ImportDataTable". Especificamos parámetros del método para indicar qué rango de filas y columnas de DataTable deben importarse.

```csharp
tableProvider.ImportDataTable(dt, false, 0, 0, 3, 1, true);
```

## Paso 5: Agregar la tabla al documento
Agregamos la tabla a la página del documento.

```csharp
doc.Pages[1].Paragraphs.Add(tableProvider);
```

## Etapa 6: Guardar el documento
Guardamos el documento PDF con la tabla que contiene el contenido HTML.

```csharp
doc.Save(dataDir + "HTMLInsideTableCell_out.pdf");
```

### Código fuente de ejemplo para etiquetas HTML dentro de la tabla usando Aspose.PDF para .NET

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
// Establecer el color del borde de la mesa como LightGray
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
En este tutorial, aprendimos cómo usar etiquetas HTML dentro de una tabla en un documento PDF usando Aspose.PDF para .NET. Puede utilizar esta guía paso a paso para insertar contenido HTML en celdas de una tabla en un documento PDF usando C#.

### Preguntas frecuentes sobre etiquetas HTML dentro de la tabla en un archivo PDF

#### P: ¿Puedo utilizar otras etiquetas y atributos HTML dentro de las celdas de la tabla?

 R: Sí, puede utilizar varias etiquetas y atributos HTML dentro de las celdas de la tabla, como`<b>`, `<i>`, `<a>`y muchos más. Aspose.PDF para .NET admite una amplia gama de elementos y estilos HTML que puede utilizar para formatear el contenido dentro de las celdas de la tabla.

#### P: ¿Puedo aplicar estilos CSS al contenido HTML dentro de las celdas de la tabla?

R: Sí, puedes aplicar estilos CSS al contenido HTML dentro de las celdas de la tabla. Aspose.PDF para .NET brinda soporte para estilos CSS básicos que se pueden aplicar a los elementos HTML.

#### P: ¿Es posible agregar imágenes junto con contenido HTML dentro de las celdas de la tabla?

 R: Sí, puedes agregar imágenes junto con contenido HTML dentro de las celdas de la tabla. Puedes usar HTML`<img>` etiquetas para incluir imágenes de diversas fuentes, como archivos locales o URL.

#### P: ¿Cómo puedo especificar diferentes anchos de columna para la tabla?

 R: Puede especificar diferentes anchos de columna para la tabla usando el`ColumnWidths` propiedad de la mesa. La propiedad toma una cadena que contiene valores separados por espacios, donde cada valor representa el ancho de una columna en puntos.

#### P: ¿Puedo usar tablas anidadas dentro de una celda con contenido HTML?

R: Sí, puedes usar tablas anidadas dentro de una celda con contenido HTML. Puede crear instancias de tablas separadas y agregarlas como parte del contenido HTML dentro de una celda para lograr el efecto de anidamiento.