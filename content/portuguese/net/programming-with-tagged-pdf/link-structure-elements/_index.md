---
title: Elementos da estrutura do link
linktitle: Elementos da estrutura do link
second_title: Referência da API do Aspose.PDF para .NET
description: Guia passo a passo para usar elementos de estrutura de link com Aspose.PDF para .NET. Crie hiperlinks em seus documentos PDF.
type: docs
weight: 120
url: /pt/net/programming-with-tagged-pdf/link-structure-elements/
---
Neste guia passo a passo, mostraremos como usar elementos de estrutura de link com o Aspose.PDF para .NET. O Aspose.PDF é uma biblioteca poderosa que permite criar e manipular documentos PDF programaticamente. Os elementos de estrutura de link permitem adicionar hiperlinks ao seu documento PDF, permitindo que os usuários cliquem nos links e naveguem para recursos online.

Vamos mergulhar no código e aprender como usar elementos de estrutura de link com Aspose.PDF para .NET.

## Pré-requisitos

Antes de começar, certifique-se de ter o seguinte:

1. Biblioteca Aspose.PDF para .NET instalada.
2. Conhecimento básico da linguagem de programação C#.

## Etapa 1: Configurando o ambiente

Para começar, abra seu ambiente de desenvolvimento C# e crie um novo projeto. Certifique-se de ter adicionado uma referência à biblioteca Aspose.PDF para .NET em seu projeto.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";
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
taggedContent.SetTitle("Example Link Items");
taggedContent.SetLanguage("fr-FR");
```

## Etapa 5: Adicionar elementos de estrutura de link

Agora vamos adicionar elementos de estrutura de link ao nosso documento. Criaremos diferentes tipos de links, incluindo links de texto simples, links de imagem e links multi-linha.
```csharp
// Obter o elemento de estrutura raiz (elemento de estrutura do documento)
StructureElement rootElement = taggedContent.RootElement;

// Adicionar um parágrafo com um hiperlink
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);
link1.Hyperlink = new WebHyperlink("http://google.com");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";

// Adicionar um parágrafo com um hiperlink contendo texto enriquecido
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";

// Adicionar um parágrafo com um hiperlink contendo texto parcialmente formatado
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

// Adicionar um parágrafo com um hiperlink multilinha
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

## Etapa 6: Salve o documento PDF marcado

Por fim, salvamos o documento PDF marcado.

```csharp
// Salvar o documento PDF marcado
document. Save(outFile);
```

## Etapa 7: Verifique a conformidade do PDF/UA

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

// Criação de documento e obtenção de conteúdo PDF marcado
Document document = new Document(); 
ITaggedContent taggedContent = document.TaggedContent;

// Definir título e idioma da natureza para o documento
taggedContent.SetTitle("Link Elements Example");
taggedContent.SetLanguage("en-US");

// Obtendo o elemento de estrutura raiz (elemento de estrutura do documento)
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

Parabéns! Você aprendeu a usar elementos de estrutura de link com o Aspose.PDF para .NET. Agora você pode criar hiperlinks em seus documentos PDF, permitindo que os usuários naveguem para recursos online. Experimente e explore mais recursos do Aspose.PDF para criar documentos PDF interativos e enriquecidos.

### Perguntas frequentes

#### P: O que são elementos de estrutura de links em um documento PDF e como eles melhoram a interatividade do documento?

A: Os elementos de estrutura de link em um documento PDF são usados para criar hiperlinks que permitem que os usuários naveguem para recursos on-line ou locais específicos dentro do documento. Esses elementos aumentam a interatividade ao fornecer links clicáveis que permitem que os usuários acessem conteúdo relacionado ou sites externos.

#### P: Como os elementos da estrutura de links podem ser benéficos em um documento PDF?

A: Os elementos de estrutura de link melhoram a experiência do usuário ao tornar o documento PDF interativo. Eles fornecem acesso rápido a informações adicionais, conteúdo relacionado, sites externos ou seções específicas dentro do documento, melhorando a navegação e facilitando a recuperação de informações.

#### P: Posso criar diferentes tipos de hiperlinks usando elementos de estrutura de links no Aspose.PDF para .NET?

R: Sim, você pode criar vários tipos de hiperlinks usando elementos de estrutura de link. O Aspose.PDF para .NET permite que você crie hiperlinks com texto simples, rich text, imagens e descrições multilinha, oferecendo versatilidade em como você vincula a conteúdo externo ou locais dentro do documento.

#### P: Como configuro e inicializo elementos de estrutura de links em um documento PDF usando o Aspose.PDF para .NET?

 R: Para usar elementos de estrutura de link, primeiro você precisa criar um novo documento PDF usando o`Document` classe. Em seguida, obtenha o conteúdo marcado usando o`TaggedContent`propriedade do documento. A partir daí, você pode criar e personalizar elementos de estrutura de link e adicioná-los ao elemento de estrutura raiz.

#### P: Como posso criar um hiperlink de texto simples usando elementos de estrutura de link?
 R: Você pode criar um hiperlink de texto simples criando um`LinkElement` e definindo seu`Hyperlink` propriedade para um`WebHyperlink` com a URL que você deseja vincular. Você também pode definir o texto de exibição do link usando o`SetText` método.

#### P: É possível criar hiperlinks com imagens usando elementos de estrutura de links?

 R: Sim, você pode criar hiperlinks com imagens usando elementos de estrutura de link. Você criaria um`LinkElement` e então anexar um`FigureElement` com uma imagem para ele. Isso permite que você crie um hiperlink baseado em imagem.

#### P: Como posso garantir que meu documento PDF com hiperlinks esteja em conformidade com o padrão PDF/UA para acessibilidade?

 R: O Aspose.PDF para .NET oferece a capacidade de validar a conformidade do seu documento PDF com o padrão PDF/UA usando o`Validate` método do`Document`classe. Isso garante que os hiperlinks do documento sejam acessíveis a usuários com deficiências.

#### P: Quais são as descrições alternativas para elementos de estrutura de links e por que elas são importantes?

A: Descrições alternativas (texto alternativo) para elementos de estrutura de link fornecem descrições textuais dos hiperlinks. Essas descrições são essenciais para acessibilidade, permitindo que usuários com deficiência visual entendam o propósito do link e seu destino.

#### P: Posso personalizar a aparência e o comportamento de hiperlinks criados usando elementos de estrutura de links?

R: Embora os elementos da estrutura de links se concentrem principalmente na criação de hiperlinks, você pode personalizar ainda mais a aparência e o comportamento dos hiperlinks usando outros recursos oferecidos pelo Aspose.PDF para .NET. Isso inclui especificar cores, estilos e ações de link.

#### P: Como os elementos da estrutura de links contribuem para tornar os documentos PDF mais interativos e fáceis de usar?

A: Os elementos de estrutura de link transformam documentos PDF estáticos em experiências interativas adicionando hiperlinks clicáveis. Essa interatividade melhora o engajamento do usuário, permite navegação perfeita entre conteúdo relacionado e melhora a usabilidade geral do documento.