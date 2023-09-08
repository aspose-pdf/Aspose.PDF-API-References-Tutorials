---
title: Resaltar carácter en archivo PDF
linktitle: Resaltar carácter en archivo PDF
second_title: Aspose.PDF para referencia de API .NET
description: Aprenda a resaltar caracteres en un archivo PDF usando Aspose.PDF para .NET.
type: docs
weight: 240
url: /es/net/programming-with-text/highlight-character-in-pdf/
---
En este tutorial, explicaremos cómo resaltar caracteres en un archivo PDF usando la biblioteca Aspose.PDF para .NET. Revisaremos el proceso paso a paso para resaltar caracteres en un PDF utilizando el código fuente C# proporcionado.

## Requisitos

Antes de comenzar, asegúrese de tener lo siguiente:

- La biblioteca Aspose.PDF para .NET instalada.
- Un conocimiento básico de la programación en C#.

## Paso 1: configurar el directorio de documentos

 Primero, debe establecer la ruta al directorio donde se encuentra su archivo PDF de entrada. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el`dataDir` variable con la ruta a su archivo PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: cargue el documento PDF

 A continuación, cargamos el documento PDF de entrada usando el`Aspose.Pdf.Document` clase.

```csharp
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
```

## Paso 3: convertir PDF a imagen

 Para resaltar caracteres, convertimos el documento PDF a una imagen usando el`PdfConverter` clase. Configuramos la resolución para la conversión y recuperamos la imagen como`Bitmap` objeto.

```csharp
int resolution = 150;
using (MemoryStream ms = new MemoryStream())
{
     PdfConverter conv = new PdfConverter(pdfDocument);
     conv. Resolution = new Resolution(resolution, resolution);
     conv. GetNextImage(ms, System.Drawing.Imaging.ImageFormat.Png);
     Bitmap bmp = (Bitmap)Bitmap.FromStream(ms);
```

## Paso 4: resalta los personajes

 Recorremos cada página del documento PDF y utilizamos un`TextFragmentAbsorber` objeto para encontrar todas las palabras de la página. Luego iteramos sobre los fragmentos, segmentos y caracteres del texto para resaltarlos usando rectángulos.

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
{
     //Establecer escala y transformar
     float scale = resolution / 72f;
     gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);

     // Recorrer las páginas
     for (int i = 0; i < pdfDocument.Pages.Count; i++)
     {
         Page page = pdfDocument.Pages[1];

         // Encuentra todas las palabras en la página.
         TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
         textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
         page. Accept(textFragmentAbsorber);
         TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

         // Recorrer fragmentos de texto
         foreach(TextFragment textFragment in textFragmentCollection)
         {
             if (i == 0)
             {
                 // Personajes destacados
                 gr.DrawRectangle(
                     Think.Yellow,
                     (float)textFragment.Position.XIndent,
                     (float)textFragment.Position.YIndent,
                     (float)textFragment.Rectangle.Width,
                     (float)textFragment.Rectangle.Height);

                 // Recorrer segmentos
                 foreach(TextSegment segment in textFragment.Segments)
                 {
                     // segmento destacado
                     gr.DrawRectangle(
                         Think Green,
                         (float)segment.Rectangle.LLX,
                         (float)segment.Rectangle.LLY,
                         (float)segment.Rectangle.Width,
                         (float)segment.Rectangle.Height);

                     // Recorrer los personajes
                     foreach(CharInfo characterInfo in segment.Characters)
                     {
                         // Resaltar personaje
                         gr.DrawRectangle(
                             Think.Black,
                             (float)characterInfo.Rectangle.LLx,
                             (float)characterInfo.Rectangle.LLY,
                             (float)characterInfo.Rectangle.Width,
                             (float)characterInfo.Rectangle.Height);
                     }
                 }
             }
         }
     }
}
```

## Paso 5: guarde la imagen de salida

Finalmente, guardamos la imagen modificada con los caracteres resaltados en el archivo de salida especificado.

```csharp
dataDir = dataDir + "HighlightCharacterInPDF_out.png";
bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
```

### Código fuente de muestra para resaltar caracteres en PDF usando Aspose.PDF para .NET 
```csharp
try
{
	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	int resolution = 150;
	Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
	using (MemoryStream ms = new MemoryStream())
	{
		PdfConverter conv = new PdfConverter(pdfDocument);
		conv.Resolution = new Resolution(resolution, resolution);
		conv.GetNextImage(ms, System.Drawing.Imaging.ImageFormat.Png);
		Bitmap bmp = (Bitmap)Bitmap.FromStream(ms);
		using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
		{
			float scale = resolution / 72f;
			gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);
			for (int i = 0; i < pdfDocument.Pages.Count; i++)
			{
				Page page = pdfDocument.Pages[1];
				// Cree un objeto TextAbsorber para encontrar todas las palabras
				TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
				textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
				page.Accept(textFragmentAbsorber);
				// Obtenga los fragmentos de texto extraídos
				TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
				// Recorre los fragmentos
				foreach (TextFragment textFragment in textFragmentCollection)
				{
					if (i == 0)
					{
						gr.DrawRectangle(
						Pens.Yellow,
						(float)textFragment.Position.XIndent,
						(float)textFragment.Position.YIndent,
						(float)textFragment.Rectangle.Width,
						(float)textFragment.Rectangle.Height);
						for (int segNum = 1; segNum <= textFragment.Segments.Count; segNum++)
						{
							TextSegment segment = textFragment.Segments[segNum];
							for (int charNum = 1; charNum <= segment.Characters.Count; charNum++)
							{
								CharInfo characterInfo = segment.Characters[charNum];
								Aspose.Pdf.Rectangle rect = page.GetPageRect(true);
								Console.WriteLine("TextFragment = " + textFragment.Text + "    Page URY = " + rect.URY +
												  "   TextFragment URY = " + textFragment.Rectangle.URY);
								gr.DrawRectangle(
								Pens.Black,
								(float)characterInfo.Rectangle.LLX,
								(float)characterInfo.Rectangle.LLY,
								(float)characterInfo.Rectangle.Width,
								(float)characterInfo.Rectangle.Height);
							}
							gr.DrawRectangle(
							Pens.Green,
							(float)segment.Rectangle.LLX,
							(float)segment.Rectangle.LLY,
							(float)segment.Rectangle.Width,
							(float)segment.Rectangle.Height);
						}
					}
				}
			}
		}
		dataDir = dataDir + "HighlightCharacterInPDF_out.png";
		bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
	}
	Console.WriteLine("\nCharacters highlighted successfully in pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.");
}
```

## Conclusión

En este tutorial, aprendió cómo resaltar caracteres en un documento PDF usando la biblioteca Aspose.PDF para .NET. Si sigue la guía paso a paso y ejecuta el código C# proporcionado, puede resaltar caracteres en un PDF y guardar el resultado como una imagen.

### Preguntas frecuentes

#### P: ¿Cuál es el propósito del tutorial "Resaltar carácter en un archivo PDF"?

R: El tutorial "Resaltar caracteres en un archivo PDF" explica cómo utilizar la biblioteca Aspose.PDF para .NET para resaltar caracteres dentro de un documento PDF. El tutorial proporciona una guía paso a paso y el código fuente C# para lograrlo.

#### P: ¿Por qué querría resaltar caracteres en un documento PDF?

R: Resaltar caracteres en un documento PDF puede resultar útil para diversos fines, como enfatizar contenido específico o hacer que cierto texto sea más visible y distinguible.

#### P: ¿Cómo configuro el directorio de documentos?

R: Para configurar el directorio de documentos:

1.  Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el`dataDir` variable con la ruta al directorio donde se encuentra su archivo PDF de entrada.

#### P: ¿Cómo cargo el documento PDF y lo convierto en una imagen?

 R: En el tutorial, el`Aspose.Pdf.Document` La clase se utiliza para cargar el documento PDF de entrada. Entonces el`PdfConverter` La clase se emplea para convertir el documento PDF en una imagen. Se establece la resolución de la imagen y la imagen se recupera como`Bitmap` objeto.

#### P: ¿Cómo resalto caracteres en la imagen del documento PDF?

R: El tutorial lo guía a través del proceso de recorrer cada página del documento PDF, encontrar palabras usando un`TextFragmentAbsorber`e iterar a través de fragmentos de texto, segmentos y caracteres para resaltarlos usando rectángulos.

#### P: ¿Puedo personalizar la apariencia de los personajes y segmentos resaltados?

R: Sí, puede personalizar la apariencia de los caracteres y segmentos resaltados modificando los colores y estilos utilizados en las operaciones de dibujo.

#### P: ¿Cómo guardo la imagen modificada con los caracteres resaltados?

 R: El tutorial demuestra cómo guardar la imagen modificada con los caracteres resaltados en el archivo de salida especificado usando el`Save` método de la`Bitmap` clase.

#### P: ¿Se requiere una licencia Aspose válida para este tutorial?

R: Sí, se requiere una licencia Aspose válida para que este tutorial funcione correctamente. Puede comprar una licencia completa u obtener una licencia temporal de 30 días en el sitio web de Aspose.