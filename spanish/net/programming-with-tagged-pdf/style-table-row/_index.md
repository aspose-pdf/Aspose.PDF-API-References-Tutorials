---
title: Fila de la tabla de estilo
linktitle: Fila de la tabla de estilo
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a personalizar las filas de la tabla con Aspose.PDF para la guía paso a paso de .NET para diseñar y dar formato a las filas.
type: docs
weight: 180
url: /es/net/programming-with-tagged-pdf/style-table-row/
---
En este tutorial detallado, lo guiaremos a través del código fuente de C# proporcionado paso a paso para formatear la fila de la tabla usando Aspose.PDF para .NET. Siga las instrucciones a continuación para comprender cómo personalizar los estilos y las propiedades de las filas de las tablas.

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
taggedContent.SetTitle("Example of Table Row Formatting");
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

## Paso 5: personalice los estilos y las propiedades de las filas de la tabla

En este paso, personalizaremos los estilos y las propiedades de las filas de la tabla.

```csharp
// Personalice los estilos y las propiedades de las filas de la tabla
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

int rowCount = 7;
int colCount = 3;
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

// Personaliza las filas del cuerpo de la tabla
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);
     trElement.BackgroundColor = Color.LightGoldenrodYellow;
     trElement.Border = new BorderInfo(BorderSide.All, 0.75F, Color.DarkGray);
     trElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.Blue);
     trElement.MinRowHeight = 100.0;
     trElement.FixedRowHeight = 120.0;
     trElement. IsInNewPage = (rowIndex % 3 == 1);
     trElement.IsRowBroken = true;
     TextState cellTextState = new TextState();
     cellTextState.ForegroundColor = Color.Red;
     trElement. DefaultCellTextState = cellTextState;
     trElement. DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
     trElement.VerticalAlignment = VerticalAlignment.Bottom;

     for (colIndex = 0; colIndex < colCount; colIndex++)
     {
         TableTDElement tdelement = trElement.CreateTD();
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
     }
}

// Crear la línea de pie de página de la tabla.
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

Hemos personalizado varios aspectos de la fila de la tabla, como el color de fondo, los bordes, la altura de la fila, la paginación, el estilo de celda predeterminado y más.

## Paso 6: Guardar el documento PDF etiquetado

Ahora que hemos creado nuestro documento con la fila de la tabla con estilo, lo guardaremos como un documento PDF etiquetado.
```csharp
// Guarde el documento PDF etiquetado
document.Save(dataDir + "StyleTableRow.pdf");
```

Guardamos el documento PDF etiquetado en el directorio especificado.

## Paso 7: Validación de cumplimiento de PDF/UA

A continuación, validaremos la conformidad PDF/UA de nuestro documento.

```csharp
// Comprobación de cumplimiento de PDF/UA
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

Subimos el documento PDF etiquetado y validamos su conformidad con PDF/UA generando un informe XML.


### Ejemplo de código fuente para Style Table Row usando Aspose.PDF para .NET 
```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crear documento
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table row style");
taggedContent.SetLanguage("en-US");

// Obtener elemento de estructura raíz
StructureElement rootElement = taggedContent.RootElement;

// Crear elemento de estructura de tabla
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 7;
int colCount = 3;
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
	trElement.BackgroundColor = Color.LightGoldenrodYellow;
	trElement.Border = new BorderInfo(BorderSide.All, 0.75F, Color.DarkGray);
	trElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.Blue);
	trElement.MinRowHeight = 100.0;
	trElement.FixedRowHeight = 120.0;
	trElement.IsInNewPage = (rowIndex % 3 == 1);
	trElement.IsRowBroken = true;
	TextState cellTextState = new TextState();
	cellTextState.ForegroundColor = Color.Red;
	trElement.DefaultCellTextState = cellTextState;
	trElement.DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
	trElement.VerticalAlignment = VerticalAlignment.Bottom;
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
document.Save(dataDir + "StyleTableRow.pdf");

// Comprobación del cumplimiento de PDF/UA
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Conclusión

En este tutorial, aprendimos a formatear filas de tablas con Aspose.PDF para .NET. Personalizamos los estilos y las propiedades de las filas de la tabla, agregamos los encabezados, las filas del cuerpo y el pie de página, guardamos el documento PDF etiquetado y validamos su conformidad con PDF/UA.

### Preguntas frecuentes

#### P: ¿Cuál es el propósito de este tutorial sobre el formato de las filas de la tabla con Aspose.PDF para .NET?

R: El propósito de este tutorial es guiarlo a través del proceso de dar formato a las filas de la tabla en un documento PDF usando Aspose.PDF para .NET. Proporciona instrucciones paso a paso y ejemplos de código fuente de C# para ayudarlo a personalizar los estilos y las propiedades de las filas de las tablas.

#### P: ¿Cuáles son los requisitos previos para seguir este tutorial?

R: Antes de comenzar, asegúrese de haber configurado su entorno de desarrollo para usar Aspose.PDF para .NET. Esto implica instalar la biblioteca Aspose.PDF y configurar su proyecto para hacer referencia a él.

#### P: ¿Cómo puedo crear un nuevo documento PDF y configurar su título e idioma usando Aspose.PDF para .NET?

 R: Para crear un nuevo documento PDF, debe crear un`Document` objeto de la biblioteca Aspose.PDF. El código fuente de C# proporcionado en el tutorial demuestra cómo crear un documento y establecer sus propiedades de título e idioma.

#### P: ¿Cuál es el significado del elemento de estructura raíz en un documento PDF?

R: El elemento de estructura raíz actúa como contenedor de otros elementos de estructura, lo que ayuda a organizar y categorizar el contenido del documento PDF. Desempeña un papel crucial en el establecimiento de la estructura lógica del documento.

#### P: ¿Cómo creo y personalizo un elemento de estructura de tabla para dar formato a las filas de la tabla usando Aspose.PDF para .NET?

R: El tutorial explica cómo crear un elemento de estructura de tabla y personalizar sus propiedades para dar formato a las filas de la tabla. Cubre aspectos como el color de fondo, los bordes, la altura de las filas, la paginación, el estilo de celda predeterminado y más.

#### P: ¿Puedo personalizar los estilos y las propiedades de las celdas individuales dentro de una fila de la tabla?

R: Sí, puede personalizar los estilos y las propiedades de las celdas individuales dentro de una fila de la tabla. El tutorial demuestra cómo establecer propiedades como el color de fondo, los bordes, el color del texto, el relleno y más para las celdas de la tabla dentro de la fila de la tabla formateada.

#### P: ¿Cómo puedo agregar encabezados, filas de cuerpo y un pie de página a la fila de la tabla con formato?

R: El tutorial proporciona ejemplos de cómo crear y agregar encabezados, filas de cuerpo y un pie de página al elemento de estructura de la tabla. Estos elementos se pueden personalizar aún más utilizando las propiedades descritas en el tutorial.

#### P: ¿Qué es el cumplimiento de PDF/UA y cómo puedo validarlo para mi documento PDF etiquetado?

 R: El cumplimiento de PDF/UA garantiza que el documento PDF cumpla con los estándares de accesibilidad, haciéndolo más accesible para usuarios con discapacidades. El tutorial demuestra cómo validar la conformidad PDF/UA usando el`Validate()` método y generar un informe de cumplimiento de XML.

#### P: ¿Cómo puedo incorporar estos conceptos en mis propias aplicaciones .NET?

R: Puede utilizar los ejemplos de código fuente de C# proporcionados como guía para implementar el formato de filas de tablas en sus propias aplicaciones .NET. Modifique y adapte el código para que coincida con sus requisitos e intégrelo en sus proyectos.

#### P: ¿Existen mejores prácticas recomendadas para formatear filas de tablas en documentos PDF?

R: Al dar formato a las filas de la tabla, tenga en cuenta la legibilidad y la accesibilidad del contenido. Asegúrese de que los colores tengan suficiente contraste, use fuentes claras y legibles y mantenga un diseño uniforme. Valide el cumplimiento de PDF/UA para garantizar que se cumplan los estándares de accesibilidad.

#### P: ¿Qué otras funciones de Aspose.PDF para .NET puedo explorar para personalizar documentos PDF?

R: Aspose.PDF para .NET ofrece una amplia gama de funciones para la personalización de documentos PDF, incluida la manipulación de texto, la inserción de imágenes, la gestión de campos de formulario, las firmas digitales, las anotaciones y más. Consulte la documentación y los recursos oficiales para explorar funcionalidades adicionales.