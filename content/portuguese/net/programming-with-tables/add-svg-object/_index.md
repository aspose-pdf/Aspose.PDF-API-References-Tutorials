---
title: Adicionar objeto SVG em arquivo PDF
linktitle: Adicionar objeto SVG em arquivo PDF
second_title: Referência da API do Aspose.PDF para .NET
description: Adicione facilmente objetos SVG em arquivos PDF usando Aspose.PDF para .NET.
type: docs
weight: 30
url: /pt/net/programming-with-tables/add-svg-object/
---
Neste tutorial, aprenderemos como adicionar um objeto SVG em um arquivo PDF usando a biblioteca Aspose.PDF para .NET. SVG (Scalable Vector Graphics) é um formato popular para gráficos vetoriais que pode ser facilmente dimensionado sem perder qualidade. Com o Aspose.PDF, você pode adicionar objetos SVG aos seus documentos PDF programaticamente.

## Requisitos

Antes de começar, certifique-se de ter o seguinte:

- Visual Studio instalado
- Biblioteca Aspose.PDF para .NET instalada

## Etapa 1: Configurar o ambiente

Primeiro, vamos configurar o ambiente criando um novo projeto C# no Visual Studio. Abra o Visual Studio e siga estas etapas:

1. Clique em "Arquivo" > "Novo" > "Projeto" para criar um novo projeto.
2. Selecione o modelo "Aplicativo de console (.NET Framework)" ou "Aplicativo de console (.NET Core)", dependendo da sua configuração.
3. Escolha um nome e local adequados para seu projeto e clique em "Criar".

## Etapa 2: Criar documentos e objetos de imagem

Nesta etapa, criaremos os objetos necessários para nosso documento PDF e imagem SVG. Abra o arquivo C# do seu projeto e adicione o seguinte código:

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Objeto de documento instantâneo
Document doc = new Document();
// Criar uma instância de imagem
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
```

## Etapa 3: Definir propriedades da imagem

Em seguida, definiremos as propriedades para nossa imagem SVG. Especificaremos o tipo de arquivo como SVG, o caminho para o arquivo SVG e as dimensões da imagem. Adicione o seguinte código após a etapa anterior:

```csharp
// Definir tipo de imagem como SVG
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// Caminho para o arquivo de origem
img.File = dataDir + "SVGToPDF.svg";
// Definir largura para instância de imagem
img. FixWidth = 50;
// Definir altura para instância de imagem
img.FixHeight = 50;
```

## Etapa 4: Crie e configure a tabela

Agora, vamos criar um objeto de tabela e definir as larguras das colunas. Criaremos uma tabela com duas colunas, cada uma com uma largura de 100 unidades. Adicione o seguinte código:

```csharp
// Criar tabela de instância
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Definir largura para células de tabela
table. ColumnWidths = "100 100";
```

## Etapa 5: Adicionar células à tabela

Nesta etapa, adicionaremos uma linha e células à tabela. Cada linha representa uma linha horizontal na tabela, e células são adicionadas às linhas. Adicione o seguinte código:

```csharp
//Crie um objeto de linha e adicione-o à instância da tabela
Aspose.Pdf.Row row = table.Rows.Add();
// Crie um objeto de célula e adicione-o à instância da linha
Aspose.Pdf.Cell cell = row.Cells.Add();
```

## Etapa 6: Adicionar texto e imagem às células

Em seguida, vamos adicionar texto e a imagem SVG às células da tabela. Adicionaremos o texto "First cell" à primeira célula e a imagem SVG à segunda célula. Adicione o seguinte código:

```csharp
// Adicionar fragmento de texto à coleção de parágrafos do objeto de célula
cell.Paragraphs.Add(new TextFragment("First cell"));
// Adicionar outra célula ao objeto de linha
cell = row. Cells. Add();
// Adicionar imagem SVG à coleção de parágrafos da instância de célula adicionada recentemente
cell.Paragraphs.Add(img);
```

## Etapa 7: Crie e adicione uma página ao documento

Agora, vamos criar um objeto de página e adicioná-lo ao documento. A tabela será adicionada à coleção de parágrafos da página. Adicione o seguinte código:

```csharp
// Crie um objeto de página e adicione-o à coleção de páginas da instância do documento
Page page = doc.Pages.Add();
// Adicionar tabela à coleção de parágrafos do objeto de página
page.Paragraphs.Add(table);
```

## Etapa 8: Salve o arquivo PDF

Por fim, salvaremos o arquivo PDF no local especificado. Adicione o seguinte código:

```csharp
dataDir = dataDir + "AddSVGObject_out.pdf";
// Salvar arquivo PDF
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);
```

### Exemplo de código-fonte para adicionar objeto SVG usando Aspose.PDF para .NET

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instanciar objeto Document
Document doc = new Document();
// Criar uma instância de imagem
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
// Definir tipo de imagem como SVG
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// Caminho para o arquivo de origem
img.File = dataDir + "SVGToPDF.svg";
// Definir largura para instância de imagem
img.FixWidth = 50;
// Definir altura para instância de imagem
img.FixHeight = 50;
// Criar instância de tabela
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Definir largura para células de tabela
table.ColumnWidths = "100 100";
//Crie um objeto de linha e adicione-o à instância da tabela
Aspose.Pdf.Row row = table.Rows.Add();
// Crie um objeto de célula e adicione-o à instância da linha
Aspose.Pdf.Cell cell = row.Cells.Add();
// Adicionar fragmento de texto à coleção de parágrafos do objeto de célula
cell.Paragraphs.Add(new TextFragment("First cell"));
// Adicionar outra célula ao objeto de linha
cell = row.Cells.Add();
// Adicionar imagem SVG à coleção de parágrafos da instância de célula adicionada recentemente
cell.Paragraphs.Add(img);
// Crie um objeto de página e adicione-o à coleção de páginas da instância do documento
Page page = doc.Pages.Add();
// Adicionar tabela à coleção de parágrafos do objeto de página
page.Paragraphs.Add(table);

dataDir = dataDir + "AddSVGObject_out.pdf";
// Salvar arquivo PDF
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);            
```

## Conclusão

Neste tutorial, aprendemos como adicionar um objeto SVG a um arquivo PDF usando a biblioteca Aspose.PDF for .NET. Cobrimos o processo passo a passo de criação de um documento, configuração do ambiente, adição de uma imagem SVG a uma célula de tabela e salvamento do arquivo PDF. Agora você pode incorporar objetos SVG em seus documentos PDF programaticamente.

### Perguntas frequentes sobre como adicionar objeto SVG em arquivo PDF

#### P: Posso adicionar vários objetos SVG ao documento PDF?

 R: Sim, você pode adicionar vários objetos SVG ao documento PDF. Basta criar e configurar objetos adicionais`Aspose.Pdf.Image` instâncias para cada imagem SVG que você deseja adicionar e, em seguida, adicione-as às células da tabela ou parágrafos desejados no documento PDF.

#### P: Como posso ajustar o tamanho e a posição da imagem SVG na célula da tabela?

 R: Para ajustar o tamanho e a posição da imagem SVG na célula da tabela, você pode modificar o`FixWidth` e`FixHeight` propriedades do`Aspose.Pdf.Image`instância. Você também pode usar outras propriedades como`HorizontalAlignment` e`VerticalAlignment` da célula da tabela para controlar o posicionamento.

#### P: É possível adicionar texto ao lado da imagem SVG na mesma célula da tabela?

 R: Sim, é possível adicionar texto ao lado da imagem SVG na mesma célula da tabela. Você pode usar o`cell.Paragraphs.Add(new TextFragment("Your Text Here"));` método para adicionar texto à célula junto com a imagem SVG.

#### P: Posso adicionar hiperlinks à imagem SVG?

 R: Sim, você pode adicionar hiperlinks à imagem SVG usando o`Hyperlink` propriedade do`Aspose.Pdf.Image` instância. Defina a URL do hiperlink ou a ação para tornar a imagem clicável.

#### P: O Aspose.PDF para .NET é compatível com o .NET Core 3.1 ou versões posteriores?

R: Sim, o Aspose.PDF para .NET é compatível com o .NET Core 3.1 e versões posteriores. Você pode usá-lo em aplicativos .NET Framework e .NET Core.