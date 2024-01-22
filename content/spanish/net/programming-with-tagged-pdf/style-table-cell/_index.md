---
title: Celda de tabla de estilo
linktitle: Celda de tabla de estilo
second_title: Aspose.PDF para referencia de API .NET
description: Aprenda a aplicar estilo a las celdas de una tabla con Aspose.PDF para .NET. Guía paso a paso para crear y personalizar tablas.
type: docs
weight: 160
url: /es/net/programming-with-tagged-pdf/style-table-cell/
---
Bienvenido a este tutorial detallado sobre cómo formatear celdas de tablas usando Aspose.PDF para .NET. En esta guía, explicaremos en detalle cada paso del código fuente C# proporcionado para ayudarlo a comprender cómo aplicar estilo a las celdas de una tabla. Asegúrese de haber instalado Aspose.PDF para .NET y configurar su entorno de desarrollo antes de comenzar.

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
taggedContent.SetTitle("Example of table cell formatting");
taggedContent.SetLanguage("fr-FR");
```

Hemos creado un nuevo documento y hemos configurado el título y el idioma del documento.

## Paso 3: Obtención del elemento de estructura raíz

En este paso obtendremos el elemento de estructura raíz de nuestro documento.

```csharp
//Obtener el elemento de estructura raíz.
StructureElement rootElement = taggedContent.RootElement;
```

Obtuvimos el elemento de estructura raíz que servirá como contenedor para los elementos de la matriz.

## Paso 4: crear el elemento de estructura de matriz

Ahora creemos un nuevo elemento de estructura de tabla para nuestro documento.

```csharp
// Crear el elemento de estructura de matriz
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

Hemos creado un nuevo elemento de estructura de matriz y lo agregamos al elemento de estructura raíz. También creamos los elementos de encabezado, cuerpo y pie de página de la tabla.

## Paso 5: agregar encabezados de tabla

En este paso agregaremos los encabezados de la tabla a nuestra tabla.

```csharp
// Número de filas y columnas de la tabla.
int rowCount = 4;
int colCount = 4;

int rowIndex;
int colIndex;

// Crear la fila del encabezado de la tabla
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTHElement theElement = headTrElement.CreateTH();
     theElement.SetText(string.Format("Header {0}", colIndex));
     theElement.BackgroundColor = Color.GreenYellow;
     theElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
     theElement. IsNoBorder = true;
     theElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
     theElement.Alignment = HorizontalAlignment.Right;
}
```

Creamos una fila de encabezado para nuestra tabla y agregamos celdas de encabezado con propiedades de formato como color de fondo, bordes, márgenes y alineación.

## Paso 6: agregar las filas del cuerpo de la tabla

Ahora agreguemos las filas del cuerpo de la tabla a nuestra tabla.
```csharp
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);

     for (colIndex = 0; colIndex < colCount; colIndex++)
     {
         int colSpan = 1;
         int rowSpan = 1;

         if (colIndex == 1 && rowIndex == 1)
         {
             colSpan = 2;
             rowSpan = 2;
         }
         else if (colIndex == 2 && (rowIndex == 1 || rowIndex == 2))
         {
             keep on going;
         }
         else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
         {
             keep on going;
         }

         TableTDElement tdelement = trElement.CreateTD();
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
         tdElement.BackgroundColor = Color.Yellow;
         tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
         tdElement.IsNoBorder = false;
         tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
         tdElement.Alignment = HorizontalAlignment.Center;

         TextState cellTextState = new TextState();
         cellTextState.ForegroundColor = Color.DarkBlue;
         cellTextState.FontSize = 7.5F;
         cellTextState.FontStyle = FontStyles.Bold;
         cellTextState.Font = FontRepository.FindFont("Arial");

         tdElement. DefaultCellTextState = cellTextState;
         tdElement.IsWordWrapped = true;
         tdElement.VerticalAlignment = VerticalAlignment.Center;
         tdElement.ColSpan = colSpan;
         tdElement. RowSpan = rowSpan;
     }
}
```

Agregamos filas al cuerpo de la tabla usando bucles para iterar sobre cada celda de la tabla. Establecemos propiedades de formato para cada celda, como color de fondo, bordes, márgenes, alineación del texto, etc.

## Paso 7: agregar el pie de página

Finalmente, agregaremos el pie de página a nuestra tabla.

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

Creamos un pie de página para nuestra tabla y agregamos celdas de pie de página con texto.



## Paso 8: guardar el documento PDF etiquetado

Ahora que hemos creado nuestro documento con la tabla con estilo, lo guardaremos como un documento PDF etiquetado.

```csharp
// Guarde el documento PDF etiquetado
document.Save(dataDir + "StyleTableCell.pdf");
```

Guardamos el documento PDF etiquetado en el directorio especificado.

## Paso 9: Validación del cumplimiento de PDF/UA

A continuación, validaremos la conformidad PDF/UA de nuestro documento.

```csharp
// Verificación de cumplimiento de PDF/UA
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

Cargamos el documento PDF etiquetado y validamos su conformidad con PDF/UA generando un informe XML.

### Código fuente de muestra para Style Table Cell usando Aspose.PDF para .NET 
```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crear documento
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table cell style");
taggedContent.SetLanguage("en-US");

// Obtener elemento de estructura raíz
StructureElement rootElement = taggedContent.RootElement;

// Crear elemento de estructura de tabla
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 4;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTHElement thElement = headTrElement.CreateTH();
	thElement.SetText(String.Format("Head {0}", colIndex));
	thElement.BackgroundColor = Color.GreenYellow;
	thElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
	thElement.IsNoBorder = true;
	thElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
	thElement.Alignment = HorizontalAlignment.Right;
}
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
	TableTRElement trElement = tableTBodyElement.CreateTR();
	trElement.AlternativeText = String.Format("Row {0}", rowIndex);
	for (colIndex = 0; colIndex < colCount; colIndex++)
	{
		int colSpan = 1;
		int rowSpan = 1;
		if (colIndex == 1 && rowIndex == 1)
		{
			colSpan = 2;
			rowSpan = 2;
		}
		else if (colIndex == 2 && (rowIndex == 1 || rowIndex == 2))
		{
			continue;
		}
		else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
		{
			continue;
		}
		TableTDElement tdElement = trElement.CreateTD();
		tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
		tdElement.BackgroundColor = Color.Yellow;
		tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
		tdElement.IsNoBorder = false;
		tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
		tdElement.Alignment = HorizontalAlignment.Center;
		TextState cellTextState = new TextState();
		cellTextState.ForegroundColor = Color.DarkBlue;
		cellTextState.FontSize = 7.5F;
		cellTextState.FontStyle = FontStyles.Bold;
		cellTextState.Font = FontRepository.FindFont("Arial");
		tdElement.DefaultCellTextState = cellTextState;
		tdElement.IsWordWrapped = true;
		tdElement.VerticalAlignment = VerticalAlignment.Center;
		tdElement.ColSpan = colSpan;
		tdElement.RowSpan = rowSpan;
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
document.Save(dataDir + "StyleTableCell.pdf");

// Comprobación del cumplimiento de PDF/UA
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Conclusión

En este tutorial, aprendimos cómo aplicar estilo a las celdas de una tabla usando Aspose.PDF para .NET. Hemos visto cómo crear un documento, agregar una tabla con encabezados, filas de cuerpo y pie de página, y personalizar estilos de celda. Finalmente, guardamos el documento PDF etiquetado y validamos su conformidad con PDF/UA. Ahora puede utilizar Aspose.PDF para .NET para crear y diseñar tablas en sus aplicaciones .NET.

### Preguntas frecuentes

#### P: ¿Cuál es el propósito de este tutorial sobre cómo formatear celdas de tablas usando Aspose.PDF para .NET?

R: Este tutorial tiene como objetivo proporcionar una guía completa sobre cómo aplicar estilo a las celdas de una tabla en un documento PDF utilizando la biblioteca Aspose.PDF para .NET. Cubre instrucciones paso a paso y ejemplos de código fuente de C# para ayudarle a comprender e implementar el formato de celdas de tablas.

#### P: ¿Cuáles son los requisitos previos para seguir este tutorial?

R: Antes de comenzar, asegúrese de haber instalado Aspose.PDF para .NET y de haber configurado su entorno de desarrollo. Esto incluye configurar su proyecto para que haga referencia a la biblioteca Aspose.PDF.

#### P: ¿Cómo creo un nuevo documento PDF usando Aspose.PDF para .NET?

R: Para crear un nuevo documento PDF, necesita crear una instancia de un`Document` objeto de la biblioteca Aspose.PDF. El código fuente de C# proporcionado demuestra cómo crear un documento y establecer su título e idioma.

#### P: ¿Cuál es el significado del elemento de estructura raíz en un documento PDF?

R: El elemento de estructura raíz sirve como contenedor para otros elementos de estructura, lo que ayuda a organizar y categorizar el contenido del documento PDF. Desempeña un papel crucial en el establecimiento de la estructura lógica del documento.

#### P: ¿Cómo puedo crear un elemento de estructura de tabla y personalizar su apariencia usando Aspose.PDF para .NET?

 R: Puede crear un elemento de estructura de tabla utilizando el`CreateTableElement()` método. El código fuente proporcionado demuestra cómo personalizar la apariencia de la tabla, incluido el encabezado, el cuerpo y el pie de página, estableciendo propiedades como el color de fondo, los bordes, los márgenes y la alineación.

#### P: ¿Puedo agregar varias filas y columnas al cuerpo de la tabla y personalizar su formato?

R: Sí, el tutorial demuestra cómo agregar varias filas y columnas al cuerpo de la tabla mediante bucles. También proporciona ejemplos de personalización del formato de celda, como color de fondo, bordes, alineación del texto, estilo de fuente y más.

#### P: ¿Cuál es el propósito de validar el cumplimiento de PDF/UA y cómo puedo realizar esta validación?

 R: La validación del cumplimiento de PDF/UA garantiza que el documento PDF cumpla con los estándares de accesibilidad, lo que lo hace más accesible para los usuarios con discapacidades. El tutorial muestra cómo validar la conformidad de PDF/UA utilizando el`Validate()` método y generar un informe XML.

#### P: ¿Cómo puedo aplicar estos conceptos a mis propias aplicaciones .NET?

R: Puede utilizar los ejemplos de código fuente de C# proporcionados como guía para implementar el formato de celdas de tablas en sus propias aplicaciones .NET. Personalice el código según sea necesario para adaptarlo a sus requisitos e intégrelo en sus proyectos.

#### P: ¿Existen prácticas recomendadas para diseñar celdas de tablas en documentos PDF?

R: Al diseñar las celdas de una tabla, considere las necesidades de su audiencia, incluidos los requisitos de accesibilidad. Utilice colores contrastantes, fuentes apropiadas y una alineación clara de las celdas para mejorar la legibilidad. Además, valide el cumplimiento de PDF/UA para garantizar que se cumplan los estándares de accesibilidad.

#### P: ¿Qué otras características de Aspose.PDF para .NET puedo explorar para la manipulación de documentos PDF?

R: Aspose.PDF para .NET ofrece una amplia gama de funciones para la manipulación de documentos PDF, incluida la extracción de texto, la inserción de imágenes, la gestión de campos de formulario, las firmas digitales y más. Explore la documentación y los recursos oficiales para conocer funcionalidades adicionales.
