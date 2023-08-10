---
title: Usar guión de látex
linktitle: Usar guión de látex
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a usar el script Latex para agregar expresiones o fórmulas matemáticas en un documento PDF usando Aspose.PDF para .NET.
type: docs
weight: 550
url: /es/net/programming-with-text/use-latex-script/
---

Este tutorial explica cómo usar el script Latex para agregar expresiones o fórmulas matemáticas en un documento PDF usando Aspose.PDF para .NET. El código fuente de C# proporcionado demuestra los pasos para crear un documento, agregar una tabla con una celda que contiene el script LaTeX y guardar el documento.

## requisitos previos

Antes de comenzar, asegúrese de tener lo siguiente:

- Conocimientos básicos del lenguaje de programación C#.
- Aspose.PDF para la biblioteca .NET instalada. Puede obtenerlo del sitio web de Aspose o usar NuGet para instalarlo en su proyecto.

## Paso 1: configurar el proyecto

Cree un nuevo proyecto de C# en su entorno de desarrollo integrado (IDE) preferido y agregue una referencia a la biblioteca Aspose.PDF para .NET.

## Paso 2: importa los espacios de nombres necesarios

Agregue las siguientes directivas using al principio de su archivo C# para importar los espacios de nombres requeridos:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Tables;
using Aspose.Pdf.Text;
```

## Paso 3: Crear y configurar el documento

 Crear un nuevo`Document` objeto y agregarle una página:

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Paso 4: Crear y configurar la tabla

Cree una tabla y agréguele una fila:

```csharp
Table table = new Table();
Row row = table.Rows.Add();
```

## Paso 5: Agrega una celda con script LaTeX

 Crea una celda y agrega un`LatexFragment` que contiene el script Latex:

```csharp
string latexText1 = "$123456789+\\sqrt{1}+\\int_a^b f(x)dx$";
Cell cell = row.Cells.Add();
LatexFragment ltext1 = new LatexFragment(latexText1, true);
cell.Paragraphs.Add(ltext1);
```

 Tenga en cuenta que el`true` parámetro en el`LatexFragment` El constructor elimina las sangrías de párrafo de Latex.

## Paso 6: Agrega la tabla a la página

Agregue la tabla a la página:

```csharp
page.Paragraphs.Add(table);
```

## Paso 7: Guarde el documento

Guarde el documento en un archivo PDF:

```csharp
doc.Save(dataDir + "LatextScriptInPdf_out.pdf");
```

### Ejemplo de código fuente para Use Latex Script usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crear un nuevo objeto de documento
Document doc = new Document();
//Agregar página en la colección de páginas
Page page = doc.Pages.Add();
// crear una tabla
Table table = new Table();
// Agregar una fila a la tabla
Row row = table.Rows.Add();
// Agregue Cell con Latex Script para agregar expresiones/fórmulas matemáticas
string latexText1 = "$123456789+\\sqrt{1}+\\int_a^b f(x)dx$";
Cell cell = row.Cells.Add();
cell.Margin = new MarginInfo { Left = 20, Right = 20, Top = 20, Bottom = 20 };
// El segundo parámetro bool del constructor LatexFragment proporciona la eliminación de sangrías de párrafo LaTeX.
LatexFragment ltext1 = new LatexFragment(latexText1, true);
cell.Paragraphs.Add(ltext1);
// Agregar tabla dentro de la página
page.Paragraphs.Add(table);
// Guardar el documento
doc.Save(dataDir + "LatextScriptInPdf_out.pdf");
```

## Conclusión

¡Felicidades! Ha aprendido con éxito cómo usar el script Latex para agregar expresiones o fórmulas matemáticas en un documento PDF usando Aspose.PDF para .NET. Este tutorial proporcionó instrucciones paso a paso sobre cómo crear un documento, agregar una tabla con una celda que contenga un script LaTeX y guardar el documento. Ahora puede incorporar este código en sus propios proyectos de C# para generar archivos PDF con contenido matemático.