---
title: Renderizar tabela em documento PDF
linktitle: Renderizar tabela em documento PDF
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como exibir uma tabela em um documento PDF usando Aspose.PDF for .NET.
type: docs
weight: 170
url: /pt/net/programming-with-tables/render-table/
---
Neste tutorial, iremos guiá-lo passo a passo para exibir uma tabela em um documento PDF usando Aspose.PDF for .NET. Explicaremos o código-fonte C# fornecido e mostraremos como implementá-lo.

## Passo 1: Criando o documento
Primeiro, criaremos um novo documento PDF:

```csharp
// Caminho para o diretório de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Crie um novo documento
Document doc = new Document();
```

## Etapa 2: configurar margens e orientação da página
A seguir, configuraremos as margens da página e definiremos a orientação para o modo paisagem:

```csharp
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo. Left = 37;
marginInfo. Right = 37;
marginInfo. Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;
```

## Etapa 3: Criando a tabela e as colunas
Agora vamos criar uma tabela e definir as larguras das colunas:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "50 100";
```

## Etapa 4: adicionar linhas e células à tabela
seguir, adicionaremos linhas e células à tabela usando um loop:

```csharp
for (int i = 1; i <= 120; i++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row. FixedRowHeight = 15;
     Aspose.Pdf.Cell cell1 = row.Cells.Add();
     cell1.Paragraphs.Add(new TextFragment("Content 1"));
     Aspose.Pdf.Cell cell2 = row.Cells.Add();
     cell2.Paragraphs.Add(new TextFragment("HHHHH"));
}
```

## Etapa 5: Adicionando a tabela à página
Agora vamos adicionar a tabela à página do documento:

```csharp
Page curPage = doc.Pages.Add();
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs. Add(table);
```

## Etapa 6: exibindo a tabela em uma nova página
A seguir, criaremos uma nova tabela e definiremos a propriedade "IsInNewPage" como "true" para exibir a tabela em uma nova página:

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table. ColumnWidths = "100 100";
for (int i = 1; i <= 10; i++)
{
     Aspose.Pdf.Row row = table1.Rows.Add();
     Aspose.Pdf.Cell cell1 = row.Cells.Add();
     cell1.Paragraphs.Add(new TextFragment("LAAAAAAA"));
     Aspose.Pdf.Cell cell2 = row.Cells.Add();
     cell2.Paragraphs.Add(new TextFragment("LAAGGGGGG"));
}
table1.IsInNewPage = true;
paragraphs. Add(table1);
```

## Passo 7: Salvar PDF
Finalmente, salvamos o documento PDF:

```csharp
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable displayed successfully on a page.\nFile saved at location: " + dataDir);
```

### Exemplo de código-fonte para Render Table usando Aspose.PDF para .NET

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo.Left = 37;
marginInfo.Right = 37;
marginInfo.Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table.ColumnWidths = "50 100";
// Página adicionada.
Page curPage = doc.Pages.Add();
for (int i = 1; i <= 120; i++)
{
	Aspose.Pdf.Row row = table.Rows.Add();
	row.FixedRowHeight = 15;
	Aspose.Pdf.Cell cell1 = row.Cells.Add();
	cell1.Paragraphs.Add(new TextFragment("Content 1"));
	Aspose.Pdf.Cell cell2 = row.Cells.Add();
	cell2.Paragraphs.Add(new TextFragment("HHHHH"));
}
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs.Add(table);
/********************************************/
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table.ColumnWidths = "100 100";
for (int i = 1; i <= 10; i++)
{
	Aspose.Pdf.Row row = table1.Rows.Add();
	Aspose.Pdf.Cell cell1 = row.Cells.Add();
	cell1.Paragraphs.Add(new TextFragment("LAAAAAAA"));
	Aspose.Pdf.Cell cell2 = row.Cells.Add();
	cell2.Paragraphs.Add(new TextFragment("LAAGGGGGG"));
}
table1.IsInNewPage = true;
// Quero manter a tabela 1 na próxima página, por favor...
paragraphs.Add(table1);
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable render successfully on a page.\nFile saved at " + dataDir);
```

## Conclusão
Parabéns! Agora você aprendeu como exibir uma tabela em um documento PDF usando Aspose.PDF for .NET. Este guia passo a passo mostrou como criar um documento, configurar margens e orientação da página, adicionar uma tabela e exibir uma tabela em uma nova página. Agora você pode aplicar esse conhecimento em seus próprios projetos.

### Perguntas frequentes sobre tabela de renderização em documento PDF

#### P: Como posso modificar a aparência da tabela, como alterar as cores das células ou adicionar bordas?

R: Para modificar a aparência da tabela, você pode definir diversas propriedades da tabela.`Aspose.Pdf.Table` e suas células. Por exemplo, você pode definir o`BackgroundColor` propriedade das células para alterar sua cor de fundo. Você também pode definir o`Border` propriedade da tabela ou células individuais para adicionar bordas. Além disso, você pode personalizar a fonte, a cor do texto e o alinhamento do conteúdo da tabela modificando o campo`TextState` do`TextFragment` objetos adicionados às células.

#### P: Posso adicionar cabeçalhos ou rodapés à tabela?

R: Sim, você pode adicionar cabeçalhos ou rodapés à tabela criando linhas adicionais no início ou no final da tabela e definindo o conteúdo apropriado nas células. Você pode personalizar os cabeçalhos ou rodapés independentemente do restante do conteúdo da tabela, adicionando estilos ou conteúdos diferentes a essas linhas específicas.

#### P: Como posso controlar a posição da tabela na página?

 R: Para controlar a posição da tabela na página, você pode ajustar o`MarginInfo` do`PageInfo` objeto. O`MarginInfo`permite definir as margens esquerda, direita, superior e inferior da página, o que afeta o espaço disponível para a tabela. Você também pode usar o`PositioningType` propriedade do`Aspose.Pdf.Table` para controlar seu alinhamento horizontal e vertical dentro da área de conteúdo da página.

#### P: Posso exportar a tabela para diferentes formatos de arquivo, como Excel ou CSV?

R: Aspose.PDF for .NET foi projetado principalmente para trabalhar com documentos PDF. Embora possa exportar o documento PDF como uma imagem ou XPS, não oferece suporte direto à exportação de tabelas para formatos como Excel ou CSV. Para exportar os dados da tabela para diferentes formatos de arquivo, pode ser necessário usar bibliotecas ou métodos adicionais para converter o conteúdo do PDF no formato desejado.

#### P: Como posso adicionar hiperlinks às células da tabela?

 R: Para adicionar hiperlinks às células da tabela, você pode usar o`Aspose.Pdf.WebHyperlink` classe para criar um hiperlink e, em seguida, adicioná-lo como uma âncora ao`TextFragment`dentro da célula. Isso permite associar um URL ou link de destino a um texto ou conteúdo específico dentro da célula, criando hiperlinks clicáveis.