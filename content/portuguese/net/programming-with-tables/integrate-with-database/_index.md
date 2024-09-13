---
title: Integrar com banco de dados em arquivo PDF
linktitle: Integrar com banco de dados em arquivo PDF
second_title: Referência da API do Aspose.PDF para .NET
description: Incorpore dados de um banco de dados em um arquivo PDF usando Aspose.PDF para .NET.
type: docs
weight: 120
url: /pt/net/programming-with-tables/integrate-with-database/
---
Neste tutorial, aprenderemos como incorporar dados de um banco de dados em um arquivo PDF usando o Aspose.PDF para .NET. Explicaremos o código-fonte em C# passo a passo. No final deste tutorial, você saberá como importar dados de tabela de um banco de dados para um documento PDF. Vamos começar!

## Etapa 1: Configurando o ambiente
Certifique-se de ter configurado seu ambiente de desenvolvimento C# com Aspose.PDF para .NET. Adicione a referência à biblioteca e importe os namespaces necessários.

## Etapa 2: Criando o DataTable
Criamos uma instância de DataTable para representar os dados que queremos incorporar no documento PDF. Neste exemplo, criamos uma DataTable com três colunas: Employee_ID, Employee_Name e Gender. Também adicionamos duas linhas à DataTable com dados fictícios.

```csharp
DataTable dt = new DataTable("Employee");
dt.Columns.Add("Employee_ID", typeof(Int32));
dt.Columns.Add("Employee_Name", typeof(string));
dt.Columns.Add("Gender", typeof(string));

DataRow dr = dt.NewRow();
dr[0] = 1;
dr[1] = "John Smith";
dr[2] = "Male";
dt.Rows.Add(dr);

dr = dt. NewRow();
dr[0] = 2;
dr[1] = "Mary Miller";
dr[2] = "Female";
dt.Rows.Add(dr);
```

## Etapa 3: Criando o documento PDF e a tabela
Criamos uma instância de Document e adicionamos uma página a esse documento. Em seguida, criamos uma instância de Table para representar nossa tabela no documento PDF. Definimos larguras de colunas de tabela e estilos de bordas.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "40 100 100 100";
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## Etapa 4: Importando dados do DataTable para a tabela
Usamos o método ImportDataTable para importar os dados da DataTable para a tabela no documento PDF.

```csharp
table.ImportDataTable(dt, true, 0, 1, 3, 3);
```

## Etapa 5: Adicionando a tabela ao documento
Adicionamos a tabela à coleção de parágrafos da página do documento.

```csharp
doc.Pages[1].Paragraphs.Add(table);
```

## Etapa 6: Salve o documento
Salvamos o documento PDF com os dados do banco de dados incorporado.

```csharp
doc.Save(dataDir + "DataIntegrated_out.pdf");
```

Parabéns! Agora você sabe como incorporar dados de banco de dados em um documento PDF usando Aspose.PDF para .NET.

### Exemplo de código-fonte para Integrar com Banco de Dados usando Aspose.PDF para .NET

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

DataTable dt = new DataTable("Employee");
dt.Columns.Add("Employee_ID", typeof(Int32));
dt.Columns.Add("Employee_Name", typeof(string));
dt.Columns.Add("Gender", typeof(string));
//Adicione 2 linhas ao objeto DataTable programaticamente
DataRow dr = dt.NewRow();
dr[0] = 1;
dr[1] = "John Smith";
dr[2] = "Male";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = 2;
dr[1] = "Mary Miller";
dr[2] = "Female";
dt.Rows.Add(dr);
// Criar instância de documento
Document doc = new Document();
doc.Pages.Add();
// Inicializa uma nova instância da Tabela
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Definir larguras de coluna da tabela
table.ColumnWidths = "40 100 100 100";
// Defina a cor da borda da tabela como LightGray
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Definir a borda para células da tabela
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.ImportDataTable(dt, true, 0, 1, 3, 3);

// Adicionar objeto de tabela à primeira página do documento de entrada
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "DataIntegrated_out.pdf";
// Salvar documento atualizado contendo objeto de tabela
doc.Save(dataDir);

Console.WriteLine("\nDatabase integrated successfully.\nFile saved at " + dataDir);
```

## Conclusão
Neste tutorial, aprendemos como incorporar dados de um banco de dados em um documento PDF usando o Aspose.PDF para .NET. Você pode usar este guia passo a passo para importar os dados do seu próprio banco de dados e exibi-los em documentos PDF. Explore mais a documentação do Aspose.PDF para descobrir outros recursos e possibilidades oferecidos por esta poderosa biblioteca.

### Perguntas frequentes para integração com banco de dados em arquivo PDF

#### P: Posso usar o Aspose.PDF para .NET com diferentes tipos de banco de dados, como MySQL, SQL Server ou Oracle?

R: Sim, você pode usar o Aspose.PDF para .NET com diferentes tipos de banco de dados como MySQL, SQL Server, Oracle e outros. O Aspose.PDF para .NET fornece funcionalidades para ler dados de várias fontes de dados, incluindo bancos de dados, arquivos XML e muito mais. Você pode recuperar dados do tipo de banco de dados desejado e preenchê-los em um DataTable ou qualquer outra estrutura de dados compatível com o Aspose.PDF para .NET.

#### P: Como posso personalizar a aparência da tabela no documento PDF?

R: Você pode personalizar a aparência da tabela no documento PDF usando várias propriedades fornecidas pela biblioteca Aspose.PDF for .NET. Por exemplo, você pode definir diferentes estilos de borda, cores de fundo, estilos de fonte e alinhamento para a tabela e suas células. Consulte a documentação do Aspose.PDF for .NET para obter mais detalhes sobre como personalizar a aparência da tabela.

#### P: É possível adicionar hiperlinks ou elementos interativos aos dados importados do banco de dados?

R: Sim, você pode adicionar hiperlinks ou outros elementos interativos aos dados importados do banco de dados. O Aspose.PDF para .NET oferece suporte à adição de hiperlinks, marcadores e outros elementos interativos ao documento PDF. Você pode manipular o conteúdo no DataTable antes de importá-lo para a tabela e incluir hiperlinks ou outros recursos interativos.

#### P: Posso paginar a tabela se ela exceder um certo número de linhas?

R: Sim, você pode paginar a tabela se ela exceder um certo número de linhas. Para conseguir isso, você pode usar o`IsInNewPage` propriedade do objeto Row para indicar que uma nova página deve começar após uma linha específica. Você pode calcular o número de linhas a serem exibidas por página e definir o`IsInNewPage` propriedade de acordo.

#### P: Como posso exportar o documento PDF com dados de banco de dados incorporados para diferentes formatos de arquivo, como DOCX ou XLSX?

R: O Aspose.PDF para .NET permite que você converta documentos PDF para vários outros formatos de arquivo, incluindo DOCX (Microsoft Word) e XLSX (Microsoft Excel). Você pode usar a biblioteca Aspose.PDF para .NET em combinação com outras bibliotecas Aspose, como Aspose.Words e Aspose.Cells para conseguir isso. Primeiro, salve o documento PDF com dados de banco de dados incorporados e, em seguida, use a respectiva biblioteca Aspose para convertê-lo para o formato de arquivo desejado.