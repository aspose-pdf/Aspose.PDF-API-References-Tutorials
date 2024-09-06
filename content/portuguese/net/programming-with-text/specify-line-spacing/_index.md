---
title: Especificar espaçamento de linha no arquivo PDF
linktitle: Especificar espaçamento de linha no arquivo PDF
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda como especificar o espaçamento entre linhas em um arquivo PDF usando o Aspose.PDF para .NET.
type: docs
weight: 510
url: /pt/net/programming-with-text/specify-line-spacing/
---
Este tutorial explica como especificar espaçamento de linha em arquivo PDF usando Aspose.PDF para .NET. O código-fonte C# fornecido demonstra o processo passo a passo.

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
using System.IO;
```

## Etapa 3: Defina o caminho para o diretório do documento

 Defina o caminho para o diretório do seu documento usando o`dataDir` variável:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório do seu documento.

## Etapa 4: Carregue o arquivo PDF de entrada

 Carregue o arquivo PDF de entrada usando o`Document` aula:

```csharp
Document doc = new Document();
```

## Etapa 5: Criar TextFormattingOptions

 Criar um`TextFormattingOptions` objeto e defina o modo de espaçamento de linha para`FullSize`:

```csharp
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
```

## Etapa 6: Crie um TextFragment

 Criar um`TextFragment` objeto e especifique o conteúdo do texto:

```csharp
TextFragment textFragment = new TextFragment("Hello world");
```

## Etapa 7: Carregue o arquivo de fonte (opcional)

 Se você quiser usar uma fonte específica para o texto, carregue o arquivo de fonte TrueType em um`FileStream` objeto:

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

## Etapa 9: Adicione o texto ao documento

 Adicione o fragmento de texto ao documento, anexando-o a um`TextBuilder` ou diretamente para uma página`Paragraphs` coleção:

```csharp
var page = doc.Pages.Add();
page.Paragraphs.Add(textFragment);
```

## Etapa 10: Salve o documento PDF resultante

Salve o documento PDF modificado:

```csharp
dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
doc.Save(dataDir);
```

 Certifique-se de substituir`"SpecifyLineSpacing_out.pdf"` com o nome do arquivo de saída desejado.

### Código-fonte de exemplo para Especificar espaçamento de linha usando Aspose.PDF para .NET 
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
//TextBuilder textBuilder = novo TextBuilder(doc.Pages[1]);
// Criar fragmento de texto com string de amostra
TextFragment textFragment = new TextFragment("Hello world");
if (fontFile != "")
{
	// Carregue a fonte TrueType no objeto de fluxo
	using (FileStream fontStream = System.IO.File.OpenRead(fontFile))
	{
		// Defina o nome da fonte para a sequência de texto
		textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
		//Especifique a posição para o Fragmento de Texto
		textFragment.Position = new Position(100, 600);
		//Defina TextFormattingOptions do fragmento atual como predefinido (que aponta para LineSpacingMode.FullSize)
		textFragment.TextState.FormattingOptions = formattingOptions;
		// Adicione o texto ao TextBuilder para que ele possa ser colocado sobre o arquivo PDF
		//textBuilder.AppendText(textFragment);
		var page = doc.Pages.Add();
		page.Paragraphs.Add(textFragment);
	}
	dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
	// Salvar documento PDF resultante
	doc.Save(dataDir);
}
```

## Conclusão

Parabéns! Você aprendeu com sucesso como especificar o espaçamento de linha em um documento PDF usando o Aspose.PDF para .NET. Este tutorial forneceu um guia passo a passo, desde a configuração do projeto até o salvamento do documento modificado. Agora você pode incorporar este código em seus próprios projetos C# para personalizar o espaçamento de linha do texto em arquivos PDF.

### Perguntas frequentes

#### P: Qual é o objetivo do tutorial "Especificar espaçamento entre linhas no arquivo PDF"?

R: O tutorial "Especificar espaçamento de linha em arquivo PDF" tem como objetivo orientar os usuários sobre como usar a biblioteca Aspose.PDF para .NET para personalizar o espaçamento de linha do texto em um documento PDF. O tutorial fornece instruções passo a passo e exemplos de código C# para demonstrar o processo.

#### P: Como este tutorial ajuda a especificar o espaçamento entre linhas em um documento PDF?

R: Este tutorial ajuda os usuários a entender como utilizar os recursos do Aspose.PDF for .NET para especificar o espaçamento de linha para texto em um documento PDF. Seguindo as etapas e exemplos de código fornecidos, os usuários podem ajustar o espaçamento de linha de acordo com suas preferências.

#### P: Quais são os pré-requisitos necessários para seguir este tutorial?

R: Antes de começar o tutorial, você deve ter um entendimento básico da linguagem de programação C#. Além disso, você precisa ter a biblioteca Aspose.PDF for .NET instalada. Você pode obtê-la no site da Aspose ou instalá-la em seu projeto usando o NuGet.

#### P: Como configuro meu projeto para seguir este tutorial?

R: Para começar, crie um novo projeto C# no seu ambiente de desenvolvimento integrado (IDE) preferido e adicione uma referência à biblioteca Aspose.PDF for .NET. Isso permite que você aproveite os recursos da biblioteca para trabalhar com documentos PDF e personalizar o espaçamento entre linhas.

#### P: Posso usar este tutorial para especificar o espaçamento entre linhas para qualquer tipo de texto?

R: Sim, este tutorial fornece instruções sobre como especificar o espaçamento de linha para qualquer conteúdo de texto dentro de um documento PDF usando o Aspose.PDF para .NET. Você pode usar os exemplos de código fornecidos para ajustar o espaçamento de linha do texto de acordo com suas necessidades.

#### P: Como especifico o modo de espaçamento de linha no tutorial?

 R: O tutorial demonstra como criar um`TextFormattingOptions` objeto e definir seu`LineSpacing` propriedade para`TextFormattingOptions.LineSpacingMode.FullSize`. Este modo especifica o espaçamento total entre linhas para o conteúdo do texto.

#### P: Como posso carregar uma fonte específica para o texto?

 R: Se você deseja usar uma fonte específica para o conteúdo do texto, o tutorial fornece orientações sobre como carregar um arquivo de fonte TrueType em um`FileStream` objeto e defini-lo como a fonte para o`TextFragment`. Isso permite que você personalize a fonte do texto junto com o espaçamento entre linhas.

#### P: Como posso personalizar a posição do texto no documento PDF?

 A: Para personalizar a posição do texto, crie um`TextFragment` objeto e definir seu`Position`propriedade para as coordenadas desejadas (X e Y). Isso permite que você controle onde o texto é colocado dentro do documento PDF.

#### P: Posso aplicar essas modificações de espaçamento de linha a documentos PDF existentes?

 R: Sim, você pode modificar o espaçamento de linha para texto em documentos PDF existentes. O tutorial demonstra como criar um`TextFragment` com o espaçamento e a posição de linha especificados e, em seguida, adicioná-lo à página`Paragraphs` coleção.