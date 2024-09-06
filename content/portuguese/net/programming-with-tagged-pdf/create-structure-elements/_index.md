---
title: Criar elementos de estrutura
linktitle: Criar elementos de estrutura
second_title: Referência da API do Aspose.PDF para .NET
description: Neste tutorial, você aprenderá como usar o Aspose.PDF for .NET para criar elementos estruturais em um documento PDF marcado.
type: docs
weight: 60
url: /pt/net/programming-with-tagged-pdf/create-structure-elements/
---
O código-fonte C# a seguir usa Aspose.PDF para .NET para criar elementos de estrutura. Siga os passos abaixo para entender como o código funciona.

## Etapa 1: Importe as bibliotecas necessárias

```csharp
using Aspose.Pdf;
```

## Etapa 2: Defina o diretório dos seus documentos

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Certifique-se de especificar o caminho correto para o diretório de documentos.

## Etapa 3: Crie um documento PDF

```csharp
Document document = new Document();
```

Criamos um novo objeto Document que representa o documento PDF.

## Etapa 4: faça o conteúdo funcionar com o TaggedPdf

```csharp
ITaggedContent taggedContent = document.TaggedContent;
```

Recuperamos o conteúdo marcado do documento PDF. Isso nos permitirá manipular elementos estruturais.

## Etapa 5: Defina o título e o idioma do documento

```csharp
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

Definimos o título e o idioma do documento PDF marcado. Isso melhora a acessibilidade do documento.

## Etapa 6: Criar elementos de agrupamento

```csharp
PartElement partElement = taggedContent.CreatePartElement();
ArtElement artElement = taggedContent.CreateArtElement();
SectElement sectElement = taggedContent.CreateSectElement();
DivElement divElement = taggedContent.CreateDivElement();
BlockQuoteElement blockQuoteElement = taggedContent.CreateBlockQuoteElement();
CaptionElement captionElement = taggedContent.CreateCaptionElement();
TOCElement tocElement = taggedContent.CreateTOCElement();
TOCIElement tociElement = taggedContent.CreateTOCIElement();
IndexElement indexElement = taggedContent.CreateIndexElement();
NonStructElement nonStructElement = taggedContent.CreateNonStructElement();
PrivateElement privateElement = taggedContent.CreatePrivateElement();
```

Criamos diferentes elementos estruturais para agrupar conteúdo no documento PDF.

## Etapa 7: Crie elementos de estrutura de parágrafo

```csharp
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
```

Criamos elementos estruturais de nível de bloco para parágrafos e títulos. O exemplo acima mostra a criação de um cabeçalho de nível 1.

## Etapa 8: Criar elementos de estrutura de nível em linha

```csharp
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
```

Criamos elementos de estrutura de nível embutido para as partes do texto que aparecem dentro de um parágrafo ou título.

## Etapa 9: Crie elementos de estrutura de arte

```csharp
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
```

Criamos elementos estruturais para as ilustrações e fórmulas matemáticas presentes no documento.

## Etapa 10: Salve o documento PDF marcado

```csharp
document.Save(dataDir + "StructureElements.pdf");
```

Salvamos o documento PDF marcado com os elementos de estrutura criados.

### Código-fonte de exemplo para criar elementos de estrutura usando Aspose.PDF para .NET 

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
// Criar Elementos de Agrupamento
PartElement partElement = taggedContent.CreatePartElement();
ArtElement artElement = taggedContent.CreateArtElement();
SectElement sectElement = taggedContent.CreateSectElement();
DivElement divElement = taggedContent.CreateDivElement();
BlockQuoteElement blockQuoteElement = taggedContent.CreateBlockQuoteElement();
CaptionElement captionElement = taggedContent.CreateCaptionElement();
TOCElement tocElement = taggedContent.CreateTOCElement();
TOCIElement tociElement = taggedContent.CreateTOCIElement();
IndexElement indexElement = taggedContent.CreateIndexElement();
NonStructElement nonStructElement = taggedContent.CreateNonStructElement();
PrivateElement privateElement = taggedContent.CreatePrivateElement();
// Criar elementos de estrutura de nível de bloco de texto
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
// Criar elementos de estrutura de nível de texto em linha
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
// Criar elementos de estrutura de ilustração
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
// Os métodos estão em desenvolvimento
ListElement listElement = taggedContent.CreateListElement();
TableElement tableElement = taggedContent.CreateTableElement();
ReferenceElement referenceElement = taggedContent.CreateReferenceElement();
BibEntryElement bibEntryElement = taggedContent.CreateBibEntryElement();
CodeElement codeElement = taggedContent.CreateCodeElement();
LinkElement linkElement = taggedContent.CreateLinkElement();
AnnotElement annotElement = taggedContent.CreateAnnotElement();
RubyElement rubyElement = taggedContent.CreateRubyElement();
WarichuElement warichuElement = taggedContent.CreateWarichuElement();
FormElement formElement = taggedContent.CreateFormElement();
// Salvar documento PDF marcado
document.Save(dataDir + "StructureElements.pdf");

```

## Conclusão

Neste tutorial, aprendemos como usar o Aspose.PDF para .NET para criar elementos de estrutura em um documento PDF marcado. Elementos estruturais ajudam a melhorar a acessibilidade do documento e a organizar o conteúdo de forma significativa. Agora você pode usar esse conhecimento para criar documentos PDF estruturados e fáceis de navegar.

### Perguntas frequentes

#### P: Qual é o propósito de criar elementos de estrutura em um documento PDF usando Aspose.PDF para .NET?

A: Criar elementos de estrutura em um documento PDF usando o Aspose.PDF for .NET melhora a acessibilidade e a organização do conteúdo do documento. Os elementos de estrutura fornecem uma estrutura hierárquica que melhora a navegação, a semântica e a compatibilidade com tecnologias assistivas.

#### P: Como o código C# fornecido cria elementos de estrutura em um documento PDF?

R: O exemplo de código demonstra como criar vários tipos de elementos de estrutura, incluindo elementos de agrupamento (como partes, seções e divs), elementos de nível de bloco (como parágrafos e títulos), elementos de nível inline (span, quote, note) e elementos de arte (como figuras e fórmulas). Esses elementos de estrutura ajudam a organizar o conteúdo.

####  P: Por que é importante definir o título e o idioma do documento usando o`SetTitle` and `SetLanguage` methods?

 A: Definir o título e o idioma do documento usando o`SetTitle` e`SetLanguage`methods melhora a acessibilidade e a semântica do documento. O título fornece uma breve descrição do propósito do documento, enquanto o atributo language melhora a renderização e a acessibilidade específicas do idioma.

####  P: Como agrupar elementos, como`PartElement` and `SectElement`, contribute to the structure of the PDF document?

A: Agrupar elementos cria uma estrutura hierárquica dentro do documento PDF, permitindo que você organize e agrupe logicamente o conteúdo relacionado. Isso melhora a navegação e fornece uma estrutura clara para os usuários.

#### P: O que são elementos estruturais em nível de bloco e em nível de linha e como eles diferem?

R: Elementos de estrutura de nível de bloco representam blocos maiores de conteúdo, como parágrafos e títulos, enquanto elementos de nível inline representam partes do texto dentro de um parágrafo ou título, como spans, citações e notas. Eles ajudam a definir a hierarquia e os relacionamentos do conteúdo.

####  P: Como os elementos da estrutura da arte, como`FigureElement` and `FormulaElement`, contribute to the document?

A: Os elementos de estrutura de arte permitem que você adicione ilustrações, figuras e fórmulas matemáticas ao documento. Eles fornecem uma maneira estruturada de incluir conteúdo visual e matemático.

#### P: Posso usar técnicas semelhantes para criar outros tipos de elementos de estrutura, como listas, tabelas ou anotações?

R: Sim, você pode usar técnicas semelhantes para criar outros tipos de elementos de estrutura, como listas, tabelas, anotações, referências e muito mais. O Aspose.PDF fornece uma ampla gama de métodos de criação de elementos de estrutura.

####  P: Como salvar o documento PDF marcado usando o`Save` method ensure the preservation of structure elements?

 A: O`Save` O método salva o documento PDF junto com os elementos de estrutura criados, garantindo que a estrutura hierárquica e semântica do documento seja preservada para acessibilidade e navegação.

#### P: Quais benefícios os elementos estruturais trazem aos documentos PDF em termos de acessibilidade e compatibilidade com tecnologias assistivas?

A: Os elementos de estrutura melhoram a acessibilidade ao fornecer uma estrutura e semântica significativas ao documento. Isso permite que tecnologias assistivas, como leitores de tela, interpretem e transmitam o conteúdo do documento de forma mais eficaz para usuários com deficiências.

#### P: Como posso personalizar e combinar ainda mais diferentes tipos de elementos estruturais em meus documentos PDF?

R: Você pode combinar e personalizar elementos de estrutura usando métodos de criação apropriados fornecidos pelo Aspose.PDF. Experimente diferentes elementos e suas propriedades para criar um documento PDF bem estruturado e organizado.