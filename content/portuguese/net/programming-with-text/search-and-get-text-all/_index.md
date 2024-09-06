---
title: Pesquisar e obter texto tudo
linktitle: Pesquisar e obter texto tudo
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda a pesquisar e obter texto de todas as páginas de um documento PDF usando o Aspose.PDF para .NET.
type: docs
weight: 420
url: /pt/net/programming-with-text/search-and-get-text-all/
---
Este tutorial explica como usar o Aspose.PDF for .NET para pesquisar e obter texto de todas as páginas de um documento PDF. O código-fonte C# fornecido demonstra o processo passo a passo.

## Pré-requisitos

Antes de prosseguir com o tutorial, certifique-se de ter o seguinte:

- Conhecimento básico da linguagem de programação C#.
- Biblioteca Aspose.PDF para .NET instalada. Você pode obtê-la no site da Aspose ou usar o NuGet para instalá-la no seu projeto.

## Etapa 1: Configurar o projeto

Comece criando um novo projeto C# no seu ambiente de desenvolvimento integrado (IDE) preferido e adicione uma referência à biblioteca Aspose.PDF para .NET.

## Etapa 2: Importar os namespaces necessários

Adicione as seguintes diretivas using no início do seu arquivo C# para importar os namespaces necessários:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Etapa 3: Carregue o documento PDF

 Defina o caminho para o diretório do seu documento PDF e carregue o documento usando o`Document` aula:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 Certifique-se de substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório do seu documento.

## Etapa 4: Pesquisar e extrair texto

 Criar um`TextFragmentAbsorber` objeto para encontrar todas as instâncias da frase de pesquisa de entrada:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 Substituir`"text"` com o texto real que você deseja pesquisar.

## Etapa 5: Pesquise em todas as páginas

Aceite o absorvedor para todas as páginas do documento:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Etapa 6: obtenha fragmentos de texto extraídos

Obtenha os fragmentos de texto extraídos usando o`TextFragments` propriedade do`TextFragmentAbsorber` objeto:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Etapa 7: Percorra os fragmentos de texto

Percorra os fragmentos de texto getd e acesse suas propriedades:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
    Console.WriteLine("Text: {0} ", textFragment.Text);
    Console.WriteLine("Position: {0} ", textFragment.Position);
    Console.WriteLine("XIndent: {0} ", textFragment.Position.XIndent);
    Console.WriteLine("YIndent: {0} ", textFragment.Position.YIndent);
    Console.WriteLine("Font - Name: {0}", textFragment.TextState.Font.FontName);
    Console.WriteLine("Font - IsAccessible: {0} ", textFragment.TextState.Font.IsAccessible);
    Console.WriteLine("Font - IsEmbedded: {0} ", textFragment.TextState.Font.IsEmbedded);
    Console.WriteLine("Font - IsSubset: {0} ", textFragment.TextState.Font.IsSubset);
    Console.WriteLine("Font Size: {0} ", textFragment.TextState.FontSize);
    Console.WriteLine("Foreground Color: {0} ", textFragment.TextState.ForegroundColor);
}
```

Você pode modificar o código dentro do loop para executar outras ações em cada fragmento de texto.

### Exemplo de código-fonte para Search And Get Text All usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
// Crie um objeto TextAbsorber para encontrar todas as instâncias da frase de pesquisa de entrada
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Aceite o absorvedor para todas as páginas
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Obtenha os fragmentos de texto extraídos
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Percorrer os fragmentos
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine("Text : {0} ", textFragment.Text);
	Console.WriteLine("Position : {0} ", textFragment.Position);
	Console.WriteLine("XIndent : {0} ", textFragment.Position.XIndent);
	Console.WriteLine("YIndent : {0} ", textFragment.Position.YIndent);
	Console.WriteLine("Font - Name : {0}", textFragment.TextState.Font.FontName);
	Console.WriteLine("Font - IsAccessible : {0} ", textFragment.TextState.Font.IsAccessible);
	Console.WriteLine("Font - IsEmbedded : {0} ", textFragment.TextState.Font.IsEmbedded);
	Console.WriteLine("Font - IsSubset : {0} ", textFragment.TextState.Font.IsSubset);
	Console.WriteLine("Font Size : {0} ", textFragment.TextState.FontSize);
	Console.WriteLine("Foreground Color : {0} ", textFragment.TextState.ForegroundColor);
}
```

## Conclusão

Parabéns! Você aprendeu com sucesso como pesquisar e obter texto de todas as páginas de um documento PDF usando o Aspose.PDF para .NET. Este tutorial forneceu um guia passo a passo, desde o carregamento do documento até o acesso aos fragmentos de texto extraídos. Agora você pode incorporar este código em seus próprios projetos C# para analisar e processar conteúdo de texto em arquivos PDF.

### Perguntas frequentes

#### P: Qual é o objetivo do tutorial "Pesquisar e obter texto completo"?

R: O tutorial "Search And Get Text All" demonstra como utilizar a biblioteca Aspose.PDF para .NET para pesquisar e extrair texto de todas as páginas de um documento PDF. O tutorial fornece instruções passo a passo junto com código C# de exemplo para executar pesquisa e recuperação de texto.

#### P: Como este tutorial ajuda a extrair texto de documentos PDF?

R: Este tutorial o guia pelo processo de extração de texto de todas as páginas de um documento PDF. Ele usa a biblioteca Aspose.PDF para localizar frases de texto específicas e recuperar informações associadas, como posição, propriedades da fonte e cores.

#### P: Quais são os pré-requisitos para seguir este tutorial?

R: Antes de começar este tutorial, você deve ter um entendimento básico da linguagem de programação C#. Além disso, você precisa ter a biblioteca Aspose.PDF for .NET instalada. Você pode obtê-la no site da Aspose ou usar o NuGet para integrá-la ao seu projeto.

#### P: Como configuro meu projeto para seguir este tutorial?

R: Para começar, crie um novo projeto C# no seu ambiente de desenvolvimento integrado (IDE) preferido e adicione uma referência à biblioteca Aspose.PDF for .NET. Isso permitirá que você acesse a funcionalidade da biblioteca no seu projeto.

#### P: Como faço para pesquisar um texto específico em um documento PDF?

 A: Você pode usar o`TextFragmentAbsorber`classe para encontrar instâncias de uma frase de pesquisa específica dentro do documento PDF. Ao criar uma instância desta classe e especificar o texto de destino, você pode capturar todas as ocorrências desse texto.

#### P: Posso pesquisar texto em todas as páginas do documento PDF?

 R: Sim, o tutorial demonstra como pesquisar texto em todas as páginas do documento PDF. O`pdfDocument.Pages.Accept(textFragmentAbsorber)` O método é usado para aceitar o absorvedor para todas as páginas, permitindo que você pesquise o texto desejado em cada página.

#### P: Como acesso os fragmentos de texto extraídos?

 R: Após a busca do texto, você pode acessar os fragmentos de texto extraídos usando o`TextFragments` propriedade do`TextFragmentAbsorber` objeto. Esta propriedade fornece acesso a uma coleção de`TextFragment` objetos que contêm o texto extraído e informações relacionadas.

#### P: Que informações posso recuperar dos fragmentos de texto extraídos?

R: Você pode recuperar vários detalhes dos fragmentos de texto extraídos, como o conteúdo real do texto, posição (coordenadas X e Y), informações de fonte (nome, tamanho, cor, etc.) e muito mais. O código de exemplo do tutorial demonstra como acessar e imprimir esses detalhes.

#### P: Posso executar outras ações nos fragmentos de texto extraídos?

R: Com certeza. Depois de extrair os fragmentos de texto, você pode modificar o código dentro do loop para executar ações personalizadas em cada fragmento. Isso pode incluir salvar o texto extraído, analisar padrões de texto ou aplicar alterações de formatação.