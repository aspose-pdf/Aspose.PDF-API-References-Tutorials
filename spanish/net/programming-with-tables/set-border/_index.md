---
title: Establecer borde
linktitle: Establecer borde
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a establecer un borde en una tabla PDF con Aspose.PDF para .NET.
type: docs
weight: 200
url: /es/net/programming-with-tables/set-border/
---

En este tutorial, lo guiaremos paso a paso para establecer un borde en una tabla de un documento PDF utilizando Aspose.PDF para .NET. Explicaremos el código fuente de C# provisto y le mostraremos cómo implementarlo.

## Paso 1: Crear una instancia del objeto Documento
Primero, crearemos una instancia de un objeto Documento:

```csharp
Document doc = new Document();
```

## Paso 2: agregar una página al documento PDF
A continuación, agregaremos una página al documento PDF:

```csharp
Page page = doc.Pages.Add();
```

## Paso 3: Crear el objeto BorderInfo
Ahora crearemos un objeto BorderInfo para definir el borde de la tabla:

```csharp
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
```

## Paso 4: especificar los bordes superior e inferior
Especificaremos que los bordes superior e inferior serán dobles:

```csharp
border.Top.IsDoubled = true;
border.Bottom.IsDoubled = true;
```

## Paso 5: Crear una instancia del objeto Table
Ahora vamos a crear una instancia de un objeto Tabla:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## Paso 6: Especificar anchos de columna
Especificaremos los anchos de las columnas de la tabla:

```csharp
table. ColumnWidths = "100";
```

## Paso 7: crear el objeto de fila
Crearemos un objeto Fila:

```csharp
Aspose.Pdf.Row row = table.Rows.Add();
```

## Paso 8: agregar una celda a la fila
A continuación, agregaremos una celda a la fila:

```csharp
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
```

## Paso 9: Establecer el borde de la celda
Vamos a definir el borde de la celda (borde doble):

```csharp
cell. Border = border;
```

## Paso 10: agregar la tabla a la página
Ahora agreguemos la tabla a la página del documento:

```csharp
page.Paragraphs.Add(table);
```

## Paso 11: Guardar documento PDF
Finalmente, guardaremos el documento PDF:

```csharp
dataDir = dataDir + "TableBorderTest_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nBorder setup successfully.\nFile saved at " + dataDir);
```

### Ejemplo de código fuente para Establecer borde usando Aspose.PDF para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instanciar objeto de documento
Document doc = new Document();
// Agregar página al documento PDF
Page page = doc.Pages.Add();
// Crear objeto BorderInfo
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
// Especifique que el borde superior será doble
border.Top.IsDoubled = true;
// Especificar que el borde inferior será doble
border.Bottom.IsDoubled = true;
// Instanciar objeto de tabla
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Especificar información de ancho de columnas
table.ColumnWidths = "100";
// Crear objeto Fila
Aspose.Pdf.Row row = table.Rows.Add();
// Agregue una celda de tabla a la colección de celdas de la fila
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
// Establecer el borde para el objeto de celda (doble borde)
cell.Border = border;
// Agregar tabla a la colección de párrafos de la página
page.Paragraphs.Add(table);
dataDir = dataDir + "TableBorderTest_out.pdf";
// Guardar el documento PDF
doc.Save(dataDir);

Console.WriteLine("\nBorder setup successfully.\nFile saved at " + dataDir);
```

## Conclusión
¡Felicidades! Ahora ha aprendido cómo establecer un borde en una tabla de un documento PDF usando Aspose.PDF para .NET. Esta guía paso a paso le mostró cómo crear un documento, agregar una página, configurar el borde de la tabla y guardar el documento PDF. Ahora puedes aplicar este conocimiento a tus propios proyectos.