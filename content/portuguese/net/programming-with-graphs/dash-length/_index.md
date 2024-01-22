---
title: Comprimento do traço
linktitle: Comprimento do traço
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como definir o comprimento dos travessões com Aspose.PDF para .NET. Guia passo a passo para personalizar padrões de traço.
type: docs
weight: 70
url: /pt/net/programming-with-graphs/dash-length/
---
Neste tutorial, orientaremos você passo a passo no seguinte código-fonte C# para definir o comprimento dos travessões usando Aspose.PDF para .NET.

Certifique-se de ter instalado a biblioteca Aspose.PDF e configurado seu ambiente de desenvolvimento antes de começar. Também possui conhecimentos básicos de programação C#.

## Etapa 1: configuração do diretório de documentos

No código-fonte fornecido, você precisa especificar o diretório onde deseja salvar o arquivo PDF resultante. Altere a variável “dataDir” para o diretório desejado.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Etapa 2: instanciar um objeto de documento e adicionar uma página

Criamos uma instância da classe Document e adicionamos uma página a este documento.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Etapa 3: Criando um objeto gráfico e adicionando-o à página

Criamos um objeto Graph com dimensões especificadas e o adicionamos à coleção de parágrafos da página.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(canvas);
```

## Etapa 4: Criando um objeto de linha e configurando

Criamos um objeto Line com as coordenadas especificadas e configuramos a cor e o comprimento dos traços.

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## Etapa 5: Adicionando a linha ao objeto gráfico

Adicionamos a linha à coleção de formas do objeto Graph.

```csharp
canvas.Shapes.Add(line);
```

## Etapa 6: salvando o arquivo PDF resultante

Finalmente, salvamos o arquivo PDF resultante com o nome "DashLength_out.pdf" no diretório especificado.

```csharp
doc.Save(dataDir + "DashLength_out.pdf");
```

### Exemplo de código-fonte para Dash Length usando Aspose.PDF para .NET 

```csharp

// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instanciar instância de documento
Document doc = new Document();
// Adicionar página à coleção de páginas do objeto Document
Page page = doc.Pages.Add();
// Criar objeto de desenho com determinadas dimensões
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Adicionar objeto de desenho à coleção de parágrafos da instância da página
page.Paragraphs.Add(canvas);
// Criar objeto Linha
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
// Definir cor para objeto Linha
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
// Especifique a matriz de traços para o objeto de linha
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
// Defina a fase de traço para a instância Line
line.GraphInfo.DashPhase = 1;
// Adicionar linha à coleção de formas do objeto de desenho
canvas.Shapes.Add(line);
dataDir = dataDir + "DashLength_out.pdf";
// Salvar documento PDF
doc.Save(dataDir);
Console.WriteLine("\nLength dashed successfully in black and white.\nFile saved at " + dataDir);            

```

## Conclusão

Neste tutorial, explicamos como definir o comprimento dos travessões usando Aspose.PDF para .NET. Agora você pode usar esse conhecimento para criar linhas com padrões de traços personalizados em seus arquivos PDF.

## Perguntas frequentes

#### P: Qual é o objetivo deste tutorial?

R: O objetivo deste tutorial é guiá-lo através do processo de configuração do comprimento dos traços para linhas usando Aspose.PDF para .NET. Você aprenderá como criar linhas com padrões de traços personalizados em seus arquivos PDF.

#### P: Quais pré-requisitos são necessários antes de começar?

R: Antes de começar, certifique-se de ter instalado a biblioteca Aspose.PDF e configurado seu ambiente de desenvolvimento. Uma compreensão básica de programação C# também é recomendada.

#### P: Como especifico o diretório para salvar o arquivo PDF?

R: Modifique a variável "dataDir" no código-fonte fornecido para indicar o diretório onde deseja salvar o arquivo PDF resultante.

#### P: Como posso criar uma linha com padrões de traços personalizados?

 R: O tutorial demonstra a criação de um objeto Line e a configuração de sua cor, matriz de traço e fase de traço usando o método`GraphInfo` objeto. Modifique essas configurações para obter o padrão de traço desejado.

#### P: Posso personalizar a cor da linha?

 R: Sim, você pode personalizar a cor da linha definindo o`Color` propriedade do`GraphInfo` objeto associado à Linha.

#### P: Como salvo o documento PDF após definir o comprimento do traço?

 R: Depois de configurar o objeto Linha com o padrão de traço desejado, você pode salvar o documento PDF resultante usando o`doc.Save(dataDir + "DashLength_out.pdf");` linha no código-fonte fornecido.