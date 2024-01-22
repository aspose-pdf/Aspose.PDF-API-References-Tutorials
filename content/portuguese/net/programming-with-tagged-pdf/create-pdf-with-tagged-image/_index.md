---
title: Crie PDF com imagem marcada
linktitle: Crie PDF com imagem marcada
second_title: Referência da API Aspose.PDF para .NET
description: Guia passo a passo para criar PDF com imagem marcada usando Aspose.PDF for .NET.
type: docs
weight: 40
url: /pt/net/programming-with-tagged-pdf/create-pdf-with-tagged-image/
---
Neste tutorial, forneceremos um guia passo a passo sobre como criar um documento PDF com uma imagem marcada usando Aspose.PDF for .NET. Aspose.PDF é uma biblioteca poderosa que permite criar, manipular e converter documentos PDF de forma programática. Usando os recursos de estrutura de conteúdo marcado do Aspose.PDF, você pode adicionar imagens marcadas ao seu documento PDF.

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

## Passo 3: Criando o documento PDF com uma imagem marcada

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

Este código cria um documento PDF vazio e adiciona uma imagem marcada usando os métodos fornecidos por Aspose.PDF. A imagem é especificada com texto alternativo, título e tag.

## Passo 4: Salvando o Documento PDF

Use o seguinte código para salvar o documento PDF:

```csharp
document.Save(dataDir + "PDFwithTaggedImage.pdf");
```

Este código salva o documento PDF com a imagem marcada em um arquivo especificado.

### Exemplo de código-fonte para Criar PDF com imagem marcada usando Aspose.PDF para .NET 
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

Neste tutorial, você aprendeu como criar um documento PDF com uma imagem marcada usando Aspose.PDF for .NET. Imagens marcadas adicionam informações estruturadas adicionais ao seu documento PDF.

### Perguntas frequentes

#### P: Qual é o propósito de criar um documento PDF com uma imagem marcada usando Aspose.PDF for .NET?

R: Criar um documento PDF com uma imagem marcada usando Aspose.PDF for .NET permite adicionar imagens marcadas ao conteúdo do documento. As imagens marcadas fornecem informações estruturadas, como texto alternativo e títulos, melhorando a acessibilidade e a organização.

#### P: Como a biblioteca Aspose.PDF auxilia na criação de um documento PDF com uma imagem marcada?

R: Aspose.PDF for .NET é uma biblioteca robusta que fornece funcionalidades para criar, manipular e converter documentos PDF de forma programática. Neste tutorial, os recursos de estrutura de conteúdo marcado da biblioteca são usados para adicionar uma imagem marcada ao documento PDF.

#### P: Quais são os pré-requisitos para criar um documento PDF com uma imagem marcada usando Aspose.PDF for .NET?

R: Antes de começar, certifique-se de ter o Visual Studio instalado com o .NET framework e de ter a biblioteca Aspose.PDF para .NET referenciada em seu projeto.

#### P: Como o código C# fornecido cria um documento PDF com uma imagem marcada?

R: O código demonstra como criar um documento PDF, definir um elemento de imagem marcado e adicioná-lo ao conteúdo do documento. A imagem marcada inclui texto alternativo, um título e uma tag usando métodos fornecidos por Aspose.PDF.

#### P: Posso usar formatos de imagem diferentes para a imagem marcada?

R: Sim, você pode usar diferentes formatos de imagem para a imagem marcada, como JPEG, PNG, GIF, etc. O exemplo de código fornecido no tutorial usa uma imagem JPEG, mas você pode substituí-la pelo caminho para um arquivo de imagem em seu formato preferido.

#### P: Como o texto alternativo (texto alternativo) é usado em imagens marcadas?

 R: O texto alternativo fornece uma descrição textual da imagem, que é lida em voz alta por leitores de tela para usuários com deficiência visual. No código fornecido, o texto alternativo é definido usando o`AlternativeText` propriedade do`IllustrationElement` representando a imagem marcada.

####  P: Como é que`SetTitle` method contribute to the PDF document's tagged image?

 R: O`SetTitle` O método define o título do conteúdo marcado do documento PDF, fornecendo contexto adicional para a imagem marcada. Este título pode ajudar a identificar o propósito ou assunto do conteúdo marcado.

#### P: Posso personalizar a tag e o título da imagem marcada?

 R: Sim, você pode personalizar a tag e o título da imagem marcada usando o`SetTag` e`Title` métodos do`IllustrationElement`. O exemplo de código demonstra como definir a tag como “Fig” e o título como “Imagem 1”.

#### P: Como posso garantir que a imagem marcada seja acessível e esteja em conformidade com os padrões de acessibilidade?

R: Ao usar os recursos de estrutura de conteúdo marcado do Aspose.PDF e fornecer texto alternativo e outras informações relevantes, você contribui para a acessibilidade da imagem marcada. Garantir a conformidade com os padrões de acessibilidade envolve seguir as melhores práticas para texto alternativo e estrutura de documentos.

#### P: É possível adicionar várias imagens marcadas ao mesmo documento PDF usando técnicas semelhantes?

 R: Sim, você pode adicionar várias imagens marcadas ao mesmo documento PDF usando técnicas semelhantes. Você criaria adicional`IllustrationElement` instâncias para cada imagem marcada e personalize suas propriedades conforme necessário.