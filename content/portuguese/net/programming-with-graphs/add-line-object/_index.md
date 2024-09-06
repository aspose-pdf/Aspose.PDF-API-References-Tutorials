---
title: Adicionar objeto de linha em arquivo PDF
linktitle: Adicionar objeto de linha em arquivo PDF
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda como adicionar um objeto de linha personalizado em um arquivo PDF usando o Aspose.PDF para .NET.
type: docs
weight: 30
url: /pt/net/programming-with-graphs/add-line-object/
---
Neste tutorial, mostraremos passo a passo o seguinte código-fonte em C# para adicionar um objeto de linha usando Aspose.PDF para .NET.

Certifique-se de ter instalado a biblioteca Aspose.PDF e configurado seu ambiente de desenvolvimento antes de começar. Também tenha conhecimento básico de programação C#.

## Etapa 1: Configuração do diretório de documentos

No código-fonte fornecido, você precisa especificar o diretório onde deseja salvar o arquivo PDF resultante. Altere a variável "dataDir" para o diretório desejado.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Etapa 2: Criando uma instância de documento e adicionando uma página

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

## Etapa 4: Criar objeto de linha e adicionar ao gráfico

Criamos um objeto Line com as coordenadas especificadas e o adicionamos à coleção de formas do gráfico.

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
graph.Shapes.Add(line);
```

## Etapa 5: Configuração da linha

Podemos especificar propriedades para a linha, como tipo de traço e fase do traço.

```csharp
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## Etapa 6: Salvando o arquivo PDF

Por fim, salvamos o arquivo PDF resultante com o nome "AddLineObject_out.pdf" no diretório especificado.

```csharp
doc.Save(dataDir + "AddLineObject_out.pdf");
```

### Código-fonte de exemplo para Adicionar objeto de linha usando Aspose.PDF para .NET 

```csharp

// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Criar instância de documento
Document doc = new Document();
// Adicionar página à coleção de páginas do arquivo PDF
Page page = doc.Pages.Add();
// Criar instância do Graph
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
// Adicionar objeto gráfico à coleção de parágrafos da instância da página
page.Paragraphs.Add(graph);
// Criar instância Rectangle
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
// Especificar cor de preenchimento para objeto Graph
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

#### P: Qual é o propósito deste tutorial?

R: Este tutorial tem como objetivo orientar você no processo de adição de um objeto de linha usando o Aspose.PDF para .NET para aprimorar seus documentos PDF.

#### P: Quais são os pré-requisitos necessários antes de começar?

R: Antes de começar, certifique-se de ter instalado a biblioteca Aspose.PDF e configurado seu ambiente de desenvolvimento. Além disso, é recomendado ter um entendimento básico de programação em C#.

#### P: Como especifico o diretório para salvar o arquivo PDF?

R: No código-fonte fornecido, você pode modificar a variável "dataDir" para indicar o diretório onde deseja salvar o arquivo PDF resultante.

#### P: Qual é o propósito do objeto Graph?

A: O objeto Graph serve como um contêiner para elementos de desenho. Ele é criado com dimensões especificadas e adicionado à coleção de parágrafos da página.

#### P: Como posso adicionar um objeto de linha ao documento PDF?

R: Para adicionar um objeto de linha, crie uma instância da classe Line com coordenadas especificadas e adicione-a à coleção de formas do gráfico.

#### P: Posso personalizar a aparência da linha?

R: Sim, você pode personalizar a aparência da linha definindo propriedades como tipo de traço e fase do traço usando a propriedade GraphInfo do objeto Linha.

#### P: Qual é o propósito de especificar a matriz de traços e a fase de traços?

R: As propriedades de matriz de traços e fase de traços permitem que você crie linhas tracejadas ou pontilhadas com padrões específicos.

#### P: Como posso salvar o arquivo PDF depois de adicionar o objeto de linha?

 R: Após adicionar o objeto de linha, você pode salvar o arquivo PDF resultante usando o`doc.Save(dataDir + "AddLineObject_out.pdf");` linha no código-fonte fornecido.

#### P: Existe um código-fonte de exemplo disponível?

R: Sim, o tutorial inclui um código-fonte de exemplo que você pode consultar para implementar as etapas descritas.