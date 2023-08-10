---
title: Insertar salto de página en archivo PDF
linktitle: Insertar salto de página en archivo PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a insertar un salto de página en un archivo PDF usando Aspose.PDF para .NET.
type: docs
weight: 110
url: /es/net/programming-with-tables/insert-page-break/
---
En este tutorial, aprenderemos cómo insertar un salto de página en un archivo PDF usando Aspose.PDF para .NET. Explicaremos el código fuente en C# paso a paso. Al final de este tutorial, sabrá cómo agregar un salto de página después de un cierto número de líneas en una tabla de un documento PDF. ¡Empecemos!

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

### Ejemplo de código fuente para Insertar salto de página usando Aspose.PDF para .NET

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

### Preguntas frecuentes sobre insertar salto de página en un archivo PDF

#### P: ¿Cómo puedo cambiar el tamaño de página para las nuevas páginas creadas después del salto de página?

 R: Para cambiar el tamaño de página de las nuevas páginas creadas después del salto de página, puede configurar el`PageSize` propiedad de la`Page` objeto. Por ejemplo, puede usar el siguiente código para establecer el tamaño de página en A4:

```csharp
// Establezca el tamaño de la página en A4
doc.Pages[1].SetPageSize(PageSize.A4);
```

#### P: ¿Puedo controlar los márgenes de las páginas nuevas después del salto de página?

 R: Sí, puede controlar los márgenes de página para las páginas nuevas después del salto de página. Utilizar el`Margin` propiedad de la`Page` objeto para establecer los márgenes de la página. Por ejemplo, para establecer todos los márgenes en 10 puntos, puede usar el siguiente código:

```csharp
// Establecer todos los márgenes a 10 puntos
doc.Pages[1].Margin = new MarginInfo(10, 10, 10, 10);
```

#### P: ¿Es posible agregar encabezados y pies de página a las nuevas páginas después del salto de página?

 R: Sí, puede agregar encabezados y pies de página a las nuevas páginas después del salto de página. Utilizar el`Page.Header` y`Page.Footer` properties para agregar contenido a las secciones de encabezado y pie de página de la página. Por ejemplo:

```csharp
// Agregar encabezado a las nuevas páginas
doc.Pages[1].Header = new HeaderFooter()
{
    Margin = new MarginInfo(10, 10, 10, 10),
    Paragraphs = { new TextFragment("Header content") }
};

// Agregar pie de página a las nuevas páginas
doc.Pages[1].Footer = new HeaderFooter()
{
    Margin = new MarginInfo(10, 10, 10, 10),
    Paragraphs = { new TextFragment("Footer content") }
};
```

#### P: ¿Puedo insertar saltos de página en ubicaciones específicas que no sean después de un cierto número de filas?

 R: Sí, puede insertar saltos de página en ubicaciones específicas que no sean después de un cierto número de filas. Puede configurar el`IsInNewPage` propiedad de una fila para`true` para obligar a la tabla a comenzar una nueva página después de esa fila.

#### P: ¿Cómo puedo ajustar el comportamiento del salto de página según la altura del contenido?

R: Puede utilizar el`IsBroken` propiedad de la tabla para habilitar o deshabilitar el salto automático de filas entre páginas. cuando se establece en`true`, permite que las filas se dividan en páginas según la altura del contenido.