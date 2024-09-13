---
title: Elementos de estrutura em linha
linktitle: Elementos de estrutura em linha
second_title: Referência da API do Aspose.PDF para .NET
description: Guia passo a passo para usar elementos estruturais online com Aspose.PDF para .NET. Organize seus PDFs com títulos e parágrafos.
type: docs
weight: 110
url: /pt/net/programming-with-tagged-pdf/inline-structure-elements/
---
Neste guia passo a passo, mostraremos como usar elementos de estrutura inline com Aspose.PDF para .NET. Aspose.PDF é uma biblioteca poderosa que permite manipular documentos PDF programaticamente. Elementos de estrutura inline permitem que você crie uma estrutura hierárquica em seu documento PDF usando títulos de diferentes níveis e parágrafos.

Vamos mergulhar no código e aprender como usar elementos de estrutura embutidos com Aspose.PDF para .NET.

## Pré-requisitos

Antes de começar, certifique-se de ter o seguinte:

1. Biblioteca Aspose.PDF para .NET instalada.
2. Conhecimento básico da linguagem de programação C#.

## Etapa 1: Configurando o ambiente

Para começar, abra seu ambiente de desenvolvimento C# e crie um novo projeto. Certifique-se de ter adicionado uma referência à biblioteca Aspose.PDF para .NET em seu projeto.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Etapa 2: Criando o documento

 O primeiro passo é criar um novo documento PDF usando o`Document` aula.

```csharp
// Crie o documento PDF
Document document = new Document();
```

## Etapa 3: trabalhe com conteúdo marcado

Então, obtemos o conteúdo marcado do documento para trabalhar.

```csharp
// Obter o conteúdo marcado do documento
ITaggedContent taggedContent = document.TaggedContent;
```

## Etapa 4: Defina o título e o idioma do documento

Agora podemos definir o título e o idioma do documento.

```csharp
// Defina o título e o idioma do documento
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

## Etapa 5: Adicionar elementos estruturais on-line

Agora vamos adicionar elementos de estrutura em linha, como títulos de diferentes níveis e parágrafos, ao nosso documento.

```csharp
// Obter o elemento de estrutura raiz
StructureElement rootElement = taggedContent.RootElement;

// Adicionar cabeçalhos de diferentes níveis
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

// Adicionar conteúdo a cada cabeçalho
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

// Adicionar um parágrafo
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P.");
rootElement.AppendChild(p);

// Adicionar conteúdo ao parágrafo
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

Aqui criamos elementos de estrutura em linha, como títulos de diferentes níveis e um parágrafo, e adicionamos conteúdo a eles.

## Etapa 6: Salve o documento PDF marcado

Por fim, salvamos o documento PDF marcado.

```csharp
// Salvar o documento PDF marcado
document.Save(dataDir + "InlineStructureElements.pdf");
```

### Código-fonte de exemplo para elementos de estrutura em linha usando Aspose.PDF para .NET 

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

// Obter elemento de estrutura raiz
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

Parabéns! Você aprendeu a usar elementos de estrutura inline com o Aspose.PDF para .NET. Agora você pode criar uma estrutura hierárquica em seu documento PDF usando títulos de diferentes níveis e parágrafos. Explore mais recursos do Aspose.PDF para descobrir todo o seu potencial.

### Perguntas frequentes

#### P: O que são elementos de estrutura em linha em um documento PDF e como eles contribuem para criar uma estrutura hierárquica?

A: Elementos de estrutura inline em um documento PDF, como títulos de diferentes níveis e parágrafos, são usados para criar uma estrutura hierárquica que organiza e apresenta o conteúdo de forma estruturada. Esses elementos permitem que você estabeleça uma hierarquia e um fluxo de informações claros dentro do documento.

#### P: Como os elementos de estrutura em linha podem melhorar a legibilidade e a organização de um documento PDF?

A: Elementos de estrutura em linha, particularmente títulos e parágrafos, ajudam a melhorar a legibilidade e a organização de um documento PDF ao fornecer uma estrutura lógica. Os títulos indicam diferentes níveis de importância e ajudam os leitores a navegar pelo conteúdo, enquanto os parágrafos agrupam informações relacionadas.

#### P: Como o Aspose.PDF para .NET facilita o uso de elementos de estrutura em linha?

A: O Aspose.PDF para .NET oferece classes e métodos para criar e manipular elementos de estrutura inline, como títulos e parágrafos. Esses elementos podem ser personalizados, organizados hierarquicamente e enriquecidos com conteúdo para melhorar a apresentação visual e a acessibilidade do documento.

####  P: Qual é o propósito do`taggedContent` object in relation to inline structure elements?

 A: O`taggedContent` objeto, obtido do`TaggedContent` propriedade de um`Document`, permite que você trabalhe com elementos estruturados, incluindo elementos de estrutura inline. Ele permite que você crie, personalize e organize títulos e parágrafos dentro do documento.

#### P: Como os elementos de estrutura em linha ajudam a criar uma hierarquia de documento clara?

A: Elementos de estrutura em linha, como títulos de vários níveis, contribuem para estabelecer uma hierarquia clara e bem definida no documento. Os leitores podem identificar rapidamente os principais tópicos, subtópicos e conteúdo relacionado, tornando o documento mais fácil de navegar e compreender.

#### P: Posso personalizar a aparência e a formatação de elementos de estrutura em linha usando o Aspose.PDF para .NET?

R: Sim, você pode personalizar a aparência e a formatação dos elementos de estrutura inline. Você pode definir propriedades como estilos de fonte, tamanhos, cores, alinhamento, recuo e espaçamento para obter a apresentação visual desejada para títulos e parágrafos.

#### P: Como posso criar e adicionar títulos de diferentes níveis a um documento PDF usando elementos de estrutura em linha no Aspose.PDF para .NET?

 R: Você pode criar títulos de diferentes níveis usando o`CreateHeaderElement`método e, em seguida, anexá-los ao elemento de estrutura raiz. Posteriormente, você pode adicionar conteúdo a cada elemento de título usando o`CreateSpanElement` método para criar extensões de texto.

#### P: Posso usar elementos de estrutura em linha para criar listas, marcadores ou outros tipos de organização de conteúdo em um documento PDF?

R: Embora os elementos de estrutura em linha sejam usados principalmente para títulos e parágrafos, você pode usá-los em combinação com outros recursos oferecidos pelo Aspose.PDF para .NET para criar listas, marcadores, tabelas e outros tipos de organização de conteúdo para uma estrutura de documento abrangente.

#### P: Como os elementos de estrutura em linha contribuem para a acessibilidade do documento?

A: Elementos de estrutura em linha desempenham um papel crucial na melhoria da acessibilidade do documento. Títulos e parágrafos adequadamente estruturados fornecem uma hierarquia de documento clara que auxilia leitores de tela e outras tecnologias assistivas a interpretar e transmitir o conteúdo com precisão para usuários com deficiências.

#### P: Posso explorar usos mais avançados de elementos de estrutura em linha, como criar elementos interativos ou incorporar multimídia?

R: Com certeza! Embora este tutorial se concentre na criação de títulos e parágrafos, o Aspose.PDF para .NET oferece recursos avançados para criar elementos interativos, incorporar multimídia, adicionar hiperlinks e muito mais. Verifique a documentação e os exemplos da biblioteca para se aprofundar nesses recursos avançados.