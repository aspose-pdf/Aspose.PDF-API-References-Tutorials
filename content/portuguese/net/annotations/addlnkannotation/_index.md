---
title: Adicionar anotação lnk
linktitle: Adicionar anotação lnk
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como adicionar o recurso Ink Annotation a documentos PDF em C# usando Aspose.PDF for .NET com guia passo a passo e código-fonte completo.
type: docs
weight: 20
url: /pt/net/annotations/addlnkannotation/
---
Aspose.PDF for .NET é uma biblioteca poderosa que permite aos desenvolvedores realizar várias operações em PDF. Uma dessas operações é adicionar anotações em tinta a documentos PDF. Neste artigo, forneceremos um guia passo a passo para explicar o código-fonte C# para adicionar anotação de tinta usando Aspose.PDF para .NET. Vamos começar!

## Compreendendo o recurso de anotação de tinta do Aspose.PDF para .NET

Antes de mergulhar no código-fonte C#, vamos primeiro entender o que é Ink Annotation e seus usos.

Anotação a tinta é uma forma de desenhar anotações a tinta de forma livre em documentos PDF. Ele permite que você crie anotações com uma caneta ou mouse. Este recurso é útil em situações onde você precisa desenhar diagramas, esboços ou outros tipos de anotações.

## Etapa 1: Criando um Novo Documento

A primeira etapa para adicionar anotação de tinta a um documento PDF é criar uma nova instância da classe Documento. Isso é conseguido usando o seguinte trecho de código:

```csharp
string dataDir = "YOUR DATA DIRECTORY";
Document doc = new Document();
Page pdfPage = doc.Pages.Add();
```

Aqui, criamos uma nova instância da classe Document e adicionamos uma nova página a ela.

## Etapa 2: Criando anotação de tinta

A próxima etapa é criar uma instância da classe InkAnnotation. Isso é feito usando o seguinte trecho de código:

```csharp
System.Drawing.Rectangle drect = new System.Drawing.Rectangle();
drect.Height = (int)pdfPage.Rect.Height;
drect.Width = (int)pdfPage.Rect.Width;
drect.X = 0;
drect.Y = 0;
Aspose.Pdf.Rectangle arect = Aspose.Pdf.Rectangle.FromRect(drect);
IList<Point[]> inkList = new List<Point[]>();
Aspose.Pdf.Point[] arrpt = new Aspose.Pdf.Point[3];
inkList.Add(arrpt);
arrpt[0] = new Aspose.Pdf.Point(100, 800);
arrpt[1] = new Aspose.Pdf.Point(200, 800);
arrpt[2] = new Aspose.Pdf.Point(200, 700);
InkAnnotation ia = new InkAnnotation(pdfPage, arect, inkList);
ia.Title = "XXX";
ia.Color = Aspose.Pdf.Color.LightBlue; // (GetColorFromString(stroke.InkColor));
ia.CapStyle = CapStyle.Rounded;
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
pdfPage.Annotations.Add(ia);
```

Aqui, primeiro criamos um retângulo usando a classe System.Drawing.Rectangle e o convertemos em Aspose.Pdf.Rectangle usando o método FromRect. Em seguida, criamos uma instância da classe InkAnnotation usando o retângulo, uma lista de pontos e a página onde a anotação é adicionada.

Em seguida, definimos várias propriedades do InkAnnotation, como título, cor, estilo de tampa, borda e opacidade. Finalmente, adicionamos a anotação à página usando o método Annotations.Add.

## Etapa 3: salvando o documento

A etapa final é salvar o documento PDF com a anotação de tinta adicionada. Isso é conseguido usando o seguinte trecho de código:

```csharp
dataDir = dataDir + "AddlnkAnnotation_out.pdf";
doc.Save(dataDir);
```

Aqui, concatenamos o nome do arquivo de saída ao diretório de dados e salvamos o documento usando o método Save.

### Exemplo de código-fonte para adicionar anotação de tinta usando Aspose.PDF para .NET

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DATA DIRECTORY";


Document doc = new Document();
Page pdfPage = doc.Pages.Add();
System.Drawing.Rectangle drect = new System.Drawing.Rectangle();
drect.Height = (int)pdfPage.Rect.Height;
drect.Width = (int)pdfPage.Rect.Width;
drect.X = 0;
drect.Y = 0;
Aspose.Pdf.Rectangle arect = Aspose.Pdf.Rectangle.FromRect(drect);
IList<Point[]> inkList = new List<Point[]>();
Aspose.Pdf.Point[] arrpt = new Aspose.Pdf.Point[3];
inkList.Add(arrpt);
arrpt[0] = new Aspose.Pdf.Point(100, 800);
arrpt[1] = new Aspose.Pdf.Point(200, 800);
arrpt[2] = new Aspose.Pdf.Point(200, 700);
InkAnnotation ia = new InkAnnotation(pdfPage, arect, inkList);
ia.Title = "XXX";
ia.Color = Aspose.Pdf.Color.LightBlue; // (GetColorFromString(stroke.InkColor));
ia.CapStyle = CapStyle.Rounded;
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
pdfPage.Annotations.Add(ia);

dataDir = dataDir + "AddlnkAnnotation_out.pdf";
// Salvar arquivo de saída
doc.Save(dataDir);
```

## Conclusão

Neste tutorial, exploramos como adicionar anotações a tinta a um documento PDF usando Aspose.PDF para .NET. Seguindo o guia passo a passo e o código-fonte C# fornecido, os desenvolvedores podem implementar facilmente a funcionalidade Ink Annotation em seus aplicativos de processamento de PDF.

### Perguntas frequentes

#### P: O que é uma anotação a tinta em um documento PDF?

R: Uma anotação a tinta em um documento PDF permite que os usuários desenhem anotações a tinta de forma livre usando uma caneta ou mouse. É comumente usado para adicionar esboços desenhados à mão, diagramas ou outras anotações à mão livre a um PDF.

#### P: Posso personalizar a aparência da anotação de tinta?

R: Sim, o Aspose.PDF for .NET fornece várias propriedades para personalizar a aparência da anotação de tinta, como cor, opacidade, estilo de tampa, largura da borda e muito mais. Os desenvolvedores podem ajustar essas propriedades para atender aos seus requisitos específicos.

#### P: É possível adicionar várias anotações em tinta a uma única página PDF?

R: Sim, você pode adicionar várias anotações de tinta a uma única página PDF usando Aspose.PDF for .NET. Cada anotação de tinta pode ter seu próprio conjunto de pontos e aparência personalizada.

#### P: Posso adicionar anotações em tinta a documentos PDF existentes?

R: Sim, o Aspose.PDF for .NET permite adicionar anotações de tinta a documentos PDF recém-criados e a arquivos PDF existentes. Você pode abrir um PDF existente, adicionar anotações à tinta e salvar o documento atualizado.

#### P: Quais são alguns casos de uso comuns para anotações em tinta em documentos PDF?

R: As anotações em tinta são úteis para uma ampla variedade de aplicações, incluindo adição de assinaturas ou notas manuscritas a formulários PDF, anotação de plantas arquitetônicas ou desenhos de engenharia e marcação de documentos para revisão colaborativa.