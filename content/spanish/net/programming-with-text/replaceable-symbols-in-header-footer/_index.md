---
title: Símbolos reemplazables en el encabezado y pie de página
linktitle: Símbolos reemplazables en el encabezado y pie de página
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a utilizar símbolos reemplazables en el encabezado y pie de página de un documento PDF utilizando Aspose.PDF para .NET.
type: docs
weight: 320
url: /es/net/programming-with-text/replaceable-symbols-in-header-footer/
---
En este tutorial, explicaremos cómo usar símbolos reemplazables en el encabezado y pie de página de un documento PDF mediante la biblioteca Aspose.PDF para .NET. Repasaremos el proceso paso a paso de creación de un PDF, configuración de márgenes, adición de encabezado y pie de página con símbolos reemplazables y guardado del PDF utilizando el código fuente C# proporcionado.

## Prerrequisitos

Antes de comenzar, asegúrese de tener lo siguiente:

- La biblioteca Aspose.PDF para .NET instalada.
- Un conocimiento básico de programación en C#.

## Paso 1: Configurar el directorio de documentos

 Primero, debes establecer la ruta al directorio donde deseas guardar el archivo PDF generado. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el`dataDir` variable con la ruta al directorio deseado.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Crear un documento y una página PDF

 A continuación, creamos un nuevo documento PDF y le agregamos una página usando el`Document` clase y`Page` clase de la biblioteca Aspose.PDF.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Paso 3: Establecer márgenes

 Establecemos los márgenes de la página utilizando el`MarginInfo` Clase. Ajuste los valores de margen según sus requisitos.

```csharp
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
page.PageInfo.Margin = marginInfo;
```

## Paso 4: Agregar encabezado con símbolos reemplazables

 Creamos una`HeaderFooter` objeto para la página y agregar un`TextFragment` con símbolos reemplazables.

```csharp
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;

TextFragment t1 = new TextFragment("report title");
// Establezca las propiedades del texto si lo desea
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t1.TextState.LineSpacing = 5f;

hfFirst.Paragraphs.Add(t1);

// Agregue más fragmentos de texto o personalícelos según sea necesario
```

## Paso 5: Agregar pie de página con símbolos reemplazables

 De manera similar, creamos una`HeaderFooter` objeto para el pie de página y agregar`TextFragment` objetos con símbolos reemplazables.

```csharp
HeaderFooter hfFoot = new HeaderFooter();
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;

TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");

// Agregue más fragmentos de texto o personalícelos según sea necesario

hfFoot.Paragraphs.Add(tab2);
```

## Paso 6: Guarde el documento PDF

Finalmente, guardamos el documento PDF en el archivo de salida especificado.

```csharp
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols replaced successfully in the header and footer.\nFile saved at " + dataDir);
```

### Código fuente de muestra para símbolos reemplazables en encabezado y pie de página utilizando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
//Asignar la instancia marginInfo a la propiedad Margin de sec1.PageInfo
page.PageInfo.Margin = marginInfo;
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;
// Cree una instancia de un párrafo de texto que almacenará el contenido que se mostrará como encabezado
TextFragment t1 = new TextFragment("report title");
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t1.TextState.LineSpacing = 5f;
hfFirst.Paragraphs.Add(t1);
TextFragment t2 = new TextFragment("Report_Name");
t2.TextState.Font = FontRepository.FindFont("Arial");
t2.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t2.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t2.TextState.LineSpacing = 5f;
t2.TextState.FontSize = 12;
hfFirst.Paragraphs.Add(t2);
// Crea un objeto HeaderFooter para la sección
HeaderFooter hfFoot = new HeaderFooter();
// Establezca el objeto HeaderFooter en pie de página par e impar
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;
// Agregar un párrafo de texto que contenga el número de página actual o el número total de páginas
TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");
// Crear una instancia de un objeto de tabla
Table tab2 = new Table();
// Añade la tabla en la colección de párrafos de la sección deseada
hfFoot.Paragraphs.Add(tab2);
// Conjunto con anchos de columnas de la tabla
tab2.ColumnWidths = "165 172 165";
//Crea filas en la tabla y luego celdas en las filas.
Row row3 = tab2.Rows.Add();
row3.Cells.Add();
row3.Cells.Add();
row3.Cells.Add();
// Establezca la alineación vertical del texto como centrada
row3.Cells[0].Alignment = Aspose.Pdf.HorizontalAlignment.Left;
row3.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
row3.Cells[2].Alignment = Aspose.Pdf.HorizontalAlignment.Right;
row3.Cells[0].Paragraphs.Add(t3);
row3.Cells[1].Paragraphs.Add(t4);
row3.Cells[2].Paragraphs.Add(t5);
//Sec1.Paragraphs.Add(New Text("Aspose.Total para Java es una compilación de cada componente Java ofrecido por Aspose. Se compila a diario para garantizar que contenga las versiones más actualizadas de cada uno de nuestros componentes Java. #$NL " + "Usando Aspose.Total para Java, los desarrolladores pueden crear una amplia gama de aplicaciones. #$NL #$NL #$NP" + "Aspose.Total para Java es una compilación de cada componente Java ofrecido por Aspose. Se compila a diario para garantizar que contenga las versiones más actualizadas de cada uno de nuestros componentes Java. #$NL " + "Usando Aspose.Total para Java, los desarrolladores pueden crear una amplia gama de aplicaciones. #$NL #$NL #$NP" + "Aspose.Total para Java es una compilación de cada componente Java ofrecido por Aspose. Se compila a diario para garantizar que contenga las versiones más actualizadas de cada uno de nuestros componentes Java. componentes. #$NL " + "Al usar Aspose.Total, los desarrolladores de Java pueden crear una amplia gama de aplicaciones. #$NL #$NL"))
Table table = new Table();
table.ColumnWidths = "33% 33% 34%";
table.DefaultCellPadding = new MarginInfo();
table.DefaultCellPadding.Top = 10;
table.DefaultCellPadding.Bottom = 10;
// Añade la tabla en la colección de párrafos de la sección deseada
page.Paragraphs.Add(table);
// Establecer el borde de celda predeterminado utilizando el objeto BorderInfo
table.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1f);
// Establecer el borde de la tabla utilizando otro objeto BorderInfo personalizado
table.Border = new BorderInfo(BorderSide.All, 1f);
table.RepeatingRowsCount = 1;
//Crea filas en la tabla y luego celdas en las filas.
Row row1 = table.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");
const string CRLF = "\r\n";
for (int i = 0; i <= 10; i++)
{
	Row row = table.Rows.Add();
	row.IsRowBroken = true;
	for (int c = 0; c <= 2; c++)
	{
		Cell c1;
		if (c == 2)
			c1 = row.Cells.Add("Aspose.Total for Java is a compilation of every Java component offered by Aspose. It is compiled on a" + CRLF + "daily basis to ensure it contains the most up to date versions of each of our Java components. " + CRLF + "daily basis to ensure it contains the most up to date versions of each of our Java components. " + CRLF + "Using Aspose.Total for Java developers can create a wide range of applications.");
		else
			c1 = row.Cells.Add("item1" + c);
		c1.Margin = new MarginInfo();
		c1.Margin.Left = 30;
		c1.Margin.Top = 10;
		c1.Margin.Bottom = 10;
	}
}
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nSymbols replaced successfully in header and footer.\nFile saved at " + dataDir);
```

## Conclusión

En este tutorial, aprendió a usar símbolos reemplazables en el encabezado y pie de página de un documento PDF mediante la biblioteca Aspose.PDF para .NET. Si sigue la guía paso a paso y ejecuta el código C# proporcionado, podrá crear un PDF, establecer márgenes, agregar encabezado y pie de página con símbolos reemplazables y guardar el PDF.

### Preguntas frecuentes

#### P: ¿Cuál es el propósito del tutorial “Símbolos reemplazables en encabezado y pie de página”?

A: El tutorial "Símbolos reemplazables en encabezado y pie de página" tiene como objetivo guiarlo a través del proceso de uso de la biblioteca Aspose.PDF para .NET para agregar símbolos reemplazables al encabezado y pie de página de un documento PDF. Los símbolos reemplazables le permiten reemplazar de manera dinámica marcadores de posición específicos con valores reales al generar el PDF.

#### P: ¿Qué son los símbolos reemplazables en el contexto de un encabezado y pie de página PDF?

R: Los símbolos reemplazables son marcadores de posición que se pueden insertar en el encabezado y pie de página de un documento PDF. Estos símbolos actúan como marcadores de posición dinámicos para valores que se pueden completar en tiempo de ejecución, como números de página, fechas e información personalizada.

#### P: ¿Por qué querría utilizar símbolos reemplazables en un encabezado y pie de página de PDF?

R: Los símbolos reemplazables en el encabezado y pie de página son útiles cuando desea incluir información dinámica en sus documentos PDF, como números de página, fechas u otros datos variables que pueden cambiar cuando se genera el documento.

#### P: ¿Cómo puedo configurar los márgenes de la página PDF?

 A: Puede configurar los márgenes de la página PDF utilizando el`MarginInfo` clase y asignarla a la`Margin` propiedad de la`PageInfo` de la página. Ajuste los valores de los márgenes según sea necesario.

#### P: ¿Cómo puedo agregar símbolos reemplazables al encabezado y pie de página?

 A: Puede agregar símbolos reemplazables creando un`HeaderFooter` objeto para el encabezado y pie de página de la página. Luego, puedes agregar`TextFragment`objetos con el texto deseado, incluidos símbolos reemplazables, a la`Paragraphs` colección de la`HeaderFooter` objeto.

#### P: ¿Puedo personalizar la apariencia de los símbolos reemplazables?

 R: Sí, puede personalizar la apariencia de los símbolos reemplazables modificando las propiedades de los mismos.`TextFragment` objetos que contienen los símbolos. Puede configurar propiedades como fuente, tamaño de fuente, color, alineación y espaciado entre líneas.

#### P: ¿Qué tipo de símbolos reemplazables puedo usar?

R: Puede utilizar una variedad de símbolos reemplazables, como:

- `$p`: Número de página actual.
- `$P`: Número total de páginas.
- `$d`:Fecha actual.
- `$t`:Hora actual.
- Marcadores de posición personalizados que usted define.

#### P: ¿Puedo incluir otro texto y formato alrededor de los símbolos reemplazables?

 R: Sí, puede incluir otro texto y formato alrededor de los símbolos reemplazables dentro del`TextFragment` objetos. Esto le permite crear encabezados y pies de página más complejos que incorporan contenido dinámico y estático.

#### P: ¿Cómo puedo guardar el documento PDF generado?

 A: Para guardar el documento PDF generado, puede utilizar el`Save` método de la`Document`Clase. Proporcione la ruta y el nombre del archivo de salida deseado como argumento.

#### P: ¿Se requiere una licencia Aspose válida para este tutorial?

R: Sí, se necesita una licencia Aspose válida para ejecutar el código correctamente en este tutorial. Puede obtener una licencia completa o una licencia temporal de 30 días en el sitio web de Aspose.