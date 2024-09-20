---
title: Agregar columna repetida en documento PDF
linktitle: Agregar columna repetida en documento PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a agregar columnas repetidas a documentos PDF con Aspose.PDF para .NET. Guía paso a paso con ejemplos y código. Perfecta para desarrolladores.
type: docs
weight: 20
url: /es/net/programming-with-tables/add-repeating-column/
---
## Introducción

Si trabaja con documentos PDF y necesita agregar columnas repetidas, ¡está en el lugar correcto! Con Aspose.PDF para .NET, puede administrar fácilmente las tablas y el contenido dentro de un PDF. Ya sea que esté creando informes dinámicos, facturas o cualquier otro documento estructurado, las columnas repetidas pueden ser un elemento innovador en la organización de datos. Veamos una guía paso a paso sobre cómo agregar columnas repetidas a un documento PDF.

## Prerrequisitos

Antes de pasar al código, asegurémonos de que tienes todo configurado:

- Aspose.PDF para .NET: debe tener la biblioteca Aspose.PDF para .NET instalada en su proyecto.
- [Descargar Aspose.PDF para .NET](https://releases.aspose.com/pdf/net/)
- [Prueba gratuita](https://releases.aspose.com/)
- Entorno de desarrollo: asegúrese de tener instalado un IDE compatible con .NET, como Visual Studio.
- Comprensión básica de C#: si bien desglosaremos todo, una comprensión básica de C# le ayudará a seguir el proceso sin problemas.
  
 Si aún no tienes Aspose.PDF para .NET, puedes obtener uno[licencia temporal](https://purchase.aspose.com/temporary-license/) para comenzar a explorar sus características.

## Importar paquetes

Para comenzar, debe importar los espacios de nombres necesarios de Aspose.PDF para .NET. A continuación, le indicamos cómo hacerlo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

Estos paquetes proporcionan las clases y métodos esenciales necesarios para trabajar con documentos PDF y manipular tablas.

Ahora, vamos a dividir el proceso en varios pasos para agregar columnas repetidas a un documento PDF. ¡Siga leyendo!

## Paso 1: Establezca la ruta al directorio de sus documentos

Antes de crear o manipular cualquier archivo, debemos definir la ruta donde se guardará el PDF generado. En su proyecto de C#, establezca la ruta del directorio donde se ubicarán sus archivos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddRepeatingColumn_out.pdf";
```

 Esta ruta apunta al directorio donde se guardará el PDF de salida. Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta actual en su máquina.

## Paso 2: Crear un nuevo documento PDF

 Para comenzar, crea una nueva instancia`Document` objeto. Este servirá como contenedor para todas las páginas y el contenido dentro del PDF.

```csharp
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

 Aquí, hemos creado un nuevo documento PDF y le hemos agregado una página en blanco.`doc.Pages.Add()` El método inserta una nueva página en el documento.

## Paso 3: Crear una instancia de la tabla externa

continuación, creamos una tabla externa. Esta tabla ocupará todo el ancho de la página y servirá como contenedor para otras tablas, incluida la que contendrá las columnas repetidas.

```csharp
Aspose.Pdf.Table outerTable = new Aspose.Pdf.Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;
```

 Hemos establecido el`ColumnWidths` propiedad al "100%", lo que significa que la tabla se extenderá por todo el ancho de la página.

## Paso 4: Crear la tabla interna

 Ahora, vamos a crear la tabla interna, que tendrá columnas repetidas. Las propiedades clave aquí son:`Broken` , lo que permite que la tabla continúe en la misma página, y`ColumnAdjustment`, que ajusta automáticamente el ancho de las columnas para adaptarse al contenido.

```csharp
Aspose.Pdf.Table mytable = new Aspose.Pdf.Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;
```

Esta tabla interna estará anidada dentro de la tabla externa.

## Paso 5: Agregar tablas a la página

Ahora que tenemos listas las tablas internas y externas, agreguémoslas a la página. Este paso garantiza que las tablas se incluyan en la estructura del documento.

```csharp
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
```

 Aquí, agregamos el`outerTable` a la página, y luego dentro de la tabla externa, anidamos el`mytable` Además, establecimos`RepeatingColumnsCount` 5, especificando cuántas columnas deben repetirse cuando se agregan datos.

## Paso 6: Agregar fila de encabezado

Ahora es el momento de agregar los encabezados a la tabla. La fila de encabezado brinda contexto a los datos y ayuda a estructurar las columnas. 

```csharp
Aspose.Pdf.Row row = mytable.Rows.Add();
row.Cells.Add("header 1");
row.Cells.Add("header 2");
row.Cells.Add("header 3");
row.Cells.Add("header 4");
row.Cells.Add("header 5");
row.Cells.Add("header 6");
row.Cells.Add("header 7");
row.Cells.Add("header 11");
row.Cells.Add("header 12");
row.Cells.Add("header 13");
row.Cells.Add("header 14");
row.Cells.Add("header 15");
row.Cells.Add("header 16");
row.Cells.Add("header 17");
```

Este fragmento de código agrega la primera fila (que usaremos como encabezados) y la llena con celdas que contienen texto como “encabezado 1”, “encabezado 2”, etc.

## Paso 7: Agregar filas de datos

Por último, podemos añadir algunos datos a la tabla. Este bucle crea filas de forma dinámica y rellena las celdas con contenido:

```csharp
for (int RowCounter = 0; RowCounter <= 5; RowCounter++)
{
    Aspose.Pdf.Row row1 = mytable.Rows.Add();
    row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 4");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 5");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 6");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 7");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 11");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 12");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 13");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 14");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 15");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 16");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 17");
}
```

El bucle se itera seis veces, agregando filas y llenando cada celda con los datos de la columna correspondiente (por ejemplo, “col 1, 1”, “col 2, 2”, etc.).

## Paso 8: Guardar el documento

Una vez agregadas todas las filas y columnas, el último paso es guardar el documento en la ruta de archivo especificada.

```csharp
doc.Save(outFile);
```

¡Su documento ahora está guardado con columnas repetidas!

## Conclusión

¡Y ya lo tienes! Con estos sencillos pasos, puedes crear un documento PDF con columnas repetidas usando Aspose.PDF para .NET. Al aprovechar la flexibilidad de las tablas anidadas, puedes lograr diseños complejos que hagan que tus archivos PDF tengan un aspecto profesional y organizado. Prueba esto en tu próximo proyecto y explora todo el potencial de Aspose.PDF para satisfacer tus necesidades de generación de archivos PDF.

## Preguntas frecuentes

### ¿Qué es Aspose.PDF para .NET?
Aspose.PDF para .NET es una potente biblioteca que permite a los desarrolladores crear, editar y administrar documentos PDF mediante programación.

### ¿Puedo ajustar dinámicamente el número de columnas repetidas?
 Sí, puede cambiar el número de columnas repetidas modificando la`RepeatingColumnsCount` propiedad.

### ¿Cómo puedo aplicar una licencia a Aspose.PDF para .NET?
 Puede aplicar una licencia desde un archivo o flujo siguiendo las instrucciones[documentación](https://reference.aspose.com/pdf/net/).

### ¿Es posible agregar imágenes a las celdas de la tabla?
Sí, Aspose.PDF para .NET admite agregar varios tipos de contenido, incluidas imágenes, a las celdas de la tabla.

### ¿Puedo personalizar aún más el diseño de la mesa?
¡Por supuesto! Aspose.PDF ofrece numerosas funciones para personalizar los estilos de tabla, incluidos bordes, relleno, alineación y más.