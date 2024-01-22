---
title: Colocando texto ao redor da imagem no arquivo PDF
linktitle: Colocando texto ao redor da imagem no arquivo PDF
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como colocar texto ao redor de uma imagem em arquivo PDF usando Aspose.PDF for .NET.
type: docs
weight: 260
url: /pt/net/programming-with-text/placing-text-around-image/
---
Neste tutorial, explicaremos como colocar texto ao redor de uma imagem em um arquivo PDF usando a biblioteca Aspose.PDF para .NET. Seguiremos o processo passo a passo de criação de uma tabela, adição de uma imagem e posicionamento do texto ao redor da imagem usando o código-fonte C# fornecido.

## Requisitos

Antes de começar, certifique-se de ter o seguinte:

- A biblioteca Aspose.PDF para .NET instalada.
- Uma compreensão básica da programação C#.

## Etapa 1: configurar o diretório de documentos

 Primeiro, você precisa definir o caminho para o diretório onde deseja salvar o arquivo PDF gerado. Substituir`"YOUR DOCUMENT DIRECTORY"` no`dataDir`variável com o caminho para o diretório desejado.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Etapa 2: crie um documento e uma página

 A seguir, criamos um`Document` objeto e adicione uma página a ele usando o`Pages.Add()` método.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Etapa 3: crie uma tabela

 Criamos uma tabela usando o`Table` class e adicione-o à coleção de parágrafos da página.

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
page.Paragraphs.Add(table1);
```

## Etapa 4: definir larguras e margens das colunas da tabela

 Definimos as larguras das colunas da tabela e criamos um`MarginInfo` objeto para definir as margens.

```csharp
table1. ColumnWidths = "120,270";
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;
table1. DefaultCellPadding = margin;
```

## Etapa 5: adicione uma imagem à tabela

 Nós criamos um`Image` objeto, especifique o caminho do arquivo de imagem e defina a altura e largura fixas da imagem. Em seguida, adicionamos a imagem à coleção de parágrafos da célula da tabela.

```csharp
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
logo.File = dataDir + "aspose-logo.jpg";
logo.FixHeight = 120;
logo.FixWidth = 110;
row1.Cells.Add();
row1.Cells[0].Paragraphs.Add(logo);
```

## Etapa 6: adicione texto ao redor da imagem

 Criamos variáveis de string contendo texto formatado em HTML e criamos um`HtmlFragment`objeto. Em seguida, adicionamos o texto HTML à célula da tabela que contém a imagem.

```csharp
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b>Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>" ;

Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
row1.Cells[1].Paragraphs.Add(TitleText);
```

## Etapa 7: adicionar texto adicional

 Criamos outro`HtmlFragment` objeto contendo texto adicional formatado em HTML e adicione-o a uma célula separada da tabela.

```csharp
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
```

## Passo 8: Salve o documento PDF

Finalmente, salvamos o documento PDF no arquivo de saída especificado.

```csharp
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

### Exemplo de código-fonte para colocar texto ao redor da imagem usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instanciar objeto de documento
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Crie uma página no PDF
Aspose.Pdf.Page page = doc.Pages.Add();
// Instanciar um objeto de tabela
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
// Adicione a tabela na coleção de parágrafos da seção desejada
page.Paragraphs.Add(table1);
// Definir com larguras de coluna da tabela
table1.ColumnWidths = "120 270";
// Crie o objeto MarginInfo e defina suas margens esquerda, inferior, direita e superior
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Defina o preenchimento padrão da célula para o objeto MarginInfo
table1.DefaultCellPadding = margin;
// Crie linhas na tabela e depois células nas linhas
Aspose.Pdf.Row row1 = table1.Rows.Add();
// Crie um objeto de imagem
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
// Especifique o caminho do arquivo de imagem
logo.File = dataDir + "aspose-logo.jpg";
// Especifique a altura fixa da imagem
logo.FixHeight = 120;
// Especifique a largura fixa da imagem
logo.FixWidth = 110;
row1.Cells.Add();
// Adicione a imagem à coleção de parágrafos da célula da tabela
row1.Cells[0].Paragraphs.Add(logo);
// Crie variáveis de string com texto contendo tags HTML
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b> Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>";
//Crie um objeto de texto para ser adicionado à direita da imagem
Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
// Adicione os parágrafos de texto contendo texto HTML à célula da tabela
row1.Cells[1].Paragraphs.Add(TitleText);
// Defina o alinhamento vertical do conteúdo da linha como Superior
row1.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
// Crie linhas na tabela e depois células nas linhas
Aspose.Pdf.Row SecondRow = table1.Rows.Add();
SecondRow.Cells.Add();
// Defina o valor do intervalo de linha para a segunda linha como 2
SecondRow.Cells[0].ColSpan = 2;
// Defina o alinhamento vertical da segunda linha como Superior
SecondRow.Cells[0].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
// Adicione os parágrafos de texto contendo texto HTML à célula da tabela
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
// Salve o arquivo PDF
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

## Conclusão

Neste tutorial, você aprendeu como colocar texto ao redor de uma imagem em um documento PDF usando a biblioteca Aspose.PDF para .NET. Seguindo o guia passo a passo e executando o código C# fornecido, você pode criar uma tabela, adicionar uma imagem e posicionar o texto ao redor da imagem em um documento PDF.

### Perguntas frequentes

#### P: Qual é o objetivo do tutorial "Colocar texto ao redor da imagem em arquivo PDF"?

R: O tutorial "Colocando texto ao redor de uma imagem em um arquivo PDF" demonstra como usar a biblioteca Aspose.PDF para .NET para colocar texto ao redor de uma imagem em um documento PDF. O tutorial fornece um guia passo a passo e código-fonte C# para ajudá-lo a criar uma tabela, adicionar uma imagem e posicionar o texto ao redor da imagem.

#### P: Por que eu desejaria colocar texto ao redor de uma imagem em um documento PDF?

R: Colocar texto ao redor de uma imagem melhora a apresentação visual dos seus documentos PDF, tornando-os mais envolventes e informativos. Essa técnica é frequentemente usada em documentos, brochuras, relatórios e outros materiais onde você deseja combinar imagens e texto de uma forma esteticamente agradável.

#### P: Como configuro o diretório de documentos?

R: Para configurar o diretório de documentos:

1.  Substituir`"YOUR DOCUMENT DIRECTORY"` no`dataDir` variável com o caminho para o diretório onde deseja salvar o arquivo PDF gerado.

#### P: Como posso criar uma tabela e adicionar uma imagem a ela?

 R: O tutorial orienta você no processo de criação de uma tabela usando o`Table` classe e adicionando uma imagem à tabela usando o`Image` aula. Você especificará o caminho, a altura e a largura do arquivo de imagem antes de adicioná-lo a uma célula da tabela.

#### P: Como posiciono o texto ao redor da imagem?

 R: Para posicionar o texto ao redor da imagem, você criará um texto formatado em HTML usando o`HtmlFragment` aula. Este texto conterá um título e um corpo de texto. Em seguida, você adicionará esse texto HTML a uma célula da tabela adjacente à célula da imagem.

#### P: Posso personalizar a aparência do texto e da imagem?

R: Sim, você pode personalizar a aparência do texto e da imagem usando tags e propriedades HTML. Por exemplo, você pode definir tamanhos de fonte, cores, estilos e alinhamento do texto. Além disso, você pode ajustar o tamanho e as dimensões da imagem.

#### P: Como faço para salvar o documento PDF?

 R: Depois de adicionar a imagem e o texto à tabela, você pode salvar o documento PDF usando o`Save` método do`Document` aula. Forneça o caminho do arquivo de saída desejado como argumento para o`Save` método.

#### P: Qual é o resultado esperado deste tutorial?

R: Seguindo o tutorial e executando o código C# fornecido, você gerará um documento PDF que demonstra como colocar texto ao redor de uma imagem. O documento de saída conterá uma tabela com uma imagem e um texto posicionados ao seu redor.

#### P: Posso usar diferentes formatos de imagem além de JPG?

 R: Sim, você pode usar diferentes formatos de imagem suportados pela biblioteca Aspose.PDF, como PNG, BMP, GIF e muito mais. Ao criar o`Image` objeto, especifique o caminho do arquivo do formato de imagem desejado.

#### P: É necessária uma licença Aspose válida para este tutorial?

R: Sim, uma licença Aspose válida é necessária para que este tutorial funcione corretamente. Você pode adquirir uma licença completa ou obter uma licença temporária de 30 dias no site Aspose.