---
title: Adicionar objeto de linha em arquivo PDF
linktitle: Adicionar objeto de linha em arquivo PDF
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como adicionar um objeto de linha personalizado em um arquivo PDF usando Aspose.PDF for .NET.
type: docs
weight: 30
url: /pt/net/programming-with-graphs/add-line-object/
---
Neste tutorial, orientaremos você passo a passo no seguinte código-fonte C# para adicionar um objeto de linha usando Aspose.PDF para .NET.

Certifique-se de ter instalado a biblioteca Aspose.PDF e configurado seu ambiente de desenvolvimento antes de começar. Também possui conhecimentos básicos de programação C#.

## Etapa 1: configuração do diretório de documentos

No código-fonte fornecido, você precisa especificar o diretório onde deseja salvar o arquivo PDF resultante. Altere a variável “dataDir” para o diretório desejado.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Etapa 2: Criando uma Instância de Documento e Adicionando uma Página

Criamos uma instância da classe Document e adicionamos uma página a este documento.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Etapa 3: Criando um objeto gráfico e adicionando-o à página

Criamos um objeto Graph com dimensões especificadas e o adicionamos à coleção de parágrafos da página.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(graph);
```

## Etapa 4: criar objeto de linha e adicionar ao gráfico

Criamos um objeto Line com as coordenadas especificadas e o adicionamos à coleção de formas do gráfico.

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
graph.Shapes.Add(line);
```

## Etapa 5: configuração da linha

Podemos especificar propriedades para a linha, como tipo de traço e fase de traço.

```csharp
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## Passo 6: Salvando o arquivo PDF

Finalmente, salvamos o arquivo PDF resultante com o nome "AddLineObject_out.pdf" no diretório especificado.

```csharp
doc.Save(dataDir + "AddLineObject_out.pdf");
```

### Exemplo de código-fonte para Adicionar objeto de linha usando Aspose.PDF para .NET 

```csharp

// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Criar instância de documento
Document doc = new Document();
// Adicionar página à coleção de páginas do arquivo PDF
Page page = doc.Pages.Add();
// Criar instância do gráfico
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
// Adicionar objeto gráfico à coleção de parágrafos da instância da página
page.Paragraphs.Add(graph);
// Criar instância de retângulo
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
// Especifique a cor de preenchimento do objeto Gráfico
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
// Adicionar objeto retângulo à coleção de formas do objeto Graph
graph.Shapes.Add(line);
dataDir = dataDir + "AddLineObject_out.pdf";
// Salvar arquivo PDF
doc.Save(dataDir);
Console.WriteLine("\nLine object added successfully to pdf.\nFile saved at " + dataDir);            

```

## Conclusão

Neste tutorial, explicamos passo a passo como adicionar um objeto de linha usando Aspose.PDF para .NET. Agora você pode usar esse conhecimento para criar documentos PDF com linhas personalizadas em seus aplicativos.

### Perguntas frequentes sobre como adicionar objeto de linha em arquivo PDF

#### P: Qual é o objetivo deste tutorial?

R: Este tutorial tem como objetivo guiá-lo através do processo de adição de um objeto de linha usando Aspose.PDF for .NET para aprimorar seus documentos PDF.

#### P: Quais pré-requisitos são necessários antes de começar?

R: Antes de começar, certifique-se de ter instalado a biblioteca Aspose.PDF e configurado seu ambiente de desenvolvimento. Além disso, é recomendável ter um conhecimento básico de programação C#.

#### P: Como especifico o diretório para salvar o arquivo PDF?

R: No código-fonte fornecido, você pode modificar a variável "dataDir" para indicar o diretório onde deseja salvar o arquivo PDF resultante.

#### P: Qual é o propósito do objeto Graph?

R: O objeto Graph serve como um contêiner para desenhar elementos. Ele é criado com dimensões especificadas e adicionado à coleção de parágrafos da página.

#### P: Como posso adicionar um objeto de linha ao documento PDF?

R: Para adicionar um objeto de linha, crie uma instância da classe Line com coordenadas especificadas e adicione-a à coleção de formas do gráfico.

#### P: Posso personalizar a aparência da linha?

R: Sim, você pode personalizar a aparência da linha definindo propriedades como tipo de traço e fase de traço usando a propriedade GraphInfo do objeto Line.

#### P: Qual é o propósito de especificar a matriz e a fase do traço?

R: As propriedades da matriz de traços e da fase de traços permitem criar linhas tracejadas ou pontilhadas com padrões específicos.

#### P: Como posso salvar o arquivo PDF após adicionar o objeto de linha?

 R: Depois de adicionar o objeto de linha, você pode salvar o arquivo PDF resultante usando o`doc.Save(dataDir + "AddLineObject_out.pdf");` linha no código-fonte fornecido.

#### P: Existe um exemplo de código-fonte disponível?

R: Sim, o tutorial inclui um exemplo de código-fonte que você pode consultar para implementar as etapas descritas.