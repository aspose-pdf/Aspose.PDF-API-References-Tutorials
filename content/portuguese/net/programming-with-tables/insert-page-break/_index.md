---
title: Inserir quebra de página em arquivo PDF
linktitle: Inserir quebra de página em arquivo PDF
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda como inserir uma quebra de página em um arquivo PDF usando o Aspose.PDF para .NET.
type: docs
weight: 110
url: /pt/net/programming-with-tables/insert-page-break/
---
Neste tutorial, aprenderemos como inserir uma quebra de página em um arquivo PDF usando o Aspose.PDF para .NET. Explicaremos o código-fonte em C# passo a passo. No final deste tutorial, você saberá como adicionar uma quebra de página após um certo número de linhas em uma tabela de um documento PDF. Vamos começar!

## Etapa 1: Configurando o ambiente
Certifique-se de ter configurado seu ambiente de desenvolvimento C# com Aspose.PDF para .NET. Adicione a referência à biblioteca e importe os namespaces necessários.

## Etapa 2: Criando o documento e a tabela
Criamos uma nova instância de Document e adicionamos uma página a esse documento. Em seguida, criamos uma instância de Table para representar nossa tabela no documento PDF. Também definimos os estilos de borda para a tabela.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab. ColumnWidths = "100 100";
```

## Etapa 3: Adicionar linhas à tabela
Usamos um loop para adicionar 200 linhas ao array. Para cada linha, criamos uma instância de Row e adicionamos duas células com conteúdo de texto.

```csharp
for (int counter = 0; counter <= 200; counter++)
{
     Aspose.Pdf.Row row = new Aspose.Pdf.Row();
     tab. Rows. Add(row);
    
     Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
     cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
     row. Cells. Add(cell1);
    
     Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
     cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
     row. Cells. Add(cell2);
    
     // Quando 10 linhas são adicionadas, inserimos uma nova quebra de página
     if (counter % 10 == 0 && counter != 0)
         row. IsInNewPage = true;
}
```

## Etapa 4: Adicionar a tabela ao documento
Adicionamos a tabela à coleção de parágrafos da página do documento.

```csharp
doc.Pages[1].Paragraphs.Add(tab);
```

## Etapa 5: Salve o documento
Salvamos o documento PDF com a quebra de página inserida.

```csharp
doc.Save(dataDir + "InsertPageBreak_out.pdf");
```

### Exemplo de código-fonte para Inserir quebra de página usando Aspose.PDF para .NET

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instanciar instância de documento
Document doc = new Document();
// Adicionar página à coleção de páginas do arquivo PDF
doc.Pages.Add();
// Criar instância de tabela
Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
// Definir estilo de borda para tabela
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// Definir estilo de borda padrão para tabela com cor de borda como Vermelho
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// Especificar largura das colunas da tabela
tab.ColumnWidths = "100 100";
// Crie um loop para adicionar 200 linhas para a tabela
for (int counter = 0; counter <= 200; counter++)
{
	Aspose.Pdf.Row row = new Aspose.Pdf.Row();
	tab.Rows.Add(row);
	Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
	cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
	row.Cells.Add(cell1); Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
	cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
	row.Cells.Add(cell2);
	// Quando 10 linhas são adicionadas, renderize a nova linha em uma nova página
	if (counter % 10 == 0 && counter != 0) row.IsInNewPage = true;
}
// Adicionar tabela à coleção de parágrafos do arquivo PDF
doc.Pages[1].Paragraphs.Add(tab);

dataDir = dataDir + "InsertPageBreak_out.pdf";
// Salvar o documento PDF
doc.Save(dataDir);

Console.WriteLine("\nPage break inserted successfully.\nFile saved at " + dataDir);
```

## Conclusão
Neste tutorial, aprendemos como inserir uma quebra de página em um documento PDF usando Aspose.PDF para .NET. Você pode usar este guia passo a passo para adicionar uma quebra de página após um certo número de linhas em uma tabela em um documento PDF usando C#.

### Perguntas frequentes sobre como inserir quebra de página em arquivo PDF

#### P: Como posso alterar o tamanho das novas páginas criadas após a quebra de página?

 R: Para alterar o tamanho da página para as novas páginas criadas após a quebra de página, você pode definir o`PageSize` propriedade do`Page` objeto. Por exemplo, você pode usar o seguinte código para definir o tamanho da página para A4:

```csharp
// Defina o tamanho da página para A4
doc.Pages[1].SetPageSize(PageSize.A4);
```

#### P: Posso controlar as margens das novas páginas após a quebra de página?

 R: Sim, você pode controlar as margens das páginas novas após a quebra de página. Use o`Margin` propriedade do`Page` objeto para definir as margens da página. Por exemplo, para definir todas as margens para 10 pontos, você pode usar o seguinte código:

```csharp
// Defina todas as margens para 10 pontos
doc.Pages[1].Margin = new MarginInfo(10, 10, 10, 10);
```

#### P: É possível adicionar cabeçalhos e rodapés às novas páginas após a quebra de página?

 R: Sim, você pode adicionar cabeçalhos e rodapés às novas páginas após a quebra de página. Use o`Page.Header` e`Page.Footer` propriedades para adicionar conteúdo às seções de cabeçalho e rodapé da página. Por exemplo:

```csharp
// Adicionar cabeçalho às novas páginas
doc.Pages[1].Header = new HeaderFooter()
{
    Margin = new MarginInfo(10, 10, 10, 10),
    Paragraphs = { new TextFragment("Header content") }
};

// Adicionar rodapé às novas páginas
doc.Pages[1].Footer = new HeaderFooter()
{
    Margin = new MarginInfo(10, 10, 10, 10),
    Paragraphs = { new TextFragment("Footer content") }
};
```

#### P: Posso inserir quebras de página em locais específicos além de um certo número de linhas?

 R: Sim, você pode inserir quebras de página em locais específicos, além de depois de um certo número de linhas. Você pode definir o`IsInNewPage` propriedade de uma linha para`true` para forçar a tabela a iniciar uma nova página depois dessa linha.

#### P: Como posso ajustar o comportamento da quebra de página com base na altura do conteúdo?

 A: Você pode usar o`IsBroken` propriedade da tabela para habilitar ou desabilitar a quebra automática de linhas entre páginas. Quando definido como`true`, permite que as linhas sejam quebradas nas páginas com base na altura do conteúdo.