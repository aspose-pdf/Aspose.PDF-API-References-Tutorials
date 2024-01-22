---
title: Adicionar desenho com preenchimento gradiente
linktitle: Adicionar desenho com preenchimento gradiente
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como adicionar um desenho com preenchimento gradiente com Aspose.PDF para .NET. Tutorial passo a passo para criar documentos PDF atraentes.
type: docs
weight: 20
url: /pt/net/programming-with-graphs/add-drawing-with-gradient-fill/
---
Neste tutorial, orientaremos você passo a passo no seguinte código-fonte C# para adicionar um desenho com preenchimento gradiente à programação com gráficos usando Aspose.PDF para .NET.

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
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 300);
page.Paragraphs.Add(graph);
```

## Etapa 4: criar objeto retângulo e adicionar ao gráfico

Criamos um objeto Rectangle com dimensões especificadas e o adicionamos à coleção de formas do gráfico.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(0, 0, 300, 300);
graph.Shapes.Add(rect);
```

## Etapa 5: configurar o preenchimento gradiente

Configuramos o preenchimento gradiente para o retângulo usando a classe GradientAxialShading.

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

Isso cria um preenchimento gradiente de vermelho para azul, do ponto (0, 0) ao ponto (300, 300).

## Passo 6: Salvando o arquivo PDF

Finalmente, salvamos o arquivo PDF resultante com o nome "AddDrawingWithGradientFill_out.pdf" no diretório especificado.

```csharp
doc.Save(dataDir + "AddDrawingWithGradientFill_out.pdf");
```

### Exemplo de código-fonte para Adicionar desenho com preenchimento gradiente usando Aspose.PDF para .NET 

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

Neste tutorial, explicamos passo a passo como adicionar um desenho com preenchimento gradiente à programação com gráficos usando Aspose.PDF for .NET. Agora você pode usar esse conhecimento para criar documentos PDF atraentes com designs personalizados e preenchimentos gradientes.

### Perguntas frequentes

#### P: Qual é o objetivo deste tutorial?

R: Este tutorial tem como objetivo guiá-lo através do processo de adição de um desenho com preenchimento gradiente à programação com gráficos usando Aspose.PDF for .NET.

#### P: Quais pré-requisitos são necessários antes de começar?

R: Antes de começar, certifique-se de ter instalado a biblioteca Aspose.PDF e configurado seu ambiente de desenvolvimento. Além disso, é recomendável ter um conhecimento básico de programação C#.

#### P: Como especifico o diretório para salvar o arquivo PDF?

R: No código-fonte fornecido, você pode alterar o valor da variável "dataDir" para indicar o diretório onde deseja salvar o arquivo PDF resultante.

#### P: Qual é o propósito do objeto Graph?

R: O objeto Graph serve como contêiner para os elementos do desenho. Ele é criado com dimensões especificadas e adicionado à coleção de parágrafos da página.

#### P: Como posso configurar o preenchimento gradiente para uma forma?

R: Para configurar o preenchimento gradiente, você pode definir a propriedade FillColor do GraphInfo de uma forma usando a classe GradientAxialShading. Isso permite definir os pontos inicial e final do gradiente e as cores de transição entre eles.

#### P: Posso personalizar as cores e a direção do preenchimento gradiente?

R: Sim, você pode personalizar as cores e a direção do preenchimento gradiente ajustando os objetos Color e especificando os pontos inicial e final do GradientAxialShading.

#### P: Qual é a etapa final do tutorial?

R: A etapa final envolve salvar o arquivo PDF resultante com o nome "AddDrawingWithGradientFill_out.pdf" no diretório especificado.

#### P: Existe um exemplo de código-fonte disponível?

R: Sim, o tutorial fornece um exemplo de código-fonte que você pode usar como referência para implementar as etapas descritas.

#### P: Posso aplicar preenchimento gradiente a outras formas além de retângulos?

R: Sim, você também pode aplicar preenchimento gradiente a outras formas. O processo envolve a configuração da propriedade FillColor do GraphInfo da forma usando a classe GradientAxialShading.