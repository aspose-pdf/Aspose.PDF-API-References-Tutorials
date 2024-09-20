---
title: Estilo Tabela Célula
linktitle: Estilo Tabela Célula
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda como estilizar células de tabela em um PDF usando Aspose.PDF para .NET com este tutorial detalhado. Siga as instruções para criar e formatar lindas tabelas em PDF.
type: docs
weight: 160
url: /pt/net/programming-with-tagged-pdf/style-table-cell/
---
## Introdução

Criar tabelas PDF com aparência profissional pode ser complicado, mas com o Aspose.PDF para .NET, é surpreendentemente simples! Não importa se você está estilizando cabeçalhos, rodapés ou células de tabela específicas, esta poderosa biblioteca fornece todas as ferramentas necessárias para criar documentos PDF lindamente formatados. Neste tutorial, mostraremos como estilizar células de tabela em um documento PDF usando o Aspose.PDF para .NET. Não se preocupe — dividiremos tudo em etapas fáceis de seguir.

## Pré-requisitos

Antes de mergulhar no código, certifique-se de ter os seguintes pré-requisitos:

1. Aspose.PDF para .NET: Baixe e instale a versão mais recente do Aspose.PDF em[aqui](https://releases.aspose.com/pdf/net/).
2. IDE (como o Visual Studio): configure um ambiente de desenvolvimento .NET.
3. Conhecimento básico de programação em C#: É necessário um pouco de familiaridade com C#.
4.  Licença Aspose.PDF: Obtenha uma licença temporária ou completa para desbloquear todos os recursos da biblioteca. Você pode obter uma avaliação gratuita[aqui](https://purchase.aspose.com/temporary-license/).

## Pacotes de importação

Antes de começar, certifique-se de importar os namespaces necessários. Você precisará do seguinte em seu projeto:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Agora que tudo está configurado, vamos para o guia passo a passo!

Vamos criar uma tabela em um documento PDF e estilizar suas células. Cada etapa explicará o processo em detalhes.

## Etapa 1: Crie um novo documento PDF

 O primeiro passo é criar um novo documento PDF. No Aspose.PDF, você pode inicializar um novo`Document` objeto, que representa seu arquivo PDF.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Criar um novo documento PDF
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table cell style");
taggedContent.SetLanguage("en-US");
```

Aqui, inicializamos um documento PDF e definimos seu título e idioma. Isso dá ao seu documento uma estrutura adequada, o que é essencial para a conformidade com PDF/UA.

## Etapa 2: Configurar a estrutura da tabela

Tabelas em PDFs são definidas dentro de elementos de estrutura. Vamos criar a tabela e definir as linhas e colunas da tabela.

```csharp
// Obter o elemento de estrutura raiz
StructureElement rootElement = taggedContent.RootElement;

// Criar um elemento de estrutura de tabela
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

Agora definimos o cabeçalho da tabela (`TableTHeadElement`), corpo (`TableTBodyElement`), e pé (`TableTFootElement`) seções. Você pode pensar nelas como o esqueleto da sua tabela.

## Etapa 3: estilize as células do cabeçalho

Estilizar as células do cabeçalho faz com que elas se destaquem. Aqui, aplicamos cores de fundo, bordas e alinhamento de texto.

```csharp
int colCount = 4;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";

for (int colIndex = 0; colIndex < colCount; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText($"Head {colIndex}");
    thElement.BackgroundColor = Color.GreenYellow;
    thElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
    thElement.IsNoBorder = true;
    thElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
    thElement.Alignment = HorizontalAlignment.Right;
}
```

Nesta etapa, fazemos um loop por cada célula de cabeçalho, dando a ela um fundo verde-amarelo, uma borda cinza e um texto alinhado à direita. Você pode ajustar essas propriedades para corresponder ao seu design desejado.

## Etapa 4: preencher e estilizar o corpo da tabela

O corpo da tabela contém os dados reais. Veja como você pode estilizar cada célula com margens, bordas e configurações de texto específicas.

```csharp
int rowCount = 4;

for (int rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    trElement.AlternativeText = $"Row {rowIndex}";

    for (int colIndex = 0; colIndex < colCount; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText($"Cell [{rowIndex}, {colIndex}]");
        tdElement.BackgroundColor = Color.Yellow;
        tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
        tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
        tdElement.Alignment = HorizontalAlignment.Center;
        
        TextState cellTextState = new TextState();
        cellTextState.ForegroundColor = Color.DarkBlue;
        cellTextState.FontSize = 7.5F;
        cellTextState.FontStyle = FontStyles.Bold;
        cellTextState.Font = FontRepository.FindFont("Arial");
        tdElement.DefaultCellTextState = cellTextState;
    }
}
```

 Nesta etapa, preenchemos o corpo da tabela com quatro linhas e estilizamos cada célula com fundos amarelos e texto centralizado em negrito azul. Também usamos o`MarginInfo`classe para definir o preenchimento ao redor do texto.

## Etapa 5: estilize o rodapé

Para dar à tabela uma estrutura completa, adicionamos e estilizamos as células do rodapé, assim como fizemos com o cabeçalho.

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";

for (int colIndex = 0; colIndex < colCount; colIndex++)
{
    TableTDElement tdElement = footTrElement.CreateTD();
    tdElement.SetText($"Foot {colIndex}");
}
```

A seção de rodapé tem um estilo semelhante ao do cabeçalho, facilitando o acompanhamento da estrutura da tabela pelos leitores.

## Etapa 6: Salvar e validar o documento PDF

Por fim, salvamos o documento PDF e verificamos se ele é compatível com PDF/UA.

```csharp
// Salvar o documento PDF marcado
document.Save(dataDir + "StyleTableCell.pdf");

// Verificando a conformidade com PDF/UA
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```

 Salvamos o PDF e usamos o`Validate` método para garantir que atenda aos padrões de acessibilidade (conformidade com PDF/UA).

## Conclusão

Estilizar tabelas em um PDF usando o Aspose.PDF para .NET é poderoso e flexível. Com algumas linhas de código, você pode criar designs de tabela personalizados que farão seus documentos PDF se destacarem. Desde personalizar bordas e fundos de células até garantir a conformidade com a acessibilidade, o Aspose.PDF facilita a criação de arquivos PDF refinados.

## Perguntas frequentes

### Posso aplicar estilos diferentes a células de tabela individuais?  
Sim, você pode estilizar células individuais personalizando o`TableTDElement` propriedades.

### Como posso mesclar células de tabela?  
 Você pode usar o`ColSpan` e`RowSpan` propriedades para mesclar células em uma tabela.

### É possível criar uma tabela compatível com PDF/UA?  
 Sim, conforme demonstrado neste guia, você pode garantir a conformidade com PDF/UA validando seu documento usando o`Validate` método.

### Posso usar fontes diferentes nas células da tabela?  
 Absolutamente! Você pode especificar fontes diferentes usando o`TextState` objeto para cada célula.

### Como faço para baixar o Aspose.PDF para .NET?  
 Você pode baixá-lo do[página de lançamentos](https://releases.aspose.com/pdf/net/).