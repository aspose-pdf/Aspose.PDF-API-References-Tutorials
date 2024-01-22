---
title: Tags HTML dentro da tabela em arquivo PDF
linktitle: Tags HTML dentro da tabela em arquivo PDF
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como usar tags HTML dentro de uma tabela em arquivo PDF com Aspose.PDF for .NET.
type: docs
weight: 100
url: /pt/net/programming-with-tables/html-tags-inside-table/
---
Neste tutorial, aprenderemos como usar tags HTML dentro de uma tabela em um documento PDF usando Aspose.PDF for .NET. Explicaremos o código-fonte em C# passo a passo. Ao final deste tutorial, você saberá como inserir conteúdo HTML em uma tabela de um documento PDF. Vamos começar!

## Passo 1: Configurando o ambiente
Certifique-se de ter configurado seu ambiente de desenvolvimento C# com Aspose.PDF para .NET. Adicione a referência à biblioteca e importe os namespaces necessários.

## Etapa 2: Criando dados da tabela
Criamos uma DataTable contendo uma coluna “dados” do tipo String. Em seguida, adicionamos linhas a este DataTable usando conteúdo HTML.

```csharp
DataTable dt = new DataTable("Employee");
dt.Columns.Add("data", System.Type.GetType("System.String"));

DataRow dr = dt.NewRow();
dr[0] = "<li>Department of Emergency Medicine: 3400 Spruce Street Ground Silverstein Bldg Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt. NewRow();
dr[0] = "<li>Penn Observation Medicine Service: 3400 Spruce Street Ground Floor Donner Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt. NewRow();
dr[0] = "<li>UPHS/Presbyterian - Dept. of Emergency Medicine: 51 N. 39th Street . Philadelphia PA 19104-2640</li>";
dt.Rows.Add(dr);
```

## Etapa 3: Criando o Documento e a Tabela
Criamos um novo documento PDF e adicionamos uma página neste documento. A seguir, inicializamos uma instância da classe Table e definimos as propriedades da tabela.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tableProvider = new Aspose.Pdf.Table();
tableProvider. ColumnWidths = "400 50";
tableProvider.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
tableProvider.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 2.5F;
margin. Left = 2.5F;
margin. Bottom = 1.0F;
tableProvider. DefaultCellPadding = margin;
```

## Passo 4: Importando dados para a tabela
Importamos os dados do DataTable para a tabela usando o método "ImportDataTable". Especificamos parâmetros de método para indicar qual intervalo de linhas e colunas do DataTable deve ser importado.

```csharp
tableProvider.ImportDataTable(dt, false, 0, 0, 3, 1, true);
```

## Passo 5: Adicionando a tabela ao documento
Adicionamos a tabela à página do documento.

```csharp
doc.Pages[1].Paragraphs.Add(tableProvider);
```

## Etapa 6: Salvando o documento
Salvamos o documento PDF com a tabela contendo conteúdo HTML.

```csharp
doc.Save(dataDir + "HTMLInsideTableCell_out.pdf");
```

### Exemplo de código-fonte para tags HTML dentro da tabela usando Aspose.PDF para .NET

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

DataTable dt = new DataTable("Employee");
dt.Columns.Add("data", System.Type.GetType("System.String"));

DataRow dr = dt.NewRow();
dr[0] = "<li>Department of Emergency Medicine: 3400 Spruce Street Ground Silverstein Bldg Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = "<li>Penn Observation Medicine Service: 3400 Spruce Street Ground Floor Donner Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = "<li>UPHS/Presbyterian - Dept. of Emergency Medicine: 51 N. 39th Street . Philadelphia PA 19104-2640</li>";
dt.Rows.Add(dr);

Document doc = new Document();
doc.Pages.Add();
// Inicializa uma nova instância da Tabela
Aspose.Pdf.Table tableProvider = new Aspose.Pdf.Table();
//Defina as larguras das colunas da tabela
tableProvider.ColumnWidths = "400 50 ";
// Defina a cor da borda da tabela como LightGray
tableProvider.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Defina a borda das células da tabela
tableProvider.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 2.5F;
margin.Left = 2.5F;
margin.Bottom = 1.0F;
tableProvider.DefaultCellPadding = margin;

tableProvider.ImportDataTable(dt, false, 0, 0, 3, 1, true);

doc.Pages[1].Paragraphs.Add(tableProvider);
doc.Save(dataDir + "HTMLInsideTableCell_out.pdf");
```

## Conclusão
Neste tutorial, aprendemos como usar tags HTML dentro de uma tabela em um documento PDF usando Aspose.PDF for .NET. Você pode usar este guia passo a passo para inserir conteúdo HTML em células de tabela em um documento PDF usando C#.

### Perguntas frequentes sobre tags HTML dentro da tabela em arquivo PDF

#### P: Posso usar outras tags e atributos HTML dentro das células da tabela?

 R: Sim, você pode usar várias tags e atributos HTML dentro das células da tabela, como`<b>`, `<i>`, `<a>`e muitos mais. Aspose.PDF for .NET oferece suporte a uma ampla variedade de elementos e estilos HTML que você pode usar para formatar o conteúdo nas células da tabela.

#### P: Posso aplicar estilos CSS ao conteúdo HTML dentro das células da tabela?

R: Sim, você pode aplicar estilos CSS ao conteúdo HTML dentro das células da tabela. Aspose.PDF for .NET fornece suporte para estilos CSS básicos que podem ser aplicados aos elementos HTML.

#### P: É possível adicionar imagens junto com conteúdo HTML dentro das células da tabela?

 R: Sim, você pode adicionar imagens junto com conteúdo HTML dentro das células da tabela. Você pode usar HTML`<img>` tags para incluir imagens de diversas fontes, como arquivos locais ou URLs.

#### P: Como posso especificar diferentes larguras de coluna para a tabela?

 R: Você pode especificar diferentes larguras de coluna para a tabela usando o`ColumnWidths` propriedade da tabela. A propriedade usa uma string contendo valores separados por espaços, onde cada valor representa a largura de uma coluna em pontos.

#### P: Posso usar tabelas aninhadas dentro de uma célula com conteúdo HTML?

R: Sim, você pode usar tabelas aninhadas dentro de uma célula com conteúdo HTML. Você pode criar instâncias de tabela separadas e adicioná-las como parte do conteúdo HTML dentro de uma célula para obter o efeito de aninhamento.