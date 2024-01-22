---
title: Definir propriedade de texto explicativo em arquivo PDF
linktitle: Definir propriedade de texto explicativo em arquivo PDF
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como definir a propriedade do texto explicativo em um arquivo PDF usando Aspose.PDF para .NET. Personalize anotações com linhas de texto explicativo, cor do texto e estilos finais.
type: docs
weight: 130
url: /pt/net/annotations/setcalloutproperty/
---
 Aspose.PDF for .NET é uma biblioteca poderosa para criar, manipular e converter documentos PDF em C#. Um dos recursos fornecidos por esta biblioteca é a capacidade de definir propriedades de texto explicativo para anotações de texto livre em documentos PDF. Isto pode ser feito usando o`FreeTextAnnotation` class, que permite criar anotações com textos explicativos.

Neste tutorial, iremos guiá-lo através do processo de configuração de propriedades de texto explicativo para uma anotação de texto livre usando Aspose.PDF para .NET em C#. Siga as etapas abaixo para começar.

## Instale Aspose.PDF para .NET

 Se ainda não o fez, você precisará[download](https://releases.aspose.com/pdf/net/) e instale o Aspose.PDF para .NET a partir dos lançamentos do Aspose ou por meio do gerenciador de pacotes NuGet.

## Passo 1: Crie um novo documento PDF

 Crie um novo documento PDF usando o`Document`classe fornecida por Aspose.PDF para .NET.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Etapa 2: adicione uma nova página ao documento

 Adicione uma nova página ao documento usando o`Pages` coleção do`Document` aula.

```csharp
Page page = doc.Pages.Add();
```

## Etapa 3: definir a aparência padrão

 Defina a aparência padrão da anotação de texto livre criando um novo`DefaultAppearance` objeto e definindo suas propriedades, como`TextColor` e`FontSize`.

```csharp
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
```

## Etapa 4: crie uma anotação de texto livre com texto explicativo

 Crie uma nova anotação de texto livre com texto explicativo usando o`FreeTextAnnotation` aula. Colocou o`Intent` propriedade para`FreeTextIntent.FreeTextCallout` para especificar que esta é uma anotação de texto explicativo. Colocou o`EndingStyle` propriedade para`LineEnding.OpenArrow` para especificar o estilo da seta no final da chamada. Colocou o`Callout` propriedade para uma matriz de`Point` objetos que representam os pontos na página onde a linha de texto explicativo deve ser desenhada.

```csharp
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
fta.Callout = new Point[]
{
    new Point(428.25,651.75), new Point(462.75,681.375), new Point(474,681.375)
};
```

## Etapa 5: adicione a anotação de texto livre à página

 Adicione a anotação de texto livre à página usando o`Annotations` coleção do`Page` aula.

```csharp
page.Annotations.Add(fta);
```

## Etapa 6: adicione texto à anotação

 Adicione texto à anotação definindo o`RichText`propriedade para uma string de XML formatado. Neste tutorial, estamos definindo a cor do texto como vermelho e o tamanho da fonte como 9.

```csharp
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"cor:#FF
```

## Etapa 7: salve o documento

Agora salve o documento usando o seguinte código:

```csharp
doc.Save(dataDir + "SetCalloutProperty.pdf")
```

### Exemplo de código-fonte para definir propriedade de texto explicativo usando Aspose.PDF para .NET

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
Page page = doc.Pages.Add();
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
fta.Callout = new Point[]
{
	new Point(428.25,651.75), new Point(462.75,681.375), new Point(474,681.375)
};
page.Annotations.Add(fta);
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"color:#FF0000;font-weight:normal;font-style:normal;font-stretch:normal\"><p dir=\"ltr\"> <span style=\"font-size:9.0pt;font-family:Helvetica\">Este é um exemplo</span></p></body>";
doc.Save(dataDir + "SetCalloutProperty.pdf");
```

## Conclusão

Neste tutorial, exploramos como definir propriedades de texto explicativo para uma anotação de texto livre em um documento PDF usando Aspose.PDF for .NET. As anotações de texto explicativo são úteis para fornecer informações ou explicações adicionais relacionadas a áreas específicas de um documento. Aspose.PDF for .NET oferece uma ampla gama de recursos e capacidades para trabalhar com arquivos PDF, incluindo a criação e personalização de anotações, como textos explicativos. Seguindo o guia passo a passo e usando o código-fonte C# fornecido, os desenvolvedores podem implementar facilmente anotações de texto explicativo em seus documentos PDF, melhorando a usabilidade e a clareza de seus documentos. Aspose.PDF for .NET é uma biblioteca versátil e confiável para operações de PDF em aplicativos .NET, oferecendo ferramentas poderosas para lidar com várias tarefas relacionadas a PDF com eficiência.

### Perguntas frequentes sobre como definir propriedades de texto explicativo em arquivo PDF

#### P: O que é uma anotação de texto explicativo em um documento PDF?

R: Uma anotação de texto explicativo em um documento PDF é um tipo de anotação que permite criar uma caixa de texto com uma linha líder apontando para uma área específica do documento. É comumente usado para fornecer informações adicionais ou comentários relacionados a uma seção ou elemento específico do documento.

#### P: Posso personalizar a aparência da anotação de texto explicativo usando Aspose.PDF for .NET?

R: Sim, você pode personalizar várias propriedades da anotação de texto explicativo, como cor, tamanho da fonte, alinhamento do texto, estilo de linha, estilo de seta e muito mais.

#### P: Como adiciono texto à anotação da frase de destaque?

 R: Para adicionar texto à anotação de texto explicativo, você pode definir o`RichText` propriedade do`FreeTextAnnotation` objeto. O`RichText` propriedade usa uma string de XML formatado que representa o texto a ser exibido na anotação de texto explicativo.

#### P: Posso adicionar várias anotações de texto explicativo a um documento PDF usando Aspose.PDF for .NET?

 R: Sim, você pode criar diversas anotações de texto explicativo em um documento PDF criando diversas instâncias do`FreeTextAnnotation`objeto e adicioná-los a diferentes páginas ou locais no documento.