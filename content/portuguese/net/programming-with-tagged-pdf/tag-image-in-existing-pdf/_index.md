---
title: Marcar imagem em PDF existente
linktitle: Marcar imagem em PDF existente
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda como marcar uma imagem em um PDF existente com Aspose.PDF para .NET. Um guia passo a passo para adicionar tags a imagens.
type: docs
weight: 210
url: /pt/net/programming-with-tagged-pdf/tag-image-in-existing-pdf/
---
Neste tutorial detalhado, nós o guiaremos pelo código-fonte C# fornecido passo a passo para marcar uma imagem em um PDF existente usando Aspose.PDF para .NET. Siga as instruções abaixo para entender como adicionar tags a uma imagem em um PDF.

## Etapa 1: Configurando o ambiente

Antes de começar, certifique-se de ter configurado seu ambiente de desenvolvimento para usar o Aspose.PDF para .NET. Isso inclui instalar a biblioteca Aspose.PDF e configurar seu projeto para referenciá-la.

## Etapa 2: Abra o documento PDF existente

Nesta etapa, abriremos um documento PDF existente usando o Aspose.PDF.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Caminhos de entrada e saída de arquivos
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// Abra o documento
Document document = new Document(inFile);
```

Abrimos o documento PDF existente usando o Aspose.PDF.

## Etapa 3: Obtenha o conteúdo marcado e o elemento de estrutura raiz

Agora obteremos o conteúdo marcado do documento PDF e o elemento de estrutura raiz correspondente.

```csharp
// Obtenha conteúdo marcado e elemento de estrutura raiz
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;
```

Obtivemos o conteúdo marcado do documento PDF e o elemento de estrutura raiz correspondente.

## Etapa 4: Definir o título do documento PDF marcado

Agora vamos definir o título do documento PDF marcado.

```csharp
// Defina o título do documento PDF marcado
taggedContent.SetTitle("Document with images");
```

Definimos o título para o documento PDF marcado.

## Etapa 5: Atribuir textos alternativos e caixa delimitadora à imagem

Agora, para cada elemento da imagem, atribuiremos um texto alternativo e uma caixa delimitadora.

```csharp
foreach(FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
     // Atribuir texto alternativo à imagem
     figureElement.AlternativeText = "Alternative text for image (technique 2)";
     // Crie e atribua a caixa delimitadora (bbox)
     StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
     bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
     StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
     figureLayoutAttributes.SetAttribute(bboxAttribute);
}
```

Atribuímos um texto alternativo e uma caixa delimitadora a cada elemento de imagem no documento PDF.

## Etapa 6: Mover o elemento Span para o parágrafo

Agora vamos mover o elemento Span para o parágrafo.

```csharp
// Mover elemento Span para o parágrafo (encontrar span e parágrafo incorretos no primeiro TD)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// Mova o elemento Span no parágrafo
spanElement.ChangeParentElement(paragraph);
```

Movemos o elemento Span para o parágrafo especificado.

## Etapa 7: Salvando o documento PDF modificado

Agora que fizemos as alterações necessárias, salvaremos o documento PDF modificado.

```csharp
// Salvar o documento PDF
document. Save(outFile);
```

Salvamos o documento PDF modificado no diretório especificado.

### Exemplo de código-fonte para Tag Image em PDF existente usando Aspose.PDF para .NET 

```csharp

// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// Abrir documento
Document document = new Document(inFile);

// Obtém conteúdo marcado e elemento de estrutura raiz
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;

// Definir título para documento PDF marcado
taggedContent.SetTitle("Document with images");
foreach (FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
	// Definir texto alternativo para figura
	figureElement.AlternativeText = "Figure alternative text (technique 2)";
	// Criar e definir atributo BBox
	StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
	bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
	StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
	figureLayoutAttributes.SetAttribute(bboxAttribute);
}

// Mover elemento de extensão para parágrafo (encontrar extensão e parágrafo errados no primeiro TD)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// Mover elemento de extensão para parágrafo
spanElement.ChangeParentElement(paragraph);

// Salvar documento
document.Save(outFile);

//Verificando a conformidade do PDF/UA para nosso documento
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Conclusão

Neste tutorial, aprendemos como marcar uma imagem em um PDF existente usando o Aspose.PDF para .NET. Agora você pode usar o Aspose.PDF para adicionar tags e fazer edições em imagens em seus documentos PDF.

### Perguntas frequentes

#### P: Qual é o objetivo principal deste tutorial sobre marcação de imagens em um PDF existente usando o Aspose.PDF para .NET?

R: O objetivo principal deste tutorial é guiá-lo pelo processo de marcação de uma imagem dentro de um documento PDF existente usando o Aspose.PDF para .NET. O tutorial fornece instruções passo a passo e exemplos de código-fonte C# para ajudar você a entender como atribuir texto alternativo e caixas delimitadoras a imagens, mover elementos dentro do documento e adicionar tags a imagens.

#### P: Quais são os pré-requisitos para seguir este tutorial sobre marcação de imagens em um PDF usando o Aspose.PDF para .NET?

R: Antes de começar, certifique-se de ter configurado seu ambiente de desenvolvimento para usar o Aspose.PDF para .NET. Isso envolve instalar a biblioteca Aspose.PDF e configurar seu projeto para referenciá-la.

#### P: Como posso abrir um documento PDF existente e acessar seu conteúdo marcado usando o Aspose.PDF para .NET?

R: O tutorial fornece exemplos de código-fonte em C# que demonstram como abrir um documento PDF existente usando o Aspose.PDF para .NET e acessar seu conteúdo marcado para manipulação posterior.

#### P: Qual é o propósito de atribuir texto alternativo e caixas delimitadoras a imagens em um documento PDF?

A: Atribuir texto alternativo e caixas delimitadoras a imagens melhora a acessibilidade ao fornecer texto descritivo para imagens e definir seu layout e posição dentro do documento. Essas informações são cruciais para leitores de tela e outras tecnologias assistivas.

#### P: Como posso definir o título de um documento PDF marcado usando o Aspose.PDF para .NET?

R: O tutorial inclui exemplos de código-fonte em C# que ilustram como definir o título de um documento PDF marcado usando Aspose.PDF para .NET.

#### P: O que envolve o processo de mover elementos dentro de um documento PDF?

A: Mover elementos dentro de um documento PDF envolve alterar o elemento pai de um elemento específico. Neste tutorial, você aprenderá como mover um elemento Span para um elemento Paragraph especificado dentro de uma tabela.

#### P: Como faço para salvar o documento PDF modificado depois de adicionar tags e fazer edições nas imagens?

 R: Depois de adicionar tags, atribuir texto alternativo, definir caixas delimitadoras e fazer edições no documento PDF, você pode usar os exemplos de código-fonte C# fornecidos para salvar o documento PDF modificado usando o`Save()` método.

#### P: Qual é o propósito do código-fonte de exemplo fornecido no tutorial?

R: O código-fonte de exemplo serve como uma referência prática para implementar marcação e manipulação de imagens usando Aspose.PDF para .NET. Você pode usar esse código como um ponto de partida e modificá-lo para atender às suas necessidades específicas.

#### P: Posso aplicar essas técnicas a outros tipos de elementos em um documento PDF, não apenas imagens?

R: Sim, as técnicas demonstradas neste tutorial podem ser adaptadas para trabalhar com vários tipos de elementos dentro de um documento PDF. Você pode aplicar princípios semelhantes para marcar e manipular outros elementos, como texto, tabelas e muito mais.

#### P: Como posso validar a conformidade com PDF/UA do documento PDF modificado?

 R: O tutorial fornece exemplos de código-fonte C# que mostram como validar a conformidade PDF/UA do documento PDF modificado usando o`Validate()` método e gerando um relatório XML.

#### P: Quais outros recursos o Aspose.PDF for .NET oferece para trabalhar com documentos PDF?

A: O Aspose.PDF para .NET oferece uma ampla gama de recursos para trabalhar com documentos PDF, incluindo manipulação de texto, inserção de imagem, criação de tabela, gerenciamento de campo de formulário, assinaturas digitais, anotações e muito mais. Consulte a documentação oficial e os recursos para exploração adicional.