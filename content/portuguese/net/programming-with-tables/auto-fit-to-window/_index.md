---
title: Ajuste automático à janela
linktitle: Ajuste automático à janela
second_title: Referência da API Aspose.PDF para .NET
description: Guia passo a passo para usar Aspose.PDF para .NET e obter ajuste automático à janela na geração de PDF.
type: docs
weight: 50
url: /pt/net/programming-with-tables/auto-fit-to-window/
---
artigo a seguir é um guia passo a passo sobre como usar o código-fonte C# fornecido para obter a funcionalidade Ajustar automaticamente à janela usando a biblioteca Aspose.PDF para .NET. A função Auto Fit To Window permite gerar arquivos PDF com layout adaptado à janela de visualização. Este recurso é particularmente útil quando você deseja que seu documento PDF se ajuste automaticamente ao tamanho da janela do leitor de PDF usada pelo usuário.

## Etapa 1: Configurando o Ambiente

Antes de começar, você precisa instalar a biblioteca Aspose.PDF para .NET em sua máquina. Certifique-se também de importar os namespaces necessários para o seu projeto.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passo 2: Criando um Documento PDF

 Para começar, você precisa criar um`Document` objeto chamando seu construtor padrão.

```csharp
Document doc = new Document();
```

 Em seguida, crie uma seção no`Pdf` objeto.

```csharp
Page sec1 = doc.Pages.Add();
```

## Passo 3: Adicionando uma Tabela ao Documento

 Nesta etapa, adicionaremos uma tabela ao nosso documento PDF. Primeiro crie um`Table` objeto.

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

Em seguida, adicione a tabela à coleção de parágrafos da seção.

```csharp
sec1.Paragraphs.Add(tab1);
```

##  Etapa 4: Personalizando a aparência da tabela

Você pode personalizar a aparência da tabela definindo propriedades como bordas e margens das células.

```csharp
tab1. ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;

tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);

Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin.Right = 5f;
margin. Bottom = 5f;

tab1. DefaultCellPadding = margin;
```

##  Etapa 4: adicionar linhas e células à tabela

Agora vamos adicionar linhas e células à nossa tabela. Comece criando uma linha e adicionando células a essa linha.

```csharp
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");

Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
```

## Etapa 5: salvando o documento

Por fim, especifique o caminho do arquivo de saída e salve o documento.

```csharp
dataDir = dataDir + "AutoFitToWindow_out.pdf";
doc.Save(dataDir);
```

### Exemplo de código-fonte para ajuste automático à janela usando Aspose.PDF para .NET

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instancie o objeto Pdf chamando seu construtor vazio
Document doc = new Document();
// Crie a seção no objeto PDF
Page sec1 = doc.Pages.Add();

// Instanciar um objeto de tabela
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Adicione a tabela na coleção de parágrafos da seção desejada
sec1.Paragraphs.Add(tab1);

// Definir com larguras de coluna da tabela
tab1.ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;

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
row1.Cells.Add("col3");
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");

dataDir = dataDir + "AutoFitToWindow_out.pdf";
// Salvar documento atualizado contendo objeto de tabela
doc.Save(dataDir);
```

## Conclusão

Neste tutorial, aprendemos como usar Aspose.PDF for .NET para gerar um arquivo PDF com o recurso Auto Fit To Window. Este recurso é extremamente útil quando você deseja que seu documento PDF se ajuste automaticamente ao tamanho da janela de visualização. Aspose.PDF for .NET oferece muitos outros recursos poderosos para gerar e manipular arquivos PDF. Eu encorajo você a explorar mais esta biblioteca para descobrir todos os seus recursos.

### Perguntas frequentes

#### P: Qual é a finalidade do recurso Ajustar automaticamente à janela na geração de PDF?

R: O recurso Ajustar automaticamente à janela na geração de PDF garante que o layout do documento PDF se ajuste automaticamente ao tamanho da janela do leitor de PDF usada pelo usuário. Isso permite uma melhor visualização e garante que o conteúdo se encaixe perfeitamente na área de visualização disponível.

#### P: Posso personalizar a aparência da tabela, como tamanho da fonte e cores?

R: Sim, você pode personalizar a aparência da tabela no documento PDF usando Aspose.PDF for .NET. O trecho de código fornecido demonstra como definir propriedades como bordas de células, margens e larguras de colunas. Você pode personalizar ainda mais o tamanho da fonte, as cores e outros aspectos de estilo da tabela e seu conteúdo.

#### P: Como integro o Aspose.PDF for .NET ao meu projeto C#?

R: Para usar o Aspose.PDF para .NET em seu projeto C#, você precisa primeiro instalar a biblioteca Aspose.PDF para .NET em sua máquina. Em seguida, você pode adicionar uma referência à biblioteca em seu projeto C#. Por fim, importe os namespaces necessários para acessar as classes e métodos fornecidos pelo Aspose.PDF for .NET.

#### P: O Aspose.PDF for .NET é compatível com aplicativos .NET Core?

R: Sim, o Aspose.PDF for .NET é compatível com aplicativos .NET Core. Ele oferece suporte a várias plataformas .NET, incluindo .NET Framework, .NET Core e .NET 5.0+.

#### P: Posso adicionar mais tabelas ao documento PDF?

R: Sim, você pode adicionar várias tabelas a um documento PDF seguindo etapas semelhantes demonstradas no trecho de código. Basta criar novas instâncias do`Aspose.Pdf.Table` class e adicione-os a diferentes seções ou páginas do documento PDF.