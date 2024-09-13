---
title: Aplicar estilo numérico em arquivo PDF
linktitle: Aplicar estilo numérico em arquivo PDF
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda a aplicar diferentes estilos numéricos (numerais romanos, alfabéticos) a títulos em um PDF usando o Aspose.PDF para .NET com este guia passo a passo.
type: docs
weight: 10
url: /pt/net/programming-with-headings/apply-number-style/
---
## Introdução

Já se viu precisando adicionar listas lindamente numeradas aos seus documentos PDF? Não importa se você está formatando documentos legais, relatórios ou apresentações, estilos de numeração adequados são essenciais para organizar informações. Com o Aspose.PDF para .NET, você pode aplicar vários estilos de numeração aos títulos do seu arquivo PDF, criando documentos bem estruturados e profissionais. 

## Pré-requisitos

Antes de mergulhar na codificação, vamos ver o que você precisa:

1. Aspose.PDF para .NET: Baixe a versão mais recente do Aspose.PDF em[aqui](https://releases.aspose.com/pdf/net/).
2. Ambiente de desenvolvimento: certifique-se de ter o Visual Studio ou qualquer outro IDE compatível com .NET.
3. .NET Framework: certifique-se de ter o .NET Framework 4.0 ou superior instalado.
4.  Licença: Você pode usar uma licença temporária de[aqui](https://purchase.aspose.com/temporary-license/) ou explorar o[teste gratuito](https://releases.aspose.com/) opções.

## Pacotes de importação

Para começar, certifique-se de ter os seguintes namespaces importados em seu projeto:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Etapa 1: Configurando o documento

Vamos começar criando um novo documento PDF e configurando suas configurações de página. Definiremos o tamanho da página e as margens para controlar o layout do nosso conteúdo.

Explicação: Nesta etapa, estamos configurando a estrutura básica do PDF, o que inclui definir o tamanho da página, a altura e as margens para uma formatação consistente.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDoc = new Document();

// Definir dimensões e margens da página
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
```

Ao fazer isso, seu documento terá um tamanho de página padrão, equivalente a uma página de 8,5 x 11 polegadas, e uma margem de 72 pontos (ou 1 polegada) em todos os lados.

## Etapa 2: Adicionar uma página ao PDF

Em seguida, adicionaremos uma nova página ao documento PDF onde aplicaremos posteriormente os estilos de numeração.

Explicação: Todo PDF requer páginas! Esta etapa adiciona uma página em branco ao PDF e define suas margens para corresponder às configurações de nível de documento.

```csharp
// Adicionar uma nova página ao documento PDF
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo.Width = 612.0;
pdfPage.PageInfo.Height = 792.0;
pdfPage.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfPage.PageInfo.Margin.Left = 72;
pdfPage.PageInfo.Margin.Right = 72;
pdfPage.PageInfo.Margin.Top = 72;
pdfPage.PageInfo.Margin.Bottom = 72;
```

## Etapa 3: Crie uma caixa flutuante

Um FloatingBox permite que você coloque conteúdo (como texto ou títulos) dentro de uma caixa que se comporta independentemente do fluxo da página. Isso é útil quando você quer controle completo sobre o layout do seu conteúdo.

Explicação: Aqui, estamos configurando um FloatingBox para conter os títulos que terão estilos numéricos aplicados.

```csharp
// Crie um FloatingBox para conteúdo estruturado
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox();
floatBox.Margin = pdfPage.PageInfo.Margin;
pdfPage.Paragraphs.Add(floatBox);
```

## Etapa 4: adicione o primeiro título com algarismos romanos

Agora vem a parte emocionante! Vamos adicionar o primeiro título com numeração em algarismos romanos minúsculos.

Explicação: Estamos aplicando o estilo NumberingStyle.NumeralsRomanLowercase ao título, que exibirá a numeração em algarismos romanos (i, ii, iii, etc.).

```csharp
// Crie o primeiro título com algarismos romanos
Aspose.Pdf.Heading heading = new Aspose.Pdf.Heading(1);
heading.IsInList = true;
heading.StartNumber = 1;
heading.Text = "List 1";
heading.Style = NumberingStyle.NumeralsRomanLowercase;
heading.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading);
```

## Etapa 5: adicione um segundo título de numeral romano

Para fins de demonstração, vamos adicionar um segundo título de algarismo romano, mas desta vez começaremos com 13.

Explicação: A propriedade StartNumber permite que você comece a numerar a partir de um número personalizado — neste caso, estamos começando em 13.

```csharp
// Crie um segundo título começando no numeral romano 13
Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
heading2.IsInList = true;
heading2.StartNumber = 13;
heading2.Text = "List 2";
heading2.Style = NumberingStyle.NumeralsRomanLowercase;
heading2.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading2);
```

## Etapa 6: Adicione um título com numeração alfabética

Para variar, vamos adicionar um terceiro título, mas desta vez usaremos numeração alfabética em letras minúsculas (a, b, c, etc.).

Explicação: Alterar o NumberingStyle para LettersLowercase nos permite aplicar numeração alfabética aos nossos títulos.

```csharp
// Crie um título com numeração alfabética
Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2);
heading3.IsInList = true;
heading3.StartNumber = 1;
heading3.Text = "the value, as of the effective date of the plan, of property to be distributed under the plan on account of each allowed";
heading3.Style = NumberingStyle.LettersLowercase;
heading3.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading3);
```

## Etapa 7: Salvando o PDF

Por fim, depois de aplicar todos os títulos e estilos de numeração, vamos salvar o arquivo PDF no diretório desejado.

Explicação: Esta etapa salva o arquivo PDF contendo todos os títulos formatados com estilos de numeração aplicados.

```csharp
// Salvar o documento PDF
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumber style applied successfully in headings.\nFile saved at " + dataDir);
```

## Conclusão

E aí está! Você aplicou com sucesso estilos de numeração — algarismos romanos e alfabéticos — a títulos em um arquivo PDF usando o Aspose.PDF para .NET. A flexibilidade fornecida pelo Aspose.PDF para controlar o layout da página, estilos de numeração e posicionamento de conteúdo fornece um poderoso conjunto de ferramentas para criar documentos PDF profissionais e bem organizados.

## Perguntas frequentes

### Posso aplicar diferentes estilos numéricos ao mesmo documento PDF?  
Sim, o Aspose.PDF para .NET permite que você misture diferentes estilos de numeração, como algarismos romanos, algarismos arábicos e numeração alfabética no mesmo documento.

### Como posso personalizar o número inicial dos títulos?  
 Você pode definir o número inicial para qualquer título usando o`StartNumber` propriedade.

### Existe uma maneira de redefinir a sequência de numeração?  
Sim, você pode redefinir a numeração ajustando o`StartNumber` propriedade para cada título.

### Posso aplicar estilo negrito ou itálico aos títulos, além da numeração?  
 Absolutamente! Você pode personalizar os estilos de título modificando propriedades como fonte, tamanho, negrito e itálico usando o`TextState` objeto.

### Como obtenho uma licença temporária para o Aspose.PDF?  
 Você pode obter uma licença temporária em[aqui](https://purchase.aspose.com/temporary-license/) para testar o Aspose.PDF sem restrições.