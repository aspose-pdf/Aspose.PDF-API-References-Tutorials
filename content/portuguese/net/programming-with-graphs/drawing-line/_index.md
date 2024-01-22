---
title: Linha de desenho
linktitle: Linha de desenho
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como desenhar uma linha em uma página usando Aspose.PDF for .NET. Guia passo a passo para criar linhas personalizadas.
type: docs
weight: 80
url: /pt/net/programming-with-graphs/drawing-line/
---
Neste tutorial, orientaremos você passo a passo no seguinte código-fonte C# para desenhar uma linha usando Aspose.PDF para .NET.

Certifique-se de ter instalado a biblioteca Aspose.PDF e configurado seu ambiente de desenvolvimento antes de começar. Também possui conhecimentos básicos de programação C#.

## Etapa 1: configuração do diretório de documentos

No código-fonte fornecido, você precisa especificar o diretório onde deseja salvar o arquivo PDF resultante. Altere a variável “dataDir” para o diretório desejado.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Etapa 2: Criando uma Instância de Documento e Adicionando uma Página

Criamos uma instância da classe Document e adicionamos uma página a este documento.

```csharp
Document pDoc = new Document();
Page pg = pDoc.Pages.Add();
```

## Etapa 3: definir as margens da página

Definimos as margens da página como 0 em todos os lados.

```csharp
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
```

## Etapa 4: Criando um Objeto Gráfico e a Primeira Linha

Criamos um objeto Graph com dimensões iguais às da página e desenhamos a primeira linha que vai do canto inferior esquerdo ao canto superior direito da página.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width, (float)pg.PageInfo.Height);
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect. URY });
graph.Shapes.Add(line);
```

## Etapa 5: desenhar a segunda linha

Desenhamos a segunda linha que vai do canto superior esquerdo ao canto inferior direito da página.

```csharp
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect. LLX });
graph.Shapes.Add(line2);
```

## Etapa 6: adicionando o objeto gráfico à página

Adicionamos o objeto Graph à coleção de parágrafos da página.

```csharp
pg.Paragraphs.Add(graph);
```

## Etapa 7: salvando o arquivo PDF resultante

Finalmente, salvamos o arquivo PDF resultante com o nome "DrawingLine_out.pdf" no diretório especificado.

```csharp
pDoc.Save(dataDir + "DrawingLine_out.pdf");
```

### Exemplo de código-fonte para Drawing Line usando Aspose.PDF para .NET 

```csharp

// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Criar instância de documento
Document pDoc = new Document();
// Adicionar página à coleção de páginas do documento PDF
Page pg = pDoc.Pages.Add();
// Defina a margem da página em todos os lados como 0
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
// Criar objeto Gráfico com Largura e Altura iguais às dimensões da página
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width , (float)pg.PageInfo.Height);
// Crie um objeto de primeira linha começando do canto inferior esquerdo ao canto superior direito da página
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect.URY });
// Adicionar linha à coleção de formas do objeto Graph
graph.Shapes.Add(line);
// Desenhe uma linha do canto superior esquerdo da página até o canto inferior direito da página
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect.LLX });
// Adicionar linha à coleção de formas do objeto Graph
graph.Shapes.Add(line2);
// Adicionar objeto Graph à coleção de parágrafos da página
pg.Paragraphs.Add(graph);
dataDir = dataDir + "DrawingLine_out.pdf";
// Salvar arquivo PDF
pDoc.Save(dataDir);
Console.WriteLine("\nLine drawn successfully across the page.\nFile saved at " + dataDir);            

```

## Conclusão

Neste tutorial, explicamos como desenhar uma linha usando Aspose.PDF para .NET. Agora você pode usar esse conhecimento para criar formas geométricas com linhas personalizadas em seus arquivos PDF.

### Perguntas frequentes

#### P: Qual é o objetivo deste tutorial?

R: O objetivo deste tutorial é guiá-lo através do processo de desenho de linhas usando Aspose.PDF para .NET. Você aprenderá como criar linhas em uma página PDF e personalizar sua aparência.

#### P: Quais pré-requisitos são necessários antes de começar?

R: Antes de começar, certifique-se de ter instalado a biblioteca Aspose.PDF e configurado seu ambiente de desenvolvimento. Conhecimento básico de programação C# também é recomendado.

#### P: Como especifico o diretório para salvar o arquivo PDF?

R: Modifique a variável "dataDir" no código-fonte fornecido para indicar o diretório onde deseja salvar o arquivo PDF resultante.

#### P: Como crio linhas em uma página PDF?

R: O tutorial demonstra a criação de um objeto Graph com as dimensões da página e a adição de objetos Line a ele. Modifique as coordenadas e propriedades dos objetos Line para criar as linhas desejadas.

#### P: Posso personalizar a aparência das linhas?

R: Sim, você pode personalizar a aparência das linhas modificando as propriedades dos objetos Linha. Isso inclui alterar suas coordenadas, cor, espessura e outros atributos gráficos.

#### P: Como salvo o documento PDF depois de desenhar as linhas?

R: Depois de adicionar o objeto Gráfico com objetos Linha à página, você pode salvar o documento PDF resultante usando o`pDoc.Save(dataDir + "DrawingLine_out.pdf");` linha no código-fonte fornecido.

#### P: Posso desenhar linhas com diferentes ângulos e orientações?

R: Sim, você pode desenhar linhas com diferentes ângulos e orientações ajustando as coordenadas e propriedades dos objetos Linha no Gráfico.