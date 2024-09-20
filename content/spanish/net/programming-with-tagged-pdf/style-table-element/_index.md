---
title: Elemento de tabla de estilos
linktitle: Elemento de tabla de estilos
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a crear y diseñar un elemento de tabla en Aspose.PDF para .NET con instrucciones paso a paso, estilos personalizados y compatibilidad con PDF/UA.
type: docs
weight: 170
url: /es/net/programming-with-tagged-pdf/style-table-element/
---
## Introducción

En este artículo, profundizaremos en cómo crear y aplicar estilo a un elemento de tabla con Aspose.PDF para .NET. Aprenderá a estructurar una tabla, aplicar estilos personalizados y validar la compatibilidad de su documento con PDF/UA. Al finalizar este tutorial, podrá crear tablas de aspecto profesional en sus archivos PDF con facilidad.

## Prerrequisitos

Antes de comenzar el tutorial, deberá asegurarse de tener lo siguiente:

1. Visual Studio o un IDE similar instalado en su máquina.
2. .NET Framework o .NET Core SDK para ejecutar la aplicación.
3.  Biblioteca Aspose.PDF para .NET descargada y referenciada en su proyecto. Puede obtener la última versión en[aquí](https://releases.aspose.com/pdf/net/).
4.  Una licencia Aspose válida o una[licencia temporal](https://purchase.aspose.com/temporary-license/) para desbloquear la funcionalidad completa de la biblioteca.

## Importar paquetes

Para comenzar, importe los espacios de nombres necesarios a su proyecto:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Estos espacios de nombres cubren las principales operaciones de PDF, contenido etiquetado, tablas y formato de texto.

Ahora, desglosaremos el proceso de creación y aplicación de estilos a una tabla en Aspose.PDF. Repasaremos cada sección en detalle para que puedas seguir el proceso.

## Paso 1: Crear un nuevo documento PDF y configurar el contenido etiquetado

En este primer paso, crearemos un documento PDF en blanco y configuraremos su contenido etiquetado.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crear un nuevo documento PDF
Document document = new Document();

// Configurar contenido etiquetado
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table style");
taggedContent.SetLanguage("en-US");
```

 Comenzamos creando un nuevo`Document` objeto, que representa nuestro PDF.`TaggedContent`El objeto se utiliza para gestionar la estructura del documento, garantizando el cumplimiento de los estándares de accesibilidad. Establecemos el título y el idioma del documento para un etiquetado adecuado.

## Paso 2: Definir el elemento raíz

A continuación, crearemos el elemento de estructura raíz, que actúa como contenedor de todo el contenido de nuestro PDF.

```csharp
// Obtener el elemento de estructura raíz
StructureElement rootElement = taggedContent.RootElement;
```

 El`RootElement` Sirve como contenedor base para todos los elementos estructurados, incluida nuestra tabla. Ayuda a mantener la jerarquía estructural del documento, lo cual es importante tanto para la organización como para la accesibilidad.

## Paso 3: Crear y darle estilo al elemento de tabla

 Ahora que el elemento raíz está configurado, crearemos un`TableElement` y aplicar estilos como color de fondo, bordes y alineación.

```csharp
// Crear elemento de estructura de tabla
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);

// Dale estilo a la mesa
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement.Alignment = HorizontalAlignment.Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
```

 Creamos una`TableElement` , que define la estructura de nuestra tabla.`BackgroundColor`, `Border` , y`Alignment` Las propiedades nos permiten personalizar la apariencia de la tabla.`Broken` La propiedad garantiza que si la tabla se divide en páginas, se divide verticalmente.

## Paso 4: Establecer las dimensiones de la tabla y los estilos de celda

En este paso, definiremos el número de columnas, el relleno de celdas y otras propiedades importantes de la tabla.

```csharp
tableElement.ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement.DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
```

 Especificamos el ancho de las columnas para garantizar que cada columna de la tabla esté espaciada de manera uniforme.`DefaultCellBorder`, `DefaultCellPadding` , y`DefaultCellTextState` definir los estilos predeterminados para las celdas, incluidos los bordes, el relleno, el color del texto y el tamaño de fuente.

## Paso 5: Agregar filas repetidas y estilos personalizados

También podemos definir estilos para filas repetidas y otros elementos específicos de la tabla, como encabezados y pies de página.

```csharp
tableElement.RepeatingRowsCount = 3;
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
```

 El`RepeatingRowsCount` garantiza que las tres primeras filas se repitan si la tabla abarca varias páginas. Establecemos el`RepeatingRowsStyle` para aplicar un color de fondo personalizado a estas filas.

## Paso 6: Agregar elementos de cabecera, cuerpo y pie de tabla

Ahora, vamos a crear las secciones de encabezado, cuerpo y pie de página de la tabla y completarlas con contenido.

```csharp
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

// Crear fila de encabezado
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (int colIndex = 0; colIndex < 5; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText($"Head {colIndex}");
}

// Rellenar el cuerpo de la tabla
for (int rowIndex = 0; rowIndex < 10; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    for (int colIndex = 0; colIndex < 5; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText($"Cell [{rowIndex}, {colIndex}]");
    }
}
```

 La tabla se divide en tres partes: encabezado, cuerpo y pie. Primero creamos la fila de encabezado usando`TableTHElement` agregamos encabezados de columnas. Luego, completamos el cuerpo de la tabla con`TableTDElement`, llenando cada celda con una etiqueta que incluye su posición.

## Paso 7: Guardar el documento

Finalmente, guardamos el documento PDF en el directorio especificado.

```csharp
// Guardar el documento PDF etiquetado
document.Save(dataDir + "StyleTableElement.pdf");
```

Este paso finaliza el proceso de creación del documento guardando el archivo PDF con la tabla con estilo.

## Paso 8: Validar la conformidad con PDF/UA

Después de guardar el documento, es esencial asegurarse de que cumpla con los estándares PDF/UA (Accesibilidad Universal).

```csharp
// Verificar la conformidad con PDF/UA
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```

Aquí, recargamos el documento y lo validamos según los estándares PDF/UA. El cumplimiento garantiza que su PDF cumpla con los requisitos de accesibilidad, lo que lo hace adecuado para una amplia gama de usuarios.

## Conclusión

Con Aspose.PDF para .NET, crear y aplicar estilos a las tablas de sus documentos PDF es sencillo e intuitivo. Si sigue los pasos que se describen en este tutorial, podrá crear tablas con estilos personalizados y asegurarse de que sus archivos PDF cumplan con los estándares de accesibilidad. Tanto si genera informes como si crea documentos estructurados, las tablas son una herramienta poderosa para presentar los datos de forma clara.

## Preguntas frecuentes

### ¿Puedo agregar imágenes dentro de las celdas de la tabla?
 Sí, puedes insertar imágenes en celdas de tablas usando el`Image` elemento.

### ¿Cómo puedo ajustar dinámicamente el ancho de las columnas?
 Puedes configurar el`ColumnAdjustment` propiedad a`AutoFitToWindow` para ajustar el ancho de las columnas automáticamente según el contenido.

### ¿Es obligatorio el cumplimiento de PDF/UA para todos los documentos?
Si bien no es obligatorio, se recomienda para documentos que requieren altos estándares de accesibilidad.

### ¿Puedo aplicar diferentes estilos a filas específicas?
 Sí, puedes personalizar filas o celdas individuales ajustando sus`TextState` o`BackgroundColor`.

### ¿Cuál es el beneficio de utilizar contenido etiquetado?
El contenido etiquetado mejora la accesibilidad de los documentos y ayuda a garantizar el cumplimiento de estándares como PDF/UA.