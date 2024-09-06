---
title: Adicionar elemento de estrutura ao elemento
linktitle: Adicionar elemento de estrutura ao elemento
second_title: Referência da API do Aspose.PDF para .NET
description: Guia passo a passo para adicionar elemento de estrutura a elemento em um documento PDF usando o Aspose.PDF para .NET.
type: docs
weight: 20
url: /pt/net/programming-with-tagged-pdf/add-structure-element-into-element/
---
Neste tutorial, forneceremos um guia passo a passo sobre como adicionar um elemento de estrutura a um elemento em um documento PDF usando o Aspose.PDF para .NET. O Aspose.PDF é uma biblioteca poderosa que permite criar, manipular e converter documentos PDF programaticamente. Usando os recursos de estrutura de conteúdo marcados do Aspose.PDF, você pode criar uma estrutura hierárquica em seu documento PDF.

## Pré-requisitos

Antes de começar, certifique-se de ter os seguintes pré-requisitos em vigor:

1. Visual Studio instalado com .NET Framework.
2. A biblioteca Aspose.PDF para .NET.

## Etapa 1: Configuração do projeto

Para começar, crie um novo projeto no Visual Studio e adicione uma referência à biblioteca Aspose.PDF for .NET. Você pode baixar a biblioteca do site oficial do Aspose e instalá-la na sua máquina.

## Etapa 2: Importe os namespaces necessários

No seu arquivo de código C#, importe os namespaces necessários para acessar as classes e métodos fornecidos pelo Aspose.PDF:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## Etapa 3: Criação do documento PDF e definição dos elementos estruturados

Use o código a seguir para criar um documento PDF e definir os elementos estruturados:

```csharp

string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
string logFile = dataDir + "46144_log.xml";

Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Text Items");
taggedContent.SetLanguage("fr-FR");

StructureElement rootElement = taggedContent.RootElement;

ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
SpanElement span11 = taggedContent.CreateSpanElement();
span11.SetText("Span_11");
SpanElement span12 = taggedContent.CreateSpanElement();
span12.SetText(" and Span_12.");
p1.SetText("Paragraph with ");
p1.AppendChild(span11);
p1.AppendChild(span12);

ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
SpanElement span21 = taggedContent.CreateSpanElement();
span21.SetText("Span_21");
SpanElement span22 = taggedContent.CreateSpanElement();
span22.SetText("Span_22.");
p2.AppendChild(span21);
p2.SetText(" and ");
p2.AppendChild(span22);

ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("Span_31");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText(" and Span_32");
p3.AppendChild(span31);
p3.AppendChild(span32);
p3.SetText(".");

ParagraphElement p4 = taggedContent.CreateParagraphElement();
root

Element.AppendChild(p4);
SpanElement span41 = taggedContent.CreateSpanElement();
SpanElement span411 = taggedContent.CreateSpanElement();
span411.SetText("Span_411, ");
span41.SetText("Span_41, ");
span41.AppendChild(span411);
SpanElement span42 = taggedContent.CreateSpanElement();
SpanElement span421 = taggedContent.CreateSpanElement();
span421.SetText("Span 421 and ");
span42.AppendChild(span421);
span42.SetText("Span_42");
p4.AppendChild(span41);
p4.AppendChild(span42);
p4.SetText(".");
```

Este código cria um documento PDF vazio e adiciona elementos estruturados, como parágrafos e spans. Cada elemento de estrutura é criado usando os métodos fornecidos pelo Aspose.PDF.

## Etapa 4: salvando o documento PDF

Use o seguinte código para salvar o documento PDF:

```csharp
document. Save(outFile);
```

Este código salva o documento PDF com os elementos estruturados em um arquivo especificado.

### Código-fonte de exemplo para Adicionar elemento de estrutura ao elemento usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
string logFile = dataDir + "46144_log.xml";
// Criação de documento e obtenção de conteúdo PDF marcado
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
// Definir título e idioma da natureza para o documento
taggedContent.SetTitle("Text Elements Example");
taggedContent.SetLanguage("en-US");
// Obtendo o elemento de estrutura raiz (elemento de estrutura do documento)
StructureElement rootElement = taggedContent.RootElement;
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
SpanElement span11 = taggedContent.CreateSpanElement();
span11.SetText("Span_11");
SpanElement span12 = taggedContent.CreateSpanElement();
span12.SetText(" and Span_12.");
p1.SetText("Paragraph with ");
p1.AppendChild(span11);
p1.AppendChild(span12);
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
SpanElement span21 = taggedContent.CreateSpanElement();
span21.SetText("Span_21");
SpanElement span22 = taggedContent.CreateSpanElement();
span22.SetText("Span_22.");
p2.AppendChild(span21);
p2.SetText(" and ");
p2.AppendChild(span22);
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("Span_31");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText(" and Span_32");
p3.AppendChild(span31);
p3.AppendChild(span32);
p3.SetText(".");
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
SpanElement span41 = taggedContent.CreateSpanElement();
SpanElement span411 = taggedContent.CreateSpanElement();
span411.SetText("Span_411, ");
span41.SetText("Span_41, ");
span41.AppendChild(span411);
SpanElement span42 = taggedContent.CreateSpanElement();
SpanElement span421 = taggedContent.CreateSpanElement();
span421.SetText("Span 421 and ");
span42.AppendChild(span421);
span42.SetText("Span_42");
p4.AppendChild(span41);
p4.AppendChild(span42);
p4.SetText(".");
// Salvar documento PDF marcado
document.Save(outFile);
// Verificando a conformidade com PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Conclusão

Neste tutorial, você aprendeu como adicionar um elemento de estrutura a um elemento em um documento PDF usando o Aspose.PDF para .NET. Usando os recursos de estrutura de conteúdo marcados do Aspose.PDF, você pode criar uma estrutura hierárquica em seu documento PDF, o que facilita o gerenciamento e a navegação pelo conteúdo.

### Perguntas frequentes

#### P: Qual é o propósito de adicionar um elemento de estrutura a um elemento em um documento PDF usando o Aspose.PDF para .NET?

A: Adicionar um elemento de estrutura a um elemento em um documento PDF usando o Aspose.PDF for .NET permite que você crie uma estrutura hierárquica dentro do conteúdo do documento. Essa estrutura hierárquica aprimora a organização e a navegação do conteúdo, facilitando o gerenciamento e o acesso a elementos específicos.

#### P: Como a biblioteca Aspose.PDF auxilia na adição de elementos de estrutura a um documento PDF?

R: Aspose.PDF para .NET é uma biblioteca poderosa que fornece recursos para criar, manipular e converter documentos PDF programaticamente. Neste tutorial, os recursos de estrutura de conteúdo marcados da biblioteca são aproveitados para criar e anexar elementos de estrutura ao conteúdo do documento PDF.

#### P: Quais são os pré-requisitos para adicionar elementos de estrutura a um documento PDF usando o Aspose.PDF para .NET?

R: Antes de começar, certifique-se de ter o Visual Studio instalado com o .NET Framework e de ter a biblioteca Aspose.PDF para .NET referenciada em seu projeto.

#### P: Como o código C# fornecido cria e acrescenta elementos de estrutura ao conteúdo do documento PDF?

R: O código demonstra como criar um documento PDF, definir um elemento de estrutura raiz e anexar vários elementos estruturados, como parágrafos e spans a ele. Cada elemento estruturado é criado usando métodos fornecidos pelo Aspose.PDF, permitindo que você construa uma estrutura hierárquica.

#### P: Posso personalizar os tipos de elementos de estrutura que adiciono ao documento PDF?

R: Sim, você pode personalizar os tipos de elementos de estrutura explorando diferentes métodos fornecidos pela biblioteca Aspose.PDF. O código mostra parágrafos e spans como exemplos, mas você pode criar e anexar outros tipos de elementos estruturados conforme necessário.

#### P: Como defino o relacionamento hierárquico entre os elementos estruturais adicionados?

 A: O relacionamento hierárquico entre elementos de estrutura é definido pela ordem em que você os anexa aos seus elementos pais. No código, os relacionamentos pai-filho são estabelecidos usando o`AppendChild` método.

#### P: Quais são os benefícios de criar uma estrutura hierárquica em um documento PDF?

R: Criar uma estrutura hierárquica em um documento PDF melhora sua acessibilidade, navegação e organização. Ela permite que tecnologias assistivas interpretem e transmitam melhor o conteúdo do documento, tornando-o mais amigável para pessoas com deficiências.

#### P: Como posso validar a conformidade com PDF/UA depois de adicionar elementos de estrutura?

 R: O código fornecido no tutorial demonstra como validar a conformidade com PDF/UA usando o`Validate` método. Ao validar o documento em relação ao padrão PDF/UA, você pode garantir que os elementos de estrutura adicionados estejam em conformidade com as diretrizes de acessibilidade.

#### P: Posso usar essa abordagem para adicionar elementos de estrutura a um documento PDF existente?

R: Sim, você pode modificar a abordagem fornecida para adicionar elementos de estrutura a um documento PDF existente. Em vez de criar um novo documento, você carregaria o documento existente usando Aspose.PDF e seguiria etapas semelhantes para anexar elementos de estrutura.