---
title: Determinar quebra de tabela em arquivo PDF
linktitle: Determinar quebra de tabela em arquivo PDF
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda como determinar quebras de tabela em arquivos PDF usando Aspose.PDF para .NET.
type: docs
weight: 60
url: /pt/net/programming-with-tables/determine-table-break/
---
Neste tutorial, aprenderemos como determinar quebras de tabela em arquivo PDF usando Aspose.PDF para .NET. Explicaremos o código-fonte em C# passo a passo. No final deste tutorial, você saberá como determinar se uma tabela excede as margens da página. Vamos começar!

## Etapa 1: Configurando o ambiente
Primeiro, certifique-se de ter configurado seu ambiente de desenvolvimento C# com Aspose.PDF para .NET. Adicione a referência à biblioteca e importe os namespaces necessários.

## Etapa 2: Criando o documento PDF
 Nesta etapa, criamos um novo`Document` objeto para representar o documento PDF.

```csharp
pdf-Document = new Document();
```

Este documento será usado para adicionar seções e tabelas.

## Etapa 3: Adicionar uma seção e uma tabela
Agora vamos adicionar uma seção ao nosso documento PDF e criar uma tabela dentro dessa seção.

```csharp
Page page = pdf.Pages.Add();
Table table1 = new Table();
table1. Margin. Top = 300;
page.Paragraphs.Add(table1);
```

Também especificamos uma margem superior de 300 pontos para a tabela. Você pode ajustar esse valor de acordo com suas necessidades.

## Etapa 4: Configuração da tabela
Nesta etapa, configuramos as propriedades da tabela, como larguras e bordas das colunas.

```csharp
table1. ColumnWidths = "100 100 100";
table1.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1F);
table1.Border = new BorderInfo(BorderSide.All, 1F);
```

Aqui definimos a largura das colunas da tabela e as bordas das células. Você pode ajustar esses valores de acordo com suas preferências.

## Etapa 5: adicionar linhas e células à tabela
Agora criaremos linhas e células na tabela usando um loop.

```csharp
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
     Row row1 = table1.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
```

Aqui criamos 17 linhas na tabela e adicionamos três células a cada linha. Você pode ajustar a fivela de acordo com suas necessidades.

## Etapa 6: Determinando quebras de tabela
Agora determinaremos se a tabela excede as margens da página comparando a altura da página com a altura total dos objetos na tabela.

```csharp
float PageHeight = (float)pdf.PageInfo.Height;
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

if ((PageHeight - TotalObjectsHeight) <= 10)
     Console.WriteLine("The height of the page - Height of objects < 10, the table will be truncated");
```

Calculamos a altura da página e a altura total dos objetos levando em conta as margens. Se a diferença for 10 ou menos, a tabela excede as margens da página.

## Etapa 7: Salvando o documento PDF
Por fim, salvamos o documento PDF com os resultados.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
dataDir = dataDir + "DetermineTableBreak_out.pdf";
pdf.Save(dataDir);
Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

Certifique-se de especificar o diretório correto do documento. O arquivo PDF resultante será salvo com as quebras de tabela determinadas.

### Exemplo de código-fonte para Determinar quebra de tabela usando Aspose.PDF para .NET

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instanciar uma classe PDF de objeto
Document pdf = new Document();
// Adicionar a seção à coleção de seções do documento PDF
Aspose.Pdf.Page page = pdf.Pages.Add();
// Instanciar um objeto de tabela
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table1.Margin.Top = 300;
// Adicione a tabela na coleção de parágrafos da seção desejada
page.Paragraphs.Add(table1);
// Conjunto com larguras de coluna da tabela
table1.ColumnWidths = "100 100 100";
// Definir borda de célula padrão usando objeto BorderInfo
table1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// Definir borda da tabela usando outro objeto BorderInfo personalizado
table1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// Crie o objeto MarginInfo e defina suas margens esquerda, inferior, direita e superior
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Defina o preenchimento de célula padrão para o objeto MarginInfo
table1.DefaultCellPadding = margin;
// Se você aumentar o contador para 17, a mesa quebrará
// Porque não pode ser acomodado mais nesta página
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
	// Crie linhas na tabela e depois células nas linhas
	Aspose.Pdf.Row row1 = table1.Rows.Add();
	row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
// Obtenha as informações de altura da página
float PageHeight = (float)pdf.PageInfo.Height;
// Obtenha as informações de altura total da margem superior e inferior da página,
// Margem do tampo da mesa e altura da mesa.
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

// Exibir altura da página, altura da tabela, margem superior da tabela e topo da página
// E informações da margem inferior
Console.WriteLine("PDF document Height = " + pdf.PageInfo.Height.ToString() + "\nTop Margin Info = " + page.PageInfo.Margin.Top.ToString() + "\nBottom Margin Info = " + page.PageInfo.Margin.Bottom.ToString() + "\n\nTable-Top Margin Info = " + table1.Margin.Top.ToString() + "\nAverage Row Height = " + table1.Rows[0].MinRowHeight.ToString() + " \nTable height " + table1.GetHeight().ToString() + "\n ----------------------------------------" + "\nTotal Page Height =" + PageHeight.ToString() + "\nCummulative height including Table =" + TotalObjectsHeight.ToString());

// Verifique se deduzimos a soma da margem superior da página + margem inferior da página
// + Margem superior da tabela e altura da tabela a partir da altura da página e seu menor
// Mais de 10 (uma linha média pode ser maior que 10)
if ((PageHeight - TotalObjectsHeight) <= 10)
	// Se o valor for menor que 10, exiba a mensagem.
	// que mostra que outra linha não pode ser colocada e se adicionarmos uma nova
	// Linha, a tabela irá quebrar. Depende do valor da altura da linha.
	Console.WriteLine("Page Height - Objects Height < 10, so table will break");


dataDir = dataDir + "DetermineTableBreak_out.pdf";
// Salvar o documento pdf
pdf.Save(dataDir);

Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

## Conclusão
Neste tutorial, aprendemos como determinar quebras de tabela em um documento PDF usando Aspose.PDF para .NET. Você pode usar este guia passo a passo para verificar se uma tabela excede as margens da página em seus próprios projetos C#.

### Perguntas frequentes para determinar quebra de tabela em arquivo PDF

#### P: Qual é o propósito de determinar quebras de tabela em um documento PDF?

R: O propósito de determinar quebras de tabela em um documento PDF é verificar se a tabela excede as margens da página. Isso garante que o conteúdo da tabela seja exibido corretamente dentro do espaço de página disponível. Ao detectar quebras de tabela, você pode lidar com o estouro de conteúdo e ajustar o layout da tabela adequadamente.

#### P: Como posso ajustar a margem superior da tabela?

 R: No código-fonte C# fornecido, você pode ajustar a margem superior da tabela modificando o valor do`table1.Margin.Top`propriedade. Aumente ou diminua o valor conforme necessário para definir a margem superior desejada para a tabela.

#### P: Posso personalizar a aparência da tabela, como cores das células e tamanho da fonte?

R: Sim, você pode personalizar a aparência da tabela e suas células usando várias propriedades e métodos fornecidos pelo Aspose.PDF para .NET. Por exemplo, você pode alterar as cores de fundo da célula, tamanho da fonte, família da fonte, alinhamento do texto e muito mais. Consulte a documentação oficial para obter mais informações sobre como personalizar a aparência da tabela.

#### P: O que acontece se a tabela exceder as margens da página?

R: Se a tabela exceder as margens da página, isso pode resultar em truncamento ou sobreposição de conteúdo, tornando o documento PDF menos legível e organizado. Ao detectar quebras de tabela e lidar com o estouro, você pode garantir que o conteúdo permaneça exibido corretamente dentro da área de página disponível.

#### P: Posso determinar quebras de tabela para várias tabelas no mesmo documento PDF?

R: Sim, você pode determinar quebras de tabela para várias tabelas no mesmo documento PDF. Basta repetir as etapas para cada tabela que você deseja analisar e ajustar o layout da tabela conforme necessário para evitar estouro de conteúdo.