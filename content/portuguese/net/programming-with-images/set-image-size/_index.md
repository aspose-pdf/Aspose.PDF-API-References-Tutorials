---
title: Definir tamanho da imagem no arquivo PDF
linktitle: Definir tamanho da imagem no arquivo PDF
second_title: Referência da API do Aspose.PDF para .NET
description: Guia passo a passo para definir o tamanho de uma imagem em arquivo PDF usando o Aspose.PDF para .NET.
type: docs
weight: 270
url: /pt/net/programming-with-images/set-image-size/
---
Neste tutorial, mostraremos como definir o tamanho de uma imagem em um arquivo PDF usando o Aspose.PDF para .NET. Siga estas etapas para executar esta operação facilmente.

## Pré-requisitos

Antes de começar, certifique-se de ter o seguinte:

- Visual Studio ou qualquer outro ambiente de desenvolvimento instalado e configurado.
- Conhecimento básico da linguagem de programação C#.
- Biblioteca Aspose.PDF para .NET instalada. Você pode baixá-la do site oficial da Aspose.

## Etapa 1: Criação do documento PDF

Para começar, use o seguinte código para criar um novo documento PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Instanciar um objeto Document
Document doc = new Document();

// Adicionar uma página à coleção de páginas do arquivo PDF
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Etapa 2: Imagem adicionada

Em seguida, adicionaremos uma imagem à página do documento PDF. Use o seguinte código:

```csharp
// Criar uma instância de imagem
Aspose.Pdf.Image img = new Aspose.Pdf.Image();

// Defina a largura e a altura da imagem em pontos
img. FixWidth = 100;
img. FixHeight = 100;

//Definir tipo de imagem como desconhecido (Desconhecido)
img.FileType = Aspose.Pdf.ImageFileType.Unknown;

// Caminho para o arquivo de origem da imagem
img.File = dataDir + "aspose-logo.jpg";

// Adicione a imagem à coleção de parágrafos da página
page.Paragraphs.Add(img);
```

Certifique-se de fornecer o caminho correto para o arquivo de origem da imagem.

## Etapa 3: Definir propriedades da página

Por fim, definiremos as propriedades da página, incluindo sua largura e altura. Use o seguinte código:

```csharp
// Definir propriedades da página
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
```

### Código-fonte de exemplo para Definir tamanho da imagem usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instanciar objeto Document
Document doc = new Document();
// adicionar página à coleção de páginas do arquivo PDF
Aspose.Pdf.Page page = doc.Pages.Add();
// Criar uma instância de imagem
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
// Definir largura e altura da imagem em pontos
img.FixWidth = 100;
img.FixHeight = 100;
// Definir tipo de imagem como SVG
img.FileType = Aspose.Pdf.ImageFileType.Unknown;
// Caminho para o arquivo de origem
img.File = dataDir + "aspose-logo.jpg";
page.Paragraphs.Add(img);
//Definir propriedades da página
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
dataDir = dataDir + "SetImageSize_out.pdf";
// salvar arquivo PDF resultante
doc.Save(dataDir);
Console.WriteLine("\nImage size added successfully.\nFile saved at " + dataDir);
```

## Conclusão

Parabéns! Você definiu com sucesso o tamanho de uma imagem em um documento PDF usando o Aspose.PDF para .NET. Agora você pode aplicar esse método aos seus próprios projetos para ajustar o tamanho das imagens em arquivos PDF.

### Perguntas frequentes sobre como definir o tamanho da imagem em um arquivo PDF

#### P: Qual é o propósito de definir o tamanho de uma imagem em um documento PDF usando o Aspose.PDF para .NET?

R: O propósito de definir o tamanho de uma imagem em um documento PDF é controlar as dimensões da imagem quando ela é adicionada ao PDF. Isso permite que você ajuste a aparência e o layout das imagens dentro dos seus arquivos PDF.

#### P: Como funciona o processo de definição do tamanho de uma imagem em um documento PDF?

 R: O processo envolve a criação de um`Aspose.Pdf.Image` instância, especificando sua largura e altura usando o`FixWidth` e`FixHeight` propriedades e, em seguida, adicionar a imagem ao documento PDF. Além disso, você pode definir as dimensões da própria página para acomodar a imagem.

#### P: Posso definir o tamanho de uma imagem para uma porcentagem específica das dimensões da página?

R: O código fornecido define a largura e a altura absolutas da imagem em pontos. Se você quiser definir o tamanho de uma imagem com base em uma porcentagem das dimensões da página, você precisaria calcular as dimensões adequadamente e ajustar o código adequadamente.

####  P: Qual é o significado do`FileType` property when adding an image to the PDF document?

 A: O`FileType`propriedade especifica o tipo de imagem que está sendo adicionada ao documento PDF. No código fornecido, o valor`Unknown` indica que o tipo da imagem é desconhecido e o Aspose.PDF tentará determinar o tipo de imagem com base na extensão do arquivo.

#### P: Posso adicionar várias imagens a uma única página usando este método?

 R: Sim, você pode adicionar várias imagens a uma única página criando várias`Aspose.Pdf.Image` instâncias e adicioná-las à coleção de parágrafos da página. Certifique-se de ajustar o posicionamento e o layout das imagens conforme necessário.

#### P: Como posso controlar o posicionamento e o alinhamento da imagem adicionada na página?

 R: O posicionamento e o alinhamento da imagem adicionada podem ser controlados ajustando as coordenadas e o layout da imagem usando propriedades como`img.Left`, `img.Top`e propriedades de formatação de parágrafo.

####  P: Qual é o propósito de definir as propriedades da página usando`page.PageInfo.Width` and `page.PageInfo.Height`?

A: Definir as propriedades da página permite que você defina as dimensões da página em si. Isso garante que as dimensões da página acomodem a imagem adicionada e qualquer outro conteúdo que você possa ter na página.

#### P: Posso definir tamanhos diferentes para imagens diferentes no mesmo documento PDF?

 R: Sim, você pode definir tamanhos diferentes para imagens diferentes criando imagens separadas`Aspose.Pdf.Image` instâncias e ajustando o`FixWidth`, `FixHeight`, e propriedades de posicionamento para cada imagem.

#### P: Como posso integrar esse método em meus próprios projetos para definir tamanhos de imagem em arquivos PDF?

R: Para integrar esse método em seus projetos, siga as etapas descritas e modifique o código conforme necessário. Você pode usar esse método para adicionar imagens de tamanhos específicos aos seus documentos PDF com base nos requisitos do seu aplicativo.