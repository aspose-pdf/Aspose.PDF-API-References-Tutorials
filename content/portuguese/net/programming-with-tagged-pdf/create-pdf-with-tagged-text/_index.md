---
title: Crie PDF com texto marcado
linktitle: Crie PDF com texto marcado
second_title: Referência da API Aspose.PDF para .NET
description: Guia passo a passo para criar um PDF com texto marcado usando Aspose.PDF for .NET.
type: docs
weight: 50
url: /pt/net/programming-with-tagged-pdf/create-pdf-with-tagged-text/
---
Neste tutorial, forneceremos um guia passo a passo sobre como criar um documento PDF com texto marcado usando Aspose.PDF for .NET. Aspose.PDF é uma biblioteca poderosa que permite criar, manipular e converter documentos PDF de forma programática. Usando os recursos de estrutura de conteúdo marcado do Aspose.PDF, você pode adicionar texto marcado ao seu documento PDF.

## Pré-requisitos

Antes de começar, certifique-se de ter os seguintes pré-requisitos em vigor:

1. Visual Studio instalado com estrutura .NET.
2. A biblioteca Aspose.PDF para .NET.

## Etapa 1: configuração do projeto

Para começar, crie um novo projeto no Visual Studio e adicione uma referência à biblioteca Aspose.PDF para .NET. Você pode baixar a biblioteca do site oficial do Aspose e instalá-la em sua máquina.

## Etapa 2: importe os namespaces necessários

Em seu arquivo de código C#, importe os namespaces necessários para acessar as classes e métodos fornecidos por Aspose.PDF:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## Passo 3: Criando o documento PDF com texto marcado

Use o código a seguir para criar um documento PDF com texto marcado:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");

HeaderElement headerElement = taggedContent.CreateHeaderElement();
headerElement.ActualText = "Header 1";

ParagraphElement paragraphElement1 = taggedContent.CreateParagraphElement();
paragraphElement1.ActualText = "test1";

// Adicione mais parágrafos aqui

// Salve o documento PDF
document.Save(dataDir + "PDFwithTagText.pdf");
```

Este código cria um documento PDF vazio e adiciona texto marcado usando os métodos fornecidos por Aspose.PDF. Você pode adicionar outros elementos de texto marcados, como títulos e parágrafos, usando os métodos apropriados.

### Exemplo de código-fonte para criar PDF com texto marcado usando Aspose.PDF para .NET 
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
// Criar elementos de estrutura em nível de bloco de texto
HeaderElement headerElement = taggedContent.CreateHeaderElement();
headerElement.ActualText = "Heading 1";
ParagraphElement paragraphElement1 = taggedContent.CreateParagraphElement();
paragraphElement1.ActualText = "test1";
ParagraphElement paragraphElement2 = taggedContent.CreateParagraphElement();
paragraphElement2.ActualText = "test 2";
ParagraphElement paragraphElement3 = taggedContent.CreateParagraphElement();
paragraphElement3.ActualText = "test 3";
ParagraphElement paragraphElement4 = taggedContent.CreateParagraphElement();
paragraphElement4.ActualText = "test 4";
ParagraphElement paragraphElement5 = taggedContent.CreateParagraphElement();
paragraphElement5.ActualText = "test 5";
ParagraphElement paragraphElement6 = taggedContent.CreateParagraphElement();
paragraphElement6.ActualText = "test 6";
ParagraphElement paragraphElement7 = taggedContent.CreateParagraphElement();
paragraphElement7.ActualText = "test 7";
// Salvar documento PDF
document.Save( dataDir + "PDFwithTaggedText.pdf");

```

## Conclusão

Neste tutorial, você aprendeu como criar um documento PDF com texto marcado usando Aspose.PDF for .NET. Os recursos de estrutura de conteúdo marcados do Aspose.PDF permitem estruturar e organizar seu texto para melhor acessibilidade e semântica.

### Perguntas frequentes

#### P: Qual é o propósito de criar um documento PDF com texto marcado usando Aspose.PDF for .NET?

R: Criar um documento PDF com texto marcado usando Aspose.PDF for .NET permite estruturar e organizar seu conteúdo de texto dentro do documento PDF. O texto marcado adiciona significado semântico e melhora a acessibilidade para os usuários, especialmente aqueles que usam tecnologias assistivas.

#### P: Como o Aspose.PDF ajuda na criação de um documento PDF com texto marcado?

R: Aspose.PDF for .NET é uma biblioteca poderosa que fornece funcionalidades para criar, manipular e converter documentos PDF de forma programática. Neste tutorial, os recursos de estrutura de conteúdo marcado da biblioteca são usados para adicionar texto estruturado e semanticamente significativo ao documento PDF.

#### P: Quais são os pré-requisitos para criar um documento PDF com texto marcado usando Aspose.PDF for .NET?

R: Antes de começar, certifique-se de ter o Visual Studio instalado com o .NET framework e de ter a biblioteca Aspose.PDF para .NET referenciada em seu projeto.

#### P: Como o código C# fornecido cria um documento PDF com texto marcado?

R: O exemplo de código demonstra como criar um documento PDF, definir vários elementos de texto marcados (como cabeçalhos e parágrafos) e adicioná-los ao conteúdo do documento. Isso é conseguido usando os recursos de estrutura de conteúdo marcado fornecidos pelo Aspose.PDF.

#### P: Como posso personalizar os elementos de texto marcados, como cabeçalhos e parágrafos?

 R: Você pode personalizar os elementos de texto marcados usando métodos apropriados, como`CreateHeaderElement` e`CreateParagraphElement` e definindo propriedades como`ActualText` para fornecer texto e semântica significativos.

#### P: Posso adicionar outros elementos de texto marcados, como listas ou links, usando técnicas semelhantes?

R: Sim, você pode adicionar outros elementos de texto marcados, como listas, links ou outras estruturas personalizadas, usando técnicas semelhantes. Aspose.PDF fornece vários métodos para criar diferentes tipos de conteúdo marcado, permitindo aprimorar a semântica do documento.

####  P: Como é que`SetTitle` method contribute to the PDF document's tagged text?

 R: O`SetTitle` O método define o título do conteúdo marcado do documento PDF, fornecendo uma breve descrição da finalidade ou assunto do documento. Essas informações ajudam os usuários a compreender o contexto do texto marcado.

#### P: Como o uso de texto marcado melhora a acessibilidade em documentos PDF?

R: O texto marcado adiciona significado semântico ao documento, tornando-o mais acessível a usuários com deficiência ou que utilizam tecnologias assistivas. Leitores de tela e outros dispositivos assistivos podem interpretar e apresentar texto marcado para melhorar a experiência do usuário.

####  P: Como é que`SetLanguage` method enhance the tagged text in a PDF document?

 R: O`SetLanguage` método define o atributo de idioma do conteúdo marcado do documento PDF. Isso ajuda a indicar o idioma no qual o texto marcado está escrito, melhorando a acessibilidade e permitindo a renderização adequada específica do idioma.

#### P: É possível adicionar outros elementos, como imagens ou multimídia, ao lado do texto marcado usando técnicas semelhantes?

R: Sim, você pode adicionar outros elementos como imagens, multimídia ou anotações ao lado do texto marcado usando técnicas semelhantes. Aspose.PDF oferece uma ampla gama de recursos para combinar diferentes tipos de conteúdo dentro do documento.