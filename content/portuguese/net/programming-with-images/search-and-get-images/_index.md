---
title: Pesquise e obtenha imagens em arquivo PDF
linktitle: Pesquise e obtenha imagens em arquivo PDF
second_title: Referência da API do Aspose.PDF para .NET
description: Guia passo a passo para pesquisar e obter imagens em arquivo PDF usando Aspose.PDF para .NET.
type: docs
weight: 260
url: /pt/net/programming-with-images/search-and-get-images/
---
Neste tutorial, mostraremos como pesquisar e obter imagens em arquivo PDF usando Aspose.PDF para .NET. Siga estas etapas para executar esta operação facilmente.

## Pré-requisitos

Antes de começar, certifique-se de ter o seguinte:

- Visual Studio ou qualquer outro ambiente de desenvolvimento instalado e configurado.
- Conhecimento básico da linguagem de programação C#.
- Biblioteca Aspose.PDF para .NET instalada. Você pode baixá-la do site oficial da Aspose.

## Etapa 1: Carregando o documento PDF

Para começar, use o seguinte código para carregar o documento PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Abra o documento
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SearchAndGetImages.pdf");
```

Certifique-se de fornecer o caminho correto para o seu documento PDF.

## Etapa 2: Pesquisando locais de imagens

Para pesquisar os locais das imagens no documento PDF, use o seguinte código:

```csharp
// Crie um objeto ImagePlacementAbsorber para pesquisar locais de imagens
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();

// Aceite o absorvedor para todas as páginas do documento
doc.Pages.Accept(abs);
```

Isso coletará os locais das imagens no absorvedor.

## Etapa 3: navegue pelos locais das imagens e obtenha imagens e suas propriedades

Em seguida, navegaremos pelos locais de imagens coletadas e obteremos as imagens e suas propriedades. Use o seguinte código:

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

Isso navegará por todos os locais de imagens, obterá imagens correspondentes e exibirá suas propriedades.

### Exemplo de código-fonte para Pesquisar e Obter Imagens usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "SearchAndGetImages.pdf");
// Crie um objeto ImagePlacementAbsorber para executar uma pesquisa de posicionamento de imagem
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
// Aceite o absorvedor para todas as páginas
doc.Pages.Accept(abs);
// Percorrer todos os ImagePlacements, obter a imagem e as propriedades do ImagePlacement
foreach (ImagePlacement imagePlacement in abs.ImagePlacements)
{
	// Obter a imagem usando o objeto ImagePlacement
	XImage image = imagePlacement.Image;
	// Exibir propriedades de posicionamento de imagem para todos os posicionamentos
	Console.Out.WriteLine("image width:" + imagePlacement.Rectangle.Width);
	Console.Out.WriteLine("image height:" + imagePlacement.Rectangle.Height);
	Console.Out.WriteLine("image LLX:" + imagePlacement.Rectangle.LLX);
	Console.Out.WriteLine("image LLY:" + imagePlacement.Rectangle.LLY);
	Console.Out.WriteLine("image horizontal resolution:" + imagePlacement.Resolution.X);
	Console.Out.WriteLine("image vertical resolution:" + imagePlacement.Resolution.Y);
}
```

## Conclusão

Parabéns! Você pesquisou e obteve imagens com sucesso em um documento PDF usando o Aspose.PDF for .NET. Agora você pode aplicar esse método aos seus próprios projetos para extrair imagens e obter suas propriedades de arquivos PDF.

### Perguntas frequentes sobre como pesquisar e obter imagens em arquivo PDF

#### P: Qual é o propósito de pesquisar e obter imagens em um documento PDF usando o Aspose.PDF para .NET?

A: Pesquisar e obter imagens em um documento PDF permite que você localize e extraia imagens dentro do arquivo PDF. Isso pode ser útil para vários propósitos, como analisar o conteúdo, verificar propriedades da imagem ou processar mais as imagens.

#### P: Como funciona o processo de busca de imagens em um documento PDF?

 R: O processo envolve o uso do`ImagePlacementAbsorber` objeto para executar uma busca por posicionamentos de imagem em todas as páginas do documento PDF. O absorber coleta informações sobre a localização, tamanho e resolução de cada imagem dentro do documento.

####  P: Qual é o propósito do`ImagePlacement` object in the code?

 A: O`ImagePlacement`objeto representa o posicionamento de uma imagem dentro do documento PDF. Ele fornece propriedades que permitem que você acesse detalhes como as dimensões, coordenadas e resolução da imagem.

#### P: Posso filtrar as imagens pesquisadas e obtidas com base em critérios específicos?

R: O código fornecido coleta informações sobre todas as imagens dentro do documento PDF. Se você quiser filtrar imagens com base em critérios específicos (por exemplo, tipo de imagem, dimensões, resolução), pode ser necessário modificar o código para incluir condições de filtragem apropriadas.

#### P: Como posso acessar o conteúdo real da imagem depois de obter suas informações de posicionamento?

 A: O`XImage` objeto obtido do`ImagePlacement` objeto representa o conteúdo real da imagem. Você pode processar isso ainda mais`XImage` objeto, como salvá-lo em um arquivo ou exibi-lo em seu aplicativo.

#### P: O que posso fazer com as propriedades da imagem obtidas?

A: As propriedades de imagem obtidas, como largura, altura, coordenadas e resolução, podem ser usadas para vários propósitos. Você pode analisar as propriedades, exibi-las ao usuário ou usá-las como entrada para processamento posterior.

#### P: Posso modificar ou editar as imagens no documento PDF usando este método?

R: O código fornecido foca na busca e obtenção de informações de posicionamento de imagem. Para modificar ou editar imagens, você pode precisar integrar funcionalidades adicionais, como manipulação de imagem, usando a biblioteca Aspose.PDF.

#### P: Como posso integrar esse método em meus próprios projetos?

R: Para integrar esse método em seus projetos, siga os passos descritos e modifique o código conforme necessário. Você pode usar as informações de posicionamento de imagem e propriedades obtidas de acordo com os requisitos de sua aplicação.

#### P: O Aspose.PDF para .NET oferece outros recursos relacionados à manipulação de imagens em documentos PDF?

R: Sim, o Aspose.PDF for .NET fornece uma variedade de recursos para trabalhar com imagens em documentos PDF, incluindo inserção de imagens, redimensionamento, rotação, extração e muito mais. Você pode explorar a documentação e os exemplos da biblioteca para descobrir todos os seus recursos.