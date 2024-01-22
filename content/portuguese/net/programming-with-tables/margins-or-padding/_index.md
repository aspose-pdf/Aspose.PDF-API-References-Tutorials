---
title: Margens ou preenchimento
linktitle: Margens ou preenchimento
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como definir margens ou preenchimento em uma tabela usando Aspose.PDF for .NET.
type: docs
weight: 140
url: /pt/net/programming-with-tables/margins-or-padding/
---
Neste tutorial, iremos guiá-lo através do processo passo a passo de uso do Aspose.PDF for .NET para definir margens ou preenchimento em uma tabela. Forneceremos explicações e trechos de código para ajudá-lo a entender e implementar essa funcionalidade em seu código-fonte C#.

## Etapa 1: configurando o documento e a página
Para começar, você precisa configurar o documento e a página usando o seguinte código:

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instancie o objeto Document chamando seu construtor vazio
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Etapa 2: Criando uma Tabela
A seguir, criaremos um objeto de tabela usando a classe Aspose.Pdf.Table:

```csharp
// Instanciar um objeto de tabela
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Adicione a tabela à coleção de parágrafos da seção desejada
page.Paragraphs.Add(tab1);
```

## Etapa 3: definir larguras de coluna e borda de célula padrão
Para definir as larguras das colunas e a borda padrão das células da tabela, use o seguinte código:

```csharp
// Defina as larguras das colunas da tabela
tab1. ColumnWidths = "50 50 50";
// Defina a borda da célula padrão usando o objeto BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## Etapa 4: definir a borda da tabela e o preenchimento da célula
Para definir a borda da tabela e o preenchimento das células, crie um objeto MarginInfo e defina suas propriedades:

```csharp
// Crie um objeto MarginInfo e defina suas margens esquerda, inferior, direita e superior
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;

// Defina o preenchimento padrão da célula para o objeto MarginInfo
tab1. DefaultCellPadding = margin;

// Defina a borda da tabela usando outro objeto BorderInfo personalizado
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
```

## Etapa 5: adicionar linhas e células
Agora, vamos adicionar linhas e células à tabela. Criaremos uma nova linha e adicionaremos células a ela:

```csharp
// Crie linhas na tabela e depois células nas linhas
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add();
```

## Etapa 6: adicionar texto às células
Para adicionar texto a uma célula, crie um objeto TextFragment e adicione-o à célula desejada:

```csharp
TextFragment mytext = new TextFragment("col3 with large text string");
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
```

## Passo 7: Salvando o PDF
Para salvar o documento PDF, use o seguinte código:

```csharp
dataDir = dataDir + "MarginsOrPadding_out.pdf";
// Salve o PDF
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir);
```

### Exemplo de código-fonte para margens ou preenchimento usando Aspose.PDF para .NET

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instancie o objeto Document chamando seu construtor vazio
Document doc = new Document();
Page page = doc.Pages.Add();
// Instanciar um objeto de tabela
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Adicione a tabela na coleção de parágrafos da seção desejada
page.Paragraphs.Add(tab1);
// Definir com larguras de coluna da tabela
tab1.ColumnWidths = "50 50 50";
// Definir borda de célula padrão usando o objeto BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// Defina a borda da tabela usando outro objeto BorderInfo personalizado
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// Crie o objeto MarginInfo e defina suas margens esquerda, inferior, direita e superior
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Defina o preenchimento padrão da célula para o objeto MarginInfo
tab1.DefaultCellPadding = margin;
// Crie linhas na tabela e depois células nas linhas
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add();
TextFragment mytext = new TextFragment("col3 with large text string");
// Row1.Cells.Add("col3 com string de texto grande para ser colocada dentro da célula");
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
// Linha1.Células[2].Paragrafos[0].FixedWidth= 80;
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
dataDir = dataDir + "MarginsOrPadding_out.pdf";
// Salve o PDF
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir); 
```

## Conclusão
Parabéns! Você aprendeu com sucesso como definir margens ou preenchimento em uma tabela usando Aspose.PDF para .NET. Esse conhecimento o ajudará a aprimorar seus recursos de formatação de documentos e a tornar suas tabelas visualmente atraentes.

### Perguntas frequentes

#### P: Posso definir margens ou preenchimento diferentes para células individuais de uma tabela?

R: Sim, você pode definir margens ou preenchimento diferentes para células individuais em uma tabela usando Aspose.PDF para .NET. No exemplo fornecido, definimos o preenchimento de célula padrão para toda a tabela usando o`DefaultCellPadding` propriedade. Para definir preenchimento diferente para células específicas, você pode acessar o`MarginInfo` de cada célula individualmente e modificar suas margens.

#### P: Como posso alterar a cor ou o estilo da borda da tabela?

 R: Para alterar a cor ou estilo da borda da tabela, você pode modificar o`Color` e`Width` propriedades do`BorderInfo` objeto. No exemplo dado, definimos a cor da borda como preto e uma largura de 1F (um ponto) usando`tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);`. Você pode ajustar a cor e a largura de acordo com suas necessidades.

#### P: É possível adicionar cabeçalhos ou rodapés à tabela?

R: Sim, você pode adicionar cabeçalhos ou rodapés à tabela usando Aspose.PDF for .NET. Cabeçalhos e rodapés normalmente são linhas separadas que contêm informações adicionais, como rótulos de colunas, títulos de tabelas ou dados de resumo. Você pode criar linhas adicionais, estilizá-las de maneira diferente e adicioná-las acima ou abaixo do conteúdo da tabela.

#### P: Como ajusto o alinhamento do texto em uma célula da tabela?

 R: Para ajustar o alinhamento do texto dentro de uma célula da tabela, você pode usar o`HorizontalAlignment` e`VerticalAlignment` propriedades do`TextFragment` objeto. Por exemplo, para centralizar o texto horizontalmente, você pode definir`mytext.HorizontalAlignment = HorizontalAlignment.Center;` . Da mesma forma, você pode definir`mytext.VerticalAlignment` para controlar o alinhamento vertical.

#### P: Posso adicionar imagens às células da tabela em vez de texto?

 R: Sim, você pode adicionar imagens às células da tabela usando Aspose.PDF for .NET. Em vez de criar um`TextFragment` objeto, você pode criar um`Image` objeto, carregue o arquivo de imagem e adicione-o à célula desejada usando o`cell.Paragraphs.Add(image);` método. Isso permite inserir imagens na tabela junto com o conteúdo do texto.