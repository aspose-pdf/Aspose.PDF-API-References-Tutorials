---
title: Pesquise e obtenha página de texto em arquivo PDF
linktitle: Pesquise e obtenha página de texto em arquivo PDF
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como pesquisar e obter texto de uma página específica em um arquivo PDF usando Aspose.PDF for .NET.
type: docs
weight: 430
url: /pt/net/programming-with-text/search-and-get-text-page/
---
Este tutorial explica como usar Aspose.PDF for .NET para pesquisar e obter texto de uma página específica em um arquivo PDF. O código-fonte C# fornecido demonstra o processo passo a passo.

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

## Passo 3: Carregue o documento PDF

 Defina o caminho para o diretório do seu documento PDF e carregue o documento usando o`Document` aula:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
```

 Certifique-se de substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório do seu documento.

## Etapa 4: pesquise e extraia texto de uma página

 Criar uma`TextFragmentAbsorber`objeto para localizar todas as instâncias da frase de pesquisa de entrada em uma página específica:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
```

 Substituir`"Figure"` com o texto real que você deseja pesquisar.

## Etapa 5: pesquise em uma página específica

Aceite o absorvente para uma página específica do documento:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Etapa 6: obtenha fragmentos de texto extraídos

Obtenha os fragmentos de texto extraídos usando o`TextFragments` propriedade do`TextFragmentAbsorber` objeto:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Etapa 7: percorrer os fragmentos e segmentos de texto

Percorra os fragmentos de texto obtidos e seus segmentos e acesse suas propriedades:

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

Você pode modificar o código dentro do loop para executar ações adicionais em cada segmento de texto.

### Exemplo de código-fonte para página de pesquisa e obtenção de texto usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
// Crie o objeto TextAbsorber para encontrar todas as instâncias da frase de pesquisa de entrada
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
// Aceite o absorvente para todas as páginas
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Obtenha os fragmentos de texto extraídos
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Percorrer os fragmentos
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text : {0} ", textSegment.Text);
		Console.WriteLine("Position : {0} ", textSegment.Position);
		Console.WriteLine("XIndent : {0} ", textSegment.Position.XIndent);
		Console.WriteLine("YIndent : {0} ", textSegment.Position.YIndent);
		Console.WriteLine("Font - Name : {0}", textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible : {0} ", textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded : {0} ", textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset : {0} ", textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size : {0} ", textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color : {0} ", textSegment.TextState.ForegroundColor);
	}
}
```

## Conclusão

Parabéns! Você aprendeu com sucesso como pesquisar e obter texto de uma página específica de um documento PDF usando Aspose.PDF for .NET. Este tutorial forneceu um guia passo a passo, desde o carregamento do documento até o acesso aos segmentos de texto extraídos. Agora você pode incorporar

### Perguntas frequentes

#### P: Qual é o objetivo do tutorial "Pesquisar e obter página de texto"?

R: O tutorial "Pesquisar e obter página de texto" foi projetado para ilustrar como usar a biblioteca Aspose.PDF para .NET para pesquisar e recuperar texto de uma página específica em um arquivo PDF. O tutorial fornece instruções detalhadas e exemplo de código C# para demonstrar o processo.

#### P: Como este tutorial ajuda a extrair texto de uma página específica de um documento PDF?

R: Este tutorial orienta você no processo de extração de texto de uma página específica de um documento PDF usando a biblioteca Aspose.PDF. Ele descreve as etapas necessárias e fornece código C# para pesquisar uma frase de texto especificada na página selecionada e recuperar segmentos de texto associados.

#### P: Quais são os pré-requisitos para seguir este tutorial?

R: Antes de iniciar este tutorial, você deve ter um conhecimento básico da linguagem de programação C#. Além disso, você precisa ter a biblioteca Aspose.PDF for .NET instalada. Você pode obtê-lo no site Aspose ou usar o NuGet para integrá-lo ao seu projeto.

#### P: Como configuro meu projeto para seguir este tutorial?

R: Para começar, crie um novo projeto C# em seu ambiente de desenvolvimento integrado (IDE) preferido e adicione uma referência à biblioteca Aspose.PDF para .NET. Isso permitirá que você utilize os recursos da biblioteca em seu projeto.

#### P: Posso pesquisar texto em uma página específica do documento PDF?

R: Sim, este tutorial demonstra como pesquisar texto em uma página específica de um documento PDF. Envolve usar o`TextFragmentAbsorber` class para localizar instâncias de uma frase de texto específica na página escolhida.

#### P: Como acesso os segmentos de texto extraídos da página específica?

 R: Depois de pesquisar o texto na página designada, você pode acessar os segmentos de texto extraídos usando o`TextSegments` propriedade do`TextFragment` objeto. Esta propriedade fornece acesso a uma coleção de`TextSegment` objetos que contêm o texto extraído e informações relacionadas.

#### P: Que informações posso recuperar dos segmentos de texto extraídos?

R: Você pode recuperar vários detalhes dos segmentos de texto extraídos, incluindo conteúdo do texto, posição (coordenadas X e Y), informações da fonte (nome, tamanho, cor, etc.) e muito mais. O código de exemplo do tutorial demonstra como acessar e imprimir esses detalhes para cada segmento de texto.

#### P: Posso realizar ações personalizadas nos segmentos de texto extraídos?

R: Certamente. Depois de extrair os segmentos de texto, você pode personalizar o código dentro do loop para executar ações adicionais em cada segmento. Isso pode incluir salvar o texto extraído, analisar padrões de texto ou aplicar alterações de formatação.