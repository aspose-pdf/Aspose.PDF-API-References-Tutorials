---
title: Exportar dados da planilha do Excel para tabela
linktitle: Exportar dados da planilha do Excel para tabela
second_title: Referência da API do Aspose.PDF para .NET
description: Exporte dados de uma planilha do Excel para uma tabela PDF usando o Aspose.PDF para .NET.
type: docs
weight: 70
url: /pt/net/programming-with-tables/export-excel-worksheet-data-to-table/
---
Neste tutorial, aprenderemos como exportar dados de uma planilha do Excel e criar uma tabela em um documento PDF usando a biblioteca Aspose.PDF for .NET. Percorreremos o código-fonte passo a passo e explicaremos cada seção em detalhes. Ao final deste tutorial, você será capaz de gerar arquivos PDF com tabelas contendo dados de planilhas do Excel. Vamos começar!

## Requisitos
Antes de começar, certifique-se de ter o seguinte:

- Conhecimento básico da linguagem de programação C#
- Visual Studio instalado em sua máquina
- Biblioteca Aspose.PDF para .NET adicionada ao seu projeto

## Etapa 1: Configurando o ambiente
Para começar, crie um novo projeto C# no Visual Studio. Adicione a referência à biblioteca Aspose.PDF for .NET clicando com o botão direito do mouse no seu projeto no Solution Explorer, selecionando "Manage NuGet Packages" e pesquisando por "Aspose.PDF". Instale o pacote e você estará pronto para começar.

## Etapa 2: Carregando a planilha do Excel
No primeiro passo do nosso código, definimos o caminho para o diretório que contém o documento do Excel. Substitua "YOUR DOCUMENT DIRECTORY" pelo caminho real do diretório onde seu arquivo do Excel está localizado.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
```

Aqui, usamos a biblioteca Aspose.Cells para carregar a pasta de trabalho do Excel. Certifique-se de substituir "newBook1.xlsx" pelo nome do seu arquivo do Excel.

## Etapa 3: Acessando a planilha
 Em seguida, precisamos acessar a primeira planilha no arquivo Excel. Fazemos isso usando o`Worksheets` coleção do`Workbook` objeto.

```csharp
// Acessando a primeira planilha no arquivo Excel
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
```

 Se o seu arquivo Excel contiver várias planilhas, você poderá alterar o valor do índice`[0]` para acessar uma planilha diferente.

## Etapa 4: Exportando dados para DataTable
 Agora, exportaremos o conteúdo da planilha do Excel para um`DataTable` objeto. Especificamos o intervalo de células a serem exportadas usando o`ExportDataTable` método.

```csharp
// Exportando o conteúdo de 7 linhas e 2 colunas começando da 1ª célula para DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);
```

Neste exemplo, exportamos todas as linhas e colunas começando da primeira célula (0, 0) até a última célula na planilha. Defina o intervalo apropriado com base em seus requisitos.

## Etapa 5: Criando um documento PDF
Agora, criaremos um novo documento PDF usando a biblioteca Aspose.PDF.

```csharp
// Instanciar uma instância de Documento
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

Isso cria um documento PDF vazio onde podemos adicionar conteúdo.

## Etapa 6: Adicionando uma página e uma tabela
Para exibir os dados em formato de tabela, precisamos adicionar uma página e uma tabela ao documento PDF.

```csharp
// Crie uma página na instância do documento
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// Criar um objeto Table
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Adicione o objeto Table na coleção de parágrafos da seção
sec1.Paragraphs.Add(tab1);
```

Aqui, criamos uma nova página e um objeto de tabela. Então, adicionamos a tabela à coleção de parágrafos da página.

## Etapa 7: Definindo propriedades da tabela
Antes de importar os dados, precisamos definir algumas propriedades da tabela, como larguras de colunas e bordas de células padrão.

```csharp
// Definir larguras de coluna da tabela
tab1.ColumnWidths = "40 100 100";

// Definir borda de célula padrão da tabela usando o objeto BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

Neste exemplo, definimos as larguras das colunas para 40, 100 e 100 unidades. Ajuste os valores com base nos seus dados. Também definimos a borda da célula padrão para exibir bordas em todos os lados de cada célula.

## Etapa 8: Importando dados para a tabela
 Agora, importaremos os dados do`DataTable` objeto na tabela usando o`ImportDataTable` método.

```csharp
// Importar dados para o objeto Table a partir do DataTable criado acima
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
```

 Aqui, especificamos o intervalo de linhas e colunas a serem importadas. Neste exemplo, importamos todas as linhas e colunas do`dataTable` objeto.

## Etapa 9: Formatando a tabela
Para melhorar a aparência da tabela, podemos aplicar formatação a células ou linhas específicas. Nesta etapa, formatamos a primeira linha e as linhas alternadas da tabela.

```csharp
// Pegue a 1ª linha da tabela
Aspose.Pdf.Row row1 = tab1.Rows[0];

// Formatar a primeira linha
foreach(Aspose.Pdf.Cell curCell in row1.Cells)
{
     // Defina a cor de fundo das células na primeira linha
     curCell.BackgroundColor = Color.Blue;// Defina a face para as células na primeira linha
     curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
    
     // Defina a cor da fonte das células na primeira linha
     curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
    
     // Defina o alinhamento do texto para as células na primeira linha
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

Aqui, iteramos pelas células na primeira linha e definimos sua cor de fundo, tipo de fonte, cor da fonte e alinhamento do texto. Então, iteramos por todas as células nas linhas alternadas e definimos sua cor de fundo e texto.

## Etapa 10: Salvando o documento PDF
Por fim, salvamos o documento PDF no local especificado.

```csharp
// Salvar o PDF
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

Certifique-se de substituir "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho do diretório e nome do arquivo desejados para o arquivo PDF de saída.

### Exemplo de código-fonte para exportar dados da planilha do Excel para uma tabela usando Aspose.PDF para .NET

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
// Acessando a primeira planilha no arquivo Excel
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
// Exportando o conteúdo de 7 linhas e 2 colunas começando da 1ª célula para DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);

// Instanciar uma instância de documento
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
// Crie uma página na instância do documento
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// Criar um objeto Table
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Adicione o objeto Table na coleção de parágrafos da seção
sec1.Paragraphs.Add(tab1);

// Defina as larguras das colunas da tabela. Precisamos especificar o ColumnCount manualmente.
// Como a planilha atual do Excel tem três colunas, estamos especificando a mesma contagem
tab1.ColumnWidths = "40 100 100";

// Definir borda de célula padrão da tabela usando o objeto BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Importar dados para o objeto Table a partir do DataTable criado acima
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
// Pegue a 1ª linha da tabela
Aspose.Pdf.Row row1 = tab1.Rows[0];

// Itere por todas as células na 1ª linha e defina a cor de fundo como azul
foreach (Aspose.Pdf.Cell curCell in row1.Cells)
{
	// Defina o plano de fundo de todas as células na 1ª linha da tabela.
	curCell.BackgroundColor = Color.Blue;
	// Defina o tipo de fonte para as células da 1ª linha da tabela.
	curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
	// Defina a cor da fonte de todas as células na 1ª linha da tabela.
	curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
	// Defina o alinhamento do texto para as células da 1ª linha como Centralizado.
	curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
	// Itere por todas as células na 1ª linha e defina a cor de fundo como azul
	foreach (Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
	{
		// Defina a cor de fundo de todas as células, exceto a da 1ª linha.
		curCell.BackgroundColor = Color.Gray;
		// Defina a cor do texto de todas as células, exceto a 1ª linha.
		curCell.DefaultCellTextState.ForegroundColor = Color.White;
	}
}

// Salvar o PDF
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

## Conclusão
Neste tutorial, aprendemos como exportar dados de uma planilha do Excel para uma tabela em PDF usando a biblioteca Aspose.PDF for .NET. Cobrimos o processo passo a passo de carregar a planilha do Excel, criar um documento PDF, adicionar uma tabela, importar dados e formatar a tabela. Agora você pode gerar arquivos PDF com tabelas contendo dados do Excel programaticamente.

### Perguntas frequentes

#### P: Qual é o propósito de exportar dados de uma planilha do Excel para uma tabela em PDF?

R: Exportar dados de planilhas do Excel para uma tabela PDF permite que você apresente os dados em um formato estruturado e organizado. Ele permite que você gere arquivos PDF com tabelas que contêm dados de planilhas do Excel, facilitando o compartilhamento e a preservação de informações em um formato de documento portátil.

#### P: Posso personalizar a aparência da tabela PDF?

R: Sim, você pode personalizar a aparência da tabela PDF usando várias propriedades fornecidas pelo Aspose.PDF para .NET. No código-fonte C# fornecido, você pode modificar as larguras das colunas, bordas das células, alinhamento do texto, estilo da fonte e muito mais para atender às suas necessidades específicas.

#### P: Como lidar com arquivos do Excel com várias planilhas?

 R: No código C# fornecido, acessamos a primeira planilha no arquivo Excel usando o índice`[0]` . Se o seu arquivo Excel contiver várias planilhas, você poderá acessá-las alterando o valor do índice de acordo, como`[1]` para a segunda planilha ou`[2]` para a terceira planilha.

#### P: Posso aplicar formatação diferente a linhas ou células específicas na tabela PDF?

R: Sim, você pode aplicar formatação diferente a linhas ou células específicas na tabela PDF. No código-fonte C# fornecido, demonstramos como formatar a primeira linha e as linhas alternativas de forma diferente, alterando sua cor de fundo, estilo de fonte e cor de fonte. Você pode aplicar técnicas de formatação semelhantes a quaisquer linhas ou células específicas, conforme necessário.

#### P: O Aspose.PDF para .NET é a única biblioteca que permite exportar dados do Excel para uma tabela PDF?

R: Aspose.PDF para .NET é uma biblioteca poderosa para trabalhar com documentos PDF em aplicativos .NET. Embora possa haver outras bibliotecas disponíveis, o Aspose.PDF para .NET oferece uma ampla gama de recursos e capacidades para gerar, manipular e exportar arquivos PDF com tabelas de dados do Excel, tornando-o uma escolha popular para tais tarefas.