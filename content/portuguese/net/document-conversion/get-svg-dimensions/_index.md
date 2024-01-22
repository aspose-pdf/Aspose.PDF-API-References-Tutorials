---
title: Obtenha dimensões SVG
linktitle: Obtenha dimensões SVG
second_title: Referência da API Aspose.PDF para .NET
description: Guia passo a passo para obter dimensões SVG usando Aspose.PDF para .NET.
type: docs
weight: 40
url: /pt/net/document-conversion/get-svg-dimensions/
---
## Introdução
Neste tutorial, orientaremos você no processo de obtenção das dimensões de um arquivo SVG usando Aspose.PDF para .NET. SVG (Scalable Vector Graphics) é um formato de imagem baseado em XML usado para representar gráficos vetoriais. Seguindo as etapas abaixo, você poderá obter as dimensões de um arquivo SVG e salvá-las como PDF.

## Pré-requisitos
Antes de começar, certifique-se de atender aos seguintes pré-requisitos:

- Conhecimento básico da linguagem de programação C#.
- Biblioteca Aspose.PDF para .NET instalada em seu sistema.
- Um ambiente de desenvolvimento como o Visual Studio.

## Passo 1: Carregando arquivo SVG
Nesta etapa, carregaremos o arquivo SVG usando Aspose.PDF for .NET. Siga o código abaixo:

```csharp
// Caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

var loadopt = new SvgLoadOptions();
loadopt.AdjustPageSize = true;
var svgDoc = new Document(dataDir + "GetSVGDimensions.svg", loadopt);
```

 Certifique-se de substituir`"YOUR DOCUMENTS DIRECTORY"` com o diretório real onde seu arquivo SVG está localizado.

## Etapa 2: ajuste do tamanho da página
Agora que carregamos o arquivo SVG, podemos ajustar o tamanho da página para acomodar o conteúdo SVG. Use o seguinte código:

```csharp
svgDoc.Pages[1].PageInfo.Margin.Top = 0;
svgDoc.Pages[1].PageInfo.Margin.Left = 0;
svgDoc.Pages[1].PageInfo.Margin.Bottom = 0;
svgDoc.Pages[1].PageInfo.Margin.Right = 0;
```

O código acima define as margens da página como zero, permitindo que o tamanho da página seja ajustado com base no conteúdo SVG.

## Passo 3: Salvando o PDF resultante
Depois de ajustar o tamanho da página, podemos salvar o documento PDF resultante. Aqui está a última etapa:

```csharp
svgDoc.Save(dataDir + "GetSVGDimensions_out.pdf");
```

 Substituir`"YOUR DOCUMENTS DIRECTORY"` com o diretório desejado onde você deseja salvar o arquivo PDF de saída.
  
### Exemplo de código-fonte para obter dimensões SVG usando Aspose.PDF para .NET

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

var loadopt = new SvgLoadOptions();
loadopt.AdjustPageSize = true;
var svgDoc = new Document(dataDir + "GetSVGDimensions.svg", loadopt);
svgDoc.Pages[1].PageInfo.Margin.Top = 0;
svgDoc.Pages[1].PageInfo.Margin.Left = 0;
svgDoc.Pages[1].PageInfo.Margin.Bottom = 0;
svgDoc.Pages[1].PageInfo.Margin.Right = 0;
svgDoc.Save(dataDir + "GetSVGDimensions_out.pdf");
```

## Conclusão
Neste tutorial, cobrimos o processo passo a passo de obtenção das dimensões de um arquivo SVG usando Aspose.PDF para .NET. Seguindo as instruções descritas acima, agora você poderá obter as dimensões de um arquivo SVG e salvá-las no formato PDF. Este recurso pode ser útil quando você precisa medir as dimensões de um gráfico vetorial.

### Perguntas frequentes

#### P: O que é SVG?

R: SVG (Scalable Vector Graphics) é um formato de imagem baseado em XML usado para representar gráficos vetoriais. Ao contrário das imagens raster, os arquivos SVG são independentes da resolução e podem ser dimensionados sem perder qualidade. SVG é amplamente utilizado para exibição de gráficos na web e pode ser editado e manipulado com facilidade.

#### P: Por que usar Aspose.PDF for .NET para conversão de SVG em PDF?

R: Aspose.PDF for .NET fornece uma maneira confiável e eficiente de lidar com arquivos SVG e convertê-los para o formato PDF. Oferece várias opções e configurações para personalizar o processo de conversão, como ajustar o tamanho da página, margens e outras propriedades para garantir uma representação precisa no PDF.

#### P: Posso converter arquivos SVG com gráficos e textos complexos?

R: Sim, o Aspose.PDF for .NET pode lidar com arquivos SVG com gráficos complexos, texto e elementos vetoriais. Preserva com precisão os detalhes e a qualidade do conteúdo SVG durante o processo de conversão, resultando em documentos PDF de alta qualidade.

#### P: É possível extrair texto de arquivos SVG com Aspose.PDF for .NET?

R: Sim, Aspose.PDF for .NET permite extrair texto de arquivos SVG. Você pode usar os recursos de extração de texto da biblioteca para extrair elementos de texto do SVG e salvá-los separadamente para processamento posterior.