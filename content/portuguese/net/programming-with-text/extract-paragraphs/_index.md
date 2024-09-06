---
title: Extrair parágrafos em arquivo PDF
linktitle: Extrair parágrafos em arquivo PDF
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda a extrair parágrafos em um arquivo PDF usando o Aspose.PDF para .NET.
type: docs
weight: 160
url: /pt/net/programming-with-text/extract-paragraphs/
---
Este tutorial guiará você pelo processo de extração de parágrafos em arquivo PDF usando Aspose.PDF para .NET. O código-fonte C# fornecido demonstra as etapas necessárias.

## Requisitos
Antes de começar, certifique-se de ter o seguinte:

- Visual Studio ou qualquer outro compilador C# instalado em sua máquina.
- Biblioteca Aspose.PDF para .NET. Você pode baixá-la do site oficial do Aspose ou usar um gerenciador de pacotes como o NuGet para instalá-la.

## Etapa 1: Configurar o projeto
1. Crie um novo projeto C# no seu ambiente de desenvolvimento preferido.
2. Adicione uma referência à biblioteca Aspose.PDF para .NET.

## Etapa 2: Importar os namespaces necessários
No arquivo de código onde você deseja extrair os parágrafos, adicione as seguintes diretivas using no topo do arquivo:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

## Etapa 3: Defina o diretório do documento
 No código, localize a linha que diz`string dataDir = "YOUR DOCUMENT DIRECTORY";` e substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho para o diretório onde seus documentos estão armazenados.

## Etapa 4: Abra o documento PDF
 Abra um documento PDF existente usando o`Document` construtor e passando o caminho para o arquivo PDF de entrada.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Etapa 5: Extrair parágrafos
 Instanciar o`ParagraphAbsorber` classe e usar sua`Visit` método para extrair parágrafos do documento.

```csharp
ParagraphAbsorber absorb = new ParagraphAbsorber();
absorb.Visit(doc);
```

## Etapa 6: iterar pelos parágrafos
Faça um loop pelos parágrafos extraídos para acessar o conteúdo do texto. Use loops aninhados para percorrer seções e linhas dentro de cada parágrafo.

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

### Exemplo de código-fonte para Extrair Parágrafos usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abra um arquivo PDF existente
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
Você extraiu parágrafos com sucesso de um documento PDF usando Aspose.PDF for .NET. Os parágrafos extraídos foram exibidos na janela do console.

### Perguntas frequentes

#### P: Qual é o propósito deste tutorial?

R: Este tutorial tem como objetivo guiá-lo pelo processo de extração de parágrafos de um arquivo PDF usando Aspose.PDF para .NET. O código-fonte C# que o acompanha fornece etapas práticas para realizar essa tarefa.

#### P: Quais namespaces devo importar?

R: No arquivo de código onde você pretende extrair os parágrafos, inclua as seguintes diretivas using no início do arquivo:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

#### P: Como especifico o diretório do documento?

 A: Localize a linha`string dataDir = "YOUR DOCUMENT DIRECTORY";` no código e substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório do seu documento.

#### P: Como abro um documento PDF existente?

 R: Na Etapa 4, você abrirá um documento PDF existente usando o`Document` construtor e fornecendo o caminho para o arquivo PDF de entrada.

#### P: Como faço para extrair parágrafos do documento?

 A: A etapa 5 envolve a criação de uma instância do`ParagraphAbsorber` classe e usando seu`Visit` método para extrair parágrafos do documento PDF.

#### P: Como faço para iterar pelos parágrafos extraídos?

R: O passo 6 orienta você a percorrer os parágrafos extraídos em loop. Loops aninhados são usados para percorrer seções e linhas dentro de cada parágrafo, acessando e exibindo o conteúdo do texto.

#### P: Qual é a principal lição deste tutorial?

R: Ao seguir este tutorial, você aprendeu como extrair parágrafos de um documento PDF usando o Aspose.PDF for .NET. Os parágrafos extraídos foram exibidos na janela do console, fornecendo a você informações valiosas sobre a estrutura de conteúdo do documento.