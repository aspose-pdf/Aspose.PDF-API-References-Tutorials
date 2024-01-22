---
title: Elementos de estrutura embutidos
linktitle: Elementos de estrutura embutidos
second_title: Referência da API Aspose.PDF para .NET
description: Guia passo a passo para usar elementos estruturais online com Aspose.PDF para .NET. Organize seus PDFs com títulos e parágrafos.
type: docs
weight: 110
url: /pt/net/programming-with-tagged-pdf/inline-structure-elements/
---
Neste guia passo a passo, mostraremos como usar elementos de estrutura embutidos com Aspose.PDF para .NET. Aspose.PDF é uma biblioteca poderosa que permite manipular documentos PDF programaticamente. Os elementos de estrutura embutida permitem criar uma estrutura hierárquica em seu documento PDF usando títulos de diferentes níveis e parágrafos.

Vamos mergulhar no código e aprender como usar elementos de estrutura embutidos com Aspose.PDF para .NET.

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
// Crie o documento PDF
Document document = new Document();
```

## Etapa 3: Trabalhe com conteúdo marcado

Em seguida, obtemos o conteúdo marcado do documento para trabalhar.

```csharp
// Obtenha o conteúdo marcado do documento
ITaggedContent taggedContent = document.TaggedContent;
```

## Etapa 4: definir o título e o idioma do documento

Agora podemos definir o título e o idioma do documento.

```csharp
// Defina o título e o idioma do documento
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

## Passo 5: Adicione elementos estruturais online

Agora vamos adicionar elementos de estrutura embutida, como títulos de diferentes níveis e parágrafos, ao nosso documento.

```csharp
// Obtenha o elemento da estrutura raiz
StructureElement rootElement = taggedContent.RootElement;

// Adicione cabeçalhos de diferentes níveis
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);

// Adicione conteúdo a cada cabeçalho
SpanElement spanH11 = taggedContent.CreateSpanElement();
spanH11.SetText("H1.");
h1.AppendChild(spanH11);
SpanElement spanH12 = taggedContent.CreateSpanElement();
spanH12.SetText("Level 1 header");
h1.AppendChild(spanH12);

SpanElement spanH21 = taggedContent.CreateSpanElement();
spanH21.SetText("H2.");
h2.AppendChild(spanH21);
SpanElement spanH22 = taggedContent.CreateSpanElement();
spanH22.SetText("Level 2 header");
h2.AppendChild(spanH22);

SpanElement spanH31 = taggedContent.CreateSpanElement();
spanH31.SetText("H3.");
h3.AppendChild(spanH31);
SpanElement spanH32 = taggedContent.CreateSpanElement();
spanH32.SetText("Level 3 header");
h3.AppendChild(spanH32);

SpanElement spanH41 = taggedContent.CreateSpanElement();
spanH41.SetText("H4.");
h4.AppendChild(spanH41);
SpanElement spanH42 = taggedContent.CreateSpanElement();
spanH42.SetText("Level 4 header");
h4.AppendChild(spanH42);

SpanElement spanH51 = taggedContent.CreateSpanElement();
spanH51.SetText("H5.");
h5.AppendChild(spanH51);
SpanElement spanH52 = taggedContent.CreateSpanElement();
spanH52.SetText("Level 5 header");
h5.AppendChild(spanH52);

SpanElement spanH61 = taggedContent.CreateSpanElement();
spanH61.SetText("H6.");
h6.AppendChild(spanH61);
SpanElement spanH62 = taggedContent.CreateSpanElement();
spanH62.SetText("Heading level 6");
h6.AppendChild(spanH62);

// Adicione um parágrafo
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P.");
rootElement.AppendChild(p);

// Adicione conteúdo ao parágrafo
SpanElement span1 = taggedContent.CreateSpanElement();
span1.SetText("Lorem ipsum dolor sit amet, consectetur adipiscing elit.");
p.AppendChild(span1);
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Aenean nec lectus ac sem faucibus imperdiet.");
p.AppendChild(span2);
SpanElement span3 = taggedContent.CreateSpanElement();
span3.SetText("Sed ut erat ac magna ullamcorper hendrerit.");
p.AppendChild(span3);
SpanElement span4 = taggedContent.CreateSpanElement();
span4.SetText("Cras pellentesque libero semper, gravida magna sed, luctus leo.");
p.AppendChild(span4);
SpanElement span5 = taggedContent.CreateSpanElement();
span5.SetText("Fusce lectus odio, laoreet nec ullamcorper ut, molestie eu elit.");
p.AppendChild(span5);
SpanElement span6 = taggedContent.CreateSpanElement();
span6.SetText("Interdum et malesuada fames ac ante ipsum primis in faucibus. ");
p.AppendChild(span6);
SpanElement span7 = taggedContent.CreateSpanElement();
span7.SetText("Aliquam lacinia sit amet elit ac consectetur. So cursus condimentum ligula, vitae volutpat sem tristique eget. ");
p.AppendChild(span7);
SpanElement span8 = taggedContent.CreateSpanElement();
span8.SetText("Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. ");
p.AppendChild(span8);
SpanElement span9 = taggedContent.CreateSpanElement();
span9.SetText("Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit.");
p.AppendChild(span9);
SpanElement span10 = taggedContent.CreateSpanElement();
span10.SetText("Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");
p.AppendChild(span10);
```

Aqui criamos elementos de estrutura inline, como títulos de diferentes níveis e um parágrafo, e adicionamos conteúdo a eles.

## Passo 6: Salve o documento PDF marcado

Finalmente, salvamos o documento PDF marcado.

```csharp
// Salve o documento PDF marcado
document.Save(dataDir + "InlineStructureElements.pdf");
```

### Exemplo de código-fonte para elementos de estrutura embutidos usando Aspose.PDF para .NET 

```csharp

// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Criar documento PDF
Document document = new Document();

// Obtenha conteúdo para trabalhar com TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;

// Definir título e idioma para Documnet
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");

// Obtenha o elemento da estrutura raiz
StructureElement rootElement = taggedContent.RootElement;
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);
SpanElement spanH11 = taggedContent.CreateSpanElement();
spanH11.SetText("H1. ");
h1.AppendChild(spanH11);
SpanElement spanH12 = taggedContent.CreateSpanElement();
spanH12.SetText("Level 1 Header");
h1.AppendChild(spanH12);
SpanElement spanH21 = taggedContent.CreateSpanElement();
spanH21.SetText("H2. ");
h2.AppendChild(spanH21);
SpanElement spanH22 = taggedContent.CreateSpanElement();
spanH22.SetText("Level 2 Header");
h2.AppendChild(spanH22);
SpanElement spanH31 = taggedContent.CreateSpanElement();
spanH31.SetText("H3. ");
h3.AppendChild(spanH31);
SpanElement spanH32 = taggedContent.CreateSpanElement();
spanH32.SetText("Level 3 Header");
h3.AppendChild(spanH32);
SpanElement spanH41 = taggedContent.CreateSpanElement();
spanH41.SetText("H4. ");
h4.AppendChild(spanH41);
SpanElement spanH42 = taggedContent.CreateSpanElement();
spanH42.SetText("Level 4 Header");
h4.AppendChild(spanH42);
SpanElement spanH51 = taggedContent.CreateSpanElement();
spanH51.SetText("H5. ");
h5.AppendChild(spanH51);
SpanElement spanH52 = taggedContent.CreateSpanElement();
spanH52.SetText("Level 5 Header");
h5.AppendChild(spanH52);
SpanElement spanH61 = taggedContent.CreateSpanElement();
spanH61.SetText("H6. ");
h6.AppendChild(spanH61);
SpanElement spanH62 = taggedContent.CreateSpanElement();
spanH62.SetText("Level 6 Header");
h6.AppendChild(spanH62);
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P. ");
rootElement.AppendChild(p);
SpanElement span1 = taggedContent.CreateSpanElement();
span1.SetText("Lorem ipsum dolor sit amet, consectetur adipiscing elit. ");
p.AppendChild(span1);
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Aenean nec lectus ac sem faucibus imperdiet. ");
p.AppendChild(span2);
SpanElement span3 = taggedContent.CreateSpanElement();
span3.SetText("Sed ut erat ac magna ullamcorper hendrerit. ");
p.AppendChild(span3);
SpanElement span4 = taggedContent.CreateSpanElement();
span4.SetText("Cras pellentesque libero semper, gravida magna sed, luctus leo. ");
p.AppendChild(span4);
SpanElement span5 = taggedContent.CreateSpanElement();
span5.SetText("Fusce lectus odio, laoreet nec ullamcorper ut, molestie eu elit. ");
p.AppendChild(span5);
SpanElement span6 = taggedContent.CreateSpanElement();
span6.SetText("Interdum et malesuada fames ac ante ipsum primis in faucibus. ");
p.AppendChild(span6);
SpanElement span7 = taggedContent.CreateSpanElement();
span7.SetText("Aliquam lacinia sit amet elit ac consectetur. Donec cursus condimentum ligula, vitae volutpat sem tristique eget. ");
p.AppendChild(span7);
SpanElement span8 = taggedContent.CreateSpanElement();
span8.SetText("Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. ");
p.AppendChild(span8);
SpanElement span9 = taggedContent.CreateSpanElement();
span9.SetText("Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit. ");
p.AppendChild(span9);
SpanElement span10 = taggedContent.CreateSpanElement();
span10.SetText("Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");
p.AppendChild(span10);

// Salvar documento PDF marcado
document.Save(dataDir + "InlineStructureElements.pdf");

```

## Conclusão

Parabéns! Você aprendeu como usar elementos de estrutura embutidos com Aspose.PDF para .NET. Agora você pode criar uma estrutura hierárquica em seu documento PDF usando títulos de diferentes níveis e parágrafos. Explore mais recursos do Aspose.PDF para descobrir todo o seu potencial.

### Perguntas frequentes

#### P: O que são elementos de estrutura inline em um documento PDF e como eles contribuem para a criação de uma estrutura hierárquica?

R: Os elementos da estrutura embutida em um documento PDF, como títulos de diferentes níveis e parágrafos, são usados para criar uma estrutura hierárquica que organiza e apresenta o conteúdo de maneira estruturada. Esses elementos permitem estabelecer uma hierarquia clara e um fluxo de informações dentro do documento.

#### P: Como os elementos da estrutura embutida podem melhorar a legibilidade e a organização de um documento PDF?

R: Os elementos da estrutura embutida, principalmente títulos e parágrafos, ajudam a melhorar a legibilidade e a organização de um documento PDF, fornecendo uma estrutura lógica. Os títulos indicam diferentes níveis de importância e ajudam os leitores a navegar pelo conteúdo, enquanto os parágrafos agrupam informações relacionadas.

#### P: Como o Aspose.PDF for .NET facilita o uso de elementos de estrutura embutidos?

R: Aspose.PDF for .NET oferece classes e métodos para criar e manipular elementos de estrutura embutidos, como títulos e parágrafos. Esses elementos podem ser customizados, organizados hierarquicamente e enriquecidos com conteúdo para melhorar a apresentação visual e acessibilidade do documento.

####  P: Qual é o propósito do`taggedContent` object in relation to inline structure elements?

 R: O`taggedContent` objeto, obtido do`TaggedContent` propriedade de um`Document`, permite trabalhar com elementos estruturados, incluindo elementos de estrutura embutida. Ele permite criar, personalizar e organizar títulos e parágrafos no documento.

#### P: Como os elementos da estrutura embutida ajudam na criação de uma hierarquia clara de documentos?

R: Os elementos da estrutura embutida, como títulos de vários níveis, contribuem para estabelecer uma hierarquia clara e bem definida no documento. Os leitores podem identificar rapidamente os principais tópicos, subtópicos e conteúdos relacionados, tornando o documento mais fácil de navegar e compreender.

#### P: Posso personalizar a aparência e a formatação de elementos de estrutura embutidos usando Aspose.PDF for .NET?

R: Sim, você pode personalizar a aparência e a formatação dos elementos da estrutura embutida. Você pode definir propriedades como estilos de fonte, tamanhos, cores, alinhamento, recuo e espaçamento para obter a apresentação visual desejada para títulos e parágrafos.

#### P: Como posso criar e adicionar títulos de diferentes níveis a um documento PDF usando elementos de estrutura embutidos no Aspose.PDF for .NET?

 R: Você pode criar títulos de diferentes níveis usando o`CreateHeaderElement` método e, em seguida, anexe-os ao elemento da estrutura raiz. Posteriormente, você pode adicionar conteúdo a cada elemento de título usando o`CreateSpanElement` método para criar extensões de texto.

#### P: Posso usar elementos de estrutura embutidos para criar listas, marcadores ou outros tipos de organização de conteúdo em um documento PDF?

R: Embora os próprios elementos da estrutura embutida sejam usados principalmente para títulos e parágrafos, você pode usá-los em combinação com outros recursos oferecidos pelo Aspose.PDF for .NET para criar listas, marcadores, tabelas e outros tipos de organização de conteúdo para uma visão abrangente. estrutura do documento.

#### P: Como os elementos da estrutura inline contribuem para a acessibilidade dos documentos?

R: Os elementos da estrutura inline desempenham um papel crucial na melhoria da acessibilidade aos documentos. Títulos e parágrafos adequadamente estruturados fornecem uma hierarquia de documentos clara que auxilia os leitores de tela e outras tecnologias assistenciais na interpretação e transmissão precisa do conteúdo aos usuários com deficiência.

#### P: Posso explorar usos mais avançados de elementos de estrutura inline, como a criação de elementos interativos ou a incorporação de multimídia?

R: Absolutamente! Embora este tutorial se concentre na criação de títulos e parágrafos, Aspose.PDF for .NET oferece recursos avançados para criar elementos interativos, incorporar multimídia, adicionar hiperlinks e muito mais. Verifique a documentação e os exemplos da biblioteca para se aprofundar nesses recursos avançados.