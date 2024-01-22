---
title: Ocultar números de página no sumário
linktitle: Ocultar números de página no sumário
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como ocultar números de página em um índice usando Aspose.PDF for .NET com este guia passo a passo.
type: docs
weight: 220
url: /pt/net/programming-with-document/hidepagenumbersintoc/
---
Neste artigo, discutiremos a implementação do recurso Ocultar números de página no TOC do Aspose.PDF para .NET usando C#. Começaremos com uma breve introdução ao Aspose.PDF para .NET e depois nos aprofundaremos no guia passo a passo para implementar esse recurso. 

## Introdução ao Aspose.PDF para .NET

Aspose.PDF for .NET é um poderoso componente de manipulação de PDF que permite aos desenvolvedores criar, editar e manipular arquivos PDF programaticamente. Ele oferece uma ampla gama de recursos e funcionalidades que facilitam o trabalho com documentos PDF. Aspose.PDF for .NET oferece suporte a sistemas operacionais de 32 e 64 bits e pode ser usado com plataformas .NET Framework, .NET Core e Xamarin. 

## O que é o recurso Ocultar números de página no TOC?

O Índice (TOC) é uma parte essencial de um documento PDF que fornece aos usuários uma rápida visão geral do conteúdo. Às vezes, os usuários podem querer ocultar os números das páginas no sumário para torná-lo mais fácil de usar. Aspose.PDF for .NET fornece um recurso integrado para ocultar números de páginas no sumário. Este recurso pode ser usado para criar documentos PDF mais fáceis de usar. 

## Pré-requisitos

Para seguir este tutorial, você precisará do seguinte:

- Visual Studio 2010 ou posterior
- Aspose.PDF para .NET instalado em seu sistema
- Conhecimento básico da linguagem de programação C#

## Guia passo a passo para implementar o recurso Ocultar números de página no sumário

Siga as etapas abaixo para implementar o recurso Ocultar números de página no TOC usando Aspose.PDF para .NET:

## Etapa 1: criar um novo aplicativo de console C# no Visual Studio

Abra o Visual Studio e crie um novo aplicativo de console C#.

## Etapa 2: adicionar referência ao Aspose.PDF para .NET

Clique com o botão direito na pasta Referências do seu projeto e selecione Adicionar Referência. Navegue até o local onde o Aspose.PDF for .NET está instalado em seu sistema e adicione uma referência a ele.

## Passo 1: Crie um novo documento PDF

Crie um novo documento PDF usando o seguinte código:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
```

## Etapa 2: crie uma página de índice

Crie uma nova página para o sumário e adicione-a ao documento PDF usando o seguinte código:

```csharp
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
```

## Etapa 3: Adicionar seção de lista à coleção de seções do documento PDF

Adicione a seção da lista à coleção de seções do documento PDF usando o seguinte código:

```csharp
tocPage.TocInfo = tocInfo;
```

## Passo 4: Defina o formato da lista de quatro níveis

Defina o formato da lista de quatro níveis definindo as margens esquerdas e as configurações de formato de texto de cada nível usando o seguinte código:

```csharp
tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
Page page = doc.Pages.Add();
```

## Etapa 5: adicione quatro títulos à seção

```csharp

for (int Level = 1; Level != 5; Level++)
{ 
	Heading heading2 = new Heading(Level); 
	TextSegment segment2 = new TextSegment(); 
	heading2.TocPage = tocPage; 
	heading2.Segments.Add(segment2); 
	heading2.IsAutoSequence = true; 
	segment2.Text = "this is heading of level " + Level; 
	heading2.IsInList = true; 
	page.Paragraphs.Add(heading2); 
}
doc.Save(outFile);

```

### Exemplo de código-fonte para ocultar números de página no sumário usando Aspose.PDF para .NET

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
//Adicione a seção da lista à coleção de seções do documento PDF
tocPage.TocInfo = tocInfo;
//Defina o formato da lista de quatro níveis definindo as margens esquerdas e
//configurações de formato de texto de cada nível

tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
Page page = doc.Pages.Add();
//Adicione quatro títulos na seção
for (int Level = 1; Level != 5; Level++)
	{ 
		Heading heading2 = new Heading(Level); 
		TextSegment segment2 = new TextSegment(); 
		heading2.TocPage = tocPage; 
		heading2.Segments.Add(segment2); 
		heading2.IsAutoSequence = true; 
		segment2.Text = "this is heading of level " + Level; 
		heading2.IsInList = true; 
		page.Paragraphs.Add(heading2); 
	}
doc.Save(outFile);
```

## Conclusão

Neste tutorial, exploramos como trabalhar com metadados XMP em um documento PDF usando Aspose.PDF for .NET. Os metadados XMP fornecem informações valiosas sobre o documento PDF, incluindo título, autor, data de criação e muito mais. Aspose.PDF for .NET permite que os desenvolvedores acessem e manipulem esses metadados, fornecendo uma API flexível e poderosa para trabalhar com documentos PDF.

### Perguntas frequentes

#### P: O que são metadados XMP em um documento PDF?

R: Os metadados XMP (Extensible Metadata Platform) em um documento PDF são um formato padrão para armazenar informações de metadados sobre o documento. Inclui detalhes como título do documento, autor, data de criação, palavras-chave e muito mais. Os metadados XMP fornecem uma maneira estruturada e padronizada de armazenar e compartilhar informações sobre o documento PDF.

#### P: Posso modificar os metadados XMP de um documento PDF usando Aspose.PDF for .NET?

 R: Sim, você pode modificar os metadados XMP de um documento PDF programaticamente usando Aspose.PDF for .NET. Você pode acessar o`Info` propriedade do`Document` objeto, que dá acesso às propriedades de metadados XMP. Você pode então atualizar os valores dessas propriedades para modificar os metadados XMP do documento PDF.

#### P: Posso extrair propriedades de metadados XMP personalizadas de um documento PDF usando Aspose.PDF for .NET?

 R: Sim, você pode extrair propriedades personalizadas de metadados XMP de um documento PDF usando Aspose.PDF for .NET. Você pode usar o`Metadata` propriedade do`Document`objeto, que fornece acesso a todas as propriedades de metadados XMP do documento PDF. Você pode então extrair propriedades customizadas e usar seus valores conforme necessário.