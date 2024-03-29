---
title: Pesquise e obtenha texto tudo
linktitle: Pesquise e obtenha texto tudo
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como pesquisar e obter texto de todas as páginas de um documento PDF usando Aspose.PDF for .NET.
type: docs
weight: 420
url: /pt/net/programming-with-text/search-and-get-text-all/
---
Este tutorial explica como usar Aspose.PDF for .NET para pesquisar e obter texto de todas as páginas de um documento PDF. O código-fonte C# fornecido demonstra o processo passo a passo.

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
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 Certifique-se de substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório do seu documento.

## Etapa 4: pesquise e extraia texto

 Criar uma`TextFragmentAbsorber` objeto para localizar todas as instâncias da frase de pesquisa de entrada:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 Substituir`"text"` com o texto real que você deseja pesquisar.

## Etapa 5: pesquise em todas as páginas

Aceite o absorvedor para todas as páginas do documento:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Etapa 6: obtenha fragmentos de texto extraídos

Obtenha os fragmentos de texto extraídos usando o`TextFragments` propriedade do`TextFragmentAbsorber` objeto:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Etapa 7: percorrer os fragmentos de texto

Percorra os fragmentos de texto obtidos e acesse suas propriedades:

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

Você pode modificar o código dentro do loop para executar ações adicionais em cada fragmento de texto.

### Exemplo de código-fonte para pesquisar e obter texto usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
// Crie o objeto TextAbsorber para encontrar todas as instâncias da frase de pesquisa de entrada
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Aceite o absorvente para todas as páginas
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

Parabéns! Você aprendeu com sucesso como pesquisar e obter texto de todas as páginas de um documento PDF usando Aspose.PDF for .NET. Este tutorial forneceu um guia passo a passo, desde o carregamento do documento até o acesso aos fragmentos de texto extraídos. Agora você pode incorporar esse código em seus próprios projetos C# para analisar e processar conteúdo de texto em arquivos PDF.

### Perguntas frequentes

#### P: Qual é o objetivo do tutorial "Pesquisar e obter texto completo"?

R: O tutorial "Pesquisar e obter texto todo" demonstra como utilizar a biblioteca Aspose.PDF para .NET para pesquisar e extrair texto de todas as páginas de um documento PDF. O tutorial fornece instruções passo a passo junto com código C# de amostra para realizar pesquisa e recuperação de texto.

#### P: Como este tutorial ajuda na extração de texto de documentos PDF?

R: Este tutorial orienta você no processo de extração de texto de todas as páginas de um documento PDF. Ele usa a biblioteca Aspose.PDF para localizar frases de texto específicas e recuperar informações associadas, como posição, propriedades de fonte e cores.

#### P: Quais são os pré-requisitos para seguir este tutorial?

R: Antes de iniciar este tutorial, você deve ter um conhecimento básico da linguagem de programação C#. Além disso, você precisa ter a biblioteca Aspose.PDF for .NET instalada. Você pode obtê-lo no site Aspose ou usar o NuGet para integrá-lo ao seu projeto.

#### P: Como configuro meu projeto para seguir este tutorial?

R: Para começar, crie um novo projeto C# em seu ambiente de desenvolvimento integrado (IDE) preferido e adicione uma referência à biblioteca Aspose.PDF para .NET. Isso permitirá que você acesse a funcionalidade da biblioteca em seu projeto.

#### P: Como pesquiso um texto específico em um documento PDF?

R: Você pode usar o`TextFragmentAbsorber`class para encontrar instâncias de uma frase de pesquisa específica no documento PDF. Ao criar uma instância desta classe e especificar o texto de destino, você pode capturar todas as ocorrências desse texto.

#### P: Posso pesquisar texto em todas as páginas do documento PDF?

 R: Sim, o tutorial demonstra como pesquisar texto em todas as páginas do documento PDF. O`pdfDocument.Pages.Accept(textFragmentAbsorber)` O método é usado para aceitar o absorvedor para todas as páginas, permitindo pesquisar o texto desejado em cada página.

#### P: Como acesso os fragmentos de texto extraídos?

 R: Depois de pesquisar o texto, você pode acessar os fragmentos de texto extraídos usando o`TextFragments` propriedade do`TextFragmentAbsorber` objeto. Esta propriedade fornece acesso a uma coleção de`TextFragment` objetos que contêm o texto extraído e informações relacionadas.

#### P: Que informações posso recuperar dos fragmentos de texto extraídos?

R: Você pode recuperar vários detalhes dos fragmentos de texto extraídos, como o conteúdo real do texto, posição (coordenadas X e Y), informações da fonte (nome, tamanho, cor, etc.) e muito mais. O código de exemplo do tutorial demonstra como acessar e imprimir esses detalhes.

#### P: Posso realizar outras ações nos fragmentos de texto extraídos?

R: Absolutamente. Depois de extrair os fragmentos de texto, você pode modificar o código dentro do loop para executar ações personalizadas em cada fragmento. Isso pode incluir salvar o texto extraído, analisar padrões de texto ou aplicar alterações de formatação.