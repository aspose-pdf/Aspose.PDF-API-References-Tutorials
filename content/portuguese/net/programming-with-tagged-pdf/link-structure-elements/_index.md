---
title: Elementos da estrutura de links
linktitle: Elementos da estrutura de links
second_title: Referência da API Aspose.PDF para .NET
description: Guia passo a passo para usar elementos de estrutura de links com Aspose.PDF para .NET. Crie hiperlinks em seus documentos PDF.
type: docs
weight: 120
url: /pt/net/programming-with-tagged-pdf/link-structure-elements/
---
Neste guia passo a passo, mostraremos como usar elementos de estrutura de links com Aspose.PDF para .NET. Aspose.PDF é uma biblioteca poderosa que permite criar e manipular documentos PDF de forma programática. Os elementos da estrutura de links permitem adicionar hiperlinks ao seu documento PDF, permitindo que os usuários cliquem nos links e naveguem para recursos online.

Vamos mergulhar no código e aprender como usar elementos de estrutura de links com Aspose.PDF for .NET.

## Pré-requisitos

Antes de começar, certifique-se de ter o seguinte:

1. Biblioteca Aspose.PDF para .NET instalada.
2. Conhecimento básico da linguagem de programação C#.

## Passo 1: Configurando o ambiente

Para começar, abra seu ambiente de desenvolvimento C# e crie um novo projeto. Certifique-se de ter adicionado uma referência à biblioteca Aspose.PDF para .NET em seu projeto.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";
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
taggedContent.SetTitle("Example Link Items");
taggedContent.SetLanguage("fr-FR");
```

## Etapa 5: adicionar elementos de estrutura de links

Agora vamos adicionar elementos de estrutura de links ao nosso documento. Criaremos diferentes tipos de links, incluindo links de texto simples, links de imagens e links multilinhas.
```csharp
// Obtenha o elemento da estrutura raiz (elemento da estrutura do documento)
StructureElement rootElement = taggedContent.RootElement;

// Adicione um parágrafo com um hiperlink
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);
link1.Hyperlink = new WebHyperlink("http://google.com");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";

// Adicione um parágrafo com um hiperlink contendo rich text
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";

// Adicione um parágrafo com um hiperlink contendo texto parcialmente formatado
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
LinkElement link3 = taggedContent.CreateLinkElement();
p3.AppendChild(link3);
link3.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("G");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText("oogle");
link3.AppendChild(span31);
link3.SetText("-");
link3.AppendChild(span32);
link3.AlternateDescriptions = "Link to Google";

// Adicione um parágrafo com um hiperlink multilinha
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://google.com");
link4.SetText("The multiline link: Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google");
link4.AlternateDescriptions = "Link to Google (multiline)";

// Adicione um parágrafo com um hiperlink contendo uma imagem
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);
LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://google.com");
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
StructureAttributes linkLayoutAttributes = link5.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
StructureAttribute placementAttribute = new StructureAttribute(AttributeKey.Placement);
placementAttribute.SetNameValue(AttributeName.Placement_Block);
linkLayoutAttributes.SetAttribute(placementAttribute);
link5.AppendChild(figure5);
link5.AlternateDescriptions = "Link to Google";
```

## Passo 6: Salve o documento PDF marcado

Finalmente, salvamos o documento PDF marcado.

```csharp
// Salve o documento PDF marcado
document. Save(outFile);
```

## Etapa 7: verifique a conformidade com PDF/UA

 Também podemos verificar a conformidade do documento com PDF/UA usando o`Validate` método do`Document` aula.

```csharp
// Verifique a conformidade com PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```


### Exemplo de código-fonte para elementos de estrutura de link usando Aspose.PDF para .NET 
```csharp

// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";

// Documento de criação e obtenção de conteúdo PDF marcado
Document document = new Document(); 
ITaggedContent taggedContent = document.TaggedContent;

// Configurando o título e o idioma natural do documento
taggedContent.SetTitle("Link Elements Example");
taggedContent.SetLanguage("en-US");

// Obtendo o elemento da estrutura raiz (elemento da estrutura do documento)
StructureElement rootElement = taggedContent.RootElement;
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);
link1.Hyperlink = new WebHyperlink("http://google.com");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
LinkElement link3 = taggedContent.CreateLinkElement();
p3.AppendChild(link3);
link3.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("G");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText("oogle");
link3.AppendChild(span31);
link3.SetText("-");
link3.AppendChild(span32);
link3.AlternateDescriptions = "Link to Google";
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://google.com");
link4.SetText("The multiline link: Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google");
link4.AlternateDescriptions = "Link to Google (multiline)";
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);
LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://google.com");
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
StructureAttributes linkLayoutAttributes = link5.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
StructureAttribute placementAttribute = new StructureAttribute(AttributeKey.Placement);
placementAttribute.SetNameValue(AttributeName.Placement_Block);
linkLayoutAttributes.SetAttribute(placementAttribute);
link5.AppendChild(figure5);
link5.AlternateDescriptions = "Link to Google";

// Salvar documento PDF marcado
document.Save(outFile);

// Verificando a conformidade com PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```
## Conclusão

Parabéns! Você aprendeu como usar elementos de estrutura de links com Aspose.PDF para .NET. Agora você pode criar hiperlinks em seus documentos PDF, permitindo que os usuários naveguem até recursos online. Experimente e explore mais recursos do Aspose.PDF para criar documentos PDF interativos e enriquecidos.

### Perguntas frequentes

#### P: O que são elementos de estrutura de links em um documento PDF e como eles melhoram a interatividade do documento?

R: Os elementos da estrutura de links em um documento PDF são usados para criar hiperlinks que permitem aos usuários navegar para recursos on-line ou locais específicos no documento. Esses elementos melhoram a interatividade, fornecendo links clicáveis que permitem aos usuários acessar conteúdo relacionado ou sites externos.

#### P: Como os elementos da estrutura de links podem ser benéficos em um documento PDF?

R: Os elementos da estrutura de links melhoram a experiência do usuário, tornando o documento PDF interativo. Eles fornecem acesso rápido a informações adicionais, conteúdos relacionados, sites externos ou seções específicas do documento, melhorando a navegação e facilitando a recuperação de informações.

#### P: Posso criar diferentes tipos de hiperlinks usando elementos de estrutura de links no Aspose.PDF for .NET?

R: Sim, você pode criar vários tipos de hiperlinks usando elementos de estrutura de links. Aspose.PDF for .NET permite criar hiperlinks com texto simples, rich text, imagens e descrições de várias linhas, oferecendo versatilidade na forma como você vincula a conteúdo externo ou locais dentro do documento.

#### P: Como configuro e inicializo elementos de estrutura de links em um documento PDF usando Aspose.PDF for .NET?

 R: Para usar elementos de estrutura de links, primeiro você precisa criar um novo documento PDF usando o`Document` aula. Em seguida, obtenha o conteúdo marcado usando o`TaggedContent`propriedade do documento. A partir daí, você pode criar e personalizar elementos da estrutura de links e adicioná-los ao elemento da estrutura raiz.

#### P: Como posso criar um hiperlink de texto simples usando elementos de estrutura de links?
 R: Você pode criar um hiperlink de texto simples criando um`LinkElement` e definindo seu`Hyperlink` propriedade para um`WebHyperlink` com o URL ao qual você deseja vincular. Você também pode definir o texto de exibição do link usando o`SetText` método.

#### P: É possível criar hiperlinks com imagens usando elementos de estrutura de links?

 R: Sim, você pode criar hiperlinks com imagens usando elementos de estrutura de links. Você criaria um`LinkElement` e depois anexe um`FigureElement` com uma imagem para ele. Isso permite que você crie um hiperlink baseado em imagem.

#### P: Como posso garantir que meu documento PDF com hiperlinks seja compatível com o padrão PDF/UA de acessibilidade?

 R: Aspose.PDF for .NET oferece a capacidade de validar a conformidade do seu documento PDF com o padrão PDF/UA usando o`Validate` método do`Document`aula. Isso garante que os hiperlinks do documento sejam acessíveis a usuários com deficiência.

#### P: O que são descrições alternativas para elementos da estrutura de links e por que são importantes?

R: Descrições alternativas (texto alternativo) para elementos da estrutura de links fornecem descrições textuais dos hiperlinks. Estas descrições são essenciais para a acessibilidade, permitindo aos utilizadores com deficiência visual compreender a finalidade do link e o seu destino.

#### P: Posso personalizar a aparência e o comportamento de hiperlinks criados usando elementos de estrutura de links?

R: Embora os elementos da estrutura de links se concentrem principalmente na criação de hiperlinks, você pode personalizar ainda mais a aparência e o comportamento dos hiperlinks usando outros recursos oferecidos pelo Aspose.PDF para .NET. Isso inclui a especificação de cores, estilos e ações de link.

#### P: Como os elementos da estrutura de links contribuem para tornar os documentos PDF mais interativos e fáceis de usar?

R: Os elementos da estrutura de links transformam documentos PDF estáticos em experiências interativas adicionando hiperlinks clicáveis. Essa interatividade melhora o envolvimento do usuário, permite uma navegação perfeita entre conteúdos relacionados e melhora a usabilidade geral do documento.