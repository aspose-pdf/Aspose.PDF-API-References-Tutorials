---
title: Renderizando símbolos substituíveis em arquivo PDF
linktitle: Renderizando símbolos substituíveis em arquivo PDF
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como renderizar símbolos substituíveis em arquivo PDF usando Aspose.PDF para .NET.
type: docs
weight: 310
url: /pt/net/programming-with-text/rendering-replaceable-symbols/
---
Neste tutorial, explicaremos como renderizar símbolos substituíveis em arquivo PDF usando a biblioteca Aspose.PDF para .NET. Passaremos pelo processo passo a passo de criação de um PDF, adição de um fragmento de texto com marcadores de nova linha, configuração de propriedades de texto, posicionamento do texto e salvamento do PDF usando o código-fonte C# fornecido.

## Pré-requisitos

Antes de começar, certifique-se de ter o seguinte:

- A biblioteca Aspose.PDF para .NET instalada.
- Uma compreensão básica da programação C#.

## Etapa 1: configurar o diretório de documentos

 Primeiro, você precisa definir o caminho para o diretório onde deseja salvar o arquivo PDF gerado. Substituir`"YOUR DOCUMENT DIRECTORY"` no`dataDir`variável com o caminho para o diretório desejado.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Etapa 2: crie um documento e uma página PDF

 A seguir, criamos um novo documento PDF e adicionamos uma página a ele usando o`Document` classe e`Page` classe da biblioteca Aspose.PDF.

```csharp
Aspose.Pdf.Document pdfApplicationDoc = new Aspose.Pdf.Document();
Aspose.Pdf.Page applicationFirstPage = (Aspose.Pdf.Page)pdfApplicationDoc.Pages.Add();
```

## Etapa 3: adicionar fragmento de texto com marcadores de nova linha

 Nós criamos um`TextFragment`objeto e definir seu texto para incluir marcadores de nova linha (`Environment.NewLine`) para representar várias linhas de texto.

```csharp
Aspose.Pdf.Text.TextFragment textFragment = new Aspose.Pdf.Text.TextFragment("Applicant Name: " + Environment.NewLine + " Joe Smoe");
```

## Etapa 4: definir propriedades do fragmento de texto

Podemos definir várias propriedades para o fragmento de texto, se desejar, como tamanho da fonte, fonte, cor de fundo e cor de primeiro plano.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
```

## Etapa 5: criar parágrafo e posição de texto

 Nós criamos um`TextParagraph` objeto, anexe o fragmento de texto ao parágrafo e defina a posição do parágrafo na página.

```csharp
TextParagraph par = new TextParagraph();
par.AppendLine(textFragment);
par.Position = new Aspose.Pdf.Text.Position(100, 600);
```

## Etapa 6: adicionar parágrafo de texto à página

 Nós criamos um`TextBuilder` objeto com a página e anexe o parágrafo de texto ao construtor de texto.

```csharp
TextBuilder textBuilder = new TextBuilder(applicationFirstPage);
textBuilder.AppendParagraph(par);
```

## Passo 7: Salve o documento PDF

Finalmente, salvamos o documento PDF no arquivo de saída especificado.

```csharp
dataDir = dataDir + "RenderingReplaceableSymbols_out.pdf";
pdfApplicationDoc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols rendered successfully during PDF creation.\nFile saved at " + dataDir);
```

### Exemplo de código-fonte para renderização de símbolos substituíveis usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document pdfApplicationDoc = new Aspose.Pdf.Document();
Aspose.Pdf.Page applicationFirstPage = (Aspose.Pdf.Page)pdfApplicationDoc.Pages.Add();
// Inicialize o novo TextFragment com texto contendo marcadores de nova linha necessários
Aspose.Pdf.Text.TextFragment textFragment = new Aspose.Pdf.Text.TextFragment("Applicant Name: " + Environment.NewLine + " Joe Smoe");
// Defina propriedades de fragmentos de texto, se necessário
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// Criar objeto TextParagraph
TextParagraph par = new TextParagraph();
// Adicionar novo TextFragment ao parágrafo
par.AppendLine(textFragment);
// Definir posição do parágrafo
par.Position = new Aspose.Pdf.Text.Position(100, 600);
// Criar objeto TextBuilder
TextBuilder textBuilder = new TextBuilder(applicationFirstPage);
// Adicione o TextParagraph usando TextBuilder
textBuilder.AppendParagraph(par);
dataDir = dataDir + "RenderingReplaceableSymbols_out.pdf";
pdfApplicationDoc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols render successfully duing pdf creation.\nFile saved at " + dataDir);
```

## Conclusão

Neste tutorial, você aprendeu como renderizar símbolos substituíveis em um documento PDF usando a biblioteca Aspose.PDF para .NET. Seguindo o guia passo a passo e executando o código C# fornecido, você pode criar um PDF, adicionar texto com marcadores de nova linha, definir propriedades de texto, posicionar o texto na página e salvar o PDF.

### Perguntas frequentes

#### P: Qual é o objetivo do tutorial "Renderizando símbolos substituíveis em arquivo PDF"?

R: O tutorial "Renderizando símbolos substituíveis em arquivo PDF" demonstra como usar a biblioteca Aspose.PDF para .NET para criar um documento PDF que inclua símbolos substituíveis. Esses símbolos são representados como fragmentos de texto com marcadores de nova linha para criar conteúdo multilinha.

#### P: Por que eu desejaria renderizar símbolos substituíveis em um documento PDF?

R: A renderização de símbolos substituíveis é útil quando você precisa gerar dinamicamente conteúdo PDF que inclui informações variáveis ou específicas do usuário. Esses símbolos atuam como espaços reservados que podem ser substituídos por dados reais durante o tempo de execução, como valores de campos de formulário ou detalhes personalizados.

#### P: Como configuro o diretório de documentos?

R: Para configurar o diretório de documentos:

1.  Substituir`"YOUR DOCUMENT DIRECTORY"` no`dataDir` variável com o caminho para o diretório onde deseja salvar o arquivo PDF gerado.

#### P: Como renderizo símbolos substituíveis em um documento PDF usando a biblioteca Aspose.PDF?

R: O tutorial orienta você passo a passo pelo processo:

1.  Crie um novo documento PDF usando o`Document` aula.
2.  Adicione uma página ao documento usando o`Page` aula.
3.  Criar uma`TextFragment` objeto com marcadores de nova linha (`Environment.NewLine`) para representar conteúdo multilinha.
4. Personalize as propriedades do fragmento de texto, como tamanho da fonte, fonte, cor de fundo e cor de primeiro plano.
5.  Criar uma`TextParagraph` objeto, anexe o fragmento de texto a ele e defina a posição do parágrafo na página.
6.  Criar uma`TextBuilder` objeto com a página e anexe o parágrafo de texto a ela.
7. Salve o documento PDF.

#### P: Qual é o propósito de usar marcadores de nova linha (`Environment.NewLine`) in the text fragment?

 R: Os marcadores de nova linha são usados para criar conteúdo multilinha em um único fragmento de texto. Usando`Environment.NewLine`, você pode indicar onde as quebras de linha devem ocorrer no texto.

#### P: Posso personalizar a aparência dos símbolos substituíveis?

R: Sim, você pode personalizar várias propriedades do fragmento de texto, como tamanho da fonte, fonte, cor de fundo e cor de primeiro plano. Estas propriedades determinam a aparência visual dos símbolos substituíveis no documento PDF.

#### P: Como especifico a posição do texto na página?

 R: Você pode definir a posição do texto criando um`TextParagraph` objeto e usando o`Position` propriedade para especificar as coordenadas X e Y na página onde o parágrafo deve ser posicionado.

#### P: Qual é o resultado esperado da execução do código fornecido?

R: Seguindo o tutorial e executando o código C# fornecido, você criará um documento PDF que inclui símbolos substituíveis. Os símbolos substituíveis serão representados como fragmentos de texto com marcadores de nova linha e propriedades personalizadas.

#### P: Posso usar essa abordagem para gerar documentos PDF personalizados de forma dinâmica?

R: Sim, esta abordagem é adequada para gerar documentos PDF de forma dinâmica com informações personalizadas. Ao substituir os símbolos substituíveis por dados reais, você pode criar conteúdo PDF personalizado para cada usuário ou cenário.