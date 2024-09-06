---
title: Pesquisar Expressão Regular em Arquivo PDF
linktitle: Pesquisar Expressão Regular em Arquivo PDF
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda a pesquisar e recuperar texto usando expressões regulares em arquivos PDF usando o Aspose.PDF para .NET.
type: docs
weight: 440
url: /pt/net/programming-with-text/search-regular-expression/
---
Este tutorial explica como usar o Aspose.PDF para .NET para pesquisar e recuperar texto que corresponde a uma expressão regular em um arquivo PDF. O código-fonte C# fornecido demonstra o processo passo a passo.

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
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
```

 Certifique-se de substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório do seu documento.

## Etapa 4: Pesquisar com expressão regular

 Criar um`TextFragmentAbsorber` objeto e defina o padrão de expressão regular para encontrar todas as frases que correspondem ao padrão:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Como 1999-2000
```

 Substituir`"\\d{4}-\\d{4}"` com o padrão de expressão regular desejado.

## Etapa 5: Defina as opções de pesquisa de texto

 Criar um`TextSearchOptions` objeto e defini-lo como`TextSearchOptions` propriedade do`TextFragmentAbsorber` objeto para habilitar o uso de expressão regular:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
```

## Etapa 6: Pesquisar em todas as páginas

Aceite o absorvedor para todas as páginas do documento:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Etapa 7: recuperar fragmentos de texto extraídos

Obtenha os fragmentos de texto extraídos usando o`TextFragments` propriedade do`TextFragmentAbsorber` objeto:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Etapa 8: Percorra os fragmentos de texto

Percorra os fragmentos de texto recuperados e acesse suas propriedades:

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

### Exemplo de código-fonte para Expressão Regular de Pesquisa usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
// Crie um objeto TextAbsorber para encontrar todas as frases que correspondem à expressão regular
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Como 1999-2000
// Defina a opção de pesquisa de texto para especificar o uso de expressão regular
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
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

Parabéns! Você aprendeu com sucesso como pesquisar e recuperar texto que corresponde a uma expressão regular em um documento PDF usando o Aspose.PDF para .NET. Este tutorial forneceu um guia passo a passo, desde o carregamento do documento até o acesso aos fragmentos de texto extraídos. Agora você pode incorporar este código em seus próprios projetos C# para executar pesquisas de texto avançadas em arquivos PDF.

### Perguntas frequentes

#### P: Qual é o objetivo do tutorial "Pesquisar expressão regular em arquivo PDF"?

R: O tutorial "Pesquisar Expressão Regular em Arquivo PDF" tem como objetivo mostrar como usar a biblioteca Aspose.PDF para .NET para pesquisar e extrair texto que corresponda a um padrão de expressão regular especificado dentro de um arquivo PDF. O tutorial fornece orientação abrangente e código C# de exemplo para demonstrar o processo.

#### P: Como este tutorial ajuda na busca de texto usando expressões regulares em um documento PDF?

R: Este tutorial fornece uma abordagem passo a passo para usar a biblioteca Aspose.PDF para conduzir pesquisas de texto em um documento PDF com base em um padrão de expressão regular. Ele detalha como configurar o projeto, carregar o documento PDF, definir um padrão de expressão regular e recuperar os fragmentos de texto correspondentes.

#### P: Quais são os pré-requisitos para seguir este tutorial?

R: Antes de começar este tutorial, você deve ter um entendimento básico da linguagem de programação C#. Além disso, você precisa ter a biblioteca Aspose.PDF for .NET instalada. Você pode obtê-la no site da Aspose ou usar o NuGet para integrá-la ao seu projeto.

#### P: Como configuro meu projeto para seguir este tutorial?

R: Para começar, crie um novo projeto C# no seu ambiente de desenvolvimento integrado (IDE) preferido e adicione uma referência à biblioteca Aspose.PDF for .NET. Isso permitirá que você aproveite os recursos da biblioteca dentro do seu projeto.

#### P: Posso usar expressões regulares para pesquisar texto em um documento PDF?

 R: Sim, este tutorial demonstra como usar expressões regulares para pesquisar e extrair texto de um documento PDF. Ele envolve a utilização de`TextFragmentAbsorber` classe e especificando um padrão de expressão regular para encontrar frases que correspondam ao padrão fornecido.

#### P: Como defino o padrão de expressão regular para pesquisa de texto?

 A: Para definir um padrão de expressão regular para pesquisa de texto, crie um`TextFragmentAbsorber` objeto e definir seu padrão usando o`Text` parâmetro. Substitua o padrão padrão`"\\d{4}-\\d{4}"` no código do tutorial com o padrão de expressão regular desejado.

#### P: Como posso habilitar o uso de expressões regulares para pesquisa de texto?

 A: O uso de expressões regulares é habilitado pela criação de um`TextSearchOptions` objeto e definindo seu valor para`true` . Atribua este objeto ao`TextSearchOptions` propriedade do`TextFragmentAbsorber` instância. Isso garante que o padrão de expressão regular seja aplicado durante a pesquisa de texto.

#### P: Posso recuperar fragmentos de texto que correspondem ao padrão de expressão regular?

 R: Com certeza. Após aplicar a pesquisa de expressão regular no documento PDF, você pode recuperar os fragmentos de texto extraídos usando o`TextFragments` propriedade do`TextFragmentAbsorber` objeto. Esses fragmentos de texto contêm os segmentos de texto que correspondem ao padrão de expressão regular especificado.

#### P: O que posso acessar dos fragmentos de texto recuperados?

R: A partir dos fragmentos de texto recuperados, você pode acessar várias propriedades, como o conteúdo do texto correspondente, posição (coordenadas X e Y), informações de fonte (nome, tamanho, cor) e muito mais. O código de exemplo dentro do loop do tutorial demonstra como acessar e exibir essas propriedades.

#### P: Como posso personalizar ações nos fragmentos de texto extraídos?

R: Depois de extrair os fragmentos de texto, você pode personalizar o código dentro do loop para executar ações adicionais em cada fragmento de texto. Isso pode incluir salvar o texto extraído, analisar padrões ou implementar alterações de formatação com base em seus requisitos.