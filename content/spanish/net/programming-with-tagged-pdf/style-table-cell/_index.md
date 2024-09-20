---
title: Celda de tabla de estilos
linktitle: Celda de tabla de estilos
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a aplicar estilo a las celdas de una tabla en un PDF con Aspose.PDF para .NET con este tutorial detallado. Siga las instrucciones para crear y dar formato a hermosas tablas PDF.
type: docs
weight: 160
url: /es/net/programming-with-tagged-pdf/style-table-cell/
---
## Introducción

Crear tablas PDF de aspecto profesional puede ser complicado, pero con Aspose.PDF para .NET, ¡es sorprendentemente sencillo! Ya sea que esté diseñando encabezados, pies de página o celdas de tabla específicas, esta poderosa biblioteca le proporciona todas las herramientas que necesita para crear documentos PDF con un formato atractivo. En este tutorial, le mostraremos cómo diseñar celdas de tabla en un documento PDF con Aspose.PDF para .NET. No se preocupe, lo desglosaremos todo en pasos fáciles de seguir.

## Prerrequisitos

Antes de sumergirse en el código, asegúrese de tener los siguientes requisitos previos:

1. Aspose.PDF para .NET: Descargue e instale la última versión de Aspose.PDF desde[aquí](https://releases.aspose.com/pdf/net/).
2. IDE (como Visual Studio): configure un entorno de desarrollo .NET.
3. Conocimientos básicos de programación en C#: Se requiere un poco de familiaridad con C#.
4.  Licencia de Aspose.PDF: Obtenga una licencia temporal o completa para desbloquear todas las funciones de la biblioteca. Puede obtener una versión de prueba gratuita[aquí](https://purchase.aspose.com/temporary-license/).

## Importar paquetes

Antes de comenzar, asegúrese de importar los espacios de nombres necesarios. Necesitará lo siguiente en su proyecto:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

¡Ahora que todo está configurado, pasemos a la guía paso a paso!

Vamos a crear una tabla en un documento PDF y aplicar estilo a sus celdas. En cada paso se explicará el proceso en detalle.

## Paso 1: Crear un nuevo documento PDF

 El primer paso es crear un nuevo documento PDF. En Aspose.PDF, puede inicializar un nuevo`Document` objeto, que representa su archivo PDF.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crear un nuevo documento PDF
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table cell style");
taggedContent.SetLanguage("en-US");
```

Aquí inicializamos un documento PDF y configuramos su título e idioma. Esto le otorga al documento una estructura adecuada, lo cual es esencial para la compatibilidad con PDF/UA.

## Paso 2: Configurar la estructura de la tabla

Las tablas en archivos PDF se definen dentro de elementos de estructura. Vamos a crear la tabla y definir sus filas y columnas.

```csharp
// Obtener el elemento de estructura raíz
StructureElement rootElement = taggedContent.RootElement;

// Crear un elemento de estructura de tabla
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

Ahora hemos definido la cabecera de la tabla (`TableTHeadElement`), cuerpo (`TableTBodyElement`), y pie (`TableTFootElement`) secciones. Puedes pensar en ellas como el esqueleto de tu tabla.

## Paso 3: Dar estilo a las celdas del encabezado

Al darle estilo a las celdas del encabezado, las hacemos resaltar. Aquí, aplicamos colores de fondo, bordes y alineación del texto.

```csharp
int colCount = 4;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";

for (int colIndex = 0; colIndex < colCount; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText($"Head {colIndex}");
    thElement.BackgroundColor = Color.GreenYellow;
    thElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
    thElement.IsNoBorder = true;
    thElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
    thElement.Alignment = HorizontalAlignment.Right;
}
```

En este paso, recorreremos cada celda del encabezado, dándole un fondo verde-amarillo, un borde gris y un texto alineado a la derecha. Puedes ajustar estas propiedades para que coincidan con el diseño que desees.

## Paso 4: Completar y dar estilo al cuerpo de la tabla

El cuerpo de la tabla contiene los datos reales. Aquí se explica cómo aplicar estilo a cada celda con márgenes, bordes y configuraciones de texto específicos.

```csharp
int rowCount = 4;

for (int rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    trElement.AlternativeText = $"Row {rowIndex}";

    for (int colIndex = 0; colIndex < colCount; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText($"Cell [{rowIndex}, {colIndex}]");
        tdElement.BackgroundColor = Color.Yellow;
        tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
        tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
        tdElement.Alignment = HorizontalAlignment.Center;
        
        TextState cellTextState = new TextState();
        cellTextState.ForegroundColor = Color.DarkBlue;
        cellTextState.FontSize = 7.5F;
        cellTextState.FontStyle = FontStyles.Bold;
        cellTextState.Font = FontRepository.FindFont("Arial");
        tdElement.DefaultCellTextState = cellTextState;
    }
}
```

 En este paso, rellenamos el cuerpo de la tabla con cuatro filas y aplicamos estilo a cada celda con fondos amarillos y texto azul centrado y en negrita. También usamos el`MarginInfo`clase para definir el relleno alrededor del texto.

## Paso 5: Dar estilo al pie de página

Para darle a la tabla una estructura completa, agregamos y estilizamos las celdas de pie de página, tal como lo hicimos con el encabezado.

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";

for (int colIndex = 0; colIndex < colCount; colIndex++)
{
    TableTDElement tdElement = footTrElement.CreateTD();
    tdElement.SetText($"Foot {colIndex}");
}
```

La sección de pie de página tiene un estilo similar al encabezado, lo que facilita que los lectores sigan la estructura de la tabla.

## Paso 6: Guardar y validar el documento PDF

Por último, guardamos el documento PDF y verificamos si es compatible con PDF/UA.

```csharp
// Guardar el documento PDF etiquetado
document.Save(dataDir + "StyleTableCell.pdf");

// Comprobación de la conformidad con PDF/UA
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```

 Guardamos el PDF y lo utilizamos`Validate` método para garantizar que cumple con los estándares de accesibilidad (conformidad con PDF/UA).

## Conclusión

La aplicación de estilos a las tablas de un PDF con Aspose.PDF para .NET es tan eficaz como flexible. Con unas pocas líneas de código, puede crear diseños de tablas personalizados que harán que sus documentos PDF se destaquen. Desde la personalización de los bordes y fondos de las celdas hasta la garantía del cumplimiento de las normas de accesibilidad, Aspose.PDF facilita la creación de archivos PDF pulidos.

## Preguntas frecuentes

### ¿Puedo aplicar diferentes estilos a celdas individuales de una tabla?  
Sí, puedes diseñar celdas individuales personalizando el`TableTDElement` propiedades.

### ¿Cómo puedo fusionar celdas de una tabla?  
 Puedes utilizar el`ColSpan` y`RowSpan` Propiedades para fusionar celdas en una tabla.

### ¿Es posible crear una tabla compatible con PDF/UA?  
 Sí, como se demuestra en esta guía, puede garantizar la conformidad con PDF/UA al validar su documento utilizando el`Validate` método.

### ¿Puedo utilizar diferentes fuentes en las celdas de la tabla?  
 ¡Por supuesto! Puedes especificar diferentes fuentes usando el`TextState` objeto para cada celda.

### ¿Cómo descargo Aspose.PDF para .NET?  
 Puedes descargarlo desde[Página de lanzamientos](https://releases.aspose.com/pdf/net/).