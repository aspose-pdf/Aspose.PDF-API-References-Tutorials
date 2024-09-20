---
title: Elemento de tabela de estilo
linktitle: Elemento de tabela de estilo
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda a criar e estilizar um elemento de tabela no Aspose.PDF para .NET com instruções passo a passo, estilo personalizado e conformidade com PDF/UA.
type: docs
weight: 170
url: /pt/net/programming-with-tagged-pdf/style-table-element/
---
## Introdução

Neste artigo, vamos nos aprofundar em como criar e estilizar um elemento de tabela usando o Aspose.PDF para .NET. Você aprenderá como estruturar uma tabela, aplicar estilos personalizados e validar a conformidade do PDF/UA do seu documento. Ao final deste tutorial, você poderá criar tabelas com aparência profissional em seus PDFs com facilidade!

## Pré-requisitos

Antes de começar o tutorial, você precisa garantir que tem o seguinte:

1. Visual Studio ou um IDE similar instalado em sua máquina.
2. .NET Framework ou .NET Core SDK para executar o aplicativo.
3.  Biblioteca Aspose.PDF para .NET baixada e referenciada em seu projeto. Você pode obter a versão mais recente em[aqui](https://releases.aspose.com/pdf/net/).
4.  Uma licença Aspose válida ou uma[licença temporária](https://purchase.aspose.com/temporary-license/) para desbloquear a funcionalidade completa da biblioteca.

## Pacotes de importação

Para começar, importe os namespaces necessários para seu projeto:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Esses namespaces abrangem operações básicas de PDF, conteúdo marcado, tabelas e formatação de texto.

Agora vamos dividir o processo de criação e estilização de uma tabela no Aspose.PDF. Passaremos por cada seção em detalhes para que você possa acompanhar.

## Etapa 1: Crie um novo documento PDF e configure o conteúdo marcado

Nesta primeira etapa, criaremos um documento PDF em branco e configuraremos seu conteúdo marcado.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Criar um novo documento PDF
Document document = new Document();

// Configurar conteúdo marcado
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table style");
taggedContent.SetLanguage("en-US");
```

 Começamos criando um novo`Document` objeto, representando nosso PDF. O`TaggedContent`object é usado para gerenciar a estrutura do documento, garantindo conformidade com os padrões de acessibilidade. Definimos o título e o idioma do documento para marcação adequada.

## Etapa 2: Defina o elemento raiz

Em seguida, criaremos o elemento de estrutura raiz, que atua como contêiner para todo o conteúdo do nosso PDF.

```csharp
// Obter o elemento de estrutura raiz
StructureElement rootElement = taggedContent.RootElement;
```

 O`RootElement` serve como o contêiner base para todos os elementos estruturados, incluindo nossa tabela. Ele ajuda a manter a hierarquia estrutural do documento, o que é importante para organização e acessibilidade.

## Etapa 3: Crie e estilize o elemento de tabela

 Agora que o elemento raiz está configurado, criaremos um`TableElement` e aplique estilos como cor de fundo, bordas e alinhamento.

```csharp
// Criar elemento de estrutura de tabela
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);

// Estilize a mesa
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement.Alignment = HorizontalAlignment.Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
```

 Nós criamos um`TableElement` , que define nossa estrutura de tabela. O`BackgroundColor`, `Border` , e`Alignment` propriedades nos permitem personalizar a aparência da tabela. O`Broken` propriedade garante que se a tabela for quebrada entre páginas, ela será quebrada verticalmente.

## Etapa 4: definir dimensões da tabela e estilos de células

Nesta etapa, definiremos o número de colunas, o preenchimento das células e outras propriedades importantes da tabela.

```csharp
tableElement.ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement.DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
```

 Especificamos as larguras das colunas para garantir que cada coluna na tabela seja uniformemente espaçada.`DefaultCellBorder`, `DefaultCellPadding` , e`DefaultCellTextState` defina os estilos padrão para as células, incluindo bordas, preenchimento, cor do texto e tamanho da fonte.

## Etapa 5: Adicionar linhas repetidas e estilos personalizados

Também podemos definir estilos para linhas repetidas e outros elementos específicos da tabela, como cabeçalhos e rodapés.

```csharp
tableElement.RepeatingRowsCount = 3;
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
```

 O`RepeatingRowsCount` garante que as três primeiras linhas se repitam se a tabela abranger várias páginas. Definimos o`RepeatingRowsStyle` para aplicar uma cor de fundo personalizada a essas linhas.

## Etapa 6: adicione elementos de cabeçalho, corpo e rodapé da tabela

Agora, vamos criar as seções de cabeçalho, corpo e rodapé da tabela e preenchê-las com conteúdo.

```csharp
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

// Criar linha de cabeçalho
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (int colIndex = 0; colIndex < 5; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText($"Head {colIndex}");
}

// Preencha o corpo da tabela
for (int rowIndex = 0; rowIndex < 10; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    for (int colIndex = 0; colIndex < 5; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText($"Cell [{rowIndex}, {colIndex}]");
    }
}
```

 A tabela é dividida em três partes: a cabeça, o corpo e o pé. Primeiro criamos a linha de cabeçalho usando`TableTHElement` adicionar títulos de coluna. Em seguida, preenchemos o corpo da tabela com`TableTDElement`, preenchendo cada célula com um rótulo que inclui sua posição.

## Etapa 7: Salve o documento

Por fim, salvamos o documento PDF no diretório especificado.

```csharp
// Salvar o documento PDF marcado
document.Save(dataDir + "StyleTableElement.pdf");
```

Esta etapa finaliza o processo de criação do documento salvando o arquivo PDF com a tabela estilizada.

## Etapa 8: Validar a conformidade com PDF/UA

Depois de salvar o documento, é essencial garantir que ele esteja em conformidade com os padrões PDF/UA (Acessibilidade Universal).

```csharp
// Verifique a conformidade com PDF/UA
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```

Aqui, recarregamos o documento e o validamos em relação aos padrões PDF/UA. A conformidade garante que seu PDF atenda aos requisitos de acessibilidade, tornando-o adequado para uma ampla gama de usuários.

## Conclusão

Com o Aspose.PDF para .NET, criar e estilizar tabelas em seus documentos PDF é simples e intuitivo. Seguindo as etapas descritas neste tutorial, você pode criar tabelas com estilos personalizados e garantir que seus PDFs atendam aos padrões de acessibilidade. Quer você esteja gerando relatórios ou criando documentos estruturados, as tabelas são uma ferramenta poderosa para apresentar dados claramente.

## Perguntas frequentes

### Posso adicionar imagens dentro de células de tabela?
 Sim, você pode inserir imagens em células de tabela usando o`Image` elemento.

### Como ajusto as larguras das colunas dinamicamente?
 Você pode definir o`ColumnAdjustment` propriedade para`AutoFitToWindow` para ajustar as larguras das colunas automaticamente com base no conteúdo.

### A conformidade com PDF/UA é obrigatória para todos os documentos?
Embora não seja obrigatório, é recomendado para documentos que exigem altos padrões de acessibilidade.

### Posso aplicar estilos diferentes a linhas específicas?
 Sim, você pode personalizar linhas ou células individuais ajustando-as`TextState` ou`BackgroundColor`.

### Qual é o benefício de usar conteúdo marcado?
conteúdo marcado melhora a acessibilidade do documento e ajuda a garantir a conformidade com padrões como PDF/UA.