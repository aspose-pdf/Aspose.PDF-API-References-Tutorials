---
title: Integrar con base de datos en archivo PDF
linktitle: Integrar con base de datos en archivo PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Incruste datos de una base de datos en un archivo PDF utilizando Aspose.PDF para .NET.
type: docs
weight: 120
url: /es/net/programming-with-tables/integrate-with-database/
---
En este tutorial, aprenderemos a incrustar datos de una base de datos en un archivo PDF utilizando Aspose.PDF para .NET. Explicaremos el código fuente en C# paso a paso. Al final de este tutorial, sabrá cómo importar datos de tablas desde una base de datos a un documento PDF. ¡Empecemos!

## Paso 1: Configuración del entorno
Asegúrese de haber configurado su entorno de desarrollo C# con Aspose.PDF para .NET. Agregue la referencia a la biblioteca e importe los espacios de nombres necesarios.

## Paso 2: crear la tabla de datos
Creamos una instancia de DataTable para representar los datos que queremos incrustar en el documento PDF. En este ejemplo, creamos un DataTable con tres columnas: Employee_ID, Employee_Name y Gender. También agregamos dos filas a DataTable con datos ficticios.

```csharp
DataTable dt = new DataTable("Employee");
dt.Columns.Add("Employee_ID", typeof(Int32));
dt.Columns.Add("Employee_Name", typeof(string));
dt.Columns.Add("Gender", typeof(string));

DataRow dr = dt.NewRow();
dr[0] = 1;
dr[1] = "John Smith";
dr[2] = "Male";
dt.Rows.Add(dr);

dr = dt. NewRow();
dr[0] = 2;
dr[1] = "Mary Miller";
dr[2] = "Female";
dt.Rows.Add(dr);
```

## Paso 3: Crear el documento PDF y la tabla
Creamos una instancia de Documento y agregamos una página a este documento. A continuación, creamos una instancia de Table para representar nuestra tabla en el documento PDF. Definimos anchos de columna de tabla y estilos de borde.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "40 100 100 100";
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## Paso 4: Importación de datos de DataTable a la tabla
Usamos el método ImportDataTable para importar los datos de DataTable a la tabla en el documento PDF.

```csharp
table.ImportDataTable(dt, true, 0, 1, 3, 3);
```

## Paso 5: agregar la tabla al documento
Agregamos la tabla a la colección de párrafos de la página del documento.

```csharp
doc.Pages[1].Paragraphs.Add(table);
```

## Paso 6: Guarde el documento
Guardamos el documento PDF con los datos de la base de datos incrustada.

```csharp
doc.Save(dataDir + "DataIntegrated_out.pdf");
```

¡Felicidades! Ahora sabe cómo incrustar datos de bases de datos en un documento PDF utilizando Aspose.PDF para .NET.

### Código fuente de ejemplo para Integrar con base de datos usando Aspose.PDF para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

DataTable dt = new DataTable("Employee");
dt.Columns.Add("Employee_ID", typeof(Int32));
dt.Columns.Add("Employee_Name", typeof(string));
dt.Columns.Add("Gender", typeof(string));
// Agregue 2 filas en el objeto DataTable mediante programación
DataRow dr = dt.NewRow();
dr[0] = 1;
dr[1] = "John Smith";
dr[2] = "Male";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = 2;
dr[1] = "Mary Miller";
dr[2] = "Female";
dt.Rows.Add(dr);
// Crear instancia de documento
Document doc = new Document();
doc.Pages.Add();
// Inicializa una nueva instancia de la tabla.
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Establecer anchos de columna de la tabla
table.ColumnWidths = "40 100 100 100";
// Establezca el color del borde de la tabla como LightGray
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Establecer el borde de las celdas de la tabla
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.ImportDataTable(dt, true, 0, 1, 3, 3);

// Agregar objeto de tabla a la primera página del documento de entrada
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "DataIntegrated_out.pdf";
// Guardar documento actualizado que contiene objeto de tabla
doc.Save(dataDir);

Console.WriteLine("\nDatabase integrated successfully.\nFile saved at " + dataDir);
```

## Conclusión
En este tutorial, aprendimos a incrustar datos de una base de datos en un documento PDF usando Aspose.PDF para .NET. Puede usar esta guía paso a paso para importar los datos de su propia base de datos y mostrarlos en documentos PDF. Explore más la documentación de Aspose.PDF para descubrir otras características y posibilidades que ofrece esta poderosa biblioteca.

### Preguntas frecuentes sobre la integración con la base de datos en un archivo PDF

#### P: ¿Puedo usar Aspose.PDF para .NET con diferentes tipos de bases de datos como MySQL, SQL Server u Oracle?

R: Sí, puede usar Aspose.PDF para .NET con diferentes tipos de bases de datos como MySQL, SQL Server, Oracle y otras. Aspose.PDF para .NET proporciona funcionalidades para leer datos de varias fuentes de datos, incluidas bases de datos, archivos XML y más. Puede recuperar datos del tipo de base de datos que desee y llenarlos en una tabla de datos o en cualquier otra estructura de datos compatible con Aspose.PDF para .NET.

#### P: ¿Cómo puedo personalizar la apariencia de la tabla en el documento PDF?

R: Puede personalizar la apariencia de la tabla en el documento PDF usando varias propiedades proporcionadas por la biblioteca Aspose.PDF para .NET. Por ejemplo, puede establecer diferentes estilos de borde, colores de fondo, estilos de fuente y alineación para la tabla y sus celdas. Consulte la documentación de Aspose.PDF para .NET para obtener más detalles sobre cómo personalizar la apariencia de la tabla.

#### P: ¿Es posible agregar hipervínculos o elementos interactivos a los datos importados de la base de datos?

R: Sí, puede agregar hipervínculos u otros elementos interactivos a los datos importados de la base de datos. Aspose.PDF para .NET admite la adición de hipervínculos, marcadores y otros elementos interactivos al documento PDF. Puede manipular el contenido de DataTable antes de importarlo a la tabla e incluir hipervínculos u otras funciones interactivas.

#### P: ¿Puedo paginar la tabla si excede un cierto número de filas?

 R: Sí, puede paginar la tabla si supera un determinado número de filas. Para lograr esto, puede utilizar el`IsInNewPage`propiedad del objeto Row para indicar que una nueva página debe comenzar después de una fila específica. Puede calcular el número de filas que se mostrarán por página y establecer el`IsInNewPage` propiedad en consecuencia.

#### P: ¿Cómo puedo exportar el documento PDF con datos de la base de datos incrustados a diferentes formatos de archivo como DOCX o XLSX?

R: Aspose.PDF para .NET le permite convertir documentos PDF a otros formatos de archivo, incluidos DOCX (Microsoft Word) y XLSX (Microsoft Excel). Puede usar la biblioteca Aspose.PDF para .NET en combinación con otras bibliotecas de Aspose, como Aspose.Words y Aspose.Cells, para lograrlo. Primero, guarde el documento PDF con los datos de la base de datos incrustada y luego use la biblioteca Aspose respectiva para convertirlo al formato de archivo deseado.