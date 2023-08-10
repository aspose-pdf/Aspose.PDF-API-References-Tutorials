---
title: Elemento de tabla de estilo
linktitle: Elemento de tabla de estilo
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a formatear el elemento de la tabla con Aspose.PDF para .NET. Guía paso a paso para personalizar estilos y propiedades.
type: docs
weight: 170
url: /es/net/programming-with-tagged-pdf/style-table-element/
---
En este tutorial detallado, lo guiaremos a través del código fuente de C# proporcionado paso a paso para formatear el elemento de la matriz usando Aspose.PDF para .NET. Siga las instrucciones a continuación para comprender cómo personalizar los estilos y las propiedades del elemento de matriz.

## Paso 1: Configuración del entorno

Antes de comenzar, asegúrese de haber configurado su entorno de desarrollo para usar Aspose.PDF para .NET. Esto incluye instalar la biblioteca Aspose.PDF y configurar su proyecto para hacer referencia a él.

## Paso 2: Creación de un documento

En este paso, crearemos un nuevo objeto de documento Aspose.PDF.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Creación de documentos
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example of table formatting");
taggedContent.SetLanguage("fr-FR");
```

Hemos creado un nuevo documento y hemos establecido el título y el idioma del documento.

## Paso 3: Obtención del elemento de estructura raíz

En este paso obtendremos el elemento de estructura raíz de nuestro documento.

```csharp
//Obtener el elemento de estructura raíz
StructureElement rootElement = taggedContent.RootElement;
```

Obtuvimos el elemento de estructura raíz que servirá como contenedor para el elemento de matriz.

## Paso 4: Crear el elemento de estructura de matriz

Ahora vamos a crear un nuevo elemento de estructura de tabla para nuestro documento.

```csharp
// Crear el elemento de estructura de matriz
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
```

Hemos creado un nuevo elemento de estructura de matriz y lo hemos agregado al elemento de estructura raíz.

## Paso 5: Personalización de estilos y propiedades de elementos de matriz

En este paso, personalizaremos los estilos y las propiedades del elemento de matriz.

```csharp
// Personaliza los estilos y las propiedades del elemento de matriz
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement. Alignment = HorizontalAlignment. Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
tableElement. ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement. DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
tableElement. DefaultColumnWidth = "70";
tableElement. IsBroken = false;
tableElement.IsBordersIncluded = true;
tableElement. Left = 0F;
tableElement. Top = 40F;
tableElement.RepeatingColumnsCount = 2;
tableElement.RepeatingRowsCount = 3;

// Personaliza el estilo de las líneas repetidas
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
```

Utilizamos varias propiedades para personalizar el elemento de la tabla, como el color de fondo, los bordes, la alineación, el estilo de celda predeterminado, los márgenes, el ancho de columna, etc.

## Paso 6: Agregar encabezados, cuerpo y pie de página de la tabla

Ahora agreguemos los encabezados, el cuerpo y el pie de página de la tabla al elemento de la tabla.
```csharp
// Agregar encabezados de tabla
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

// Número de filas y columnas en la tabla
int rowCount = 10;
int colCount = 5;
int rowIndex;
int colIndex;

// Crear la fila del encabezado de la tabla
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTHElement theElement = headTrElement.CreateTH();
     theElement.SetText(string.Format("Header {0}", colIndex));
}

//Agregar las filas del cuerpo de la tabla
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);

     for (colIndex = 0; colIndex < colCount; colIndex++)
     {
         TableTDElement tdelement = trElement.CreateTD();
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
     }
}

// Agregar la línea de pie de la tabla
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

Agregamos los encabezados, las filas del cuerpo y la fila del pie de página a la tabla usando los elementos correspondientes.

## Paso 7: Guardar el documento PDF etiquetado

Ahora que hemos creado nuestro documento con el elemento de tabla con estilo, lo guardaremos como un documento PDF etiquetado.

```csharp
// Guarde el documento PDF etiquetado
document.Save(dataDir + "StyleTableElement.pdf");
```

Guardamos el documento PDF etiquetado en el directorio especificado.

## Paso 8: Validación de cumplimiento de PDF/UA

A continuación, validaremos la conformidad PDF/UA de nuestro documento.

```csharp
// Comprobación de cumplimiento de PDF/UA
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

Subimos el documento PDF etiquetado y validamos su conformidad con PDF/UA generando un informe XML.

### Ejemplo de código fuente para el elemento de la tabla de estilos usando Aspose.PDF para .NET 

```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crear documento
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table style");
taggedContent.SetLanguage("en-US");

// Obtener elemento de estructura raíz
StructureElement rootElement = taggedContent.RootElement;

// Crear elemento de estructura de tabla
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement.Alignment = HorizontalAlignment.Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
tableElement.ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement.DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
tableElement.DefaultColumnWidth = "70";
tableElement.IsBroken = false;
tableElement.IsBordersIncluded = true;
tableElement.Left = 0F;
tableElement.Top = 40F;
tableElement.RepeatingColumnsCount = 2;
tableElement.RepeatingRowsCount = 3;
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 10;
int colCount = 5;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTHElement thElement = headTrElement.CreateTH();
	thElement.SetText(String.Format("Head {0}", colIndex));
}
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
	TableTRElement trElement = tableTBodyElement.CreateTR();
	trElement.AlternativeText = String.Format("Row {0}", rowIndex);
	for (colIndex = 0; colIndex < colCount; colIndex++)
	{
		TableTDElement tdElement = trElement.CreateTD();
		tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
	}
}
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTDElement tdElement = footTrElement.CreateTD();
	tdElement.SetText(String.Format("Foot {0}", colIndex));
}

// Guardar documento PDF etiquetado
document.Save(dataDir + "StyleTableElement.pdf");

// Comprobación del cumplimiento de PDF/UA
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Conclusión

En este tutorial, aprendimos cómo formatear el elemento de matriz con Aspose.PDF para .NET. Personalizamos los estilos y las propiedades del elemento de la tabla, agregamos encabezados, filas de cuerpo y un pie de página, guardamos el documento PDF etiquetado y validamos su compatibilidad con PDF/UA.

### Preguntas frecuentes

#### P: ¿Cuál es el propósito de este tutorial sobre cómo formatear el elemento de matriz usando Aspose.PDF para .NET?

R: El objetivo de este tutorial es guiarlo a través del proceso de dar formato al elemento de matriz en un documento PDF utilizando Aspose.PDF para .NET. Proporciona instrucciones paso a paso y ejemplos de código fuente de C# para ayudarlo a personalizar los estilos y las propiedades del elemento de matriz.

#### P: ¿Cuáles son los requisitos previos para seguir este tutorial?

R: Antes de comenzar, asegúrese de haber configurado su entorno de desarrollo para usar Aspose.PDF para .NET. Esto implica instalar la biblioteca Aspose.PDF y configurar su proyecto para hacer referencia a él.

#### P: ¿Cómo puedo crear un nuevo documento PDF y configurar su título e idioma usando Aspose.PDF para .NET?

 R: Para crear un nuevo documento PDF, debe crear un`Document` objeto de la biblioteca Aspose.PDF. El código fuente de C# proporcionado en el tutorial demuestra cómo crear un documento y establecer sus propiedades de título e idioma.

#### P: ¿Cuál es el significado del elemento de estructura raíz en un documento PDF?

R: El elemento de estructura raíz actúa como contenedor de otros elementos de estructura, lo que ayuda a organizar y categorizar el contenido del documento PDF. Desempeña un papel crucial en el establecimiento de la estructura lógica del documento.

#### P: ¿Cómo creo y personalizo un elemento de estructura de matriz usando Aspose.PDF para .NET?

 R: Puede crear un elemento de estructura de matriz usando el`CreateTableElement()` método. El código fuente del tutorial proporciona ejemplos de cómo personalizar varias propiedades del elemento de la tabla, como el color de fondo, los bordes, la alineación, el ancho de columna y más.

#### P: ¿Puedo personalizar los estilos y las propiedades de las celdas de la tabla dentro del elemento de la matriz?

R: Sí, el tutorial cubre cómo personalizar los estilos y las propiedades de todo el elemento de la tabla, incluidos los encabezados, las filas del cuerpo y el pie de página. Sin embargo, no aborda específicamente la personalización de celdas de tablas individuales.

#### P: ¿Cómo puedo agregar encabezados, filas de cuerpo y un pie de página al elemento de la tabla?

R: El tutorial explica cómo crear y agregar encabezados, filas de cuerpo y un pie de página al elemento de la tabla utilizando los métodos apropiados proporcionados por Aspose.PDF para .NET.

#### P: ¿Qué es el cumplimiento de PDF/UA y cómo puedo validarlo para mi documento PDF etiquetado?

 R: El cumplimiento de PDF/UA garantiza que el documento PDF cumpla con los estándares de accesibilidad, haciéndolo más accesible para usuarios con discapacidades. El tutorial demuestra cómo validar la conformidad PDF/UA usando el`Validate()` método y generar un informe de cumplimiento de XML.

#### P: ¿Cómo puedo incorporar estos conceptos en mis propias aplicaciones .NET?

R: Puede utilizar los ejemplos de código fuente de C# proporcionados como guía para implementar el formato de elementos de matriz en sus propias aplicaciones .NET. Modifique y adapte el código para que coincida con sus requisitos e intégrelo en sus proyectos.

#### P: ¿Existen mejores prácticas recomendadas para formatear elementos de matriz en documentos PDF?

R: Al dar formato a los elementos de la matriz (tablas), tenga en cuenta la legibilidad y la accesibilidad del contenido. Use fuentes claras y legibles, colores apropiados y mantenga un diseño consistente. Valide el cumplimiento de PDF/UA para garantizar que se cumplan los estándares de accesibilidad.

#### P: ¿Qué otras funciones de Aspose.PDF para .NET puedo explorar para personalizar documentos PDF?

R: Aspose.PDF para .NET ofrece una variedad de funciones para la personalización de documentos PDF, que incluyen manipulación de texto, inserción de imágenes, administración de campos de formulario, firmas digitales, anotaciones y más. Consulte la documentación y los recursos oficiales para explorar funcionalidades adicionales.