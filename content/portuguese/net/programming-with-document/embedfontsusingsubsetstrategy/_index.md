---
title: Incorporar fontes em arquivo PDF com estratégia de subconjunto
linktitle: Incorporar fontes com estratégia de subconjunto
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como incorporar fontes em um arquivo PDF com Estratégia de Subconjunto usando Aspose.PDF para .NET. Otimize o tamanho do seu PDF incorporando apenas os caracteres necessários.
type: docs
weight: 130
url: /pt/net/programming-with-document/embedfontsusingsubsetstrategy/
---
Neste tutorial, discutiremos como incorporar fontes em um arquivo PDF com uma estratégia de subconjunto usando Aspose.PDF for .NET. Aspose.PDF for .NET é uma biblioteca poderosa que permite aos desenvolvedores criar, editar e manipular documentos PDF de forma programática. Incorporar fontes em um arquivo PDF é uma etapa importante para garantir que o documento seja exibido corretamente em diferentes dispositivos, independentemente de as fontes necessárias estarem instaladas nesses dispositivos ou não.

## Etapa 1: criar um novo aplicativo de console C#
Para começar, crie um novo aplicativo de console C# no Visual Studio. Você pode nomeá-lo como quiser. Depois que o projeto for criado, você precisará adicionar uma referência à biblioteca Aspose.PDF for .NET.

## Etapa 2: importar o namespace Aspose.PDF
Adicione a seguinte linha de código na parte superior do seu arquivo C# para importar o namespace Aspose.PDF:

```csharp
using Aspose.Pdf;
```

## Etapa 3: carregar um arquivo PDF existente
Para incorporar fontes em um arquivo PDF existente, você precisa carregar esse arquivo usando a classe Document. O código a seguir demonstra como carregar um arquivo PDF existente:

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Carregar um arquivo PDF existente
Document doc = new Document(dataDir + "input.pdf");
```

## Etapa 4: incorporar fontes com estratégia de subconjunto
Aspose.PDF for .NET fornece duas estratégias para incorporação de fontes: SubsetAllFonts e SubsetEmbeddedFontsOnly.

A estratégia SubsetAllFonts incorporará todas as fontes no documento como um subconjunto. Um subconjunto é uma parte da fonte que contém apenas os caracteres usados no documento. Esta estratégia é útil para reduzir o tamanho do arquivo do documento PDF.

estratégia SubsetEmbeddedFontsOnly incorporará apenas o subconjunto de fontes que já estão incorporadas no documento. Se uma fonte não estiver incorporada, ela não será afetada por esta estratégia.

O código a seguir demonstra como incorporar fontes em um arquivo PDF com uma estratégia de subconjunto:

```csharp
// Todas as fontes serão incorporadas como subconjunto no documento no caso de SubsetAllFonts.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetAllFonts);

// O subconjunto de fontes será incorporado para fontes totalmente incorporadas, mas as fontes que não estão incorporadas ao documento não serão afetadas.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetEmbeddedFontsOnly);
```

## Etapa 5: salve o documento PDF
Depois de incorporar todas as fontes no arquivo PDF com uma estratégia de subconjunto, você precisa salvar o documento. O código a seguir demonstra como salvar o arquivo PDF:

```csharp
doc.Save(dataDir + "Output_out.pdf");
```

### Exemplo de código-fonte para incorporar fontes com estratégia de subconjunto usando Aspose.PDF para .NET. 

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
// Todas as fontes serão incorporadas como subconjunto no documento no caso de SubsetAllFonts.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetAllFonts);
// O subconjunto de fontes será incorporado para fontes totalmente incorporadas, mas as fontes que não estão incorporadas ao documento não serão afetadas.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetEmbeddedFontsOnly);
doc.Save(dataDir + "Output_out.pdf");
```

## Conclusão
Neste artigo, discutimos como incorporar fontes em um arquivo PDF com uma estratégia de subconjunto usando Aspose.PDF para .NET. Aspose.PDF for .NET fornece uma API simples e fácil de usar para trabalhar com documentos PDF, incluindo adição e incorporação de fontes com diferentes estratégias. Incorporar fontes em um arquivo PDF é uma etapa importante para garantir que o documento seja exibido corretamente em diferentes dispositivos, e a estratégia de subconjunto é um recurso útil para reduzir o tamanho do arquivo do documento PDF.

### Perguntas frequentes sobre fontes incorporadas em arquivos PDF com estratégia de subconjunto

#### P: Qual é uma estratégia de subconjunto para incorporação de fontes em um arquivo PDF?

R: Uma estratégia de subconjunto para incorporação de fontes em um arquivo PDF significa que apenas uma parte da fonte que contém os caracteres usados no documento será incorporada. Isso ajuda a reduzir o tamanho do arquivo do documento PDF, eliminando dados de fonte desnecessários.

#### P: Qual é a diferença entre as estratégias SubsetAllFonts e SubsetEmbeddedFontsOnly?

 R: O`SubsetAllFonts`estratégia irá incorporar todas as fontes no documento como um subconjunto, enquanto o`SubsetEmbeddedFontsOnly` A estratégia incorporará apenas o subconjunto de fontes que já estão incorporadas no documento. A última estratégia não afetará as fontes que ainda não estejam incorporadas.

#### P: Por que a incorporação de fontes com uma estratégia de subconjunto é importante?

R: A incorporação de fontes com uma estratégia de subconjunto é importante para garantir que o arquivo PDF contenha os dados de fonte necessários para a exibição correta do texto, ao mesmo tempo que mantém o tamanho do arquivo menor, incluindo apenas os caracteres usados no documento.

#### P: Posso usar Aspose.PDF for .NET para incorporar fontes com estratégias diferentes?

 R: Sim, Aspose.PDF for .NET fornece várias estratégias para incorporação de fontes, incluindo`SubsetAllFonts` e`SubsetEmbeddedFontsOnly`. Você pode escolher a estratégia apropriada com base em suas necessidades.

#### P: Aspose.PDF for .NET é uma biblioteca confiável para trabalhar com documentos PDF?

R: Sim, Aspose.PDF for .NET é uma biblioteca confiável e poderosa para trabalhar com documentos PDF. Ele fornece recursos abrangentes para criar, editar e manipular arquivos PDF em aplicativos .NET.