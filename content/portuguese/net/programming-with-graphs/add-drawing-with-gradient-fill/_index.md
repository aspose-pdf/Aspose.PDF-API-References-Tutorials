---
title: Adicionar desenho com preenchimento de gradiente
linktitle: Adicionar desenho com preenchimento de gradiente
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda como adicionar um desenho com preenchimento de gradiente com Aspose.PDF para .NET. Tutorial passo a passo para criar documentos PDF atraentes.
type: docs
weight: 20
url: /pt/net/programming-with-graphs/add-drawing-with-gradient-fill/
---
Neste tutorial, mostraremos passo a passo o seguinte código-fonte em C# para adicionar um desenho com preenchimento de gradiente à programação com gráficos usando o Aspose.PDF para .NET.

Certifique-se de ter instalado a biblioteca Aspose.PDF e configurado seu ambiente de desenvolvimento antes de começar. Também tenha conhecimento básico de programação C#.

## Etapa 1: Configuração do diretório de documentos

No código-fonte fornecido, você precisa especificar o diretório onde deseja salvar o arquivo PDF resultante. Altere a variável "dataDir" para o diretório desejado.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Etapa 2: Instanciando um objeto de documento e adicionando uma página

Criamos uma instância da classe Document e adicionamos uma página a este documento.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Etapa 3: Criando um objeto gráfico e adicionando-o à página

Criamos um objeto Graph com dimensões especificadas e o adicionamos à coleção de parágrafos da página.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 300);
page.Paragraphs.Add(graph);
```

## Etapa 4: Crie um objeto retângulo e adicione ao gráfico

Criamos um objeto Rectangle com dimensões especificadas e o adicionamos à coleção de formas do gráfico.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(0, 0, 300, 300);
graph.Shapes.Add(rect);
```

## Etapa 5: Configurando o preenchimento de gradiente

Configuramos o preenchimento de gradiente para o retângulo usando a classe GradientAxialShading.

```csharp
rect.GraphInfo.FillColor = new Aspose.Pdf.Color
{
PatternColorSpace = new GradientAxialShading(Color.Red, Color.Blue)
{
Start = new Point(0, 0),
End = new Point(300, 300)
}
};
```

Isso cria um preenchimento gradiente do vermelho ao azul, do ponto (0, 0) ao ponto (300, 300).

## Etapa 6: Salvando o arquivo PDF

Por fim, salvamos o arquivo PDF resultante com o nome "AddDrawingWithGradientFill_out.pdf" no diretório especificado.

```csharp
doc.Save(dataDir + "AddDrawingWithGradientFill_out.pdf");
```

### Código-fonte de exemplo para Adicionar desenho com preenchimento de gradiente usando Aspose.PDF para .NET 

```csharp

// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 300);
page.Paragraphs.Add(graph);
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(0, 0, 300, 300);
graph.Shapes.Add(rect);
rect.GraphInfo.FillColor = new Aspose.Pdf.Color
{
	PatternColorSpace = new GradientAxialShading(Color.Red, Color.Blue)
	{
		Start = new Point(0, 0),
		End = new Point(300, 300)
	}
};
doc.Save(dataDir + "AddDrawingWithGradientFill_out.pdf");

```
## Conclusão

Neste tutorial, explicamos passo a passo como adicionar um desenho com preenchimento de gradiente à programação com gráficos usando Aspose.PDF para .NET. Agora você pode usar esse conhecimento para criar documentos PDF atraentes com designs personalizados e preenchimentos de gradiente.

### Perguntas frequentes

#### P: Qual é o propósito deste tutorial?

R: Este tutorial tem como objetivo orientar você no processo de adição de um desenho com preenchimento de gradiente à programação com gráficos usando o Aspose.PDF para .NET.

#### P: Quais são os pré-requisitos necessários antes de começar?

R: Antes de começar, certifique-se de ter instalado a biblioteca Aspose.PDF e configurado seu ambiente de desenvolvimento. Além disso, é recomendado ter um entendimento básico de programação em C#.

#### P: Como especifico o diretório para salvar o arquivo PDF?

R: No código-fonte fornecido, você pode alterar o valor da variável "dataDir" para indicar o diretório onde deseja salvar o arquivo PDF resultante.

#### P: Qual é o propósito do objeto Graph?

A: O objeto Graph serve como um contêiner para os elementos de desenho. Ele é criado com dimensões especificadas e adicionado à coleção de parágrafos da página.

#### P: Como posso configurar o preenchimento de gradiente para uma forma?

R: Para configurar o preenchimento de gradiente, você pode definir a propriedade FillColor do GraphInfo de uma forma usando a classe GradientAxialShading. Isso permite que você defina os pontos inicial e final do gradiente e as cores para transição entre eles.

#### P: Posso personalizar as cores e a direção do preenchimento gradiente?

R: Sim, você pode personalizar as cores e a direção do preenchimento de gradiente ajustando os objetos Color e especificando os pontos inicial e final do GradientAxialShading.

#### P: Qual é a etapa final do tutorial?

R: A etapa final envolve salvar o arquivo PDF resultante com o nome "AddDrawingWithGradientFill_out.pdf" no diretório especificado.

#### P: Existe um código-fonte de exemplo disponível?

R: Sim, o tutorial fornece um código-fonte de exemplo que você pode usar como referência para implementar as etapas descritas.

#### P: Posso aplicar preenchimento de gradiente a outras formas além de retângulos?

R: Sim, você pode aplicar preenchimento de gradiente a outras formas também. O processo envolve configurar a propriedade FillColor do GraphInfo da forma usando a classe GradientAxialShading.