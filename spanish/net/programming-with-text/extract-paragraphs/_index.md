---
title: Extraer párrafos
linktitle: Extraer párrafos
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a extraer párrafos de un documento PDF utilizando Aspose.PDF para .NET.
type: docs
weight: 160
url: /es/net/programming-with-text/extract-paragraphs/
---

Este tutorial lo guiará a través del proceso de extracción de párrafos de un documento PDF usando Aspose.PDF para .NET. El código fuente de C# proporcionado demuestra los pasos necesarios.

## Requisitos
Antes de comenzar, asegúrese de tener lo siguiente:

- Visual Studio o cualquier otro compilador de C# instalado en su máquina.
- Aspose.PDF para la biblioteca .NET. Puede descargarlo del sitio web oficial de Aspose o usar un administrador de paquetes como NuGet para instalarlo.

## Paso 1: configurar el proyecto
1. Cree un nuevo proyecto de C# en su entorno de desarrollo preferido.
2. Agregue una referencia a la biblioteca Aspose.PDF para .NET.

## Paso 2: importa los espacios de nombres requeridos
En el archivo de código donde desea extraer párrafos, agregue las siguientes directivas using en la parte superior del archivo:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

## Paso 3: establecer el directorio de documentos
 En el código, busque la línea que dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` y reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta al directorio donde se almacenan sus documentos.

## Paso 4: Abra el documento PDF
 Abra un documento PDF existente usando el`Document` constructor y pasando la ruta al archivo PDF de entrada.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Paso 5: Extraer párrafos
 Instanciar el`ParagraphAbsorber` clase y usar su`Visit` método para extraer párrafos del documento.

```csharp
ParagraphAbsorber absorb = new ParagraphAbsorber();
absorb.Visit(doc);
```

## Paso 6: iterar a través de los párrafos
Recorra los párrafos extraídos para acceder al contenido del texto. Use bucles anidados para atravesar secciones y líneas dentro de cada párrafo.

```csharp
foreach(PageMarkup markup in absorber.PageMarkups)
{
     int i = 1;
     foreach(MarkupSection section in markup.Sections)
     {
         int j = 1;
         foreach(MarkupParagraph paragraph in section.Paragraphs)
         {
             StringBuilder paragraphText = new StringBuilder();
             foreach(List<TextFragment> line in paragraph.Lines)
             {
                 foreach(TextFragment fragment in line)
                 {
                     paragraphText.Append(fragment.Text);
                 }
                 paragraphText. Append("\r\n");
             }
             paragraphText. Append("\r\n");
             Console.WriteLine("Paragraph {0} of section {1} on page {2}:", j, i, markup.Number);
             Console.WriteLine(paragraphText.ToString());
             j++;
         }
         i++;
     }
}
```

### Ejemplo de código fuente para Extraer párrafos usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir un archivo PDF existente
Document doc = new Document(dataDir + "input.pdf");
// Instanciar ParagraphAbsorber
ParagraphAbsorber absorber = new ParagraphAbsorber();
absorber.Visit(doc);
foreach (PageMarkup markup in absorber.PageMarkups)
{
	int i = 1;
	foreach (MarkupSection section in markup.Sections)
	{
		int j = 1;
		foreach (MarkupParagraph paragraph in section.Paragraphs)
		{
			StringBuilder paragraphText = new StringBuilder();
			foreach (List<TextFragment> line in paragraph.Lines)
			{
				foreach (TextFragment fragment in line)
				{
					paragraphText.Append(fragment.Text);
				}
				paragraphText.Append("\r\n");
			}
			paragraphText.Append("\r\n");
			Console.WriteLine("Paragraph {0} of section {1} on page {2}:", j, i, markup.Number);
			Console.WriteLine(paragraphText.ToString());
			j++;
		}
		i++;
	}
}
```

## Conclusión
Ha extraído con éxito párrafos de un documento PDF utilizando Aspose.PDF para .NET. Los párrafos extraídos se han mostrado en la ventana de la consola.