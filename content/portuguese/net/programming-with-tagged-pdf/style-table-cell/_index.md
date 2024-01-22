---
title: Célula de tabela de estilo
linktitle: Célula de tabela de estilo
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como estilizar células de tabela com Aspose.PDF para .NET. Guia passo a passo para criar e personalizar tabelas.
type: docs
weight: 160
url: /pt/net/programming-with-tagged-pdf/style-table-cell/
---
Bem-vindo a este tutorial detalhado sobre formatação de células de tabela usando Aspose.PDF para .NET. Neste guia, explicaremos em detalhes cada etapa do código-fonte C# fornecido para ajudá-lo a entender como estilizar células de tabela. Certifique-se de ter instalado o Aspose.PDF for .NET e configurado seu ambiente de desenvolvimento antes de começar.

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
taggedContent.SetTitle("Example of table cell formatting");
taggedContent.SetLanguage("fr-FR");
```

Criamos um novo documento e definimos o título e o idioma do documento.

## Etapa 3: Obtenção do elemento da estrutura raiz

Nesta etapa obteremos o elemento da estrutura raiz do nosso documento.

```csharp
//Obtenha o elemento da estrutura raiz
StructureElement rootElement = taggedContent.RootElement;
```

Obtivemos o elemento da estrutura raiz que servirá como contêiner para os elementos do array.

## Etapa 4: Criando o elemento da estrutura do array

Agora vamos criar um novo elemento de estrutura de tabela para nosso documento.

```csharp
// Crie o elemento da estrutura do array
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

Criamos um novo elemento de estrutura de array e o adicionamos ao elemento de estrutura raiz. Também criamos os elementos de cabeçalho, corpo e rodapé da tabela.

## Etapa 5: adicionar cabeçalhos de tabela

Nesta etapa adicionaremos os cabeçalhos da tabela à nossa tabela.

```csharp
// Número de linhas e colunas na tabela
int rowCount = 4;
int colCount = 4;

int rowIndex;
int colIndex;

// Crie a linha do cabeçalho da tabela
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTHElement theElement = headTrElement.CreateTH();
     theElement.SetText(string.Format("Header {0}", colIndex));
     theElement.BackgroundColor = Color.GreenYellow;
     theElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
     theElement. IsNoBorder = true;
     theElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
     theElement.Alignment = HorizontalAlignment.Right;
}
```

Criamos uma linha de cabeçalho para nossa tabela e adicionamos células de cabeçalho com propriedades de formatação como cor de fundo, bordas, margens e alinhamento.

## Etapa 6: adicionar as linhas do corpo da tabela

Agora vamos adicionar as linhas do corpo da tabela à nossa tabela.
```csharp
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);

     for (colIndex = 0; colIndex < colCount; colIndex++)
     {
         int colSpan = 1;
         int rowSpan = 1;

         if (colIndex == 1 && rowIndex == 1)
         {
             colSpan = 2;
             rowSpan = 2;
         }
         else if (colIndex == 2 && (rowIndex == 1 || rowIndex == 2))
         {
             keep on going;
         }
         else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
         {
             keep on going;
         }

         TableTDElement tdelement = trElement.CreateTD();
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
         tdElement.BackgroundColor = Color.Yellow;
         tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
         tdElement.IsNoBorder = false;
         tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
         tdElement.Alignment = HorizontalAlignment.Center;

         TextState cellTextState = new TextState();
         cellTextState.ForegroundColor = Color.DarkBlue;
         cellTextState.FontSize = 7.5F;
         cellTextState.FontStyle = FontStyles.Bold;
         cellTextState.Font = FontRepository.FindFont("Arial");

         tdElement. DefaultCellTextState = cellTextState;
         tdElement.IsWordWrapped = true;
         tdElement.VerticalAlignment = VerticalAlignment.Center;
         tdElement.ColSpan = colSpan;
         tdElement. RowSpan = rowSpan;
     }
}
```

Adicionamos linhas ao corpo da tabela usando loops para iterar em cada célula da tabela. Definimos propriedades de formatação para cada célula, como cor de fundo, bordas, margens, alinhamento de texto, etc.

## Passo 7: Adicionando o rodapé

Finalmente, adicionaremos o rodapé da tabela à nossa tabela.

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

Criamos um rodapé para nossa tabela e adicionamos células de rodapé com texto.



## Passo 8: Salvando o documento PDF marcado

Agora que criamos nosso documento com a tabela estilizada, vamos salvá-lo como um documento PDF marcado.

```csharp
// Salve o documento PDF marcado
document.Save(dataDir + "StyleTableCell.pdf");
```

Salvamos o documento PDF marcado no diretório especificado.

## Etapa 9: Validação de conformidade com PDF/UA

A seguir, validaremos a conformidade PDF/UA do nosso documento.

```csharp
// Verificação de conformidade com PDF/UA
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

Carregamos o documento PDF marcado e validamos sua conformidade com PDF/UA gerando um relatório XML.

### Exemplo de código-fonte para célula de tabela de estilos usando Aspose.PDF para .NET 
```csharp

// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Criar documento
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table cell style");
taggedContent.SetLanguage("en-US");

// Obtenha o elemento da estrutura raiz
StructureElement rootElement = taggedContent.RootElement;

// Criar elemento de estrutura de tabela
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 4;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTHElement thElement = headTrElement.CreateTH();
	thElement.SetText(String.Format("Head {0}", colIndex));
	thElement.BackgroundColor = Color.GreenYellow;
	thElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
	thElement.IsNoBorder = true;
	thElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
	thElement.Alignment = HorizontalAlignment.Right;
}
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
	TableTRElement trElement = tableTBodyElement.CreateTR();
	trElement.AlternativeText = String.Format("Row {0}", rowIndex);
	for (colIndex = 0; colIndex < colCount; colIndex++)
	{
		int colSpan = 1;
		int rowSpan = 1;
		if (colIndex == 1 && rowIndex == 1)
		{
			colSpan = 2;
			rowSpan = 2;
		}
		else if (colIndex == 2 && (rowIndex == 1 || rowIndex == 2))
		{
			continue;
		}
		else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
		{
			continue;
		}
		TableTDElement tdElement = trElement.CreateTD();
		tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
		tdElement.BackgroundColor = Color.Yellow;
		tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
		tdElement.IsNoBorder = false;
		tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
		tdElement.Alignment = HorizontalAlignment.Center;
		TextState cellTextState = new TextState();
		cellTextState.ForegroundColor = Color.DarkBlue;
		cellTextState.FontSize = 7.5F;
		cellTextState.FontStyle = FontStyles.Bold;
		cellTextState.Font = FontRepository.FindFont("Arial");
		tdElement.DefaultCellTextState = cellTextState;
		tdElement.IsWordWrapped = true;
		tdElement.VerticalAlignment = VerticalAlignment.Center;
		tdElement.ColSpan = colSpan;
		tdElement.RowSpan = rowSpan;
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
document.Save(dataDir + "StyleTableCell.pdf");

// Verificando a conformidade com PDF/UA
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Conclusão

Neste tutorial, aprendemos como estilizar células de tabela usando Aspose.PDF para .NET. Vimos como criar um documento, adicionar uma tabela com cabeçalhos, linhas de corpo e rodapé e personalizar estilos de células. Por fim, salvamos o documento PDF marcado e validamos sua conformidade com PDF/UA. Agora você pode usar Aspose.PDF for .NET para criar e estilizar tabelas em seus aplicativos .NET.

### Perguntas frequentes

#### P: Qual é o objetivo deste tutorial sobre formatação de células de tabela usando Aspose.PDF for .NET?

R: Este tutorial tem como objetivo fornecer um guia abrangente sobre como estilizar células de tabela em um documento PDF usando a biblioteca Aspose.PDF para .NET. Ele abrange instruções passo a passo e exemplos de código-fonte C# para ajudá-lo a compreender e implementar a formatação de células de tabela.

#### P: Quais são os pré-requisitos para seguir este tutorial?

R: Antes de começar, certifique-se de ter instalado o Aspose.PDF for .NET e de ter configurado seu ambiente de desenvolvimento. Isso inclui configurar seu projeto para fazer referência à biblioteca Aspose.PDF.

#### P: Como faço para criar um novo documento PDF usando Aspose.PDF for .NET?

R: Para criar um novo documento PDF, você precisa instanciar um`Document` objeto da biblioteca Aspose.PDF. O código-fonte C# fornecido demonstra como criar um documento e definir seu título e idioma.

#### P: Qual é o significado do elemento de estrutura raiz em um documento PDF?

R: O elemento da estrutura raiz serve como contêiner para outros elementos da estrutura, ajudando a organizar e categorizar o conteúdo do documento PDF. Desempenha um papel crucial no estabelecimento da estrutura lógica do documento.

#### P: Como posso criar um elemento de estrutura de tabela e personalizar sua aparência usando Aspose.PDF for .NET?

 R: Você pode criar um elemento de estrutura de tabela usando o`CreateTableElement()` método. O código-fonte fornecido demonstra como personalizar a aparência da tabela, incluindo cabeçalho, corpo e rodapé, definindo propriedades como cor de fundo, bordas, margens e alinhamento.

#### P: Posso adicionar diversas linhas e colunas ao corpo da tabela e personalizar sua formatação?

R: Sim, o tutorial demonstra como adicionar múltiplas linhas e colunas ao corpo da tabela usando loops. Ele também fornece exemplos de personalização de formatação de células, como cor de fundo, bordas, alinhamento de texto, estilo de fonte e muito mais.

#### P: Qual é o propósito de validar a conformidade com PDF/UA e como posso realizar essa validação?

 R: A validação da conformidade com PDF/UA garante que o documento PDF cumpra os padrões de acessibilidade, tornando-o mais acessível para usuários com deficiência. O tutorial mostra como validar a conformidade PDF/UA usando o`Validate()` método e gerar um relatório XML.

#### P: Como posso aplicar esses conceitos aos meus próprios aplicativos .NET?

R: Você pode usar os exemplos de código-fonte C# fornecidos como um guia para implementar a formatação de células de tabela em seus próprios aplicativos .NET. Personalize o código conforme necessário para atender às suas necessidades e integre-o aos seus projetos.

#### P: Há alguma prática recomendada para estilizar células de tabela em documentos PDF?

R: Ao definir o estilo das células da tabela, considere as necessidades do seu público, incluindo os requisitos de acessibilidade. Use cores contrastantes, fontes apropriadas e alinhamento claro das células para melhorar a legibilidade. Além disso, valide a conformidade com PDF/UA para garantir que os padrões de acessibilidade sejam atendidos.

#### P: Que outros recursos do Aspose.PDF for .NET posso explorar para manipulação de documentos PDF?

R: Aspose.PDF for .NET oferece uma ampla gama de recursos para manipulação de documentos PDF, incluindo extração de texto, inserção de imagens, gerenciamento de campos de formulário, assinaturas digitais e muito mais. Explore a documentação e os recursos oficiais para aprender sobre funcionalidades adicionais.
