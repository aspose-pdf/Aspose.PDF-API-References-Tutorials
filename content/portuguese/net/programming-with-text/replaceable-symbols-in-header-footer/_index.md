---
title: Símbolos substituíveis no cabeçalho e rodapé
linktitle: Símbolos substituíveis no cabeçalho e rodapé
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda a usar símbolos substituíveis no cabeçalho e rodapé de um documento PDF usando o Aspose.PDF para .NET.
type: docs
weight: 320
url: /pt/net/programming-with-text/replaceable-symbols-in-header-footer/
---
Neste tutorial, explicaremos como usar símbolos substituíveis no cabeçalho e rodapé de um documento PDF usando a biblioteca Aspose.PDF para .NET. Passaremos pelo processo passo a passo de criação de um PDF, configuração de margens, adição de cabeçalho e rodapé com símbolos substituíveis e salvamento do PDF usando o código-fonte C# fornecido.

## Pré-requisitos

Antes de começar, certifique-se de ter o seguinte:

- A biblioteca Aspose.PDF para .NET instalada.
- Uma compreensão básica da programação em C#.

## Etapa 1: Configurar o diretório de documentos

 Primeiro, você precisa definir o caminho para o diretório onde deseja salvar o arquivo PDF gerado. Substituir`"YOUR DOCUMENT DIRECTORY"` no`dataDir` variável com o caminho para o diretório desejado.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Etapa 2: Crie um documento PDF e uma página

 Em seguida, criamos um novo documento PDF e adicionamos uma página a ele usando o`Document` classe e`Page` classe da biblioteca Aspose.PDF.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Etapa 3: Defina as margens

 Definimos as margens da página usando o`MarginInfo` classe. Ajuste os valores de margem de acordo com suas necessidades.

```csharp
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
page.PageInfo.Margin = marginInfo;
```

## Etapa 4: Adicionar cabeçalho com símbolos substituíveis

 Nós criamos um`HeaderFooter` objeto para a página e adicione um`TextFragment` com símbolos substituíveis.

```csharp
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;

TextFragment t1 = new TextFragment("report title");
// Defina as propriedades do texto se desejar
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t1.TextState.LineSpacing = 5f;

hfFirst.Paragraphs.Add(t1);

// Adicione mais TextFragments ou personalize conforme necessário
```

## Etapa 5: Adicionar rodapé com símbolos substituíveis

 Da mesma forma, criamos um`HeaderFooter` objeto para o rodapé da página e adicionar`TextFragment` objetos com símbolos substituíveis.

```csharp
HeaderFooter hfFoot = new HeaderFooter();
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;

TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");

// Adicione mais TextFragments ou personalize conforme necessário

hfFoot.Paragraphs.Add(tab2);
```

## Etapa 6: Salve o documento PDF

Por fim, salvamos o documento PDF no arquivo de saída especificado.

```csharp
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols replaced successfully in the header and footer.\nFile saved at " + dataDir);
```

### Exemplo de código-fonte para símbolos substituíveis no cabeçalho e rodapé usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
//Atribuir a instância marginInfo à propriedade Margin de sec1.PageInfo
page.PageInfo.Margin = marginInfo;
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;
// Instanciar um parágrafo de texto que armazenará o conteúdo a ser exibido como cabeçalho
TextFragment t1 = new TextFragment("report title");
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t1.TextState.LineSpacing = 5f;
hfFirst.Paragraphs.Add(t1);
TextFragment t2 = new TextFragment("Report_Name");
t2.TextState.Font = FontRepository.FindFont("Arial");
t2.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t2.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t2.TextState.LineSpacing = 5f;
t2.TextState.FontSize = 12;
hfFirst.Paragraphs.Add(t2);
// Crie um objeto HeaderFooter para a seção
HeaderFooter hfFoot = new HeaderFooter();
// Defina o objeto HeaderFooter como rodapé ímpar e par
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;
// Adicione um parágrafo de texto contendo o número da página atual ou o número total de páginas
TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");
// Instanciar um objeto de tabela
Table tab2 = new Table();
// Adicione a tabela na coleção de parágrafos da seção desejada
hfFoot.Paragraphs.Add(tab2);
// Conjunto com larguras de coluna da tabela
tab2.ColumnWidths = "165 172 165";
//Crie linhas na tabela e depois células nas linhas
Row row3 = tab2.Rows.Add();
row3.Cells.Add();
row3.Cells.Add();
row3.Cells.Add();
// Defina o alinhamento vertical do texto como centralizado
row3.Cells[0].Alignment = Aspose.Pdf.HorizontalAlignment.Left;
row3.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
row3.Cells[2].Alignment = Aspose.Pdf.HorizontalAlignment.Right;
row3.Cells[0].Paragraphs.Add(t3);
row3.Cells[1].Paragraphs.Add(t4);
row3.Cells[2].Paragraphs.Add(t5);
//Sec1.Paragraphs.Add(New Text("Aspose.Total para Java é uma compilação de todos os componentes Java oferecidos pela Aspose. Ele é compilado em uma#$NL" + "base diária para garantir que ele contenha as versões mais atualizadas de cada um dos nossos componentes Java. #$NL " + "Usando o Aspose.Total para Java, os desenvolvedores podem criar uma ampla gama de aplicativos. #$NL #$NL #$NP" + "Aspose.Total para Java é uma compilação de todos os componentes Java oferecidos pela Aspose. Ele é compilado em uma#$NL" + "base diária para garantir que ele contenha as versões mais atualizadas de cada um dos nossos componentes Java. #$NL " + "Usando o Aspose.Total para Java, os desenvolvedores podem criar uma ampla gama de aplicativos. #$NL #$NL #$NP" + "Aspose.Total para Java é uma compilação de todos os componentes Java oferecidos pela Aspose. Ele é compilado em uma#$NL" + "base diária para garantir que ele contenha as versões mais atualizadas de cada um dos nossos componentes Java. #$NL " + "Usando o Aspose.Total para desenvolvedores Java, é possível criar uma ampla variedade de aplicativos. #$NL #$NL"))
Table table = new Table();
table.ColumnWidths = "33% 33% 34%";
table.DefaultCellPadding = new MarginInfo();
table.DefaultCellPadding.Top = 10;
table.DefaultCellPadding.Bottom = 10;
// Adicione a tabela na coleção de parágrafos da seção desejada
page.Paragraphs.Add(table);
// Definir borda de célula padrão usando objeto BorderInfo
table.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1f);
// Definir borda da tabela usando outro objeto BorderInfo personalizado
table.Border = new BorderInfo(BorderSide.All, 1f);
table.RepeatingRowsCount = 1;
//Crie linhas na tabela e depois células nas linhas
Row row1 = table.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");
const string CRLF = "\r\n";
for (int i = 0; i <= 10; i++)
{
	Row row = table.Rows.Add();
	row.IsRowBroken = true;
	for (int c = 0; c <= 2; c++)
	{
		Cell c1;
		if (c == 2)
			c1 = row.Cells.Add("Aspose.Total for Java is a compilation of every Java component offered by Aspose. It is compiled on a" + CRLF + "daily basis to ensure it contains the most up to date versions of each of our Java components. " + CRLF + "daily basis to ensure it contains the most up to date versions of each of our Java components. " + CRLF + "Using Aspose.Total for Java developers can create a wide range of applications.");
		else
			c1 = row.Cells.Add("item1" + c);
		c1.Margin = new MarginInfo();
		c1.Margin.Left = 30;
		c1.Margin.Top = 10;
		c1.Margin.Bottom = 10;
	}
}
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nSymbols replaced successfully in header and footer.\nFile saved at " + dataDir);
```

## Conclusão

Neste tutorial, você aprendeu como usar símbolos substituíveis no cabeçalho e rodapé de um documento PDF usando a biblioteca Aspose.PDF para .NET. Seguindo o guia passo a passo e executando o código C# fornecido, você pode criar um PDF, definir margens, adicionar cabeçalho e rodapé com símbolos substituíveis e salvar o PDF.

### Perguntas frequentes

#### P: Qual é o objetivo do tutorial "Símbolos substituíveis no cabeçalho e rodapé"?

R: O tutorial "Símbolos substituíveis no cabeçalho e rodapé" tem como objetivo guiá-lo pelo processo de uso da biblioteca Aspose.PDF para .NET para adicionar símbolos substituíveis ao cabeçalho e rodapé de um documento PDF. Símbolos substituíveis permitem que você substitua dinamicamente espaços reservados específicos por valores reais ao gerar o PDF.

#### P: O que são símbolos substituíveis no contexto de um cabeçalho e rodapé de PDF?

R: Símbolos substituíveis são espaços reservados que você pode inserir no cabeçalho e rodapé de um documento PDF. Esses símbolos agem como espaços reservados dinâmicos para valores que podem ser preenchidos em tempo de execução, como números de página, datas e informações personalizadas.

#### P: Por que eu usaria símbolos substituíveis em um cabeçalho e rodapé de PDF?

R: Símbolos substituíveis no cabeçalho e rodapé são úteis quando você deseja incluir informações dinâmicas em seus documentos PDF, como números de página, datas ou outros dados variáveis que podem mudar quando o documento é gerado.

#### P: Como posso definir as margens da página PDF?

 R: Você pode definir as margens da página PDF usando o`MarginInfo` classe e atribuindo-a ao`Margin` propriedade do`PageInfo` da página. Ajuste os valores de margem conforme necessário.

#### P: Como adiciono símbolos substituíveis ao cabeçalho e rodapé?

 R: Você pode adicionar símbolos substituíveis criando um`HeaderFooter` objeto para o cabeçalho e rodapé da página. Então, você pode adicionar`TextFragment`objetos com o texto desejado, incluindo símbolos substituíveis, para o`Paragraphs` coleção do`HeaderFooter` objeto.

#### P: Posso personalizar a aparência dos símbolos substituíveis?

 R: Sim, você pode personalizar a aparência dos símbolos substituíveis modificando as propriedades dos mesmos.`TextFragment` objetos que contêm os símbolos. Você pode definir propriedades como fonte, tamanho da fonte, cor, alinhamento e espaçamento de linha.

#### P: Que tipos de símbolos substituíveis posso usar?

R: Você pode usar uma variedade de símbolos substituíveis, como:

- `$p`: Número da página atual.
- `$P`: Número total de páginas.
- `$d`: Data atual.
- `$t`: Hora atual.
- Espaços reservados personalizados que você define.

#### P: Posso incluir outro texto e formatação em torno dos símbolos substituíveis?

 R: Sim, você pode incluir outros textos e formatações em torno dos símbolos substituíveis dentro do`TextFragment` objetos. Isso permite que você crie cabeçalhos e rodapés mais complexos que incorporam conteúdo dinâmico e estático.

#### P: Como posso salvar o documento PDF gerado?

 R: Para salvar o documento PDF gerado, você pode usar o`Save` método do`Document`classe. Forneça o caminho e o nome do arquivo de saída desejado como argumento.

#### P: É necessária uma licença Aspose válida para este tutorial?

R: Sim, uma Licença Aspose válida é necessária para executar o código com sucesso neste tutorial. Você pode obter uma licença completa ou uma licença temporária de 30 dias no site da Aspose.