---
title: Adicionar objeto SVG em arquivo PDF
linktitle: Adicionar objeto SVG em arquivo PDF
second_title: Referência da API Aspose.PDF para .NET
description: Adicione facilmente objetos SVG em arquivos PDF usando Aspose.PDF para .NET.
type: docs
weight: 30
url: /pt/net/programming-with-tables/add-svg-object/
---
Neste tutorial, aprenderemos como adicionar um objeto SVG em um arquivo PDF usando a biblioteca Aspose.PDF for .NET. SVG (Scalable Vector Graphics) é um formato popular para gráficos vetoriais que pode ser facilmente dimensionado sem perder qualidade. Com Aspose.PDF, você pode adicionar objetos SVG aos seus documentos PDF de forma programática.

## Requisitos

Antes de começarmos, certifique-se de ter o seguinte:

- Visual Studio instalado
- Biblioteca Aspose.PDF para .NET instalada

## Etapa 1: configurar o ambiente

Primeiro, vamos configurar o ambiente criando um novo projeto C# no Visual Studio. Abra o Visual Studio e siga estas etapas:

1. Clique em “Arquivo” > “Novo” > “Projeto” para criar um novo projeto.
2. Selecione o modelo "Aplicativo de console (.NET Framework)" ou "Aplicativo de console (.NET Core)", dependendo da sua configuração.
3. Escolha um nome e local adequados para o seu projeto e clique em “Criar”.

## Etapa 2: criar objetos de documento e imagem

Nesta etapa criaremos os objetos necessários para nosso documento PDF e imagem SVG. Abra o arquivo C# do seu projeto e adicione o seguinte código:

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Objeto Documento Instantâneo
Document doc = new Document();
// Crie uma instância de imagem
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
```

## Etapa 3: definir propriedades da imagem

A seguir, definiremos as propriedades de nossa imagem SVG. Especificaremos o tipo de arquivo como SVG, o caminho para o arquivo SVG e as dimensões da imagem. Adicione o seguinte código após a etapa anterior:

```csharp
// Defina o tipo de imagem como SVG
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// Caminho para o arquivo de origem
img.File = dataDir + "SVGToPDF.svg";
// Definir largura para instância de imagem
img. FixWidth = 50;
// Definir altura para instância de imagem
img.FixHeight = 50;
```

## Etapa 4: criar e configurar a tabela

Agora, vamos criar um objeto de tabela e definir as larguras das colunas. Criaremos uma tabela com duas colunas, cada uma com largura de 100 unidades. Adicione o seguinte código:

```csharp
// Criar tabela de instância
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Definir largura para células da tabela
table. ColumnWidths = "100 100";
```

## Etapa 5: adicionar células à tabela

Nesta etapa, adicionaremos uma linha e células à tabela. Cada linha representa uma linha horizontal na tabela e células são adicionadas às linhas. Adicione o seguinte código:

```csharp
//Crie um objeto de linha e adicione-o à instância da tabela
Aspose.Pdf.Row row = table.Rows.Add();
// Crie um objeto de célula e adicione-o à instância de linha
Aspose.Pdf.Cell cell = row.Cells.Add();
```

## Etapa 6: adicionar texto e imagem às células

A seguir, vamos adicionar o texto e a imagem SVG às células da tabela. Adicionaremos o texto “Primeira célula” à primeira célula e a imagem SVG à segunda célula. Adicione o seguinte código:

```csharp
// Adicionar fragmento de texto à coleção de parágrafos do objeto de célula
cell.Paragraphs.Add(new TextFragment("First cell"));
// Adicione outra célula ao objeto de linha
cell = row. Cells. Add();
// Adicionar imagem SVG à coleção de parágrafos da instância de célula adicionada recentemente
cell.Paragraphs.Add(img);
```

## Etapa 7: crie e adicione uma página ao documento

Agora, vamos criar um objeto de página e adicioná-lo ao documento. A tabela será adicionada à coleção de parágrafos da página. Adicione o seguinte código:

```csharp
// Crie um objeto de página e adicione-o à coleção de páginas da instância do documento
Page page = doc.Pages.Add();
// Adicionar tabela à coleção de parágrafos do objeto de página
page.Paragraphs.Add(table);
```

## Etapa 8: salve o arquivo PDF

Finalmente, salvaremos o arquivo PDF no local especificado. Adicione o seguinte código:

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
// Crie uma instância de imagem
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
// Defina o tipo de imagem como SVG
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// Caminho para o arquivo de origem
img.File = dataDir + "SVGToPDF.svg";
// Definir largura para instância de imagem
img.FixWidth = 50;
// Definir altura para instância de imagem
img.FixHeight = 50;
// Criar instância de tabela
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Definir largura para células da tabela
table.ColumnWidths = "100 100";
//Crie um objeto de linha e adicione-o à instância da tabela
Aspose.Pdf.Row row = table.Rows.Add();
// Crie um objeto de célula e adicione-o à instância de linha
Aspose.Pdf.Cell cell = row.Cells.Add();
// Adicionar fragmento de texto à coleção de parágrafos do objeto de célula
cell.Paragraphs.Add(new TextFragment("First cell"));
// Adicione outra célula ao objeto de linha
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

Neste tutorial, aprendemos como adicionar um objeto SVG a um arquivo PDF usando a biblioteca Aspose.PDF for .NET. Abordamos o processo passo a passo de criação de um documento, configuração do ambiente, adição de uma imagem SVG a uma célula da tabela e salvamento do arquivo PDF. Agora você pode incorporar objetos SVG em seus documentos PDF de forma programática.

### Perguntas frequentes sobre como adicionar objeto SVG em arquivo PDF

#### P: Posso adicionar vários objetos SVG ao documento PDF?

 R: Sim, você pode adicionar vários objetos SVG ao documento PDF. Basta criar e configurar adicionais`Aspose.Pdf.Image` instâncias para cada imagem SVG que você deseja adicionar e, em seguida, adicione-as às células ou parágrafos desejados da tabela no documento PDF.

#### P: Como posso ajustar o tamanho e a posição da imagem SVG na célula da tabela?

 R: Para ajustar o tamanho e a posição da imagem SVG na célula da tabela, você pode modificar o`FixWidth` e`FixHeight` propriedades do`Aspose.Pdf.Image`instância. Você também pode usar outras propriedades como`HorizontalAlignment` e`VerticalAlignment` da célula da tabela para controlar o posicionamento.

#### P: É possível adicionar texto ao lado da imagem SVG na mesma célula da tabela?

 R: Sim, é possível adicionar texto ao lado da imagem SVG na mesma célula da tabela. Você pode usar o`cell.Paragraphs.Add(new TextFragment("Your Text Here"));` método para adicionar texto à célula junto com a imagem SVG.

#### P: Posso adicionar hiperlinks à imagem SVG?

 R: Sim, você pode adicionar hiperlinks à imagem SVG usando o`Hyperlink` propriedade do`Aspose.Pdf.Image` instância. Defina o URL ou ação do hiperlink para tornar a imagem clicável.

#### P: O Aspose.PDF for .NET é compatível com o .NET Core 3.1 ou versões posteriores?

R: Sim, Aspose.PDF for .NET é compatível com .NET Core 3.1 e versões posteriores. Você pode usá-lo em aplicativos .NET Framework e .NET Core.