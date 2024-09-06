---
title: Personalize os números de página ao adicionar o TOC
linktitle: Personalize os números de página ao adicionar o TOC
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda a personalizar números de página ao adicionar um Índice aos seus documentos PDF usando o Aspose.PDF para .NET neste tutorial abrangente.
type: docs
weight: 100
url: /pt/net/programming-with-document/customizepagenumbeswhileaddingtoc/
---
## Introdução

No mundo do gerenciamento de documentos, os PDFs reinam supremos. Eles são o formato ideal para compartilhar e preservar documentos em várias plataformas. Mas o que acontece quando você quer aprimorar seus documentos PDF com recursos como um Índice (TOC)? É aí que o Aspose.PDF para .NET entra em cena! Esta biblioteca poderosa permite que os desenvolvedores manipulem arquivos PDF com facilidade, permitindo que eles adicionem, modifiquem e personalizem o conteúdo sem esforço. Neste tutorial, vamos nos aprofundar em como personalizar números de página enquanto adicionamos um TOC aos seus documentos PDF usando o Aspose.PDF para .NET. Então, pegue seu chapéu de codificação e vamos começar!

## Pré-requisitos

Antes de começarmos o código, há algumas coisas que você precisa ter em mente:

1. Visual Studio: Certifique-se de ter o Visual Studio instalado em sua máquina. Este será nosso ambiente de desenvolvimento.
2. Aspose.PDF para .NET: Você precisa baixar e instalar a biblioteca Aspose.PDF. Você pode encontrá-la[aqui](https://releases.aspose.com/pdf/net/).
3. Conhecimento básico de C#: A familiaridade com a programação em C# ajudará você a entender melhor os trechos de código.
4. Um arquivo PDF de amostra: Tenha um arquivo PDF de amostra pronto com o qual podemos trabalhar. Você pode criar um simples ou baixar um PDF existente.

## Pacotes de importação

Para começar, precisamos importar os pacotes necessários. Abra seu projeto do Visual Studio e adicione uma referência à biblioteca Aspose.PDF. Você pode fazer isso usando o NuGet Package Manager:

1. Clique com o botão direito do mouse no seu projeto no Solution Explorer.
2. Selecione "Gerenciar pacotes NuGet".
3. Procure por "Aspose.PDF" e instale-o.

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Depois de instalar a biblioteca, você pode começar a codificar!

## Etapa 1: configure seu diretório de documentos

Primeiro, precisamos configurar nosso diretório de documentos. É aqui que armazenaremos nossos arquivos PDF de entrada e saída. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "42824.pdf";
string outFile = dataDir + "42824_out.pdf";
```

Neste trecho, substitua`YOUR DOCUMENT DIRECTORY` com o caminho real onde seus arquivos PDF estão localizados. Isso nos ajudará a carregar o PDF existente e salvar a versão modificada.

## Etapa 2: Carregue o arquivo PDF existente

Agora que configuramos nosso diretório de documentos, vamos carregar o arquivo PDF existente. 

```csharp
Document doc = new Document(inFile);
```

 Aqui, criamos um novo`Document` objeto passando o caminho do arquivo de entrada. Isso nos permite manipular o conteúdo do PDF programaticamente.

## Etapa 3: Insira uma nova página para o TOC

Em seguida, precisamos criar uma nova página em nosso PDF onde o Índice ficará.

```csharp
Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
```

Esta linha insere uma nova página no início do documento. O TOC será exibido nesta página.

## Etapa 4: Criar informações do TOC

Agora, vamos criar um objeto para representar as informações do TOC.

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocInfo.PageNumbersPrefix = "P";
tocPage.TocInfo = tocInfo;
```

 Nesta etapa, criamos um`TocInfo` objeto e definir seu título como "Índice". Também personalizamos o tamanho e o estilo da fonte. O`PageNumbersPrefix` é definido como "P", que prefixará os números de página no TOC.

## Etapa 5: Adicionar títulos ao TOC

Agora vem a parte divertida! Vamos percorrer as páginas do documento e adicionar títulos ao nosso TOC.

```csharp
for (int i = 1; i < doc.Pages.Count; i++)
{
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);
    heading2.DestinationPage = doc.Pages[i + 1];
    heading2.Top = doc.Pages[i + 1].Rect.Height;
    segment2.Text = "Page " + i.ToString();
    tocPage.Paragraphs.Add(heading2);
}
```

 Neste loop, criamos um novo`Heading` objeto para cada página. Definimos a página de destino para cada título e especificamos o texto a ser exibido, que é "Página X", onde X é o número da página. Por fim, adicionamos o título à página TOC.

## Etapa 6: Salve o documento atualizado

Depois de adicionar todos os títulos necessários, é hora de salvar nosso documento atualizado.

```csharp
doc.Save(outFile);
```

Esta linha salva o PDF modificado com o TOC incluído. Agora você pode abrir o arquivo de saída e ver seu Índice personalizado!

## Conclusão

aí está! Você personalizou com sucesso os números de página ao adicionar um Índice ao seu documento PDF usando o Aspose.PDF para .NET. Esta biblioteca poderosa facilita a manipulação de arquivos PDF e, com apenas algumas linhas de código, você pode aprimorar seus documentos significativamente. Quer você esteja criando relatórios, eBooks ou qualquer outro tipo de PDF, ter um TOC pode melhorar muito a navegação para seus leitores. Então, o que você está esperando? Mergulhe no Aspose.PDF e comece a criar PDFs incríveis hoje mesmo!

## Perguntas frequentes

### O que é Aspose.PDF para .NET?
Aspose.PDF para .NET é uma biblioteca que permite aos desenvolvedores criar, manipular e converter documentos PDF programaticamente.

### Posso usar o Aspose.PDF gratuitamente?
 Sim, o Aspose oferece uma versão de teste gratuita que você pode usar para explorar os recursos da biblioteca. Você pode baixá-la[aqui](https://releases.aspose.com/).

### Como obtenho suporte para o Aspose.PDF?
 Você pode obter suporte visitando o fórum Aspose[aqui](https://forum.aspose.com/c/pdf/10).

### Existe uma licença temporária disponível?
 Sim, você pode solicitar uma licença temporária para Aspose.PDF[aqui](https://purchase.aspose.com/temporary-license/).

### Onde posso comprar o Aspose.PDF para .NET?
 Você pode comprar Aspose.PDF para .NET[aqui](https://purchase.aspose.com/buy).