---
title: Linha da tabela de estilos
linktitle: Linha da tabela de estilos
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como personalizar linhas da tabela com o guia passo a passo Aspose.PDF for .NET para estilizar e formatar linhas.
type: docs
weight: 180
url: /pt/net/programming-with-tagged-pdf/style-table-row/
---
Neste tutorial detalhado, orientaremos você passo a passo pelo código-fonte C# fornecido para formatar a linha da tabela usando Aspose.PDF para .NET. Siga as instruções abaixo para entender como personalizar estilos e propriedades de linha da tabela.

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
taggedContent.SetTitle("Example of Table Row Formatting");
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

## Etapa 5: personalizar estilos e propriedades de linha da tabela

Nesta etapa, personalizaremos os estilos e propriedades das linhas da tabela.

```csharp
// Personalize estilos e propriedades de linha da tabela
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

int rowCount = 7;
int colCount = 3;
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

// Personalize as linhas do corpo da tabela
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);
     trElement.BackgroundColor = Color.LightGoldenrodYellow;
     trElement.Border = new BorderInfo(BorderSide.All, 0.75F, Color.DarkGray);
     trElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.Blue);
     trElement.MinRowHeight = 100.0;
     trElement.FixedRowHeight = 120.0;
     trElement. IsInNewPage = (rowIndex % 3 == 1);
     trElement.IsRowBroken = true;
     TextState cellTextState = new TextState();
     cellTextState.ForegroundColor = Color.Red;
     trElement. DefaultCellTextState = cellTextState;
     trElement. DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
     trElement.VerticalAlignment = VerticalAlignment.Bottom;

     for (colIndex = 0; colIndex < colCount; colIndex++)
     {
         TableTDElement tdelement = trElement.CreateTD();
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
     }
}

// Crie a linha de rodapé da tabela
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

Personalizamos vários aspectos da linha da tabela, como cor de fundo, bordas, altura da linha, paginação, estilo de célula padrão e muito mais.

## Passo 6: Salvando o documento PDF marcado

Agora que criamos nosso documento com a linha da tabela estilizada, vamos salvá-lo como um documento PDF marcado.
```csharp
// Salve o documento PDF marcado
document.Save(dataDir + "StyleTableRow.pdf");
```

Salvamos o documento PDF marcado no diretório especificado.

## Etapa 7: Validação de conformidade com PDF/UA

A seguir, validaremos a conformidade PDF/UA do nosso documento.

```csharp
// Verificação de conformidade com PDF/UA
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

Carregamos o documento PDF marcado e validamos sua conformidade com PDF/UA gerando um relatório XML.


### Exemplo de código-fonte para linha da tabela de estilos usando Aspose.PDF para .NET 
```csharp

// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Criar documento
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table row style");
taggedContent.SetLanguage("en-US");

// Obtenha o elemento da estrutura raiz
StructureElement rootElement = taggedContent.RootElement;

// Criar elemento de estrutura de tabela
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 7;
int colCount = 3;
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
	trElement.BackgroundColor = Color.LightGoldenrodYellow;
	trElement.Border = new BorderInfo(BorderSide.All, 0.75F, Color.DarkGray);
	trElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.Blue);
	trElement.MinRowHeight = 100.0;
	trElement.FixedRowHeight = 120.0;
	trElement.IsInNewPage = (rowIndex % 3 == 1);
	trElement.IsRowBroken = true;
	TextState cellTextState = new TextState();
	cellTextState.ForegroundColor = Color.Red;
	trElement.DefaultCellTextState = cellTextState;
	trElement.DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
	trElement.VerticalAlignment = VerticalAlignment.Bottom;
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
document.Save(dataDir + "StyleTableRow.pdf");

// Verificando a conformidade com PDF/UA
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Conclusão

Neste tutorial, aprendemos como formatar linhas da tabela com Aspose.PDF para .NET. Personalizamos os estilos e propriedades das linhas da tabela, adicionamos cabeçalhos, linhas do corpo e rodapé, salvamos o documento PDF marcado e validamos sua conformidade com PDF/UA.

### Perguntas frequentes

#### P: Qual é o objetivo deste tutorial sobre formatação de linhas de tabela usando Aspose.PDF for .NET?

R: O objetivo deste tutorial é guiá-lo através do processo de formatação de linhas de tabela em um documento PDF usando Aspose.PDF for .NET. Ele fornece instruções passo a passo e exemplos de código-fonte C# para ajudá-lo a personalizar estilos e propriedades de linha da tabela.

#### P: Quais são os pré-requisitos para seguir este tutorial?

R: Antes de começar, certifique-se de ter configurado seu ambiente de desenvolvimento para usar Aspose.PDF for .NET. Isso envolve a instalação da biblioteca Aspose.PDF e a configuração do seu projeto para referenciá-la.

#### P: Como posso criar um novo documento PDF e definir seu título e idioma usando Aspose.PDF for .NET?

 R: Para criar um novo documento PDF, você precisa criar um`Document` objeto da biblioteca Aspose.PDF. O código-fonte C# fornecido pelo tutorial demonstra como criar um documento e definir seu título e propriedades de idioma.

#### P: Qual é o significado do elemento de estrutura raiz em um documento PDF?

R: O elemento da estrutura raiz atua como um contêiner para outros elementos da estrutura, ajudando a organizar e categorizar o conteúdo do documento PDF. Desempenha um papel crucial no estabelecimento da estrutura lógica do documento.

#### P: Como posso criar e personalizar um elemento de estrutura de tabela para formatar linhas de tabela usando Aspose.PDF para .NET?

R: O tutorial explica como criar um elemento de estrutura de tabela e personalizar suas propriedades para formatar linhas da tabela. Abrange aspectos como cor de fundo, bordas, altura da linha, paginação, estilo de célula padrão e muito mais.

#### P: Posso personalizar os estilos e propriedades de células individuais em uma linha da tabela?

R: Sim, você pode personalizar os estilos e propriedades de células individuais em uma linha da tabela. O tutorial demonstra como definir propriedades como cor de fundo, bordas, cor do texto, preenchimento e muito mais para células da tabela dentro da linha formatada da tabela.

#### P: Como posso adicionar cabeçalhos, linhas de corpo e rodapé à linha formatada da tabela?

R: O tutorial fornece exemplos de criação e adição de cabeçalhos, linhas de corpo e rodapé ao elemento da estrutura da tabela. Esses elementos podem ser personalizados usando as propriedades descritas no tutorial.

#### P: O que é conformidade com PDF/UA e como posso validá-la para meu documento PDF marcado?

 R: A conformidade com PDF/UA garante que o documento PDF esteja em conformidade com os padrões de acessibilidade, tornando-o mais acessível para usuários com deficiência. O tutorial demonstra como validar a conformidade PDF/UA usando o`Validate()` método e gerar um relatório de conformidade XML.

#### P: Como posso incorporar esses conceitos em meus próprios aplicativos .NET?

R: Você pode usar os exemplos de código-fonte C# fornecidos como um guia para implementar a formatação de linha da tabela em seus próprios aplicativos .NET. Modifique e adapte o código para atender às suas necessidades e integre-o aos seus projetos.

#### P: Existem práticas recomendadas para formatação de linhas de tabela em documentos PDF?

R: Ao formatar linhas da tabela, considere a legibilidade e acessibilidade do conteúdo. Certifique-se de que as cores tenham contraste suficiente, use fontes claras e legíveis e mantenha um layout consistente. Valide a conformidade com PDF/UA para garantir que os padrões de acessibilidade sejam atendidos.

#### P: Que outros recursos do Aspose.PDF for .NET posso explorar para personalização de documentos PDF?

R: Aspose.PDF for .NET oferece uma ampla gama de recursos para personalização de documentos PDF, incluindo manipulação de texto, inserção de imagens, gerenciamento de campos de formulário, assinaturas digitais, anotações e muito mais. Consulte a documentação e recursos oficiais para explorar funcionalidades adicionais.