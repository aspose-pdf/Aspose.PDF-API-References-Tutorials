---
title: Destacar caractere no arquivo PDF
linktitle: Destacar caractere no arquivo PDF
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como destacar caracteres em um arquivo PDF usando Aspose.PDF for .NET.
type: docs
weight: 240
url: /pt/net/programming-with-text/highlight-character-in-pdf/
---
Neste tutorial, explicaremos como destacar caracteres em um arquivo PDF usando a biblioteca Aspose.PDF para .NET. Seguiremos o processo passo a passo de destaque de caracteres em um PDF usando o código-fonte C# fornecido.

## Requisitos

Antes de começar, certifique-se de ter o seguinte:

- A biblioteca Aspose.PDF para .NET instalada.
- Uma compreensão básica da programação C#.

## Etapa 1: configurar o diretório de documentos

 Primeiro, você precisa definir o caminho para o diretório onde o arquivo PDF de entrada está localizado. Substituir`"YOUR DOCUMENT DIRECTORY"` no`dataDir` variável com o caminho para o seu arquivo PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passo 2: Carregue o Documento PDF

 A seguir, carregamos o documento PDF de entrada usando o`Aspose.Pdf.Document` aula.

```csharp
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
```

## Passo 3: Converter PDF em Imagem

 Para destacar caracteres, convertemos o documento PDF em uma imagem usando o`PdfConverter` aula. Definimos a resolução para a conversão e recuperamos a imagem como um`Bitmap` objeto.

```csharp
int resolution = 150;
using (MemoryStream ms = new MemoryStream())
{
     PdfConverter conv = new PdfConverter(pdfDocument);
     conv. Resolution = new Resolution(resolution, resolution);
     conv. GetNextImage(ms, System.Drawing.Imaging.ImageFormat.Png);
     Bitmap bmp = (Bitmap)Bitmap.FromStream(ms);
```

## Etapa 4: destacar caracteres

 Percorremos cada página do documento PDF e usamos um`TextFragmentAbsorber` objeto para encontrar todas as palavras na página. Em seguida, iteramos sobre os fragmentos de texto, segmentos e caracteres para destacá-los usando retângulos.

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
{
     //Definir escala e transformar
     float scale = resolution / 72f;
     gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);

     // Percorrer as páginas
     for (int i = 0; i < pdfDocument.Pages.Count; i++)
     {
         Page page = pdfDocument.Pages[1];

         // Encontre todas as palavras na página
         TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
         textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
         page. Accept(textFragmentAbsorber);
         TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

         // Percorrer fragmentos de texto
         foreach(TextFragment textFragment in textFragmentCollection)
         {
             if (i == 0)
             {
                 // Destacar personagens
                 gr.DrawRectangle(
                     Think.Yellow,
                     (float)textFragment.Position.XIndent,
                     (float)textFragment.Position.YIndent,
                     (float)textFragment.Rectangle.Width,
                     (float)textFragment.Rectangle.Height);

                 // Loop através de segmentos
                 foreach(TextSegment segment in textFragment.Segments)
                 {
                     // Segmento de destaque
                     gr.DrawRectangle(
                         Think Green,
                         (float)segment.Rectangle.LLX,
                         (float)segment.Rectangle.LLY,
                         (float)segment.Rectangle.Width,
                         (float)segment.Rectangle.Height);

                     // Percorrer personagens
                     foreach(CharInfo characterInfo in segment.Characters)
                     {
                         // Destacar personagem
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

## Etapa 5: salve a imagem de saída

Finalmente, salvamos a imagem modificada com os caracteres destacados no arquivo de saída especificado.

```csharp
dataDir = dataDir + "HighlightCharacterInPDF_out.png";
bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
```

### Exemplo de código-fonte para destaque de caractere em PDF usando Aspose.PDF para .NET 
```csharp
try
{
	// O caminho para o diretório de documentos.
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
				// Crie o objeto TextAbsorber para encontrar todas as palavras
				TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
				textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
				page.Accept(textFragmentAbsorber);
				// Obtenha os fragmentos de texto extraídos
				TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
				// Percorrer os fragmentos
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
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// www.aspose.com/purchase/default.aspx.");
}
```

## Conclusão

Neste tutorial, você aprendeu como destacar caracteres em um documento PDF usando a biblioteca Aspose.PDF para .NET. Seguindo o guia passo a passo e executando o código C# fornecido, você pode destacar caracteres em um PDF e salvar a saída como uma imagem.

### Perguntas frequentes

#### P: Qual é o objetivo do tutorial "Destacar caractere no arquivo PDF"?

R: O tutorial "Destacar caracteres em arquivo PDF" explica como usar a biblioteca Aspose.PDF para .NET para destacar caracteres em um documento PDF. O tutorial fornece um guia passo a passo e código-fonte C# para fazer isso.

#### P: Por que eu gostaria de destacar caracteres em um documento PDF?

R: Destacar caracteres em um documento PDF pode ser útil para diversos fins, como enfatizar um conteúdo específico ou tornar determinado texto mais visível e distinguível.

#### P: Como configuro o diretório de documentos?

R: Para configurar o diretório de documentos:

1.  Substituir`"YOUR DOCUMENT DIRECTORY"` no`dataDir` variável com o caminho para o diretório onde seu arquivo PDF de entrada está localizado.

#### P: Como carrego o documento PDF e o converto em uma imagem?

 R: No tutorial, o`Aspose.Pdf.Document` class é usada para carregar o documento PDF de entrada. Então o`PdfConverter` classe é empregada para converter o documento PDF em uma imagem. A resolução da imagem é definida e a imagem é recuperada como um`Bitmap` objeto.

#### P: Como realço caracteres na imagem do documento PDF?

R: O tutorial orienta você no processo de percorrer cada página do documento PDF, encontrando palavras usando um`TextFragmentAbsorber`e iterar fragmentos de texto, segmentos e caracteres para destacá-los usando retângulos.

#### P: Posso personalizar a aparência dos caracteres e segmentos destacados?

R: Sim, você pode personalizar a aparência dos caracteres e segmentos destacados modificando as cores e estilos usados nas operações de desenho.

#### P: Como salvo a imagem modificada com os caracteres destacados?

 R: O tutorial demonstra como salvar a imagem modificada com os caracteres destacados no arquivo de saída especificado usando o`Save` método do`Bitmap` aula.

#### P: É necessária uma licença Aspose válida para este tutorial?

R: Sim, uma licença Aspose válida é necessária para que este tutorial funcione corretamente. Você pode adquirir uma licença completa ou obter uma licença temporária de 30 dias no site Aspose.