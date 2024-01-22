---
title: Extraia parágrafos em arquivo PDF
linktitle: Extraia parágrafos em arquivo PDF
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como extrair parágrafos em arquivo PDF usando Aspose.PDF for .NET.
type: docs
weight: 160
url: /pt/net/programming-with-text/extract-paragraphs/
---
Este tutorial irá guiá-lo através do processo de extração de parágrafos em arquivo PDF usando Aspose.PDF for .NET. O código-fonte C# fornecido demonstra as etapas necessárias.

## Requisitos
Antes de começar, certifique-se de ter o seguinte:

- Visual Studio ou qualquer outro compilador C# instalado em sua máquina.
- Biblioteca Aspose.PDF para .NET. Você pode baixá-lo do site oficial do Aspose ou usar um gerenciador de pacotes como o NuGet para instalá-lo.

## Etapa 1: configurar o projeto
1. Crie um novo projeto C# em seu ambiente de desenvolvimento preferido.
2. Adicione uma referência à biblioteca Aspose.PDF para .NET.

## Etapa 2: importar namespaces necessários
No arquivo de código onde você deseja extrair parágrafos, adicione o seguinte usando diretivas na parte superior do arquivo:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

## Etapa 3: definir o diretório do documento
 No código, localize a linha que diz`string dataDir = "YOUR DOCUMENT DIRECTORY";` e substitua`"YOUR DOCUMENT DIRECTORY"` com o caminho para o diretório onde seus documentos estão armazenados.

## Passo 4: Abra o documento PDF
 Abra um documento PDF existente usando o`Document`construtor e passando o caminho para o arquivo PDF de entrada.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Etapa 5: extrair parágrafos
 Instancie o`ParagraphAbsorber` classe e usar seu`Visit` método para extrair parágrafos do documento.

```csharp
ParagraphAbsorber absorb = new ParagraphAbsorber();
absorb.Visit(doc);
```

## Etapa 6: iterar pelos parágrafos
Percorra os parágrafos extraídos para acessar o conteúdo do texto. Use loops aninhados para percorrer seções e linhas dentro de cada parágrafo.

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

### Exemplo de código-fonte para extrair parágrafos usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//Abra um arquivo PDF existente
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

## Conclusão
Você extraiu com sucesso parágrafos de um documento PDF usando Aspose.PDF for .NET. Os parágrafos extraídos foram exibidos na janela do console.

### Perguntas frequentes

#### P: Qual é o objetivo deste tutorial?

R: Este tutorial tem como objetivo guiá-lo através do processo de extração de parágrafos de um arquivo PDF usando Aspose.PDF for .NET. O código-fonte C# que acompanha fornece etapas práticas para realizar essa tarefa.

#### P: Quais namespaces devo importar?

R: No arquivo de código onde você pretende extrair parágrafos, inclua o seguinte usando diretivas no início do arquivo:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

#### P: Como especifico o diretório do documento?

 R: Localize a linha`string dataDir = "YOUR DOCUMENT DIRECTORY";` no código e substitua`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório do seu documento.

#### P: Como abro um documento PDF existente?

 R: Na Etapa 4, você abrirá um documento PDF existente usando o`Document` construtor e fornecendo o caminho para o arquivo PDF de entrada.

#### P: Como extraio parágrafos do documento?

 R: A etapa 5 envolve a criação de uma instância do`ParagraphAbsorber` classe e usando seu`Visit` método para extrair parágrafos do documento PDF.

#### P: Como faço para percorrer os parágrafos extraídos?

R: A Etapa 6 orienta você no loop pelos parágrafos extraídos. Loops aninhados são usados para percorrer seções e linhas dentro de cada parágrafo, acessando e exibindo o conteúdo do texto.

#### P: Qual é a principal conclusão deste tutorial?

R: Seguindo este tutorial, você aprendeu como extrair parágrafos de um documento PDF usando Aspose.PDF for .NET. Os parágrafos extraídos foram exibidos na janela do console, fornecendo informações valiosas sobre a estrutura do conteúdo do documento.