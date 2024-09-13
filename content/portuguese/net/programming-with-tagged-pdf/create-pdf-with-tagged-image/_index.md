---
title: Criar PDF com imagem marcada
linktitle: Criar PDF com imagem marcada
second_title: Referência da API do Aspose.PDF para .NET
description: Guia passo a passo para criar PDF com imagem marcada usando Aspose.PDF para .NET.
type: docs
weight: 40
url: /pt/net/programming-with-tagged-pdf/create-pdf-with-tagged-image/
---
Neste tutorial, forneceremos um guia passo a passo sobre como criar um documento PDF com uma imagem marcada usando o Aspose.PDF para .NET. O Aspose.PDF é uma biblioteca poderosa que permite criar, manipular e converter documentos PDF programaticamente. Usando os recursos de estrutura de conteúdo marcado do Aspose.PDF, você pode adicionar imagens marcadas ao seu documento PDF.

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

## Etapa 3: Criando o documento PDF com uma imagem marcada

Use o código a seguir para criar um documento PDF com uma imagem marcada:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Creating a PDF with a tagged image");
taggedContent.SetLanguage("fr-FR");

IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
figure1.AlternativeText = "Aspose Logo";
figure1.Title = "Picture 1";
figure1.SetTag("Fig");
figure1.SetImage(dataDir + @"aspose-logo.jpg");
```

Este código cria um documento PDF vazio e adiciona uma imagem marcada usando os métodos fornecidos pelo Aspose.PDF. A imagem é especificada com texto alt, título e marca.

## Etapa 4: salvando o documento PDF

Use o seguinte código para salvar o documento PDF:

```csharp
document.Save(dataDir + "PDFwithTaggedImage.pdf");
```

Este código salva o documento PDF com a imagem marcada em um arquivo especificado.

### Código-fonte de exemplo para criar PDF com imagem marcada usando Aspose.PDF para .NET 
```csharp

// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("CreatePDFwithTaggedImage");
taggedContent.SetLanguage("en-US");
IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
figure1.AlternativeText = "Aspose Logo";
figure1.Title = "Image 1";
figure1.SetTag("Fig");
// Adicionar imagem com resolução de 300 DPI (por padrão)
figure1.SetImage(dataDir + @"aspose-logo.jpg");
// Salvar documento PDF
document.Save(dataDir + "PDFwithTaggedImage.pdf");

```

## Conclusão

Neste tutorial, você aprendeu como criar um documento PDF com uma imagem marcada usando o Aspose.PDF para .NET. Imagens marcadas adicionam informações adicionais e estruturadas ao seu documento PDF.

### Perguntas frequentes

#### P: Qual é o propósito de criar um documento PDF com uma imagem marcada usando o Aspose.PDF para .NET?

A: Criar um documento PDF com uma imagem marcada usando o Aspose.PDF for .NET permite que você adicione imagens marcadas ao conteúdo do documento. Imagens marcadas fornecem informações estruturadas, como texto alternativo e títulos, melhorando a acessibilidade e a organização.

#### P: Como a biblioteca Aspose.PDF auxilia na criação de um documento PDF com uma imagem marcada?

R: Aspose.PDF para .NET é uma biblioteca robusta que fornece funcionalidades para criar, manipular e converter documentos PDF programaticamente. Neste tutorial, os recursos de estrutura de conteúdo marcado da biblioteca são usados para adicionar uma imagem marcada ao documento PDF.

#### P: Quais são os pré-requisitos para criar um documento PDF com uma imagem marcada usando o Aspose.PDF para .NET?

R: Antes de começar, certifique-se de ter o Visual Studio instalado com o .NET Framework e de ter a biblioteca Aspose.PDF para .NET referenciada em seu projeto.

#### P: Como o código C# fornecido cria um documento PDF com uma imagem marcada?

R: O código demonstra como criar um documento PDF, definir um elemento de imagem marcado e adicioná-lo ao conteúdo do documento. A imagem marcada inclui texto alt, um título e uma tag usando métodos fornecidos pelo Aspose.PDF.

#### P: Posso usar formatos de imagem diferentes para a imagem marcada?

R: Sim, você pode usar diferentes formatos de imagem para a imagem marcada, como JPEG, PNG, GIF, etc. O exemplo de código fornecido no tutorial usa uma imagem JPEG, mas você pode substituí-lo pelo caminho para um arquivo de imagem no seu formato preferido.

#### P: Como o texto alternativo (alt text) é usado em imagens marcadas?

 A: O texto alternativo fornece uma descrição textual da imagem, que é lida em voz alta por leitores de tela para usuários com deficiência visual. No código fornecido, o texto alternativo é definido usando o`AlternativeText` propriedade do`IllustrationElement` representando a imagem marcada.

#### P: Como é que o`SetTitle` method contribute to the PDF document's tagged image?

 A: O`SetTitle` O método define o título do conteúdo marcado do documento PDF, fornecendo contexto adicional para a imagem marcada. Este título pode ajudar a identificar o propósito ou assunto do conteúdo marcado.

#### P: Posso personalizar a tag e o título da imagem marcada?

 R: Sim, você pode personalizar a tag e o título da imagem marcada usando o`SetTag` e`Title` métodos do`IllustrationElement`. O exemplo de código demonstra como definir a tag como "Fig" e o título como "Imagem 1".

#### P: Como posso garantir que a imagem marcada seja acessível e esteja em conformidade com os padrões de acessibilidade?

R: Ao usar os recursos de estrutura de conteúdo marcado do Aspose.PDF e fornecer texto alternativo e outras informações relevantes, você contribui para a acessibilidade da imagem marcada. Garantir a conformidade com os padrões de acessibilidade envolve seguir as melhores práticas para texto alternativo e estrutura de documento.

#### P: É possível adicionar várias imagens marcadas ao mesmo documento PDF usando técnicas semelhantes?

R: Sim, você pode adicionar várias imagens marcadas ao mesmo documento PDF usando técnicas semelhantes. Você criaria imagens adicionais`IllustrationElement` instâncias para cada imagem marcada e personalizar suas propriedades conforme necessário.