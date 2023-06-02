---
title: Insertar salto de página
linktitle: Insertar salto de página
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a insertar un salto de página en un documento PDF con Aspose.PDF para .NET.
type: docs
weight: 110
url: /es/net/programming-with-tables/insert-page-break/
---

En este tutorial, aprenderemos cómo insertar un salto de página en un documento PDF utilizando Aspose.PDF para .NET. Explicaremos el código fuente en C# paso a paso. Al final de este tutorial, sabrá cómo agregar un salto de página después de un cierto número de líneas en una tabla de un documento PDF. ¡Empecemos!

## Paso 1: Configuración del entorno
Asegúrese de haber configurado su entorno de desarrollo C# con Aspose.PDF para .NET. Agregue la referencia a la biblioteca e importe los espacios de nombres necesarios.

## Paso 2: Creación del documento y la tabla
Creamos una nueva instancia de Documento y agregamos una página a este documento. A continuación, creamos una instancia de Table para representar nuestra tabla en el documento PDF. También definimos los estilos de borde para la tabla.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab. ColumnWidths = "100 100";
```

## Paso 3: agregar filas a la tabla
Usamos un ciclo para agregar 200 filas a la matriz. Para cada fila, creamos una instancia de Fila y agregamos dos celdas con contenido de texto.

```csharp
for (int counter = 0; counter <= 200; counter++)
{
     Aspose.Pdf.Row row = new Aspose.Pdf.Row();
     tab. Rows. Add(row);
    
     Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
     cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
     row. Cells. Add(cell1);
    
     Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
     cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
     row. Cells. Add(cell2);
    
     // Cuando se agregan 10 líneas, insertamos un nuevo salto de página
     if (counter % 10 == 0 && counter != 0)
         row. IsInNewPage = true;
}
```

## Paso 4: agregar la tabla al documento
Agregamos la tabla a la colección de párrafos de la página del documento.

```csharp
doc.Pages[1].Paragraphs.Add(tab);
```

## Paso 5: Guarde el documento
Guardamos el documento PDF con el salto de página insertado.

```csharp
doc.Save(dataDir + "InsertPageBreak_out.pdf");
```

### Ejemplo de código fuente para Insertar salto de página usando Aspose.Words para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instanciar instancia de documento
Document doc = new Document();
// Agregar página a la colección de páginas del archivo PDF
doc.Pages.Add();
// Crear instancia de tabla
Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
// Establecer estilo de borde para la tabla
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// Establezca el estilo de borde predeterminado para la tabla con color de borde como rojo
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// Especificar el ancho de las columnas de la tabla
tab.ColumnWidths = "100 100";
// Crea un bucle para agregar 200 filas para la tabla
for (int counter = 0; counter <= 200; counter++)
{
	Aspose.Pdf.Row row = new Aspose.Pdf.Row();
	tab.Rows.Add(row);
	Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
	cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
	row.Cells.Add(cell1); Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
	cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
	row.Cells.Add(cell2);
	// Cuando se agregan 10 filas, renderiza una nueva fila en una nueva página
	if (counter % 10 == 0 && counter != 0) row.IsInNewPage = true;
}
// Agregar tabla a la colección de párrafos del archivo PDF
doc.Pages[1].Paragraphs.Add(tab);

dataDir = dataDir + "InsertPageBreak_out.pdf";
// Guardar el documento PDF
doc.Save(dataDir);

Console.WriteLine("\nPage break inserted successfully.\nFile saved at " + dataDir);
```

## Conclusión
En este tutorial, aprendimos cómo insertar un salto de página en un documento PDF usando Aspose.PDF para .NET. Puede usar esta guía paso a paso para agregar un salto de página después de un cierto número de líneas en una tabla en un documento PDF usando C#.