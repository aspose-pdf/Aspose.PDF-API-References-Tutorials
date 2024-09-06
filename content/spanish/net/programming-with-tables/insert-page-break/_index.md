---
title: Insertar salto de página en un archivo PDF
linktitle: Insertar salto de página en un archivo PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a insertar un salto de página en un archivo PDF utilizando Aspose.PDF para .NET.
type: docs
weight: 110
url: /es/net/programming-with-tables/insert-page-break/
---
En este tutorial, aprenderemos a insertar un salto de página en un archivo PDF utilizando Aspose.PDF para .NET. Explicaremos el código fuente en C# paso a paso. Al final de este tutorial, sabrá cómo agregar un salto de página después de una cierta cantidad de líneas en una tabla de un documento PDF. ¡Comencemos!

## Paso 1: Configuración del entorno
Asegúrese de haber configurado su entorno de desarrollo de C# con Aspose.PDF para .NET. Agregue la referencia a la biblioteca e importe los espacios de nombres necesarios.

## Paso 2: Creación del documento y la tabla
Creamos una nueva instancia de Documento y añadimos una página a este documento. A continuación, creamos una instancia de Tabla para representar nuestra tabla en el documento PDF. También definimos los estilos de borde para la tabla.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab. ColumnWidths = "100 100";
```

## Paso 3: Agregar filas a la tabla
Usamos un bucle para agregar 200 filas a la matriz. Para cada fila, creamos una instancia de Row y agregamos dos celdas con contenido de texto.

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
    
     // Cuando se agregan 10 líneas, insertamos un nuevo salto de página.
     if (counter % 10 == 0 && counter != 0)
         row. IsInNewPage = true;
}
```

## Paso 4: Agregar la tabla al documento
Añadimos la tabla a la colección de párrafos de la página del documento.

```csharp
doc.Pages[1].Paragraphs.Add(tab);
```

## Paso 5: Guardar el documento
Guardamos el documento PDF con el salto de página insertado.

```csharp
doc.Save(dataDir + "InsertPageBreak_out.pdf");
```

### Código fuente de ejemplo para insertar un salto de página con Aspose.PDF para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crear una instancia de documento
Document doc = new Document();
// Agregar página a la colección de páginas del archivo PDF
doc.Pages.Add();
// Crear una instancia de tabla
Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
// Establecer el estilo del borde de la tabla
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// Establecer el estilo de borde predeterminado para la tabla con color de borde rojo
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// Especificar el ancho de la columna de la tabla
tab.ColumnWidths = "100 100";
// Crea un bucle para agregar 200 filas a la tabla
for (int counter = 0; counter <= 200; counter++)
{
	Aspose.Pdf.Row row = new Aspose.Pdf.Row();
	tab.Rows.Add(row);
	Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
	cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
	row.Cells.Add(cell1); Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
	cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
	row.Cells.Add(cell2);
	// Cuando se agregan 10 filas, se representa la nueva fila en una nueva página
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
En este tutorial, aprendimos a insertar un salto de página en un documento PDF con Aspose.PDF para .NET. Puede utilizar esta guía paso a paso para agregar un salto de página después de una determinada cantidad de líneas en una tabla de un documento PDF con C#.

### Preguntas frecuentes sobre cómo insertar un salto de página en un archivo PDF

#### P: ¿Cómo puedo cambiar el tamaño de la página de las nuevas páginas creadas después del salto de página?

 A: Para cambiar el tamaño de página de las nuevas páginas creadas después del salto de página, puede configurar el`PageSize` propiedad de la`Page` objeto. Por ejemplo, puede utilizar el siguiente código para establecer el tamaño de página en A4:

```csharp
// Establezca el tamaño de la página en A4
doc.Pages[1].SetPageSize(PageSize.A4);
```

#### P: ¿Puedo controlar los márgenes de las páginas nuevas después del salto de página?

 A: Sí, puedes controlar los márgenes de las páginas nuevas después del salto de página. Utiliza el`Margin` propiedad de la`Page` Objeto para establecer los márgenes de la página. Por ejemplo, para establecer todos los márgenes en 10 puntos, puede utilizar el siguiente código:

```csharp
// Establezca todos los márgenes en 10 puntos
doc.Pages[1].Margin = new MarginInfo(10, 10, 10, 10);
```

#### P: ¿Es posible agregar encabezados y pies de página a las nuevas páginas después del salto de página?

 R: Sí, puede agregar encabezados y pies de página a las páginas nuevas después del salto de página. Utilice el botón`Page.Header` y`Page.Footer` Propiedades para agregar contenido a las secciones de encabezado y pie de página de la página. Por ejemplo:

```csharp
// Añadir encabezado a las nuevas páginas
doc.Pages[1].Header = new HeaderFooter()
{
    Margin = new MarginInfo(10, 10, 10, 10),
    Paragraphs = { new TextFragment("Header content") }
};

// Añadir pie de página a las nuevas páginas
doc.Pages[1].Footer = new HeaderFooter()
{
    Margin = new MarginInfo(10, 10, 10, 10),
    Paragraphs = { new TextFragment("Footer content") }
};
```

#### P: ¿Puedo insertar saltos de página en ubicaciones específicas que no sean después de un cierto número de filas?

 R: Sí, puedes insertar saltos de página en lugares específicos, además de después de un número determinado de filas. Puedes configurar el`IsInNewPage` propiedad de una fila a`true` para forzar la tabla a comenzar una nueva página después de esa fila.

#### P: ¿Cómo puedo ajustar el comportamiento del salto de página en función de la altura del contenido?

 A: Puedes utilizar el`IsBroken` propiedad de la tabla para habilitar o deshabilitar la división automática de filas en las distintas páginas. Cuando se establece en`true`, permite que las filas se dividan en las páginas según la altura del contenido.