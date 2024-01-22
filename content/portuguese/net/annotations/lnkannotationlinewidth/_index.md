---
title: Largura da linha de anotação lnk
linktitle: Largura da linha de anotação lnk
second_title: Referência da API Aspose.PDF para .NET
description: Este artigo fornece um guia passo a passo para definir a largura da linha da anotação lnk usando Aspose.PDF para .NET.
type: docs
weight: 110
url: /pt/net/annotations/lnkannotationlinewidth/
---
Aspose.PDF é uma ferramenta poderosa e amplamente utilizada para trabalhar com arquivos PDF em aplicativos .NET. Ele fornece uma variedade de recursos para criar, editar e manipular arquivos PDF, incluindo a capacidade de adicionar anotações às páginas. Neste tutorial, explicaremos como definir a largura da linha de uma anotação de link usando Aspose.PDF para .NET.

Depois de ter esses pré-requisitos, crie um novo projeto de aplicativo de console no Visual Studio. Em seguida, adicione uma referência à biblioteca Aspose.PDF para .NET clicando com o botão direito do mouse no projeto no Solution Explorer, selecionando "Gerenciar pacotes NuGet" e pesquisando "Aspose.PDF" no Gerenciador de pacotes NuGet.

Para adicionar uma anotação lnk a um documento PDF, siga estas etapas:

##  Passo 1: Crie um novo`Document` object.
```csharp
Document doc = new Document();
```
## Passo 2: Adicione uma nova página ao documento.
```csharp
doc.Pages.Add();
```
##  Passo 3: Crie uma lista de`Point` arrays that represent the ink gesture for the annotation.
```csharp
IList<Point[]> inkList = new List<Point[]>();
```
##  Passo 4: Crie um novo`LineInfo` object that defines the properties of the ink gesture.
```csharp
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = System.Drawing.Color.Red;
lineInfo.LineWidth = 2;
```
##  Passo 5: Crie um novo`Aspose.Pdf.Point` array that represents the gesture from the `LineInfo` object.
```csharp
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
    gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}
```
## Etapa 6: adicione o gesto à lista de gestos de tinta.
```csharp
inkList.Add(gesture);
```
##  Passo 7: Crie um novo`InkAnnotation` object that represents the link annotation.
```csharp
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
```
## Passo 8: Defina o assunto e o título da anotação.
```csharp
a1.Subject = "Test";
a1.Title = "Title";
```
## Etapa 9: Defina a cor da anotação.
```csharp
a1.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
```
##  Passo 10: Crie um novo`Border` object that defines the properties of the annotation's border.
```csharp
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
```
## Etapa 11: adicione a anotação à página.
```csharp
doc.Pages[1].Annotations.Add(a1);
```
## Etapa 12: Salve o documento em um arquivo.
```csharp
// Salvar arquivo de saída
doc.Save(dataDir);


```
### O exemplo mostra a largura da linha de anotação lnk com Aspose.PDF para .NET

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
IList<Point[]> inkList = new List<Point[]>();
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = System.Drawing.Color.Red;
lineInfo.LineWidth = 2;
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}

inkList.Add(gesture);
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
a1.Subject = "Test";
a1.Title = "Title";
a1.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
doc.Pages[1].Annotations.Add(a1);

dataDir = dataDir + "lnkAnnotationLineWidth_out.pdf";
// Salvar arquivo de saída
doc.Save(dataDir);
```

## Conclusão

Neste tutorial, aprendemos como definir a largura da linha de uma anotação de link em um documento PDF usando Aspose.PDF for .NET. Aspose.PDF for .NET oferece uma ampla gama de ferramentas e recursos para trabalhar com documentos PDF, incluindo a capacidade de criar e personalizar anotações de link. Seguindo o guia passo a passo e usando o código-fonte C# fornecido, os desenvolvedores podem facilmente adicionar links interativos aos seus documentos PDF, melhorando a experiência do usuário e a interatividade de seus aplicativos. Aspose.PDF for .NET é uma biblioteca versátil que permite aos desenvolvedores .NET trabalhar com arquivos PDF de maneira eficiente e eficaz.

### Perguntas frequentes

#### P: O que é uma anotação de link em um documento PDF?

R: Uma anotação de link em um documento PDF é um elemento interativo que permite criar hiperlinks ou ações que direcionam o usuário para outro local no mesmo documento, um site externo ou um documento PDF diferente.

#### P: Como posso definir a largura da linha de uma anotação de link usando Aspose.PDF for .NET?

R: Para definir a largura da linha de uma anotação de link usando Aspose.PDF for .NET, você pode criar um`InkAnnotation` objeto e especifique a propriedade de largura da linha.

#### P: Quais propriedades podem ser personalizadas para uma anotação de link no Aspose.PDF for .NET?

R: Você pode personalizar várias propriedades de uma anotação de link no Aspose.PDF for .NET, como localização, tamanho, cor, propriedades de borda (largura, estilo, padrão de traço e efeito), assunto, título e visibilidade.

#### P: Posso criar uma anotação de link que contenha vários gestos de tinta digital?

 R: Sim, você pode criar uma anotação de link que contenha vários gestos de tinta adicionando vários`Point` matrizes para o`InkAnnotation` objeto.

#### P: Como posso adicionar uma anotação de link a uma página específica do documento PDF?

 R: Para adicionar uma anotação de link a uma página específica do documento PDF, você precisa especificar o número da página ao criar o`InkAnnotation` objeto. Por exemplo,`new InkAnnotation(doc.Pages[1], ...)` adiciona a anotação do link à primeira página.