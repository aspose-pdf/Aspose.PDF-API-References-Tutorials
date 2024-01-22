---
title: Criar retângulo preenchido
linktitle: Criar retângulo preenchido
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como criar um retângulo preenchido com Aspose.PDF para .NET. Guia passo a passo para personalizar a cor de preenchimento.
type: docs
weight: 50
url: /pt/net/programming-with-graphs/create-filled-rectangle/
---
Neste tutorial, orientaremos você através do seguinte código-fonte C#, passo a passo, para criar um retângulo preenchido usando Aspose.PDF para .NET.

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

## Etapa 4: criar objeto retângulo e adicionar ao gráfico

Criamos um objeto Rectangle com as dimensões especificadas e o adicionamos à coleção de formas do gráfico.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
graph.Shapes.Add(rect);
```

## Etapa 5: definir a cor de preenchimento

Podemos especificar a cor de preenchimento do retângulo usando a propriedade FillColor do objeto GraphInfo.

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
```

## Etapa 6: salvando o arquivo PDF resultante

Finalmente, salvamos o arquivo PDF resultante com o nome "CreateFilledRectangle_out.pdf" no diretório especificado.

```csharp
doc.Save(dataDir + "CreateFilledRectangle_out.pdf");
```

### Exemplo de código-fonte para Criar retângulo preenchido usando Aspose.PDF para .NET 

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
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
// Especifique a cor de preenchimento do objeto Gráfico
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
// Adicionar objeto retângulo à coleção de formas do objeto Graph
graph.Shapes.Add(rect);
dataDir = dataDir + "CreateFilledRectangle_out.pdf";
// Salvar arquivo PDF
doc.Save(dataDir);
Console.WriteLine("\nFilled rectangle object created successfully.\nFile saved at " + dataDir);            

```

## Conclusão

Neste tutorial, explicamos como criar um retângulo preenchido usando Aspose.PDF for .NET. Agora você pode usar esse conhecimento para criar formas geométricas com cores de preenchimento personalizadas em seus arquivos PDF.

## Perguntas frequentes

#### P: Qual é o objetivo deste tutorial?

R: O objetivo deste tutorial é guiá-lo através do processo de criação de um retângulo preenchido usando Aspose.PDF for .NET, permitindo adicionar formas geométricas personalizadas com cores de preenchimento aos seus arquivos PDF.

#### P: Quais pré-requisitos são necessários antes de começar?

R: Antes de começar, certifique-se de ter instalado a biblioteca Aspose.PDF e configurado seu ambiente de desenvolvimento. Além disso, é recomendável ter um conhecimento básico de programação C#.

#### P: Como especifico o diretório para salvar o arquivo PDF?

R: No código-fonte fornecido, você pode modificar a variável "dataDir" para indicar o diretório onde deseja salvar o arquivo PDF resultante.

#### P: Qual é o propósito do objeto Graph?

R: O objeto Graph atua como um contêiner para desenhar elementos. Ele é criado com dimensões especificadas e adicionado à coleção de parágrafos da página.

#### P: Como posso adicionar um retângulo preenchido ao documento PDF?

R: Para adicionar um retângulo preenchido, crie uma instância da classe Rectangle com dimensões e cor de preenchimento especificadas e adicione-a à coleção de formas do gráfico.

#### P: Posso personalizar as dimensões e a cor de preenchimento do retângulo?

 R: Sim, você pode personalizar as dimensões e a cor de preenchimento do retângulo modificando os parâmetros passados para o`Aspose.Pdf.Drawing.Rectangle` construtor e definindo a propriedade FillColor.

#### P: Como salvo o arquivo PDF resultante após criar o retângulo preenchido?

 R: Depois de criar o retângulo preenchido, você pode salvar o arquivo PDF resultante usando o`doc.Save(dataDir + "CreateFilledRectangle_out.pdf");` linha no código-fonte fornecido.