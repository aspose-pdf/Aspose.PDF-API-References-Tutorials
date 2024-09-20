---
title: Colocando texto ao redor da imagem em arquivo PDF
linktitle: Colocando texto ao redor da imagem em arquivo PDF
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda a colocar texto ao redor de imagens em PDFs usando Aspose.PDF para .NET. Siga nosso guia passo a passo para criar PDFs profissionais com imagens e texto lado a lado.
type: docs
weight: 260
url: /pt/net/programming-with-text/placing-text-around-image/
---
## Introdução

Você já tentou colocar texto ao redor de uma imagem em um arquivo PDF, mas achou desafiador? Se sim, você está no lugar certo! O Aspose.PDF para .NET simplifica esse processo, permitindo que você coloque texto ao lado de imagens com apenas algumas linhas de código. Não importa se você está criando relatórios, documentos ou apresentações, esse recurso é uma maneira fantástica de aprimorar o layout do seu conteúdo e torná-lo mais atraente visualmente. Hoje, mostraremos como usar o Aspose.PDF para .NET para colocar texto ao redor de imagens em um documento PDF.

## Pré-requisitos

Antes de pularmos para o código, vamos nos certificar de que temos tudo configurado. Aqui está o que você vai precisar:

-  Aspose.PDF para .NET: Você pode baixá-lo em[aqui](https://releases.aspose.com/pdf/net/).
- Visual Studio: certifique-se de ter a versão mais recente instalada para acompanhar sem problemas.
- .NET Framework: Este exemplo usa .NET, portanto, certifique-se de que seu ambiente esteja configurado para desenvolvimento .NET.
-  Uma licença temporária: você pode solicitar uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/) se você estiver avaliando o produto.

Se você ainda não configurou o Aspose.PDF para .NET, siga as instruções de instalação no[documentação](https://reference.aspose.com/pdf/net/).

## Importar namespaces

Antes de começarmos a codificar, precisamos importar os namespaces necessários. Aqui está o trecho de código para fazer isso:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

 Esses namespaces são essenciais, pois fornecem acesso a classes como`Document`, `Page`, `Image` , e`HtmlFragment`, que usaremos para criar e manipular o PDF.

Agora que definimos o cenário, vamos detalhar como colocar texto ao redor de uma imagem no seu arquivo PDF usando o Aspose.PDF para .NET. Nós o guiaremos por isso passo a passo.

## Etapa 1: Instanciar o objeto Document

 Primeiro, você precisa criar um documento PDF. No Aspose.PDF, isso é feito instanciando um`Document` objeto. Este objeto servirá como base para todo o conteúdo que adicionaremos.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

Aqui, criamos um documento PDF vazio. Ele ainda não tem nenhuma página, mas não se preocupe, adicionaremos uma na próxima etapa.

## Etapa 2: Adicionar uma página ao documento

Agora que temos nosso documento, é hora de adicionar uma página. Pense nisso como criar uma folha de papel em branco onde você adicionará seu conteúdo.

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

Este código adiciona uma nova página ao documento. Por padrão, a página está em branco, mas estamos prestes a mudar isso.

## Etapa 3: Crie uma tabela para organizar o conteúdo

Para manter nossa imagem e texto alinhados corretamente, usaremos uma tabela. Tabelas em PDFs podem ajudar a estruturar seu layout, assim como em documentos Word ou HTML.

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
page.Paragraphs.Add(table1);
```

Este snippet cria uma tabela e a adiciona à página. Pense na tabela como a estrutura para alinhar sua imagem e texto.

## Etapa 4: Defina as larguras das colunas para a tabela

Agora que adicionamos uma tabela, precisamos definir a largura das colunas. Isso garante que a imagem e o texto sejam dimensionados apropriadamente na página.

```csharp
table1.ColumnWidths = "120 270";
```

Esta linha define a largura de duas colunas — uma para a imagem e outra para o texto. Ajuste esses valores se sua imagem ou texto precisar de mais ou menos espaço.

## Etapa 5: Definir margens e preenchimento

Para garantir que tudo fique organizado, vamos adicionar algumas margens e preenchimento à tabela.

```csharp
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
table1.DefaultCellPadding = margin;
```

Essas configurações garantem que sua tabela tenha espaçamento consistente, tornando o conteúdo visualmente atraente.

## Etapa 6: Insira uma imagem na tabela

Agora, vamos para a parte divertida — adicionar uma imagem. Neste caso, adicionaremos o logotipo Aspose, mas fique à vontade para usar qualquer imagem que você goste.

```csharp
Aspose.Pdf.Row row1 = table1.Rows.Add();
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
logo.File = dataDir + "aspose-logo.jpg";
logo.FixHeight = 120;
logo.FixWidth = 110;
row1.Cells.Add();
row1.Cells[0].Paragraphs.Add(logo);
```

Veja o que está acontecendo:
- Carregamos a imagem do diretório especificado.
- Definimos a altura e a largura da imagem.
- Por fim, adicionamos a imagem à primeira célula da tabela.

## Etapa 7: adicione texto ao lado da imagem

Agora que a imagem está no lugar, vamos adicionar algum texto ao lado dela. Para este exemplo, usaremos texto formatado em HTML para estilizar o conteúdo.

```csharp
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b> Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF document reporting component that enables .NET applications to <b>create PDF documents from scratch</b> without utilizing Adobe Acrobat.</font>";

Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
row1.Cells[1].Paragraphs.Add(TitleText);
```

Este bloco adiciona um título estilizado e uma descrição na célula ao lado da imagem. Você pode formatar o texto usando tags HTML para mais personalização.

## Etapa 8: ajuste o alinhamento vertical

Por padrão, o conteúdo nas células da tabela pode não se alinhar da maneira que você quer. Neste caso, queremos ter certeza de que o texto esteja alinhado ao topo da célula.

```csharp
row1.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
```

Isso garante que o texto fique no topo da célula, mantendo o layout limpo e profissional.

## Etapa 9: adicione mais texto abaixo da imagem e da descrição

Talvez você queira incluir mais conteúdo abaixo da imagem e do texto. Vamos adicionar outra linha à tabela para esse propósito.

```csharp
Aspose.Pdf.Row SecondRow = table1.Rows.Add();
SecondRow.Cells.Add();
SecondRow.Cells[0].ColSpan = 2;
SecondRow.Cells[0].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;

string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
```

Aqui, adicionamos outra linha com texto adicional, abrangendo ambas as colunas para manter o equilíbrio no layout.

## Etapa 10: Salve o documento PDF

Por fim, precisamos salvar o documento para que você possa visualizar as alterações.

```csharp
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

Isso salva o PDF com a imagem e o texto formatados exatamente como queremos.

## Conclusão

Colocar texto em volta de imagens em um PDF pode parecer uma tarefa assustadora, mas o Aspose.PDF para .NET simplifica o processo. Ao aproveitar tabelas, imagens e texto estilizado, você pode criar PDFs com aparência profissional com o mínimo de esforço. Com apenas algumas linhas de código, você pode posicionar o conteúdo exatamente onde quiser, dando aos seus documentos uma aparência polida e bem organizada.

## Perguntas frequentes

### Posso usar esse método para colocar várias imagens com texto?
Sim, basta adicionar mais linhas e células à sua tabela para incluir imagens e texto adicionais.

### Posso alterar o alinhamento da imagem?
Absolutamente! Você pode modificar o alinhamento da imagem ajustando as propriedades de alinhamento da célula.

### Como posso estilizar ainda mais o texto?
 Você pode usar tags HTML dentro do`HtmlFragment` objeto para aplicar vários estilos como negrito, itálico ou fontes diferentes.

### Posso controlar o espaçamento entre o texto e a imagem?
 Sim, usando o`MarginInfo` objeto permite que você controle o preenchimento e as margens entre os elementos.

### É possível adicionar links ao texto?
 Definitivamente! Você pode incorporar hiperlinks no texto formatado em HTML usando o`<a>` marcação.