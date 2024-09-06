---
title: Obter propriedades PDF
linktitle: Obter propriedades PDF
second_title: Referência da API do Aspose.PDF para .NET
description: Guia passo a passo para obter propriedades de PDF, como dimensões de caixa e rotação, usando o Aspose.PDF para .NET.
type: docs
weight: 100
url: /pt/net/programming-with-pdf-pages/get-properties/
---
Neste tutorial, nós o guiaremos pelo processo passo a passo para obter as propriedades de um PDF usando o Aspose.PDF para .NET. Explicaremos o código-fonte C# incluído e forneceremos um guia abrangente para ajudar você a entender e implementar esse recurso em seus próprios projetos. No final deste tutorial, você saberá como acessar diferentes propriedades de uma página PDF, como caixa de arte, caixa de corte, caixa de corte, etc., usando o Aspose.PDF para .NET.

## Pré-requisitos
Antes de começar, certifique-se de ter o seguinte:

- Um conhecimento básico da linguagem de programação C#
- Aspose.PDF para .NET instalado em seu ambiente de desenvolvimento

## Etapa 1: definir diretório de documentos
Primeiro, você precisa definir o caminho para o seu diretório de documentos. Este é o local do arquivo PDF cujas propriedades você quer obter. Substitua "YOUR DOCUMENTS DIRECTORY" pelo caminho apropriado.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Etapa 2: Abra o documento PDF
 Em seguida, você precisa abrir o documento PDF usando o`Document` classe de Aspose.PDF. Certifique-se de especificar o caminho correto para o arquivo PDF.

```csharp
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
```

## Etapa 3: Acesse a coleção de páginas
 Agora você pode acessar a coleção de páginas do documento usando o`Pages` propriedade do`pdfDocument` objeto.

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## Etapa 4: vá para uma página específica
Então você pode pular para uma página específica usando o índice da página na coleção. No exemplo abaixo, acessamos a segunda página (índice 1).

```csharp
Page pdfPage = pageCollection[1];
```

## Etapa 5: Obtenha as propriedades da página
 Agora você pode obter as diferentes propriedades da página PDF, como caixa de arte, caixa de corte, caixa de corte, etc., usando as propriedades correspondentes do`pdfPage` objeto.

```csharp
Console.WriteLine("ArtBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.ArtBox.Height, pdfPage.ArtBox.Width, pdfPage.ArtBox.LLX, pdfPage.ArtBox.LLY, pdfPage.ArtBox.URX, pdfPage.ArtBox.URY);
Console.WriteLine("BleedBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.BleedBox.Height, pdf

Page.BleedBox.Width, pdfPage.BleedBox.LLX, pdfPage.BleedBox.LLY, pdfPage.BleedBox.URX, pdfPage.BleedBox.URY);
Console.WriteLine("CropBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.CropBox.Height, pdfPage.CropBox.Width, pdfPage.CropBox.LLX, pdfPage.CropBox.LLY, pdfPage.CropBox.URX, pdfPage.CropBox.URY);
Console.WriteLine("MediaBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.MediaBox.Height, pdfPage.MediaBox.Width, pdfPage.MediaBox.LLX, pdfPage.MediaBox.LLY, pdfPage.MediaBox.URX, pdfPage.MediaBox.URY);
Console.WriteLine("TrimBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.TrimBox.Height, pdfPage.TrimBox.Width, pdfPage.TrimBox.LLX, pdfPage.TrimBox.LLY, pdfPage.TrimBox.URX, pdfPage.TrimBox.URY);
Console.WriteLine("Rect: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.Rect.Height, pdfPage.Rect.Width, pdfPage.Rect.LLX, pdfPage.Rect.LLY, pdfPage.Rect.URX, pdfPage.Rect.URY);
Console.WriteLine("Page number: {0}", pdfPage.Number);
Console.WriteLine("Rotate: {0}", pdfPage.Rotate);
```

### Código-fonte de exemplo para Obter propriedades usando Aspose.PDF para .NET 

```csharp

// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
// Obter coleção de páginas
PageCollection pageCollection = pdfDocument.Pages;
// Obter página específica
Page pdfPage = pageCollection[1];
// Obter propriedades da página
System.Console.WriteLine("ArtBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.ArtBox.Height, pdfPage.ArtBox.Width, pdfPage.ArtBox.LLX, pdfPage.ArtBox.LLY, pdfPage.ArtBox.URX, pdfPage.ArtBox.URY);
System.Console.WriteLine("BleedBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.BleedBox.Height, pdfPage.BleedBox.Width, pdfPage.BleedBox.LLX, pdfPage.BleedBox.LLY, pdfPage.BleedBox.URX, pdfPage.BleedBox.URY);
System.Console.WriteLine("CropBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.CropBox.Height, pdfPage.CropBox.Width, pdfPage.CropBox.LLX, pdfPage.CropBox.LLY, pdfPage.CropBox.URX, pdfPage.CropBox.URY);
System.Console.WriteLine("MediaBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.MediaBox.Height, pdfPage.MediaBox.Width, pdfPage.MediaBox.LLX, pdfPage.MediaBox.LLY, pdfPage.MediaBox.URX, pdfPage.MediaBox.URY);
System.Console.WriteLine("TrimBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.TrimBox.Height, pdfPage.TrimBox.Width, pdfPage.TrimBox.LLX, pdfPage.TrimBox.LLY, pdfPage.TrimBox.URX, pdfPage.TrimBox.URY);
System.Console.WriteLine("Rect : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.Rect.Height, pdfPage.Rect.Width, pdfPage.Rect.LLX, pdfPage.Rect.LLY, pdfPage.Rect.URX, pdfPage.Rect.URY);
System.Console.WriteLine("Page Number : {0}", pdfPage.Number);
System.Console.WriteLine("Rotate : {0}", pdfPage.Rotate);

```

## Conclusão
Parabéns! Você obteve com sucesso as propriedades de um PDF usando o Aspose.PDF para .NET. Você aprendeu como abrir um documento PDF, navegar para uma página específica e obter várias propriedades de página, como caixas de dimensão e rotação. Agora você pode usar essas informações para personalizar o manuseio de seus arquivos PDF com base em suas propriedades.

Não deixe de conferir a documentação oficial do Aspose.PDF para .NET para obter mais informações sobre recursos avançados e possibilidades de personalização.

### Perguntas frequentes

#### P: Como posso obter as propriedades de um PDF usando o Aspose.PDF para .NET?

R: Para obter as propriedades de um PDF usando o Aspose.PDF para .NET, você pode seguir estas etapas:

1. Defina o diretório do documento especificando o caminho para o arquivo PDF cujas propriedades você deseja recuperar.
2.  Abra o documento PDF usando o`Document` classe de Aspose.PDF, fornecendo o caminho correto para o arquivo PDF.
3.  Acesse a coleção de páginas do documento usando o`Pages` propriedade do`pdfDocument` objeto.
4. Ir para uma página específica usando o índice da página na coleção (a indexação começa em 1).
5.  Obtenha as diferentes propriedades da página PDF, como ArtBox, BleedBox, CropBox, MediaBox, TrimBox, Rect, Número de página e Rotação, usando as propriedades correspondentes do`pdfPage` objeto.

#### P: Quais são as diferentes propriedades de uma página PDF que posso recuperar usando o Aspose.PDF para .NET?

R: Você pode recuperar várias propriedades de uma página PDF usando Aspose.PDF para .NET, como:

- ArtBox: Representa as dimensões da arte da página.
- BleedBox: representa as dimensões do sangramento da página.
- CropBox: representa as dimensões do conteúdo visível da página após o corte.
- MediaBox: Representa as dimensões da mídia física da página.
- TrimBox: representa as dimensões do conteúdo recortado da página.
- Retângulo: representa as dimensões da caixa delimitadora da página.
- Número da página: representa o número da página no documento.
- Girar: representa o ângulo de rotação da página.

#### P: Como acesso uma página específica no documento PDF para recuperar suas propriedades?

 R: Para acessar uma página específica no documento PDF e recuperar suas propriedades, você pode usar o`Pages` propriedade do`pdfDocument` objeto para acessar a coleção de páginas do documento. Então, você pode usar o índice da página na coleção para pular para a página desejada. Por exemplo, para acessar a segunda página, você pode usar`pdfDocument.Pages[1]` (a indexação começa em 1).

#### P: Posso executar operações nas propriedades recuperadas, como modificar ou redimensionar as caixas de página?

R: Sim, depois de recuperar as propriedades de uma página PDF usando o Aspose.PDF for .NET, você pode executar várias operações nelas. Por exemplo, você pode modificar as dimensões das caixas de página, girar a página ou usar as informações recuperadas para processamento e manipulação personalizados do documento PDF.

#### P: O Aspose.PDF para .NET oferece suporte à extração de propriedades de arquivos PDF criptografados ou protegidos por senha?

R: Sim, o Aspose.PDF para .NET suporta a extração de propriedades de arquivos PDF criptografados ou protegidos por senha. Desde que você forneça a senha correta para abrir o documento PDF, você pode acessar e recuperar suas propriedades usando a mesma abordagem demonstrada no tutorial.