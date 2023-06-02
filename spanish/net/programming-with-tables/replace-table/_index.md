---
title: Reemplazar tabla
linktitle: Reemplazar tabla
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a reemplazar una tabla en un documento PDF usando Aspose.PDF para .NET.
type: docs
weight: 180
url: /es/net/programming-with-tables/replace-table/
---

En este tutorial, lo guiaremos paso a paso para reemplazar una tabla en un documento PDF usando Aspose.PDF para .NET. Explicaremos el código fuente de C# provisto y le mostraremos cómo implementarlo.

## Paso 1: Cargar el documento PDF existente
Primero, debe cargar el documento PDF existente usando el siguiente código:

```csharp
// Ruta al directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cargue el documento PDF existente
Document pdfDocument = new Document(dataDir + @"Table_input.pdf");
```

## Paso 2: Crear el objeto TableAbsorber para encontrar las tablas
A continuación, crearemos un objeto TableAbsorber para encontrar las tablas en el documento PDF:

```csharp
// Cree un objeto TableAbsorber para encontrar las tablas
TableAbsorber absorber = new TableAbsorber();
```

## Paso 3: Visite la primera página con el absorbedor
Ahora visitaremos la primera página del documento PDF usando el absorbedor:

```csharp
//Visite la primera página con el absorbedor
absorb.Visit(pdfDocument.Pages[1]);
```

## Paso 4: Obtener la primera tabla en la página
Para poder reemplazar la tabla, obtendremos la primera tabla de la página:

```csharp
// Obtenga la primera tabla en la página
AbsorbedTable table = absorb.TableList[0];
```

## Paso 5: Creando una nueva tabla
Ahora crearemos una nueva tabla con las columnas y celdas deseadas:

```csharp
Table newTable = new Table();
newTable.ColumnWidths = "100 100 100";
newTable.DefaultCellBorder = new BorderInfo(BorderSide.All, 1F);

Row row = newTable.Rows.Add();
row. Cells. Add("Col 1");
row. Cells. Add("Col 2");
row. Cells. Add("Col 3");
```

## Paso 6: Reemplazar la mesa existente con la nueva mesa
Ahora reemplazaremos la tabla existente con la nueva tabla en la primera página del documento:

```csharp
// Reemplazar la mesa con la nueva mesa
absorb.Replace(pdfDocument.Pages[1], table, newTable);
```

## Paso 7: Guardar el documento
Finalmente, guardamos el documento PDF modificado:

```csharp
pdfDocument.Save(dataDir + "TableReplaced_out.pdf");
```

### Ejemplo de código fuente para Reemplazar tabla usando Aspose.Words para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Cargar documento PDF existente
Document pdfDocument = new Document(dataDir + @"Table_input.pdf");

// Crear objeto TableAbsorber para encontrar tablas
TableAbsorber absorber = new TableAbsorber();

// Visita la primera página con absorbedor
absorber.Visit(pdfDocument.Pages[1]);

// Obtener la primera mesa en la página
AbsorbedTable table = absorber.TableList[0];

// Crear nueva tabla
Table newTable = new Table();
newTable.ColumnWidths = "100 100 100";
newTable.DefaultCellBorder = new BorderInfo(BorderSide.All, 1F);

Row row = newTable.Rows.Add();
row.Cells.Add("Col 1");
row.Cells.Add("Col 2");
row.Cells.Add("Col 3");

// Reemplace la mesa por una nueva
absorber.Replace(pdfDocument.Pages[1], table, newTable);

// Guardar documento
pdfDocument.Save(dataDir + "TableReplaced_out.pdf");
```

## Conclusión
¡Felicidades! Ahora ha aprendido cómo reemplazar una tabla en un documento PDF usando Aspose.PDF para .NET. Esta guía paso a paso le mostró cómo cargar el documento, encontrar la tabla existente, crear una nueva tabla y reemplazarla. Ahora puedes aplicar este conocimiento a tus propios proyectos.