---
title: Elemento de tabela de estilo
linktitle: Elemento de tabela de estilo
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como formatar o elemento da tabela com Aspose.PDF para .NET. Guia passo a passo para personalizar estilos e propriedades.
type: docs
weight: 170
url: /pt/net/programming-with-tagged-pdf/style-table-element/
---
Neste tutorial detalhado, orientaremos você passo a passo pelo código-fonte C# fornecido para formatar o elemento da matriz usando Aspose.PDF para .NET. Siga as instruções abaixo para entender como personalizar os estilos e propriedades do elemento da matriz.

## Passo 1: Configurando o ambiente

Antes de começar, certifique-se de ter configurado seu ambiente de desenvolvimento para usar Aspose.PDF for .NET. Isso inclui a instalação da biblioteca Aspose.PDF e a configuração do seu projeto para referenciá-la.

## Passo 2: Criando um documento

Nesta etapa, criaremos um novo objeto de documento Aspose.PDF.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Criação de documento
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example of table formatting");
taggedContent.SetLanguage("fr-FR");
```

Criamos um novo documento e definimos o título e o idioma do documento.

## Etapa 3: Obtenção do elemento da estrutura raiz

Nesta etapa obteremos o elemento da estrutura raiz do nosso documento.

```csharp
//Obtenha o elemento da estrutura raiz
StructureElement rootElement = taggedContent.RootElement;
```

Obtivemos o elemento da estrutura raiz que servirá como contêiner para o elemento do array.

## Etapa 4: Criando o elemento da estrutura do array

Agora vamos criar um novo elemento de estrutura de tabela para nosso documento.

```csharp
// Crie o elemento da estrutura do array
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
```

Criamos um novo elemento de estrutura de array e o adicionamos ao elemento de estrutura raiz.

## Etapa 5: Personalização de estilos e propriedades de elementos de matriz

Nesta etapa, personalizaremos os estilos e propriedades do elemento do array.

```csharp
// Personalize os estilos e propriedades do elemento da matriz
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement. Alignment = HorizontalAlignment. Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
tableElement. ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement. DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
tableElement. DefaultColumnWidth = "70";
tableElement. IsBroken = false;
tableElement.IsBordersIncluded = true;
tableElement. Left = 0F;
tableElement. Top = 40F;
tableElement.RepeatingColumnsCount = 2;
tableElement.RepeatingRowsCount = 3;

// Personalize o estilo das linhas repetidas
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
```

Usamos várias propriedades para personalizar o elemento da tabela, como cor de fundo, bordas, alinhamento, estilo de célula padrão, margens, largura da coluna, etc.

## Etapa 6: adicionar cabeçalhos, corpo e rodapé da tabela

Agora vamos adicionar os cabeçalhos, corpo e rodapé da tabela ao elemento da tabela.
```csharp
// Adicionar cabeçalhos de tabela
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

// Número de linhas e colunas na tabela
int rowCount = 10;
int colCount = 5;
int rowIndex;
int colIndex;

// Crie a linha do cabeçalho da tabela
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTHElement theElement = headTrElement.CreateTH();
     theElement.SetText(string.Format("Header {0}", colIndex));
}

//Adicione as linhas do corpo da tabela
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);

     for (colIndex = 0; colIndex < colCount; colIndex++)
     {
         TableTDElement tdelement = trElement.CreateTD();
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
     }
}

// Adicione a linha de rodapé da mesa
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

Adicionamos os cabeçalhos, as linhas do corpo e a linha do rodapé à tabela usando os elementos correspondentes.

## Passo 7: Salvando o documento PDF marcado

Agora que criamos nosso documento com o elemento de tabela estilizado, vamos salvá-lo como um documento PDF marcado.

```csharp
// Salve o documento PDF marcado
document.Save(dataDir + "StyleTableElement.pdf");
```

Salvamos o documento PDF marcado no diretório especificado.

## Etapa 8: Validação de conformidade com PDF/UA

A seguir, validaremos a conformidade PDF/UA do nosso documento.

```csharp
// Verificação de conformidade com PDF/UA
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

Carregamos o documento PDF marcado e validamos sua conformidade com PDF/UA gerando um relatório XML.

### Exemplo de código-fonte para elemento de tabela de estilo usando Aspose.PDF para .NET 

```csharp

// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Criar documento
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table style");
taggedContent.SetLanguage("en-US");

// Obtenha o elemento da estrutura raiz
StructureElement rootElement = taggedContent.RootElement;

// Criar elemento de estrutura de tabela
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement.Alignment = HorizontalAlignment.Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
tableElement.ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement.DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
tableElement.DefaultColumnWidth = "70";
tableElement.IsBroken = false;
tableElement.IsBordersIncluded = true;
tableElement.Left = 0F;
tableElement.Top = 40F;
tableElement.RepeatingColumnsCount = 2;
tableElement.RepeatingRowsCount = 3;
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 10;
int colCount = 5;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTHElement thElement = headTrElement.CreateTH();
	thElement.SetText(String.Format("Head {0}", colIndex));
}
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
	TableTRElement trElement = tableTBodyElement.CreateTR();
	trElement.AlternativeText = String.Format("Row {0}", rowIndex);
	for (colIndex = 0; colIndex < colCount; colIndex++)
	{
		TableTDElement tdElement = trElement.CreateTD();
		tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
	}
}
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTDElement tdElement = footTrElement.CreateTD();
	tdElement.SetText(String.Format("Foot {0}", colIndex));
}

// Salvar documento PDF marcado
document.Save(dataDir + "StyleTableElement.pdf");

// Verificando a conformidade com PDF/UA
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Conclusão

Neste tutorial, aprendemos como formatar o elemento do array com Aspose.PDF para .NET. Personalizamos os estilos e propriedades do elemento de tabela, adicionamos cabeçalhos, linhas de corpo e rodapé, salvamos o documento PDF marcado e validamos sua conformidade com PDF/UA.

### Perguntas frequentes

#### P: Qual é o objetivo deste tutorial sobre como formatar o elemento da matriz usando Aspose.PDF para .NET?

R: O objetivo deste tutorial é guiá-lo através do processo de formatação do elemento array em um documento PDF usando Aspose.PDF for .NET. Ele fornece instruções passo a passo e exemplos de código-fonte C# para ajudá-lo a personalizar os estilos e as propriedades do elemento de matriz.

#### P: Quais são os pré-requisitos para seguir este tutorial?

R: Antes de começar, certifique-se de ter configurado seu ambiente de desenvolvimento para usar Aspose.PDF for .NET. Isso envolve a instalação da biblioteca Aspose.PDF e a configuração do seu projeto para referenciá-la.

#### P: Como posso criar um novo documento PDF e definir seu título e idioma usando Aspose.PDF for .NET?

 R: Para criar um novo documento PDF, você precisa criar um`Document` objeto da biblioteca Aspose.PDF. O código-fonte C# fornecido pelo tutorial demonstra como criar um documento e definir seu título e propriedades de idioma.

#### P: Qual é o significado do elemento de estrutura raiz em um documento PDF?

R: O elemento da estrutura raiz atua como um contêiner para outros elementos da estrutura, ajudando a organizar e categorizar o conteúdo do documento PDF. Desempenha um papel crucial no estabelecimento da estrutura lógica do documento.

#### P: Como posso criar e personalizar um elemento de estrutura de array usando Aspose.PDF for .NET?

 R: Você pode criar um elemento de estrutura de array usando o`CreateTableElement()` método. O código-fonte do tutorial fornece exemplos de personalização de várias propriedades do elemento da tabela, como cor de fundo, bordas, alinhamento, largura da coluna e muito mais.

#### P: Posso personalizar os estilos e propriedades das células da tabela no elemento da matriz?

R: Sim, o tutorial aborda como personalizar os estilos e propriedades de todo o elemento da tabela, incluindo cabeçalhos, linhas do corpo e rodapé. No entanto, ele não aborda especificamente a personalização de células individuais da tabela.

#### P: Como posso adicionar cabeçalhos, linhas de corpo e rodapé ao elemento da tabela?

R: O tutorial explica como criar e adicionar cabeçalhos, linhas de corpo e rodapé ao elemento da tabela usando os métodos apropriados fornecidos pelo Aspose.PDF para .NET.

#### P: O que é conformidade com PDF/UA e como posso validá-la para meu documento PDF marcado?

 R: A conformidade com PDF/UA garante que o documento PDF esteja em conformidade com os padrões de acessibilidade, tornando-o mais acessível para usuários com deficiência. O tutorial demonstra como validar a conformidade PDF/UA usando o`Validate()` método e gerar um relatório de conformidade XML.

#### P: Como posso incorporar esses conceitos em meus próprios aplicativos .NET?

R: Você pode usar os exemplos de código-fonte C# fornecidos como um guia para implementar a formatação de elementos de matriz em seus próprios aplicativos .NET. Modifique e adapte o código para atender às suas necessidades e integre-o aos seus projetos.

#### P: Existem práticas recomendadas para formatação de elementos de matriz em documentos PDF?

R: Ao formatar elementos de array (tabelas), considere a legibilidade e acessibilidade do conteúdo. Use fontes claras e legíveis, cores apropriadas e mantenha um layout consistente. Valide a conformidade com PDF/UA para garantir que os padrões de acessibilidade sejam atendidos.

#### P: Que outros recursos do Aspose.PDF for .NET posso explorar para personalização de documentos PDF?

R: Aspose.PDF for .NET oferece uma variedade de recursos para personalização de documentos PDF, incluindo manipulação de texto, inserção de imagens, gerenciamento de campos de formulário, assinaturas digitais, anotações e muito mais. Consulte a documentação e recursos oficiais para explorar funcionalidades adicionais.