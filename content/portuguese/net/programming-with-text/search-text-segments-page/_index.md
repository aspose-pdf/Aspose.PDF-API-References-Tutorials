---
title: Pesquisar página de segmentos de texto em arquivo PDF
linktitle: Pesquisar página de segmentos de texto em arquivo PDF
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como pesquisar segmentos de texto em uma página em arquivo PDF e recuperar suas propriedades usando Aspose.PDF for .NET.
type: docs
weight: 470
url: /pt/net/programming-with-text/search-text-segments-page/
---
Este tutorial explica como usar Aspose.PDF for .NET para pesquisar segmentos de texto específicos em uma página de arquivo PDF e recuperar suas propriedades. O código-fonte C# fornecido demonstra o processo passo a passo.

## Pré-requisitos

Antes de prosseguir com o tutorial, certifique-se de ter o seguinte:

- Conhecimento básico da linguagem de programação C#.
- Biblioteca Aspose.PDF para .NET instalada. Você pode obtê-lo no site Aspose ou usar o NuGet para instalá-lo em seu projeto.

## Etapa 1: configurar o projeto

Comece criando um novo projeto C# em seu ambiente de desenvolvimento integrado (IDE) preferido e adicione uma referência à biblioteca Aspose.PDF para .NET.

## Etapa 2: importe os namespaces necessários

Adicione as seguintes diretivas using no início do arquivo C# para importar os namespaces necessários:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Etapa 3: Defina o caminho para o diretório do documento

 Defina o caminho para o diretório do seu documento usando o`dataDir` variável:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório do seu documento.

## Passo 4: Carregue o documento PDF

 Carregue o documento PDF usando o`Document` aula:

```csharp
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
```

 Substituir`"SearchTextSegmentsPage.pdf"` com o nome real do seu arquivo PDF.

## Etapa 5: crie um TextFragmentAbsorber

 Criar uma`TextFragmentAbsorber` objeto para localizar todas as instâncias da frase de pesquisa de entrada:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 Substituir`"text"` com a frase de pesquisa desejada.

## Etapa 6: escolha o absorvente para uma página específica

Aceite o absorvente para a página desejada do documento:

```csharp
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
```

 Substituir`2` com o número da página desejada (índice baseado em 1).

## Etapa 7: recuperar os segmentos de texto extraídos

 Obtenha os segmentos de texto extraídos usando o`TextFragments` propriedade do`TextFragmentAbsorber` objeto:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Etapa 8: percorrer os segmentos de texto

Percorra os segmentos de texto recuperados e acesse suas propriedades:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text: {0} ", textSegment.Text);
		Console.WriteLine("Position: {0} ", textSegment.Position);
		Console.WriteLine("XIndent: {0} ", textSegment.Position.XIndent);
		Console.WriteLine("YIndent: {0} ", textSegment.Position.YIndent);
		Console.WriteLine("Font - Name: {0}", textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible: {0} ", textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded: {0} ", textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset: {0} ", textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size: {0} ", textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color: {0} ", textSegment.TextState.ForegroundColor);
	}
}
```

Modifique o código dentro do loop para executar ações adicionais em cada segmento de texto, se necessário.

### Exemplo de código-fonte para página de pesquisa de segmentos de texto usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
// Crie o objeto TextAbsorber para encontrar todas as instâncias da frase de pesquisa de entrada
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Aceite o absorvente para todas as páginas
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
// Obtenha os fragmentos de texto extraídos
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Percorrer os fragmentos
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text : {0} ", textSegment.Text);
		Console.WriteLine("Position : {0} ", textSegment.Position);
		Console.WriteLine("XIndent : {0} ",
		textSegment.Position.XIndent);
		Console.WriteLine("YIndent : {0} ",
		textSegment.Position.YIndent);
		Console.WriteLine("Font - Name : {0}",
		textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible : {0} ",
		textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded : {0} ",
		textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset : {0} ",
		textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size : {0} ",
		textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color : {0} ",
		textSegment.TextState.ForegroundColor);
	}
}
```

## Conclusão

Parabéns! Você aprendeu com sucesso como pesquisar segmentos de texto específicos em uma página de um documento PDF usando Aspose.PDF for .NET. Este tutorial forneceu um guia passo a passo, desde o carregamento do documento até o acesso aos segmentos de texto extraídos. Agora você pode incorporar esse código em seus próprios projetos C# para realizar pesquisas avançadas de segmentos de texto em arquivos PDF.

### Perguntas frequentes

#### P: Qual é o objetivo do tutorial "Pesquisar página de segmentos de texto em arquivo PDF"?

R: O tutorial "Pesquisar página de segmentos de texto em arquivo PDF" fornece um guia abrangente sobre como utilizar a biblioteca Aspose.PDF para .NET para pesquisar segmentos de texto específicos em uma página específica de um documento PDF. Abrange o processo de configuração de um projeto, carregamento de um documento PDF, pesquisa de segmentos de texto e recuperação de suas propriedades usando código C#.

#### P: Como este tutorial ajuda na busca por segmentos de texto específicos em um documento PDF?

R: Este tutorial demonstra o processo de localização e extração de segmentos de texto específicos em uma página específica de um documento PDF. Seguindo as etapas e os exemplos de código fornecidos, os usuários podem pesquisar com eficiência os segmentos de texto desejados e recuperar informações sobre suas propriedades.

#### P: Quais pré-requisitos são necessários para seguir este tutorial?

R: Antes de iniciar o tutorial, você deve ter um conhecimento básico da linguagem de programação C#. Além disso, você precisa ter a biblioteca Aspose.PDF for .NET instalada. Você pode obtê-lo no site Aspose ou instalá-lo em seu projeto usando NuGet.

#### P: Como configuro meu projeto para seguir este tutorial?

R: Para começar, crie um novo projeto C# em seu ambiente de desenvolvimento integrado (IDE) preferido e adicione uma referência à biblioteca Aspose.PDF para .NET. Isso permitirá que você utilize os recursos da biblioteca para pesquisar e trabalhar com documentos PDF.

#### P: Posso usar este tutorial para pesquisar segmentos de texto específicos em qualquer página de um PDF?

R: Sim, este tutorial fornece instruções sobre como pesquisar segmentos de texto específicos em uma página selecionada de um documento PDF. Ele orienta os usuários na configuração de um projeto, no carregamento de um PDF e no uso da biblioteca Aspose.PDF para localizar e recuperar propriedades dos segmentos de texto desejados.

#### P: Como especifico o texto que desejo pesquisar neste tutorial?

 R: Para especificar o texto que deseja pesquisar, crie um`TextFragmentAbsorber` objeto e defina seu parâmetro de pesquisa usando o`Text` propriedade. Substitua o padrão`"text"` no código do tutorial com a frase de pesquisa desejada.

#### P: Como recupero propriedades dos segmentos de texto extraídos?

Depois de aceitar o`TextFragmentAbsorber` para uma página específica do PDF, você pode recuperar os segmentos de texto extraídos usando o`TextFragments` propriedade do objeto absorvedor. Isto fornece acesso a uma coleção de fragmentos de texto, cada um contendo vários segmentos de texto.

#### P: Posso personalizar o código para executar ações adicionais em cada segmento de texto?

R: Absolutamente. O código de exemplo do tutorial fornece um loop para iterar pelos segmentos de texto recuperados. Você pode personalizar o código nesse loop para executar ações adicionais em cada segmento de texto, com base nos requisitos do seu projeto.

#### P: Como salvo o documento PDF modificado após extrair segmentos de texto?

R: Este tutorial se concentra principalmente na pesquisa de segmentos de texto e na recuperação de suas propriedades. Se você pretende fazer modificações no PDF, você pode consultar outra documentação do Aspose.PDF para aprender como manipular e salvar o documento com base em suas necessidades específicas.