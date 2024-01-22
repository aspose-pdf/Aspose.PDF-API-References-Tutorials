---
title: Pesquise e obtenha imagens em arquivo PDF
linktitle: Pesquise e obtenha imagens em arquivo PDF
second_title: Referência da API Aspose.PDF para .NET
description: Guia passo a passo para pesquisar e obter imagens em arquivo PDF usando Aspose.PDF for .NET.
type: docs
weight: 260
url: /pt/net/programming-with-images/search-and-get-images/
---
Neste tutorial, orientaremos você sobre como pesquisar e obter imagens em arquivo PDF usando Aspose.PDF for .NET. Siga estas etapas para realizar esta operação facilmente.

## Pré-requisitos

Antes de começar, certifique-se de ter o seguinte:

- Visual Studio ou qualquer outro ambiente de desenvolvimento instalado e configurado.
- Conhecimento básico da linguagem de programação C#.
- Biblioteca Aspose.PDF para .NET instalada. Você pode baixá-lo no site oficial do Aspose.

## Passo 1: Carregando o documento PDF

Para começar, use o seguinte código para carregar o documento PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Abra o documento
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SearchAndGetImages.pdf");
```

Certifique-se de fornecer o caminho correto para o seu documento PDF.

## Etapa 2: pesquisando locais de imagens

Para pesquisar a localização das imagens no documento PDF, use o seguinte código:

```csharp
// Crie um objeto ImagePlacementAbsorber para pesquisar locais de imagens
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();

// Aceite o absorvedor para todas as páginas do documento
doc.Pages.Accept(abs);
```

Isto irá coletar as localizações das imagens no absorvedor.

## Etapa 3: navegue pelos locais das imagens e obtenha as imagens e suas propriedades

A seguir, navegaremos pelos locais das imagens coletadas e obteremos as imagens e suas propriedades. Use o seguinte código:

```csharp
foreach(ImagePlacement imagePlacement in abs.ImagePlacements)
{
     // Obtenha a imagem usando o objeto ImagePlacement
     XImage image = imagePlacement.Image;

     // Exibir as propriedades de localização da imagem
     Console.Out.WriteLine("Image Width: " + imagePlacement.Rectangle.Width);
     Console.Out.WriteLine("Image Height: " + imagePlacement.Rectangle.Height);
     Console.Out.WriteLine("LLX of image: " + imagePlacement.Rectangle.LLX);
     Console.Out.WriteLine("LLY of image: " + imagePlacement.Rectangle.LLY);
     Console.Out.WriteLine("Horizontal image resolution: " + imagePlacement.Resolution.X);
     Console.Out.WriteLine("Vertical image resolution: " + imagePlacement.Resolution.Y);
}
```

Isso navegará por todos os locais das imagens, obterá imagens correspondentes e exibirá suas propriedades.

### Exemplo de código-fonte para pesquisar e obter imagens usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "SearchAndGetImages.pdf");
// Crie o objeto ImagePlacementAbsorber para realizar a pesquisa de posicionamento de imagens
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
// Aceite o absorvente para todas as páginas
doc.Pages.Accept(abs);
// Percorra todos os ImagePlacements, obtenha a imagem e as propriedades do ImagePlacement
foreach (ImagePlacement imagePlacement in abs.ImagePlacements)
{
	// Obtenha a imagem usando o objeto ImagePlacement
	XImage image = imagePlacement.Image;
	// Exibir propriedades de posicionamento de imagem para todos os canais
	Console.Out.WriteLine("image width:" + imagePlacement.Rectangle.Width);
	Console.Out.WriteLine("image height:" + imagePlacement.Rectangle.Height);
	Console.Out.WriteLine("image LLX:" + imagePlacement.Rectangle.LLX);
	Console.Out.WriteLine("image LLY:" + imagePlacement.Rectangle.LLY);
	Console.Out.WriteLine("image horizontal resolution:" + imagePlacement.Resolution.X);
	Console.Out.WriteLine("image vertical resolution:" + imagePlacement.Resolution.Y);
}
```

## Conclusão

Parabéns! Você pesquisou e obteve imagens em um documento PDF com sucesso usando Aspose.PDF for .NET. Agora você pode aplicar este método aos seus próprios projetos para extrair imagens e obter suas propriedades de arquivos PDF.

### FAQ's para pesquisar e obter imagens em arquivo PDF

#### P: Qual é o propósito de pesquisar e obter imagens em um documento PDF usando Aspose.PDF for .NET?

R: Pesquisar e obter imagens em um documento PDF permite localizar e extrair imagens dentro do arquivo PDF. Isso pode ser útil para diversos fins, como análise de conteúdo, verificação de propriedades de imagem ou processamento adicional de imagens.

#### P: Como funciona o processo de busca de imagens em um documento PDF?

 R: O processo envolve o uso do`ImagePlacementAbsorber` objeto para realizar uma pesquisa por posicionamentos de imagens em todas as páginas do documento PDF. O absorvedor coleta informações sobre a localização, tamanho e resolução de cada imagem no documento.

####  P: Qual é o propósito do`ImagePlacement` object in the code?

 R: O`ImagePlacement`objeto representa o posicionamento de uma imagem dentro do documento PDF. Ele fornece propriedades que permitem acessar detalhes como dimensões, coordenadas e resolução da imagem.

#### P: Posso filtrar as imagens pesquisadas e obtidas com base em critérios específicos?

R: O código fornecido coleta informações sobre todas as imagens do documento PDF. Se desejar filtrar imagens com base em critérios específicos (por exemplo, tipo de imagem, dimensões, resolução), talvez seja necessário modificar o código para incluir condições de filtragem apropriadas.

#### P: Como posso acessar o conteúdo real da imagem após obter as informações de posicionamento?

 R: O`XImage` objeto obtido do`ImagePlacement` objeto representa o conteúdo real da imagem. Você pode processar isso ainda mais`XImage` objeto, como salvá-lo em um arquivo ou exibi-lo em seu aplicativo.

#### P: O que posso fazer com as propriedades da imagem obtidas?

R: As propriedades da imagem obtidas, como largura, altura, coordenadas e resolução, podem ser usadas para diversos fins. Você pode analisar as propriedades, exibi-las ao usuário ou usá-las como entrada para processamento posterior.

#### P: Posso modificar ou editar as imagens do documento PDF usando este método?

R: O código fornecido se concentra na busca e obtenção de informações sobre posicionamento de imagens. Para modificar ou editar imagens, pode ser necessário integrar funcionalidades adicionais, como manipulação de imagens, usando a biblioteca Aspose.PDF.

#### P: Como posso integrar esse método em meus próprios projetos?

R: Para integrar este método em seus projetos, siga as etapas descritas e modifique o código conforme necessário. Você pode usar as informações e propriedades de posicionamento da imagem obtidas de acordo com os requisitos de sua aplicação.

#### P: O Aspose.PDF for .NET oferece outros recursos relacionados à manipulação de imagens em documentos PDF?

R: Sim, o Aspose.PDF for .NET oferece uma variedade de recursos para trabalhar com imagens em documentos PDF, incluindo inserção, redimensionamento, rotação, extração de imagens e muito mais. Você pode explorar a documentação e os exemplos da biblioteca para descobrir todos os seus recursos.