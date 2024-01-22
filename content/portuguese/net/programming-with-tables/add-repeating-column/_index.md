---
title: Adicionar coluna repetida em documento PDF
linktitle: Adicionar coluna repetida em documento PDF
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como adicionar uma coluna repetida em um documento PDF usando Aspose.PDF for .NET.
type: docs
weight: 20
url: /pt/net/programming-with-tables/add-repeating-column/
---
Neste tutorial, aprenderemos como adicionar uma coluna repetida em um documento PDF usando Aspose.PDF for .NET. Explicaremos o código-fonte em C# passo a passo. Ao final deste tutorial, você saberá como criar uma tabela com coluna repetida em um documento PDF. Vamos começar!

## Passo 1: Configurando o ambiente
Primeiro, certifique-se de configurar seu ambiente de desenvolvimento C# com Aspose.PDF for .NET. Adicione a referência à biblioteca e importe os namespaces necessários.

## Passo 2: Criando o documento PDF
Nesta etapa, criamos um novo documento PDF.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

Criamos um documento PDF vazio onde podemos adicionar conteúdo.

## Etapa 3: Criando as tabelas
Nesta etapa criamos uma tabela principal (`outerTable`) e uma tabela aninhada (`mytable`) que será repetido na coluna.

```csharp
Table outerTable = new Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;

Table mytable = new Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;
```

Especificamos propriedades da tabela, como largura da coluna e modo de quebra de tabela aninhada.

## Passo 4: Adicionando as tabelas ao documento
Agora adicionamos as tabelas criadas ao documento PDF.

```csharp
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
page.Paragraphs.Add(mytable);
```

Primeiro adicionamos a tabela principal (`outerTable`) para o documento PDF. A seguir, adicionamos a tabela aninhada (`mytable` ) como um parágrafo em uma célula da tabela principal. Também especificamos o número de colunas repetidas para`mytable` (neste exemplo, 5 colunas).

## Etapa 5: adicionar cabeçalhos e linhas
Agora adicionamos os cabeçalhos e as linhas à tabela.

```csharp
Row headerRow = mytable.Rows.Add();
headerRow.Cells.Add("header 1");
headerRow.Cells.Add("header 2");
headerRow.Cells.Add("header 3");
// ...
// Adicione outros cabeçalhos aqui

for (int RowCounter = 0; RowCounter <= 5; RowCounter++)
{
     Row row1 = mytable.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
     // ...
     // Adicione as outras colunas aqui
}
```

Primeiro adicionamos os cabeçalhos à primeira linha da tabela (`headerRow`). Em seguida, adicionamos as linhas de dados de um loop. Neste exemplo, adicionamos 6 linhas de dados.

## Passo 6: Salvando o documento PDF
Finalmente, salvamos o documento PDF no arquivo especificado.

```csharp
string outFile = dataDir + "AddRepeatingColumn_out.pdf";
doc.Save(outFile);
```

Certifique-se de especificar o diretório e o nome de arquivo corretos para salvar o arquivo PDF de saída.

### Exemplo de código-fonte para adicionar coluna repetida usando Aspose.PDF para .NET

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

string outFile = dataDir + "AddRepeatingColumn_out.pdf";
// Crie um novo documento
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();

// Instancie uma tabela externa que ocupe a página inteira
Aspose.Pdf.Table outerTable = new Aspose.Pdf.Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;

//Instancie um objeto de tabela que será aninhado dentro de outerTable que irá quebrar dentro da mesma página
Aspose.Pdf.Table mytable = new Aspose.Pdf.Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;

// Adicione o outerTable aos parágrafos da página
// Adicione minha tabela a outerTable
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
page.Paragraphs.Add(mytable);

// Adicionar linha de cabeçalho
Aspose.Pdf.Row row = mytable.Rows.Add();
row.Cells.Add("header 1");
row.Cells.Add("header 2");
row.Cells.Add("header 3");
row.Cells.Add("header 4");
row.Cells.Add("header 5");
row.Cells.Add("header 6");
row.Cells.Add("header 7");
row.Cells.Add("header 11");
row.Cells.Add("header 12");
row.Cells.Add("header 13");
row.Cells.Add("header 14");
row.Cells.Add("header 15");
row.Cells.Add("header 16");
row.Cells.Add("header 17");

for (int RowCounter = 0; RowCounter <= 5; RowCounter++)

{
	// Crie linhas na tabela e depois células nas linhas
	Aspose.Pdf.Row row1 = mytable.Rows.Add();
	row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 4");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 5");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 6");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 7");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 11");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 12");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 13");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 14");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 15");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 16");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 17");
}
doc.Save(outFile);
```

## Conclusão
Neste tutorial, aprendemos como adicionar uma coluna repetida em um documento PDF usando Aspose.PDF for .NET. Você pode usar este guia passo a passo para criar tabelas com colunas repetidas em seus próprios projetos C#.

### Perguntas frequentes sobre como adicionar colunas repetidas em documentos PDF

#### P: Posso personalizar o número de colunas repetidas na tabela aninhada?

 R: Sim, você pode personalizar o número de colunas repetidas na tabela aninhada. No exemplo fornecido, definimos`mytable.RepeatingColumnsCount = 5;`, o que significa que haverá 5 colunas repetidas. Você pode alterar esse valor para qualquer número desejado.

#### P: É possível adicionar mais linhas à tabela aninhada dinamicamente?

R: Sim, você pode adicionar dinamicamente mais linhas à tabela aninhada da mesma forma mostrada no tutorial. Você pode usar loops ou qualquer outra lógica para adicionar linhas com base nos seus dados.

#### P: Posso aplicar estilos e formatação à tabela e suas células?

R: Sim, você pode aplicar estilos e formatação à tabela e suas células usando Aspose.PDF for .NET. A biblioteca fornece várias propriedades e métodos para personalizar a aparência da tabela e seu conteúdo.

#### P: O Aspose.PDF for .NET é compatível com o .NET Core?

R: Sim, Aspose.PDF for .NET é compatível com .NET Core. Você pode usá-lo em aplicativos .NET Framework e .NET Core.

#### P: Posso usar esta abordagem para adicionar colunas repetidas em um documento PDF existente?

R: Sim, você pode usar esta abordagem para adicionar colunas repetidas em um documento PDF existente. Basta carregar o documento existente usando Aspose.PDF for .NET e seguir as mesmas etapas para criar e adicionar a coluna de repetição.