---
title: Extrair Borda em Arquivo PDF
linktitle: Extrair Borda em Arquivo PDF
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda como extrair bordas de um arquivo PDF e salvá-las como uma imagem usando o Aspose.PDF para .NET. Guia passo a passo com exemplos de código e dicas para o sucesso.
type: docs
weight: 80
url: /pt/net/programming-with-tables/extract-border/
---
## Introdução

Ao trabalhar com PDFs, extrair elementos específicos, como bordas ou caminhos gráficos, pode parecer uma tarefa assustadora. Mas com o Aspose.PDF para .NET, você pode facilmente extrair bordas ou formas de um arquivo PDF e salvá-las como uma imagem. Neste tutorial, vamos nos aprofundar no processo de extrair uma borda de um PDF e salvá-la como uma imagem PNG. Prepare-se para assumir o controle do conteúdo gráfico do seu PDF!

## Pré-requisitos

Antes de mergulharmos no código, certifique-se de ter tudo configurado:

1.  Aspose.PDF para .NET: Se você ainda não instalou a biblioteca Aspose.PDF, você pode[baixe aqui](https://releases.aspose.com/pdf/net/). Você também precisará aplicar a licença, seja por meio do teste gratuito ou de uma licença comprada.
2. Configuração do IDE: Configure um projeto C# no Visual Studio ou qualquer outro IDE .NET. Certifique-se de ter adicionado as referências necessárias à biblioteca Aspose.PDF.
3. Arquivo PDF de entrada: Tenha um arquivo PDF pronto do qual você extrairá as bordas. Este tutorial fará referência a um arquivo chamado`input.pdf`.

## Importando Pacotes Necessários

Vamos começar importando os namespaces necessários. Esses pacotes fornecem as ferramentas necessárias para manipular o conteúdo do PDF.

```csharp
using System.IO;
using System;
using System.Drawing.Drawing2D;
using System.Drawing.Imaging;
using System.Collections;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
```

Agora que já entendemos o básico, vamos passar para o guia passo a passo, onde detalharemos cada parte do código.


## Etapa 1: Carregando o documento PDF

O primeiro passo é carregar o documento PDF que contém a borda que você quer extrair. Pense nisso como abrir um livro antes de começar a ler — você precisa acessar o conteúdo!

 Começaremos especificando o diretório onde seu arquivo PDF está armazenado e carregaremos o documento usando o`Aspose.Pdf.Document` aula.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
```

 Este código carrega o`input.pdf` arquivo do seu diretório especificado. Certifique-se de que o caminho do arquivo esteja correto, ou você pode obter um erro de arquivo não encontrado.

## Etapa 2: Configurando gráficos e bitmap

Antes de começarmos a extrair, precisamos criar uma tela para desenhar. No mundo do .NET, isso significa configurar um Bitmap e objetos Graphics. O Bitmap representa a imagem, e o objeto Graphics nos permitirá desenhar formas, como bordas, extraídas do PDF.

```csharp
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);
```

Aqui está uma análise:
- Criamos uma imagem bitmap do tamanho da primeira página do PDF.
- GraphicsPath é usado para definir formas (neste caso, bordas).
- A matriz define como os gráficos serão transformados; precisamos de uma matriz de inversão porque PDF e .NET têm sistemas de coordenadas diferentes.

## Etapa 3: Processando o conteúdo do PDF


O arquivo PDF é uma série de comandos de desenho, e precisamos processar cada um desses comandos para identificar e extrair as informações da borda.

```csharp
foreach (Operator op in doc.Pages[1].Contents)
{
    // Comandos de processamento como salvar/restaurar estado, desenhar linhas, preencher formas, etc.
}
```

O código faz um loop por cada operador de desenho no fluxo de conteúdo do PDF. Cada operador pode representar uma linha, retângulo ou outra instrução gráfica.

## Etapa 4: Manipulando operadores PDF

Cada operador no arquivo PDF controla uma ação. Para extrair a borda, precisamos identificar comandos como "move to", "line to" e "draw rectangle". Os seguintes operadores lidam com essas ações:

- MoveTo: move o cursor para um ponto inicial.
- LineTo: Desenha uma linha do ponto atual até um novo ponto.
- Re: Desenha um retângulo (isso pode ser parte da borda).

```csharp
Aspose.Pdf.Operators.MoveTo opMoveTo = op as Aspose.Pdf.Operators.MoveTo;
Aspose.Pdf.Operators.LineTo opLineTo = op as Aspose.Pdf.Operators.LineTo;
Aspose.Pdf.Operators.Re opRe = op as Aspose.Pdf.Operators.Re;

if (opMoveTo != null)
{
    lastPoint = new System.Drawing.PointF((float)opMoveTo.X, (float)opMoveTo.Y);
}
else if (opLineTo != null)
{
    System.Drawing.PointF linePoint = new System.Drawing.PointF((float)opLineTo.X, (float)opLineTo.Y);
    graphicsPath.AddLine(lastPoint, linePoint);
    lastPoint = linePoint;
}
else if (opRe != null)
{
    System.Drawing.RectangleF re = new System.Drawing.RectangleF((float)opRe.X, (float)opRe.Y, (float)opRe.Width, (float)opRe.Height);
    graphicsPath.AddRectangle(re);
}
```

Nesta etapa:
- Capturamos os pontos para cada linha ou forma desenhada.
- Para retângulos (`opRe` ), nós os adicionamos diretamente ao`graphicsPath`, que usaremos mais tarde para desenhar a borda.

## Etapa 5: Desenhando a Borda

Uma vez que identificamos as linhas e retângulos que formam a borda, precisamos realmente desenhá-los no objeto Bitmap. É aqui que o objeto Graphics entra.

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
    gr.SmoothingMode = SmoothingMode.HighQuality;
    gr.DrawPath(new System.Drawing.Pen(strokeColor), graphicsPath);
}
```

- Criamos um objeto gráfico com base no bitmap.
- SmoothingMode.HighQuality garante que obtemos uma imagem suave e agradável.
- Por fim, usamos DrawPath para desenhar a borda.

## Etapa 6: Salvando a Borda Extraída

Agora que extraímos a borda, é hora de salvá-la como um arquivo de imagem. Isso salvará a borda como um PNG.

```csharp
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);
```

- O bitmap é salvo como uma imagem PNG.
- Agora você pode abrir esta imagem para visualizar a borda extraída.

## Conclusão

Extrair bordas de um arquivo PDF usando Aspose.PDF para .NET pode parecer complicado no começo, mas depois que você decompõe, fica simples. Ao entender os operadores de desenho em um PDF e utilizar as poderosas bibliotecas .NET, você pode manipular e extrair conteúdo gráfico de forma eficiente. Este guia fornece uma base sólida para começar a manipular PDF!

## Perguntas frequentes

### Como lidar com várias páginas no PDF?  
 Você pode percorrer cada página do documento iterando sobre`doc.Pages` em vez de codificar`doc.Pages[1]`.

### Posso extrair outros elementos, como texto, usando a mesma abordagem?  
Sim, o Aspose.PDF fornece APIs avançadas para extrair texto, imagens e outros conteúdos de arquivos PDF.

### Como posso solicitar uma licença para evitar limitações?  
 Você pode[aplicar uma licença](https://purchase.aspose.com/temporary-license/) carregando-o através do`License` aula fornecida pela Aspose.

### E se meu PDF não tiver bordas?  
Se o seu PDF não contiver bordas visíveis, o processo de extração de gráficos pode não gerar nenhum resultado. Certifique-se de que o conteúdo do PDF inclua bordas desenháveis.

### Posso salvar a saída em formatos diferentes de PNG?  
 Sim, basta alterar o`ImageFormat.Png` para outro formato suportado, como`ImageFormat.Jpeg`.