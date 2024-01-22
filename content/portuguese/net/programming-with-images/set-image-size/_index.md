---
title: Definir o tamanho da imagem no arquivo PDF
linktitle: Definir o tamanho da imagem no arquivo PDF
second_title: Referência da API Aspose.PDF para .NET
description: Guia passo a passo para definir o tamanho de uma imagem em arquivo PDF usando Aspose.PDF for .NET.
type: docs
weight: 270
url: /pt/net/programming-with-images/set-image-size/
---
Neste tutorial, orientaremos você sobre como definir o tamanho de uma imagem em um arquivo PDF usando Aspose.PDF for .NET. Siga estas etapas para realizar esta operação facilmente.

## Pré-requisitos

Antes de começar, certifique-se de ter o seguinte:

- Visual Studio ou qualquer outro ambiente de desenvolvimento instalado e configurado.
- Conhecimento básico da linguagem de programação C#.
- Biblioteca Aspose.PDF para .NET instalada. Você pode baixá-lo no site oficial do Aspose.

## Passo 1: Criação do documento PDF

Para começar, use o seguinte código para criar um novo documento PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Instanciar um objeto Document
Document doc = new Document();

// Adicione uma página à coleção de páginas do arquivo PDF
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Etapa 2: imagem adicionada

A seguir, adicionaremos uma imagem à página do documento PDF. Use o seguinte código:

```csharp
// Crie uma instância de imagem
Aspose.Pdf.Image img = new Aspose.Pdf.Image();

// Defina a largura e a altura da imagem em pontos
img. FixWidth = 100;
img. FixHeight = 100;

// Defina o tipo de imagem como desconhecido (desconhecido)
img.FileType = Aspose.Pdf.ImageFileType.Unknown;

//Caminho para o arquivo de origem da imagem
img.File = dataDir + "aspose-logo.jpg";

// Adicione a imagem à coleção de parágrafos da página
page.Paragraphs.Add(img);
```

Certifique-se de fornecer o caminho correto para o arquivo de origem da imagem.

## Etapa 3: definir as propriedades da página

Finalmente, definiremos as propriedades da página, incluindo largura e altura. Use o seguinte código:

```csharp
// Definir propriedades da página
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
```

### Exemplo de código-fonte para definir tamanho da imagem usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instanciar objeto Document
Document doc = new Document();
// adicionar página à coleção de páginas do arquivo PDF
Aspose.Pdf.Page page = doc.Pages.Add();
// Crie uma instância de imagem
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
// Definir largura e altura da imagem em pontos
img.FixWidth = 100;
img.FixHeight = 100;
// Defina o tipo de imagem como SVG
img.FileType = Aspose.Pdf.ImageFileType.Unknown;
// Caminho para o arquivo de origem
img.File = dataDir + "aspose-logo.jpg";
page.Paragraphs.Add(img);
//Definir propriedades da página
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
dataDir = dataDir + "SetImageSize_out.pdf";
// salvar o arquivo PDF resultante
doc.Save(dataDir);
Console.WriteLine("\nImage size added successfully.\nFile saved at " + dataDir);
```

## Conclusão

Parabéns! Você definiu com sucesso o tamanho de uma imagem em um documento PDF usando Aspose.PDF for .NET. Agora você pode aplicar este método aos seus próprios projetos para ajustar o tamanho das imagens em arquivos PDF.

### Perguntas frequentes sobre como definir o tamanho da imagem em arquivo PDF

#### P: Qual é o propósito de definir o tamanho de uma imagem em um documento PDF usando Aspose.PDF for .NET?

R: O objetivo de definir o tamanho de uma imagem em um documento PDF é controlar as dimensões da imagem quando ela é adicionada ao PDF. Isso permite ajustar a aparência e o layout das imagens nos seus arquivos PDF.

#### P: Como funciona o processo de configuração do tamanho de uma imagem em um documento PDF?

 R: O processo envolve a criação de um`Aspose.Pdf.Image` instância, especificando sua largura e altura usando o`FixWidth` e`FixHeight` propriedades e, em seguida, adicionar a imagem ao documento PDF. Além disso, você pode definir as dimensões da própria página para acomodar a imagem.

#### P: Posso definir o tamanho de uma imagem para uma porcentagem específica das dimensões da página?

R: O código fornecido define a largura e altura absolutas da imagem em pontos. Se quiser definir o tamanho de uma imagem com base em uma porcentagem das dimensões da página, você precisará calcular as dimensões de acordo e ajustar o código de acordo.

####  P: Qual é o significado do`FileType` property when adding an image to the PDF document?

 R: O`FileType`propriedade especifica o tipo de imagem que está sendo adicionada ao documento PDF. No código fornecido, o valor`Unknown` indica que o tipo da imagem é desconhecido e o Aspose.PDF tentará determinar o tipo de imagem com base na extensão do arquivo.

#### P: Posso adicionar várias imagens a uma única página usando este método?

 R: Sim, você pode adicionar várias imagens a uma única página criando vários`Aspose.Pdf.Image` instâncias e adicioná-las à coleção de parágrafos da página. Certifique-se de ajustar o posicionamento e o layout das imagens conforme necessário.

#### P: Como posso controlar o posicionamento e o alinhamento da imagem adicionada na página?

 R: O posicionamento e o alinhamento da imagem adicionada podem ser controlados ajustando as coordenadas e o layout da imagem usando propriedades como`img.Left`, `img.Top`e propriedades de formatação de parágrafo.

####  P: Qual é o propósito de definir as propriedades da página usando`page.PageInfo.Width` and `page.PageInfo.Height`?

R: Definir as propriedades da página permite definir as dimensões da própria página. Isso garante que as dimensões da página acomodam a imagem adicionada e qualquer outro conteúdo que você possa ter na página.

#### P: Posso definir tamanhos diferentes para imagens diferentes no mesmo documento PDF?

 R: Sim, você pode definir tamanhos diferentes para imagens diferentes criando`Aspose.Pdf.Image` instâncias e ajustando o`FixWidth`, `FixHeight`e propriedades de posicionamento para cada imagem.

#### P: Como posso integrar esse método em meus próprios projetos para definir tamanhos de imagens em arquivos PDF?

R: Para integrar este método em seus projetos, siga as etapas descritas e modifique o código conforme necessário. Você pode usar este método para adicionar imagens de tamanhos específicos aos seus documentos PDF com base nos requisitos do seu aplicativo.