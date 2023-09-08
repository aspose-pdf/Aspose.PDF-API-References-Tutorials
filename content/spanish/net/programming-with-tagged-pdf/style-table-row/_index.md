---
title: Fila de tabla de estilo
linktitle: Fila de tabla de estilo
second_title: Aspose.PDF para referencia de API .NET
description: Aprenda a personalizar las filas de una tabla con Aspose.PDF para .NET, guía paso a paso para diseñar y formatear filas.
type: docs
weight: 180
url: /es/net/programming-with-tagged-pdf/style-table-row/
---
En este tutorial detallado, lo guiaremos paso a paso a través del código fuente de C# proporcionado para formatear la fila de la tabla usando Aspose.PDF para .NET. Siga las instrucciones a continuación para comprender cómo personalizar los estilos y propiedades de las filas de la tabla.

## Paso 1: configurar el entorno

Antes de comenzar, asegúrese de haber configurado su entorno de desarrollo para usar Aspose.PDF para .NET. Esto incluye instalar la biblioteca Aspose.PDF y configurar su proyecto para hacer referencia a ella.

## Paso 2: crear un documento

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

Hemos creado un nuevo documento y hemos configurado el título y el idioma del documento.

## Paso 3: Obtención del elemento de estructura raíz

En este paso obtendremos el elemento de estructura raíz de nuestro documento.

```csharp
//Obtener el elemento de estructura raíz.
StructureElement rootElement = taggedContent.RootElement;
```

Obtuvimos el elemento de estructura raíz que servirá como contenedor para el elemento de matriz.

## Paso 4: crear el elemento de estructura de matriz

Ahora creemos un nuevo elemento de estructura de tabla para nuestro documento.

```csharp
// Crear el elemento de estructura de matriz
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
```

Hemos creado un nuevo elemento de estructura de matriz y lo agregamos al elemento de estructura raíz.

## Paso 5: Personalice los estilos y propiedades de las filas de la tabla

En este paso, personalizaremos los estilos y propiedades de las filas de la tabla.

```csharp
// Personalizar estilos y propiedades de filas de tablas
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

// Personaliza las filas del cuerpo de la tabla.
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

## Paso 7: Validación del cumplimiento de PDF/UA

A continuación, validaremos la conformidad PDF/UA de nuestro documento.

```csharp
// Verificación de cumplimiento de PDF/UA
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

Cargamos el documento PDF etiquetado y validamos su conformidad con PDF/UA generando un informe XML.


### Código fuente de muestra para Style Table Row usando Aspose.PDF para .NET 
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

En este tutorial, aprendimos cómo formatear las filas de una tabla con Aspose.PDF para .NET. Personalizamos los estilos y propiedades de las filas de la tabla, agregamos los encabezados, las filas del cuerpo y el pie de página, guardamos el documento PDF etiquetado y validamos su conformidad con PDF/UA.

### Preguntas frecuentes

#### P: ¿Cuál es el propósito de este tutorial sobre cómo formatear filas de tablas usando Aspose.PDF para .NET?

R: El propósito de este tutorial es guiarlo a través del proceso de formatear filas de una tabla en un documento PDF usando Aspose.PDF para .NET. Proporciona instrucciones paso a paso y ejemplos de código fuente C# para ayudarle a personalizar los estilos y propiedades de las filas de la tabla.

#### P: ¿Cuáles son los requisitos previos para seguir este tutorial?

R: Antes de comenzar, asegúrese de haber configurado su entorno de desarrollo para utilizar Aspose.PDF para .NET. Esto implica instalar la biblioteca Aspose.PDF y configurar su proyecto para hacer referencia a ella.

#### P: ¿Cómo puedo crear un nuevo documento PDF y configurar su título e idioma usando Aspose.PDF para .NET?

 R: Para crear un nuevo documento PDF, necesita crear un`Document` objeto de la biblioteca Aspose.PDF. El código fuente C# proporcionado en el tutorial demuestra cómo crear un documento y establecer su título y sus propiedades de idioma.

#### P: ¿Cuál es el significado del elemento de estructura raíz en un documento PDF?

R: El elemento de estructura raíz actúa como contenedor para otros elementos de estructura, lo que ayuda a organizar y categorizar el contenido del documento PDF. Desempeña un papel crucial en el establecimiento de la estructura lógica del documento.

#### P: ¿Cómo creo y personalizo un elemento de estructura de tabla para formatear filas de tabla usando Aspose.PDF para .NET?

R: El tutorial explica cómo crear un elemento de estructura de tabla y personalizar sus propiedades para dar formato a las filas de la tabla. Cubre aspectos como el color de fondo, los bordes, la altura de la fila, la paginación, el estilo de celda predeterminado y más.

#### P: ¿Puedo personalizar los estilos y propiedades de celdas individuales dentro de una fila de la tabla?

R: Sí, puedes personalizar los estilos y propiedades de celdas individuales dentro de una fila de la tabla. El tutorial muestra cómo configurar propiedades como color de fondo, bordes, color de texto, relleno y más para las celdas de la tabla dentro de la fila de la tabla formateada.

#### P: ¿Cómo puedo agregar encabezados, filas del cuerpo y un pie de página a la fila de la tabla formateada?

R: El tutorial proporciona ejemplos de cómo crear y agregar encabezados, filas de cuerpo y un pie de página al elemento de estructura de tabla. Estos elementos se pueden personalizar aún más utilizando las propiedades descritas en el tutorial.

#### P: ¿Qué es el cumplimiento de PDF/UA y cómo puedo validarlo para mi documento PDF etiquetado?

 R: La compatibilidad con PDF/UA garantiza que el documento PDF cumpla con los estándares de accesibilidad, lo que lo hace más accesible para usuarios con discapacidades. El tutorial demuestra cómo validar la conformidad de PDF/UA utilizando el`Validate()` método y generar un informe de cumplimiento XML.

#### P: ¿Cómo puedo incorporar estos conceptos en mis propias aplicaciones .NET?

R: Puede utilizar los ejemplos de código fuente de C# proporcionados como guía para implementar el formato de filas de tablas en sus propias aplicaciones .NET. Modifique y adapte el código para que se ajuste a sus requisitos e intégrelo en sus proyectos.

#### P: ¿Existen prácticas recomendadas para formatear filas de tablas en documentos PDF?

R: Al formatear las filas de la tabla, considere la legibilidad y accesibilidad del contenido. Asegúrese de que los colores tengan suficiente contraste, utilice fuentes claras y legibles y mantenga un diseño coherente. Valide el cumplimiento de PDF/UA para garantizar que se cumplan los estándares de accesibilidad.

#### P: ¿Qué otras características de Aspose.PDF para .NET puedo explorar para personalizar documentos PDF?

R: Aspose.PDF para .NET ofrece una amplia gama de funciones para la personalización de documentos PDF, incluida la manipulación de texto, inserción de imágenes, gestión de campos de formulario, firmas digitales, anotaciones y más. Consulte la documentación y los recursos oficiales para explorar funcionalidades adicionales.