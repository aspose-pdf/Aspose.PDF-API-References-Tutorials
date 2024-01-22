---
title: Exportar dados da planilha do Excel para tabela
linktitle: Exportar dados da planilha do Excel para tabela
second_title: Referência da API Aspose.PDF para .NET
description: Exporte dados de uma planilha Excel para uma tabela PDF usando Aspose.PDF for .NET.
type: docs
weight: 70
url: /pt/net/programming-with-tables/export-excel-worksheet-data-to-table/
---
Neste tutorial, aprenderemos como exportar dados de uma planilha Excel e criar uma tabela em um documento PDF usando a biblioteca Aspose.PDF for .NET. Percorreremos o código-fonte passo a passo e explicaremos cada seção em detalhes. Ao final deste tutorial, você será capaz de gerar arquivos PDF com tabelas contendo dados de planilhas Excel. Vamos começar!

## Requisitos
Antes de começarmos, certifique-se de ter o seguinte:

- Conhecimento básico da linguagem de programação C#
- Visual Studio instalado em sua máquina
- Biblioteca Aspose.PDF para .NET adicionada ao seu projeto

## Etapa 1: Configurando o Ambiente
Para começar, crie um novo projeto C# no Visual Studio. Adicione a referência à biblioteca Aspose.PDF para .NET clicando com o botão direito do mouse em seu projeto no Solution Explorer, selecionando "Gerenciar pacotes NuGet" e procurando por "Aspose.PDF". Instale o pacote e você estará pronto para começar.

## Etapa 2: Carregando a planilha do Excel
Na primeira etapa do nosso código, definimos o caminho para o diretório que contém o documento Excel. Substitua "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho real do diretório onde seu arquivo Excel está localizado.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
```

Aqui, usamos a biblioteca Aspose.Cells para carregar a pasta de trabalho do Excel. Certifique-se de substituir “newBook1.xlsx” pelo nome do seu arquivo Excel.

## Etapa 3: acessando a planilha
 A seguir, precisamos acessar a primeira planilha do arquivo Excel. Fazemos isso usando o`Worksheets` coleção do`Workbook` objeto.

```csharp
// Acessando a primeira planilha do arquivo Excel
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
```

 Se o seu arquivo Excel contiver várias planilhas, você poderá alterar o valor do índice`[0]` para acessar uma planilha diferente.

## Etapa 4: exportando dados para DataTable
 Agora, exportaremos o conteúdo da planilha Excel para um`DataTable` objeto. Especificamos o intervalo de células a exportar usando o`ExportDataTable` método.

```csharp
// Exportando o conteúdo de 7 linhas e 2 colunas começando da 1ª célula para DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);
```

Neste exemplo, exportamos todas as linhas e colunas começando da primeira célula (0, 0) até a última célula da planilha. Defina o intervalo apropriado com base em seus requisitos.

## Passo 5: Criando um Documento PDF
Agora, criaremos um novo documento PDF usando a biblioteca Aspose.PDF.

```csharp
// Instanciar uma instância de Documento
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

Isso cria um documento PDF vazio onde podemos adicionar conteúdo.

## Etapa 6: adicionar uma página e uma tabela
Para exibir os dados em formato de tabela, precisamos adicionar uma página e uma tabela ao documento PDF.

```csharp
// Crie uma página na instância do documento
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// Crie um objeto Tabela
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Adicione o objeto Tabela na coleção de parágrafos da seção
sec1.Paragraphs.Add(tab1);
```

Aqui, criamos uma nova página e um objeto de tabela. Em seguida, adicionamos a tabela à coleção de parágrafos da página.

## Etapa 7: definindo as propriedades da tabela
Antes de importar os dados, precisamos definir algumas propriedades da tabela, como larguras de colunas e bordas de células padrão.

```csharp
// Defina as larguras das colunas da tabela
tab1.ColumnWidths = "40 100 100";

// Defina a borda da célula padrão da tabela usando o objeto BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

Neste exemplo, definimos as larguras das colunas para 40, 100 e 100 unidades. Ajuste os valores com base nos seus dados. Também definimos a borda da célula padrão para exibir bordas em todos os lados de cada célula.

## Passo 8: Importando Dados para a Tabela
 Agora, importaremos os dados do`DataTable` objeto na tabela usando o`ImportDataTable` método.

```csharp
// Importe dados para o objeto Table do DataTable criado acima
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
```

 Aqui, especificamos o intervalo de linhas e colunas a serem importadas. Neste exemplo, importamos todas as linhas e colunas do`dataTable` objeto.

## Passo 9: Formatando a Tabela
Para melhorar a aparência da tabela, podemos aplicar formatação a células ou linhas específicas. Nesta etapa, formataremos a primeira linha e as linhas alternativas da tabela.

```csharp
// Obtenha a primeira linha da tabela
Aspose.Pdf.Row row1 = tab1.Rows[0];

// Formate a primeira linha
foreach(Aspose.Pdf.Cell curCell in row1.Cells)
{
     // Defina a cor de fundo das células na primeira linha
     curCell.BackgroundColor = Color.Blue;// Defina a face das células na primeira linha
     curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
    
     // Defina a cor da fonte das células na primeira linha
     curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
    
     // Defina o alinhamento do texto para as células da primeira linha
     curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

// Formato de linha alternativo
for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
     foreach(Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
     {
         // Defina a cor de fundo das células em linhas alternadas
         curCell.BackgroundColor = Color.Gray;
        
         // Defina a cor do texto das células em linhas alternadas
         curCell.DefaultCellTextState.ForegroundColor = Color.White;
     }
}
```

Aqui, iteramos pelas células da primeira linha e definimos a cor de fundo, o tipo da fonte, a cor da fonte e o alinhamento do texto. Em seguida, iteramos por todas as células nas linhas alternativas e definimos o plano de fundo e a cor do texto.

## Passo 10: Salvando o Documento PDF
Finalmente, salvamos o documento PDF no local especificado.

```csharp
// Salve o PDF
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

Certifique-se de substituir "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho do diretório e nome de arquivo desejado para o arquivo PDF de saída.

### Exemplo de código-fonte para exportar dados de planilha do Excel para tabela usando Aspose.PDF para .NET

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
// Acessando a primeira planilha do arquivo Excel
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
// Exportando o conteúdo de 7 linhas e 2 colunas começando da 1ª célula para DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);

// Instanciar uma instância de documento
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
// Crie uma página na instância do documento
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// Crie um objeto Tabela
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Adicione o objeto Tabela na coleção de parágrafos da seção
sec1.Paragraphs.Add(tab1);

// Defina as larguras das colunas da tabela. Precisamos especificar o ColumnCount manualmente.
// Como a planilha Excel atual possui três colunas, estamos especificando a mesma contagem
tab1.ColumnWidths = "40 100 100";

// Defina a borda da célula padrão da tabela usando o objeto BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Importe dados para o objeto Table do DataTable criado acima
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
// Obtenha a primeira linha da tabela
Aspose.Pdf.Row row1 = tab1.Rows[0];

// Itere por todas as células na primeira linha e defina a cor de fundo como azul
foreach (Aspose.Pdf.Cell curCell in row1.Cells)
{
	// Defina o plano de fundo de todas as células da primeira linha da tabela.
	curCell.BackgroundColor = Color.Blue;
	// Defina o tipo de fonte para as células da 1ª linha da tabela.
	curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
	// Defina a cor da fonte de todas as células da primeira linha da tabela.
	curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
	// Defina o alinhamento do texto para as células da 1ª linha como Centro.
	curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
	// Itere por todas as células na primeira linha e defina a cor de fundo como azul
	foreach (Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
	{
		// Defina a cor de fundo de todas as células, exceto da primeira linha.
		curCell.BackgroundColor = Color.Gray;
		// Defina a cor do texto de todas as células, exceto a primeira linha.
		curCell.DefaultCellTextState.ForegroundColor = Color.White;
	}
}

// Salve o PDF
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

## Conclusão
Neste tutorial, aprendemos como exportar dados de uma planilha Excel para uma tabela PDF usando a biblioteca Aspose.PDF for .NET. Abordamos o processo passo a passo de carregamento da planilha do Excel, criação de um documento PDF, adição de uma tabela, importação de dados e formatação da tabela. Agora você pode gerar arquivos PDF com tabelas contendo dados do Excel de forma programática.

### Perguntas frequentes

#### P: Qual é o propósito de exportar dados de planilhas do Excel para uma tabela PDF?

R: Exportar dados de planilhas do Excel para uma tabela PDF permite apresentar os dados em um formato estruturado e organizado. Ele permite gerar arquivos PDF com tabelas que contêm dados de planilhas do Excel, facilitando o compartilhamento e a preservação de informações em formato de documento portátil.

#### P: Posso personalizar a aparência da tabela PDF?

R: Sim, você pode personalizar a aparência da tabela PDF usando várias propriedades fornecidas pelo Aspose.PDF for .NET. No código-fonte C# fornecido, você pode modificar as larguras das colunas, bordas das células, alinhamento do texto, estilo da fonte e muito mais para atender aos seus requisitos específicos.

#### P: Como posso lidar com arquivos Excel com várias planilhas?

 R: No código C# fornecido, acessamos a primeira planilha do arquivo Excel usando o índice`[0]` . Se o seu arquivo Excel contiver várias planilhas, você poderá acessá-las alterando o valor do índice de acordo, como`[1]` para a segunda planilha ou`[2]` para a terceira planilha.

#### P: Posso aplicar formatação diferente a linhas ou células específicas na tabela PDF?

R: Sim, você pode aplicar formatação diferente a linhas ou células específicas na tabela PDF. No código-fonte C# fornecido, demonstramos como formatar a primeira linha e as linhas alternativas de maneira diferente, alterando a cor de fundo, o estilo da fonte e a cor da fonte. Você pode aplicar técnicas de formatação semelhantes a quaisquer linhas ou células específicas, conforme necessário.

#### P: Aspose.PDF for .NET é a única biblioteca que permite exportar dados do Excel para uma tabela PDF?

R: Aspose.PDF for .NET é uma biblioteca poderosa para trabalhar com documentos PDF em aplicativos .NET. Embora possa haver outras bibliotecas disponíveis, o Aspose.PDF for .NET oferece uma ampla gama de recursos e capacidades para gerar, manipular e exportar arquivos PDF com tabelas de dados do Excel, tornando-o uma escolha popular para tais tarefas.