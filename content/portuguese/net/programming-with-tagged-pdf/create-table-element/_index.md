---
title: Criar elemento de tabela
linktitle: Criar elemento de tabela
second_title: Referência da API Aspose.PDF para .NET
description: Guia passo a passo para criar um elemento de array com Aspose.PDF para .NET. Gere PDFs dinâmicos com tabelas facilmente.
type: docs
weight: 80
url: /pt/net/programming-with-tagged-pdf/create-table-element/
---
Neste guia passo a passo, orientaremos você no processo de criação de um elemento de array usando Aspose.PDF para .NET. Aspose.PDF é uma biblioteca poderosa que permite manipular documentos PDF programaticamente. Criar um elemento de array é um requisito comum ao gerar PDFs dinâmicos, e Aspose.PDF oferece uma maneira fácil e eficiente de fazer isso.

Vamos mergulhar no código e aprender como criar um elemento de array usando Aspose.PDF para .NET.

## Pré-requisitos

Antes de começar, certifique-se de ter o seguinte:

1. Biblioteca Aspose.PDF para .NET instalada.
2. Conhecimento básico da linguagem de programação C#.

## Passo 1: Configurando o ambiente

Para começar, abra seu ambiente de desenvolvimento C# e crie um novo projeto. Certifique-se de ter adicionado uma referência à biblioteca Aspose.PDF para .NET em seu projeto.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passo 2: Criando o documento

 O primeiro passo é criar um novo documento PDF usando o`Document` aula.

```csharp
// Crie o documento
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Array");
taggedContent.SetLanguage("fr-FR");
```

Aqui também definimos o título e o idioma do conteúdo marcado.

## Etapa 3: Criando o elemento array

 seguir, precisamos criar o elemento array e adicioná-lo ao documento. Começamos obtendo o elemento de estrutura raiz e, em seguida, criamos um novo elemento de tabela usando o`CreateTableElement` método.

```csharp
// Obtenha o elemento da estrutura raiz
StructureElement rootElement = taggedContent.RootElement;
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.Border = new BorderInfo(BorderSide.All, 1.2F, Color.DarkBlue);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 50;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";
headTrElement.BackgroundColor = Color.LightGray;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
TableTHElement theElement = headTrElement.CreateTH();
thElement.SetText(String.Format("Header {0}", colIndex));
theElement.BackgroundColor = Color.GreenYellow;
theElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
theElement. IsNoBorder = true;
theElement.Margin = new MarginInfo(16.0, 2

.0, 8.0, 2.0);
theElement.Alignment = HorizontalAlignment.Right;
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
keep on going;
}
else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
{
keep on going;
}
TableTDElement tdelement = trElement.CreateTD();
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
tdElement. DefaultCellTextState = cellTextState;
tdElement.IsWordWrapped = true;
tdElement.VerticalAlignment = VerticalAlignment.Center;
tdElement.ColSpan = colSpan;
tdElement. RowSpan = rowSpan;
}
}
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";
footTrElement.BackgroundColor = Color.LightSeaGreen;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
TableTDElement tdElement = footTrElement.CreateTD();
tdElement.SetText(String.Format("Foot {0}", colIndex));
tdElement.Alignment = HorizontalAlignment.Center;
tdElement.StructureTextState.FontSize = 7F;
tdElement.StructureTextState.FontStyle = FontStyles.Bold;
}
StructureAttributes tableAttributes = tableElement.Attributes.GetAttributes(AttributeOwnerStandard.Table);
StructureAttribute summaryAttribute = new StructureAttribute(AttributeKey.Summary);
summaryAttribute.SetStringValue("The summary text for the table");
tableAttributes.SetAttribute(summaryAttribute);

// Salve o documento PDF marcado
document.Save(dataDir + "CreateTableElement.pdf");

// Verificação de conformidade com PDF/UA
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

### Exemplo de código-fonte para criar elemento de tabela usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Criar documento
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table");
taggedContent.SetLanguage("en-US");

// Obtenha o elemento da estrutura raiz
StructureElement rootElement = taggedContent.RootElement;
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.Border = new BorderInfo(BorderSide.All, 1.2F, Color.DarkBlue);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 50;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
headTrElement.BackgroundColor = Color.LightGray;
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
footTrElement.BackgroundColor = Color.LightSeaGreen;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTDElement tdElement = footTrElement.CreateTD();
	tdElement.SetText(String.Format("Foot {0}", colIndex));
	tdElement.Alignment = HorizontalAlignment.Center;
	tdElement.StructureTextState.FontSize = 7F;
	tdElement.StructureTextState.FontStyle = FontStyles.Bold;
}
StructureAttributes tableAttributes = tableElement.Attributes.GetAttributes(AttributeOwnerStandard.Table);
StructureAttribute summaryAttribute = new StructureAttribute(AttributeKey.Summary);
summaryAttribute.SetStringValue("The summary text for table");
tableAttributes.SetAttribute(summaryAttribute);

// Salvar documento PDF marcado
document.Save(dataDir + "CreateTableElement.pdf");

// Verificando a conformidade com PDF/UA
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Conclusão

Você aprendeu como criar um elemento de array usando Aspose.PDF para .NET. Agora você pode gerar documentos PDF com tabelas dinâmicas usando este método. Sinta-se à vontade para explorar mais recursos do Aspose.PDF para descobrir todo o seu potencial.

### Perguntas frequentes

#### P: O que é um elemento de array em um documento PDF e por que eu precisaria criar um usando Aspose.PDF for .NET?

R: Um elemento de matriz em um documento PDF representa uma coleção estruturada de dados, frequentemente usada para criar tabelas ou grades. Pode ser necessário criar um elemento de matriz usando Aspose.PDF for .NET ao gerar PDFs dinâmicos que exigem apresentação de dados estruturados, como informações tabulares ou grades.

#### P: Como o Aspose.PDF for .NET simplifica o processo de criação de um elemento de array?

R: Aspose.PDF for .NET fornece um conjunto abrangente de classes e métodos que permitem criar, personalizar e gerenciar elementos de array (tabelas) em um documento PDF de forma programática. Isso elimina a necessidade de manipulação manual de PDF e agiliza a criação de representações de dados estruturados.

#### P: Quais são as principais etapas envolvidas na criação de um elemento de array usando Aspose.PDF for .NET?

R: As principais etapas incluem configurar o ambiente, criar o documento, obter o elemento da estrutura raiz, criar um elemento de tabela, definir linhas e células na tabela e especificar a formatação e as propriedades dos elementos. O exemplo de código fornecido demonstra essas etapas.

####  P: Qual é o papel do`taggedContent` object play in creating an array element?

 R: O`taggedContent` objeto, obtido do documento`TaggedContent`propriedade, permite definir a estrutura do conteúdo marcado no documento PDF. Isso inclui criar e organizar elementos de array e seus elementos filhos de maneira hierárquica.

#### P: Como o código garante a acessibilidade e a semântica do elemento do array criado?

 R: O código define atributos como`AlternativeText`, `BackgroundColor`, `Border`, `Margin`, `Alignment` , e`ColSpan` para melhorar a acessibilidade e a semântica do elemento da matriz. Esses atributos contribuem para uma representação dos dados bem estruturada, informativa e visualmente atraente.

#### P: Qual é a importância da conformidade com PDF/UA no contexto da criação de elementos de array?

 R: A conformidade com PDF/UA (Acessibilidade Universal) garante que os documentos PDF gerados sejam acessíveis a usuários com deficiência e atendam a determinados padrões de acessibilidade. O exemplo de código verifica a conformidade com PDF/UA usando o`Validate` método, ajudando você a criar documentos inclusivos e acessíveis.

#### P: Posso personalizar ainda mais a formatação e a aparência dos elementos da matriz?

R: Sim, você pode personalizar a formatação e a aparência dos elementos da matriz ajustando atributos como cor de fundo, estilo de borda, tamanho da fonte e alinhamento. Aspose.PDF for .NET oferece uma ampla gama de propriedades para adaptar a apresentação visual às suas necessidades.

#### P: Como posso ampliar esse conhecimento para criar estruturas de tabelas mais complexas ou incorporar elementos de array em documentos PDF maiores?

R: Você pode ampliar esse conhecimento explorando recursos adicionais do Aspose.PDF para .NET, como mesclar vários elementos de matriz, criar tabelas aninhadas, adicionar cabeçalhos e rodapés e integrar elementos de matriz em layouts PDF maiores. A documentação e os exemplos da biblioteca fornecem orientação para esses cenários avançados.

#### P: É possível importar dados de fontes externas, como bancos de dados ou planilhas, para preencher os elementos do array?

R: Sim, você pode importar dados de fontes externas para preencher elementos do array. Você pode usar técnicas de recuperação e transformação de dados em C# para buscar dados de bancos de dados, planilhas ou outras fontes e, em seguida, preencher os elementos da matriz de acordo.

#### P: Como posso usar o conhecimento adquirido neste tutorial para melhorar a qualidade e a usabilidade dos documentos PDF que crio programaticamente?

R: O conhecimento adquirido neste tutorial permite criar elementos de array (tabelas) estruturados e visualmente atraentes em documentos PDF. Ao incorporar essas técnicas, você pode melhorar a legibilidade, a acessibilidade e a experiência do usuário de PDFs gerados dinamicamente, tornando-os mais informativos e fáceis de usar.