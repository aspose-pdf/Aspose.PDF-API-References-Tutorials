---
title: Ajuste automático a la ventana
linktitle: Ajuste automático a la ventana
second_title: Referencia de API de Aspose.PDF para .NET
description: Guía paso a paso para usar Aspose.PDF para .NET y lograr el ajuste automático a la ventana en la generación de PDF.
type: docs
weight: 50
url: /es/net/programming-with-tables/auto-fit-to-window/
---

El siguiente artículo es una guía paso a paso sobre cómo usar el código fuente de C# provisto para lograr la funcionalidad de ajuste automático a la ventana usando la biblioteca Aspose.PDF para .NET. La función Auto Fit To Window le permite generar archivos PDF con un diseño adaptado a la ventana de visualización. Esta función es particularmente útil cuando desea que su documento PDF se ajuste automáticamente al tamaño de la ventana del lector de PDF utilizada por el usuario.

## Paso 1: Configuración del entorno

Antes de comenzar, debe instalar la biblioteca Aspose.PDF para .NET en su máquina. También asegúrese de importar los espacios de nombres necesarios en su proyecto.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Creación de un documento PDF

 Para comenzar, debe crear un`Document` objeto llamando a su constructor predeterminado.

```csharp
Document doc = new Document();
```

 A continuación, cree una sección en el`Pdf` objeto.

```csharp
Page sec1 = doc.Pages.Add();
```

## Paso 3: agregar una tabla al documento

 En este paso, vamos a agregar una tabla a nuestro documento PDF. Primero crea un`Table` objeto.

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

A continuación, agregue la tabla a la colección de párrafos de la sección.

```csharp
sec1.Paragraphs.Add(tab1);
```

##  Paso 4: Personalización de la apariencia de la mesa

Puede personalizar la apariencia de la tabla configurando propiedades como los bordes de las celdas y el margen.

```csharp
tab1. ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;

tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);

Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin.Right = 5f;
margin. Bottom = 5f;

tab1. DefaultCellPadding = margin;
```

##  Paso 4: agregar filas y celdas a la tabla

Ahora agreguemos filas y celdas a nuestra tabla. Comience creando una fila y agregando celdas a esa fila.

```csharp
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");

Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
```

## Paso 5: Guardar el documento

Finalmente, especifique la ruta del archivo de salida y guarde el documento.

```csharp
dataDir = dataDir + "AutoFitToWindow_out.pdf";
doc.Save(dataDir);
```

### Código fuente de ejemplo para Ajuste automático a la ventana usando Aspose.Words para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crea una instancia del objeto Pdf llamando a su constructor vacío
Document doc = new Document();
// Crear la sección en el objeto Pdf
Page sec1 = doc.Pages.Add();

// Crear una instancia de un objeto de tabla
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Agregue la tabla en la colección de párrafos de la sección deseada
sec1.Paragraphs.Add(tab1);

// Establecer con anchos de columna de la tabla
tab1.ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;

// Establecer borde de celda predeterminado usando el objeto BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Establecer el borde de la tabla usando otro objeto BorderInfo personalizado
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// Cree el objeto MarginInfo y establezca sus márgenes izquierdo, inferior, derecho y superior
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;

// Establezca el relleno de celda predeterminado en el objeto MarginInfo
tab1.DefaultCellPadding = margin;

// Crear filas en la tabla y luego celdas en las filas
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");

dataDir = dataDir + "AutoFitToWindow_out.pdf";
// Guardar documento actualizado que contiene objeto de tabla
doc.Save(dataDir);
```

## Conclusión

En este tutorial, aprendimos a usar Aspose.PDF para .NET para generar un archivo PDF con la función Ajuste automático a la ventana. Esta característica es extremadamente útil cuando desea que su documento PDF se ajuste automáticamente al tamaño de la ventana de visualización. Aspose.PDF para .NET ofrece muchas otras potentes funciones para generar y manipular archivos PDF. Le animo a explorar más esta biblioteca para descubrir todas sus capacidades.