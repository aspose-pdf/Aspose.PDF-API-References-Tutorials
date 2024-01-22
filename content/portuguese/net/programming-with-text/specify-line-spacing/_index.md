---
title: Especifique o espaçamento entre linhas no arquivo PDF
linktitle: Especifique o espaçamento entre linhas no arquivo PDF
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como especificar o espaçamento entre linhas em um arquivo PDF usando Aspose.PDF para .NET.
type: docs
weight: 510
url: /pt/net/programming-with-text/specify-line-spacing/
---
Este tutorial explica como especificar o espaçamento entre linhas em um arquivo PDF usando Aspose.PDF para .NET. O código-fonte C# fornecido demonstra o processo passo a passo.

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
using System.IO;
```

## Etapa 3: Defina o caminho para o diretório do documento

 Defina o caminho para o diretório do seu documento usando o`dataDir` variável:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório do seu documento.

## Passo 4: Carregue o arquivo PDF de entrada

 Carregue o arquivo PDF de entrada usando o`Document` aula:

```csharp
Document doc = new Document();
```

## Etapa 5: criar opções de TextFormatting

 Criar uma`TextFormattingOptions` objeto e defina o modo de espaçamento entre linhas para`FullSize`:

```csharp
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
```

## Etapa 6: crie um TextFragment

 Criar uma`TextFragment` objeto e especifique o conteúdo do texto:

```csharp
TextFragment textFragment = new TextFragment("Hello world");
```

## Etapa 7: carregue o arquivo de fonte (opcional)

 Se você quiser usar uma fonte específica para o texto, carregue o arquivo de fonte TrueType em um arquivo`FileStream` objeto:

```csharp
string fontFile = dataDir + "HPSimplified.TTF";
using (FileStream fontStream = File.OpenRead(fontFile))
{
    textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
}
```

 Substituir`"HPSimplified.TTF"` com o nome real do arquivo da fonte.

## Etapa 8: especifique a posição do texto e o espaçamento entre linhas

 Defina a posição do fragmento de texto e atribua o`TextFormattingOptions` para o`TextState.FormattingOptions` propriedade:

```csharp
textFragment.Position = new Position(100, 600);
textFragment.TextState.FormattingOptions = formattingOptions;
```

## Etapa 9: adicione o texto ao documento

 Adicione o fragmento de texto ao documento, anexando-o a um`TextBuilder` ou diretamente para uma página`Paragraphs` coleção:

```csharp
var page = doc.Pages.Add();
page.Paragraphs.Add(textFragment);
```

## Passo 10: Salve o documento PDF resultante

Salve o documento PDF modificado:

```csharp
dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
doc.Save(dataDir);
```

 Certifique-se de substituir`"SpecifyLineSpacing_out.pdf"` com o nome do arquivo de saída desejado.

### Exemplo de código-fonte para Especificar espaçamento entre linhas usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string fontFile = dataDir + "HPSimplified.TTF";
// Carregar arquivo PDF de entrada
Document doc = new Document();
//Crie TextFormattingOptions com LineSpacingMode.FullSize
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
// Crie um objeto construtor de texto para a primeira página do documento
//TextBuilder textBuilder = new TextBuilder(doc.Pages[1]);
// Crie um fragmento de texto com uma string de amostra
TextFragment textFragment = new TextFragment("Hello world");
if (fontFile != "")
{
	// Carregue a fonte TrueType no objeto stream
	using (FileStream fontStream = System.IO.File.OpenRead(fontFile))
	{
		//Defina o nome da fonte para string de texto
		textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
		// Especifique a posição do fragmento de texto
		textFragment.Position = new Position(100, 600);
		//Defina TextFormattingOptions do fragmento atual como predefinido (que aponta para LineSpacingMode.FullSize)
		textFragment.TextState.FormattingOptions = formattingOptions;
		// Adicione o texto ao TextBuilder para que possa ser colocado sobre o arquivo PDF
		//textBuilder.AppendText(textFragment);
		var page = doc.Pages.Add();
		page.Paragraphs.Add(textFragment);
	}
	dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
	// Salve o documento PDF resultante
	doc.Save(dataDir);
}
```

## Conclusão

Parabéns! Você aprendeu com sucesso como especificar o espaçamento entre linhas em um documento PDF usando Aspose.PDF for .NET. Este tutorial forneceu um guia passo a passo, desde a configuração do projeto até salvar o documento modificado. Agora você pode incorporar esse código em seus próprios projetos C# para personalizar o espaçamento entre linhas de texto em arquivos PDF.

### Perguntas frequentes

#### P: Qual é o objetivo do tutorial "Especificar espaçamento entre linhas em arquivo PDF"?

R: O tutorial "Especificar o espaçamento entre linhas no arquivo PDF" tem como objetivo orientar os usuários sobre como usar a biblioteca Aspose.PDF para .NET para personalizar o espaçamento entre linhas do texto em um documento PDF. O tutorial fornece instruções passo a passo e exemplos de código C# para demonstrar o processo.

#### P: Como este tutorial ajuda a especificar o espaçamento entre linhas em um documento PDF?

R: Este tutorial ajuda os usuários a entender como utilizar os recursos do Aspose.PDF for .NET para especificar o espaçamento entre linhas para texto em um documento PDF. Seguindo as etapas fornecidas e exemplos de código, os usuários podem ajustar o espaçamento entre linhas de acordo com suas preferências.

#### P: Quais pré-requisitos são necessários para seguir este tutorial?

R: Antes de iniciar o tutorial, você deve ter um conhecimento básico da linguagem de programação C#. Além disso, você precisa ter a biblioteca Aspose.PDF for .NET instalada. Você pode obtê-lo no site Aspose ou instalá-lo em seu projeto usando NuGet.

#### P: Como configuro meu projeto para seguir este tutorial?

R: Para começar, crie um novo projeto C# em seu ambiente de desenvolvimento integrado (IDE) preferido e adicione uma referência à biblioteca Aspose.PDF para .NET. Isso permite que você aproveite os recursos da biblioteca para trabalhar com documentos PDF e personalizar o espaçamento entre linhas.

#### P: Posso usar este tutorial para especificar o espaçamento entre linhas para qualquer tipo de texto?

R: Sim, este tutorial fornece instruções sobre como especificar o espaçamento entre linhas para qualquer conteúdo de texto em um documento PDF usando Aspose.PDF for .NET. Você pode usar os exemplos de código fornecidos para ajustar o espaçamento entre linhas do texto de acordo com suas necessidades.

#### P: Como especifico o modo de espaçamento entre linhas no tutorial?

 R: O tutorial demonstra como criar um`TextFormattingOptions` objeto e definir seu`LineSpacing` propriedade para`TextFormattingOptions.LineSpacingMode.FullSize`. Este modo especifica o espaçamento completo entre linhas para o conteúdo do texto.

#### P: Como posso carregar uma fonte específica para o texto?

 R: Se desejar usar uma fonte específica para o conteúdo do texto, o tutorial fornece orientação sobre como carregar um arquivo de fonte TrueType em um arquivo.`FileStream` objeto e defina-o como a fonte para o`TextFragment`. Isso permite que você personalize a fonte do texto junto com o espaçamento entre linhas.

#### P: Como posso personalizar a posição do texto no documento PDF?

 R: Para personalizar a posição do texto, crie um`TextFragment` objeto e definir seu`Position`propriedade para as coordenadas desejadas (X e Y). Isso permite controlar onde o texto é colocado no documento PDF.

#### P: Posso aplicar essas modificações de espaçamento entre linhas a documentos PDF existentes?

 R: Sim, você pode modificar o espaçamento entre linhas de texto em documentos PDF existentes. O tutorial demonstra como criar um`TextFragment` com o espaçamento e posição de linha especificados e, em seguida, adicione-o à página`Paragraphs` coleção.