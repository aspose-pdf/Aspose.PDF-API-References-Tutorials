---
title: Extraer párrafos en un archivo PDF
linktitle: Extraer párrafos en un archivo PDF
second_title: Aspose.PDF para referencia de API .NET
description: Aprenda a extraer párrafos en un archivo PDF usando Aspose.PDF para .NET.
type: docs
weight: 160
url: /es/net/programming-with-text/extract-paragraphs/
---
Este tutorial lo guiará a través del proceso de extracción de párrafos en un archivo PDF usando Aspose.PDF para .NET. El código fuente de C# proporcionado demuestra los pasos necesarios.

## Requisitos
Antes de comenzar, asegúrese de tener lo siguiente:

- Visual Studio o cualquier otro compilador de C# instalado en su máquina.
- Aspose.PDF para la biblioteca .NET. Puede descargarlo del sitio web oficial de Aspose o utilizar un administrador de paquetes como NuGet para instalarlo.

## Paso 1: configurar el proyecto
1. Cree un nuevo proyecto de C# en su entorno de desarrollo preferido.
2. Agregue una referencia a la biblioteca Aspose.PDF para .NET.

## Paso 2: importar los espacios de nombres necesarios
En el archivo de código donde desea extraer párrafos, agregue las siguientes directivas de uso en la parte superior del archivo:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

## Paso 3: configurar el directorio de documentos
 En el código, localice la línea que dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` y reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta al directorio donde están almacenados sus documentos.

## Paso 4: abre el documento PDF
 Abra un documento PDF existente usando el`Document`constructor y pasando la ruta al archivo PDF de entrada.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Paso 5: extraer párrafos
 Instanciar el`ParagraphAbsorber` clase y usar su`Visit` Método para extraer párrafos del documento.

```csharp
ParagraphAbsorber absorb = new ParagraphAbsorber();
absorb.Visit(doc);
```

## Paso 6: iterar a través de los párrafos
Recorra los párrafos extraídos para acceder al contenido del texto. Utilice bucles anidados para recorrer secciones y líneas dentro de cada párrafo.

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

### Código fuente de muestra para extraer párrafos usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//Abrir un archivo PDF existente
Document doc = new Document(dataDir + "input.pdf");
// Crear una instancia del absorbente de párrafos
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

### Preguntas frecuentes

#### P: ¿Cuál es el propósito de este tutorial?

R: Este tutorial tiene como objetivo guiarlo a través del proceso de extracción de párrafos de un archivo PDF usando Aspose.PDF para .NET. El código fuente C# adjunto proporciona pasos prácticos para realizar esta tarea.

#### P: ¿Qué espacios de nombres debo importar?

R: En el archivo de código donde desea extraer párrafos, incluya las siguientes directivas de uso al principio del archivo:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

#### P: ¿Cómo especifico el directorio de documentos?

 R: Localice la línea`string dataDir = "YOUR DOCUMENT DIRECTORY";` en el código y reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

#### P: ¿Cómo abro un documento PDF existente?

 R: En el Paso 4, abrirá un documento PDF existente usando el`Document` constructor y proporcionando la ruta al archivo PDF de entrada.

#### P: ¿Cómo extraigo párrafos del documento?

 R: El paso 5 implica crear una instancia del`ParagraphAbsorber` clase y usando su`Visit` Método para extraer párrafos del documento PDF.

#### P: ¿Cómo repito los párrafos extraídos?

R: El paso 6 lo guía para recorrer los párrafos extraídos. Los bucles anidados se utilizan para recorrer secciones y líneas dentro de cada párrafo y, en última instancia, acceder y mostrar el contenido del texto.

#### P: ¿Cuál es la conclusión clave de este tutorial?

R: Al seguir este tutorial, habrá aprendido cómo extraer párrafos de un documento PDF usando Aspose.PDF para .NET. Los párrafos extraídos se muestran en la ventana de la consola, brindándole información valiosa sobre la estructura del contenido del documento.