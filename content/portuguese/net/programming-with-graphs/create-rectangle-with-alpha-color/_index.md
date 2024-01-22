---
title: Crie retângulo com cor alfa
linktitle: Crie retângulo com cor alfa
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como criar um retângulo com cor transparente usando Aspose.PDF para .NET. Guia passo a passo para personalizar a transparência.
type: docs
weight: 60
url: /pt/net/programming-with-graphs/create-rectangle-with-alpha-color/
---
Neste tutorial, orientaremos você através do seguinte código-fonte C#, passo a passo, para criar um retângulo com cor alfa usando Aspose.PDF para .NET.

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
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Etapa 3: Criando um objeto gráfico e um retângulo

Criamos um objeto Graph com dimensões específicas e um retângulo com dimensões específicas.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
```

## Etapa 4: configurar a cor alfa do retângulo

Podemos especificar uma cor alfa para o retângulo usando o método FromArgb da classe System.Drawing.Color.

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
```

## Etapa 5: Adicionando o retângulo ao objeto gráfico

Adicionamos o retângulo à coleção de formas do objeto Graph.

```csharp
canvas.Shapes.Add(rect);
```

## Etapa 6: Criando um segundo retângulo com uma cor alfa diferente

Criamos um segundo retângulo com dimensões específicas e outra cor alfa.

```csharp
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
```

## Etapa 7: adicionando o objeto gráfico à página

Adicionamos o objeto Graph à coleção Paragraph do objeto Page.

```csharp
page.Paragraphs.Add(canvas);
```

## Etapa 8: salvando o arquivo PDF resultante

Finalmente, salvamos o arquivo PDF resultante com o nome "CreateRectangleWithAlphaColor_out.pdf" no diretório especificado.

```csharp
doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");
```

### Exemplo de código-fonte para Criar retângulo com cor alfa usando Aspose.PDF para .NET 

```csharp

// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instanciar instância de documento
Document doc = new Document();
// Adicionar página à coleção de páginas do arquivo PDF
Aspose.Pdf.Page page = doc.Pages.Add();
// Criar instância do gráfico
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Crie um objeto retângulo com dimensões específicas
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
//Defina a cor de preenchimento do gráfico da estrutura System.Drawing.Color a partir de um valor ARGB de 32 bits
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
// Adicionar objeto retângulo à coleção de formas da instância Graph
canvas.Shapes.Add(rect);
// Crie o segundo objeto retângulo
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
// Adicionar instância de gráfico à coleção de parágrafos do objeto de página
page.Paragraphs.Add(canvas);
dataDir = dataDir + "CreateRectangleWithAlphaColor_out.pdf";
// Salvar arquivo PDF
doc.Save(dataDir);
Console.WriteLine("\nRectangle object created successfully with alpha color.\nFile saved at " + dataDir);            

```

## Conclusão

Neste tutorial, explicamos como criar um retângulo com cor alfa usando Aspose.PDF for .NET. Agora você pode usar esse conhecimento para criar formas geométricas com cores transparentes em seus arquivos PDF.

## Perguntas frequentes

#### P: Qual é o objetivo deste tutorial?

R: Este tutorial tem como objetivo guiá-lo através do processo de criação de um retângulo com cor alfa usando Aspose.PDF para .NET. Você aprenderá como adicionar formas geométricas com cores transparentes aos seus arquivos PDF.

#### P: Quais pré-requisitos são necessários antes de começar?

R: Antes de começar, certifique-se de ter instalado a biblioteca Aspose.PDF e configurado seu ambiente de desenvolvimento. Além disso, é recomendável ter um conhecimento básico de programação C#.

#### P: Como especifico o diretório para salvar o arquivo PDF?

R: No código-fonte fornecido, você pode modificar a variável "dataDir" para indicar o diretório onde deseja salvar o arquivo PDF resultante.

#### P: Qual é a finalidade do objeto Graph e do retângulo?

R: O objeto Graph atua como um contêiner para elementos de desenho, enquanto o Rectangle representa a forma geométrica que você adicionará ao PDF.

#### P: Como posso configurar uma cor alfa para o retângulo?

R: Você pode especificar uma cor alfa para o retângulo usando o`FillColor` propriedade do`GraphInfo` objeto e o`Color.FromRgb` método com um valor ARGB.

#### P: Posso criar vários retângulos com cores alfa diferentes?

R: Sim, você pode criar vários retângulos com diferentes cores alfa seguindo etapas semelhantes demonstradas no tutorial.

#### P: Como salvo o arquivo PDF resultante após criar retângulos com cores alfa?

 R: Depois de criar os retângulos com cores alfa, você pode salvar o arquivo PDF resultante usando o`doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");` linha no código-fonte fornecido.