---
title: Largura da linha de anotação lnk
linktitle: Largura da linha de anotação lnk
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda como definir a largura da linha de anotação de tinta em um PDF usando o Aspose.PDF para .NET. Este tutorial detalhado o guia por cada etapa, garantindo uma saída de alta qualidade.
type: docs
weight: 110
url: /pt/net/annotations/lnkannotationlinewidth/
---
## Introdução

Ao trabalhar com documentos PDF, adicionar anotações pode ser uma maneira poderosa de destacar informações ou adicionar elementos interativos aos seus arquivos. Uma dessas anotações é a Ink Annotation, que permite desenhar linhas de forma livre no seu PDF. Mas e se você precisar personalizar a aparência dessas linhas, particularmente a largura da linha? Neste tutorial, vamos orientá-lo no processo de configuração da largura da linha de anotação de tinta usando o Aspose.PDF para .NET.

## Pré-requisitos

Antes de mergulhar no código, vamos garantir que você tenha tudo configurado para seguir este tutorial sem problemas:

1.  Aspose.PDF para .NET: Certifique-se de ter a biblioteca Aspose.PDF para .NET instalada. Você pode baixá-la do[página de download](https://releases.aspose.com/pdf/net/) ou instale-o por meio do Gerenciador de Pacotes NuGet no Visual Studio.
2. Ambiente de desenvolvimento: Este tutorial pressupõe que você esteja trabalhando em um ambiente de desenvolvimento .NET, como o Visual Studio.
3. Conhecimento básico de C#: uma compreensão básica de C# ajudará você a acompanhar as etapas de codificação.
4. Documento PDF: use um documento PDF existente ou crie um novo para este tutorial.

## Importando namespaces necessários

Antes de começar a codificar, certifique-se de importar os namespaces necessários no seu projeto:

```csharp
using System.IO;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using System;
using System.Collections;
using System.Collections.Generic;
```

Esses namespaces fornecem as classes e os métodos necessários para manipular documentos PDF, trabalhar com anotações e manipular elementos gráficos.

Agora que definimos nossos pré-requisitos, vamos dividir o processo de definição da largura da linha de anotação de tinta em etapas claras e gerenciáveis.

## Etapa 1: inicializar o documento PDF

Primeiro, precisamos criar ou abrir um documento PDF. Para este tutorial, criaremos um novo documento PDF do zero.

```csharp
// Inicializar o documento PDF
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Especifique seu diretório de documentos
Document doc = new Document();
doc.Pages.Add(); // Adicionar uma página em branco ao documento
```

 Aqui, estamos inicializando um novo`Document` objeto, que representa nosso arquivo PDF. Então, adicionamos uma página em branco a esse documento para trabalhar.

## Etapa 2: Crie a anotação de tinta

Em seguida, criaremos a anotação de tinta em si. Isso envolve definir os pontos que compõem os traços de tinta.

```csharp
// Crie a anotação de tinta
IList<Point[]> inkList = new List<Point[]>();
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = Color.Red;
lineInfo.LineWidth = 2;
```

 Nesta etapa, definimos o`LineInfo` objeto, que contém as coordenadas dos traços de tinta, sua visibilidade, cor e largura inicial da linha. O`VerticeCoordinate` array contém as coordenadas X e Y de cada ponto no traço.

## Etapa 3: converter coordenadas em pontos

Agora, precisamos converter essas coordenadas em pontos que podem ser usados pela Anotação de Tinta.

```csharp
// Converter coordenadas em pontos
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
    gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}

inkList.Add(gesture);
```

 Este loop processa a matriz de coordenadas, convertendo cada par de coordenadas em um`Point` objeto, que é então adicionado ao nosso`inkList`.

## Etapa 4: adicione a anotação de tinta à página PDF

Com os pontos prontos, agora podemos criar a anotação de tinta e adicioná-la à página PDF.

```csharp
// Adicione a anotação de tinta à página PDF
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
a1.Subject = "Test";
a1.Title = "Title";
a1.Color = Aspose.Pdf.Color.FromRgb(Color.Green);
```

 Nesta etapa, inicializamos um`InkAnnotation`objeto, especificando a página, um retângulo delimitador e nossa lista de pontos. Também definimos o assunto, o título e a cor da anotação.

## Etapa 5: Personalize a borda da anotação

Para personalizar ainda mais a aparência da nossa anotação, modificaremos suas propriedades de borda.

```csharp
// Personalize a borda da anotação
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
doc.Pages[1].Annotations.Add(a1);
```

 Aqui, criamos um`Border` objeto para nossa anotação, definindo sua largura, efeito, padrão de traço e estilo. Esta etapa garante que a anotação se destaque visualmente na página PDF.

## Etapa 6: Salve o documento PDF

Por fim, depois de fazer todas as alterações necessárias, é hora de salvar o documento.

```csharp
// Salvar o documento PDF
dataDir = dataDir + "lnkAnnotationLineWidth_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nInk annotation line width setup successfully.\nFile saved at " + dataDir);
```

 Este código salva o documento PDF modificado com a anotação de tinta no diretório especificado. O`Console.WriteLine` declaração confirma a execução bem-sucedida do código.

## Conclusão

Parabéns! Você criou e personalizou com sucesso uma anotação de tinta em um documento PDF usando o Aspose.PDF para .NET. Este tutorial cobriu todo o processo, desde a inicialização do documento até salvar o arquivo final. Com esse conhecimento, você pode explorar ainda mais os vastos recursos do Aspose.PDF para .NET e aplicar técnicas semelhantes a outros tipos de anotações ou manipulações de PDF.

## Perguntas frequentes

### Posso usar cores diferentes para diferentes partes da anotação de tinta?  
 Sim, você pode criar vários`InkAnnotation` objetos com cores diferentes e adicioná-los à mesma página ou a páginas diferentes do seu PDF.

### Como altero a largura da linha dinamicamente?  
 Você pode ajustar o`LineWidth` propriedade do`LineInfo` objeto antes de converter as coordenadas em pontos.

### É possível tornar a anotação de tinta transparente?  
 Sim, você pode modificar o`Opacity` propriedade do`InkAnnotation` objeto para torná-lo transparente.

### Posso adicionar várias anotações de tinta na mesma página?  
Claro! Você pode adicionar quantas anotações de tinta quiser a uma única página repetindo o processo.

### Como faço para remover uma anotação de tinta de um PDF?  
 Você pode remover uma anotação usando o`doc.Pages[1].Annotations.Delete(a1)` método, onde`a1` é seu objeto de anotação.