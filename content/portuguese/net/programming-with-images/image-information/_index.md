---
title: Informações da imagem em arquivo PDF
linktitle: Informações da imagem em arquivo PDF
second_title: Referência da API Aspose.PDF para .NET
description: Extraia informações de imagem em arquivo PDF usando Aspose.PDF para .NET.
type: docs
weight: 160
url: /pt/net/programming-with-images/image-information/
---
Este guia irá guiá-lo passo a passo como extrair informações sobre imagens em arquivo PDF usando Aspose.PDF for .NET. Certifique-se de já ter configurado seu ambiente e siga as etapas abaixo:

## Passo 1: Defina o diretório do documento

 Certifique-se de definir o diretório de documentos correto. Substituir`"YOUR DOCUMENT DIRECTORY"` no código com o caminho para o diretório onde seu documento PDF está localizado.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passo 2: Carregue o arquivo PDF de origem

 Nesta etapa, carregaremos o arquivo PDF de origem usando o`Document` classe de Aspose.PDF. Use o`Document` construtor e passe o caminho para o documento PDF.

```csharp
Document doc = new Document(dataDir + "ImageInformation.pdf");
```

## Etapa 3: definir a resolução padrão

Nesta etapa, definiremos a resolução padrão das imagens. No exemplo, a resolução padrão é definida como 72.

```csharp
int defaultResolution = 72;
```

## Etapa 4: inicializar objetos e contadores

Nesta etapa, inicializaremos os objetos e contadores necessários para recuperar as informações da imagem.

```csharp
System.Collections.Stack graphicsState = new System.Collections.Stack();
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
```

## Etapa 5: percorrer os operadores na primeira página do documento

Nesta etapa, percorreremos os operadores da primeira página do documento para identificar as operações relacionadas à imagem.

```csharp
foreach(Operator op in doc.Pages[1].Contents)
{
```

## Passo 6: Gerenciar operadores e extrair informações da imagem

Nesta etapa iremos gerenciar os diferentes tipos de operadores e extrair as informações sobre as imagens.

```csharp
Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;

//Lidar com operações GSave e GRestore para transformações
if (opSaveState != null)
{
     graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
}
else if (opRestoreState != null)
{
     graphicsState. Pop();
}
// Lidar com a operação ConcatenateMatrix para transformações
else if (opCtm != null)
{
     // Aplicar a matriz de transformação
     System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
        (float)opCtm.Matrix.A,
        (float)opCtm.Matrix.B,
        (float)opCtm.Matrix.C,
        (float)opCtm.Matrix.D,
        (float)opCtm.Matrix.E,
        (float)opCtm.Matrix.F);


     ((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
     keep on going;
}
// Lidar com a operação Do para imagens
else if (opDo != null)
{
     if (imageNames.Contains(opDo.Name))
     {
         // Recuperar a imagem
         XImage image = doc.Pages[1].Resources.Images[opDo.Name];
         // Recuperar as dimensões da imagem
         double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
         double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
         // Calcule a resolução com base nas informações acima
         double resHorizontal = originalWidth * defaultResolution / scaledWidth;
         double resVertical = originalHeight * defaultResolution / scaledHeight;
         // Exibir informações da imagem
         Console.Out.WriteLine(
                 string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
     }
}
```

### Exemplo de código-fonte para informações de imagem usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Carregue o arquivo PDF de origem
Document doc = new Document(dataDir+ "ImageInformation.pdf");
// Defina a resolução padrão da imagem
int defaultResolution = 72;
System.Collections.Stack graphicsState = new System.Collections.Stack();
// Defina o objeto da lista de array que conterá os nomes das imagens
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
// Insira um objeto para empilhar
graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));
// Obtenha todos os operadores na primeira página do documento
foreach (Operator op in doc.Pages[1].Contents)
{
	// Use os operadores GSave/GRestore para reverter as transformações para o valor definido anteriormente
	Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
	Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
	// Instancie o objeto ConcatenateMatrix conforme ele define a matriz de transformação atual.
	Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
	// Operador Create Do que extrai objetos de recursos. Ele desenha objetos Form e objetos Image
	Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;
	if (opSaveState != null)
	{
		//Salve o estado anterior e coloque o estado atual no topo da pilha
		graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
	}
	else if (opRestoreState != null)
	{
		// Jogue fora o estado atual e restaure o anterior
		graphicsState.Pop();
	}
	else if (opCtm != null)
	{
		System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
		   (float)opCtm.Matrix.A,
		   (float)opCtm.Matrix.B,
		   (float)opCtm.Matrix.C,
		   (float)opCtm.Matrix.D,
		   (float)opCtm.Matrix.E,
		   (float)opCtm.Matrix.F);
		// Multiplique a matriz atual pela matriz de estado
		((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
		continue;
	}
	else if (opDo != null)
	{
		// Caso este seja um operador de desenho de imagem
		if (imageNames.Contains(opDo.Name))
		{
			System.Drawing.Drawing2D.Matrix lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
			// Crie o objeto XImage para armazenar imagens da primeira página do PDF
			XImage image = doc.Pages[1].Resources.Images[opDo.Name];
			// Obtenha dimensões da imagem
			double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
			double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
			// Obtenha informações de altura e largura da imagem
			double originalWidth = image.Width;
			double originalHeight = image.Height;
			// Calcular resolução com base nas informações acima
			double resHorizontal = originalWidth * defaultResolution / scaledWidth;
			double resVertical = originalHeight * defaultResolution / scaledHeight;
			// Exibir informações de dimensão e resolução de cada imagem
			Console.Out.WriteLine(
					string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
		}
	}
}
```

## Conclusão

Parabéns! Agora você aprendeu como extrair informações de imagem em um arquivo PDF usando Aspose.PDF for .NET. Você pode usar essas informações para diversas tarefas de processamento de imagens em seus aplicativos.

### Perguntas frequentes sobre informações de imagens em arquivo PDF

#### P: Qual é o propósito de extrair informações de imagem de um documento PDF usando Aspose.PDF for .NET?

R: A extração de informações de imagem de um documento PDF fornece insights sobre as dimensões, resolução e outros atributos das imagens no documento. Essas informações podem ser usadas para tarefas de processamento, análise ou otimização de imagens.

#### P: Como o Aspose.PDF for .NET auxilia na extração de informações de imagem de um documento PDF?

R: Aspose.PDF for .NET fornece ferramentas para acessar e analisar o conteúdo de um documento PDF, incluindo suas imagens. O código fornecido demonstra como extrair e exibir informações de imagem usando vários operadores.

#### P: Que tipo de informação de imagem pode ser extraída usando este método?

R: Este método permite extrair e exibir informações como dimensões em escala, resolução e nomes de imagens em um documento PDF.

#### P: Como o código identifica e processa operadores relacionados a imagens em um documento PDF?

R: O código percorre os operadores em uma página específica do documento PDF. Ele identifica e processa operadores relacionados a operações, transformações e renderização de imagens.

#### P: Qual é o significado da resolução padrão e como ela é usada no código?

R: A resolução padrão é usada como ponto de referência para calcular a resolução real das imagens. O código calcula a resolução de cada imagem com base em suas dimensões e na configuração de resolução padrão.

#### P: Como as informações extraídas da imagem podem ser utilizadas em cenários do mundo real?

R: As informações extraídas da imagem podem ser usadas para tarefas como avaliação da qualidade da imagem, otimização de imagens, geração de miniaturas de imagens e facilitação de processos de tomada de decisão relacionados a imagens.

#### P: Posso modificar o código para extrair atributos adicionais relacionados à imagem?

R: Sim, você pode personalizar o código para extrair atributos adicionais de imagens, como espaço de cores, profundidade de pixels ou tipo de imagem.

#### P: O processo de extração de informações de imagem consome muitos recursos ou é demorado?

R: O processo de extração de informações de imagem é eficiente e otimizado para desempenho, garantindo impacto mínimo no uso de recursos e no tempo de processamento.

#### P: Como os desenvolvedores podem se beneficiar da identificação e extração de informações de imagens de documentos PDF?

R: Os desenvolvedores podem obter informações sobre as características das imagens em documentos PDF, permitindo-lhes tomar decisões informadas sobre manipulação, processamento e otimização de imagens.

#### P: Este método pode ser usado para processamento em lote de documentos PDF contendo imagens?

R: Sim, esse método pode ser estendido para processamento em lote, iterando várias páginas ou documentos, extraindo informações de imagem e executando tarefas relacionadas a imagens.