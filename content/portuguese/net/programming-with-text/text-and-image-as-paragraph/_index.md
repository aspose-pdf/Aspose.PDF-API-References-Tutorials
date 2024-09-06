---
title: Texto e imagem como parágrafo em arquivo PDF
linktitle: Texto e imagem como parágrafo em arquivo PDF
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda a adicionar texto e uma imagem como parágrafos embutidos em um arquivo PDF usando o Aspose.PDF para .NET.
type: docs
weight: 530
url: /pt/net/programming-with-text/text-and-image-as-paragraph/
---
Este tutorial explica como adicionar texto e uma imagem como parágrafos inline em um arquivo PDF usando Aspose.PDF para .NET. O código-fonte C# fornecido demonstra o processo passo a passo.

## Pré-requisitos

Antes de prosseguir com o tutorial, certifique-se de ter o seguinte:

- Conhecimento básico da linguagem de programação C#.
- Biblioteca Aspose.PDF para .NET instalada. Você pode obtê-la no site da Aspose ou usar o NuGet para instalá-la no seu projeto.

## Etapa 1: Configurar o projeto

Comece criando um novo projeto C# no seu ambiente de desenvolvimento integrado (IDE) preferido e adicione uma referência à biblioteca Aspose.PDF para .NET.

## Etapa 2: Importar os namespaces necessários

Adicione as seguintes diretivas using no início do seu arquivo C# para importar os namespaces necessários:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Drawing;
```

## Etapa 3: Defina o caminho para o diretório do documento

 Defina o caminho para o diretório do seu documento usando o`dataDir` variável:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório do seu documento.

## Etapa 4: Crie um novo documento e página

 Criar um novo`Document` objeto e adicione uma página à sua coleção de páginas:

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Etapa 5: crie um TextFragment e adicione-o como um parágrafo

 Criar um`TextFragment` objeto e adicione-o à coleção de parágrafos da página:

```csharp
TextFragment text = new TextFragment("Hello World.. ");
page.Paragraphs.Add(text);
```

## Etapa 6: adicione uma imagem como um parágrafo embutido

 Criar um`Aspose.Pdf.Image` objeto e defina-o como um parágrafo embutido para que apareça logo após o parágrafo anterior:

```csharp
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
image.IsInLineParagraph = true;
image.File = dataDir + "aspose-logo.jpg";
image.FixHeight = 30; // Opcional: Definir altura da imagem
image.FixWidth = 100; // Opcional: Definir largura da imagem
page.Paragraphs.Add(image);
```

 Substituir`"aspose-logo.jpg"` com o nome real do arquivo de imagem e ajuste a altura e largura da imagem opcional conforme desejado.

## Etapa 7: adicione outro TextFragment como um parágrafo embutido

 Reinicializar o`TextFragment` objeto com conteúdo diferente e adicione-o como um parágrafo embutido:

```csharp
text = new TextFragment(" Hello Again..");
text.IsInLineParagraph = true;
page.Paragraphs.Add(text);
```

## Etapa 8: Salve o documento PDF

Salve o documento PDF modificado:

```csharp
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
```

 Certifique-se de substituir`"TextAndImageAsParagraph_out.pdf"` com o nome do arquivo de saída desejado.

### Exemplo de código-fonte para Texto e Imagem como Parágrafo usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instanciar instância de documento
Document doc = new Document();
// Adicionar página à coleção de páginas da instância do documento
Page page = doc.Pages.Add();
// Criar TextFragmnet
TextFragment text = new TextFragment("Hello World.. ");
// Adicionar fragmento de texto à coleção de parágrafos do objeto Page
page.Paragraphs.Add(text);
// Criar uma instância de imagem
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
// Defina a imagem como um parágrafo embutido para que ela apareça logo depois
// O objeto do parágrafo anterior (TextFragment)
image.IsInLineParagraph = true;
// Especificar caminho do arquivo de imagem
image.File = dataDir + "aspose-logo.jpg";
// Definir altura da imagem (opcional)
image.FixHeight = 30;
// Definir largura da imagem (opcional)
image.FixWidth = 100;
// Adicionar imagem à coleção de parágrafos do objeto de página
page.Paragraphs.Add(image);
// Reinicializar objeto TextFragment com conteúdos diferentes
text = new TextFragment(" Hello Again..");
// Definir TextFragment como parágrafo embutido
text.IsInLineParagraph = true;
// Adicionar TextFragment recém-criado à coleção de parágrafos da página
page.Paragraphs.Add(text);
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nText and image added successfully as an inline paragraphs.\nFile saved at " + dataDir);
```

## Conclusão

Parabéns! Você aprendeu com sucesso como adicionar texto e uma imagem como parágrafos inline em um documento PDF usando o Aspose.PDF para .NET. Este tutorial forneceu um guia passo a passo, desde a configuração do projeto até salvar o documento modificado. Agora você pode incorporar este código em seus próprios projetos C# para personalizar o layout de texto e imagens em arquivos PDF.

### Perguntas frequentes

#### P: Qual é o objetivo do tutorial "Texto e imagem como parágrafo em arquivo PDF"?

R: O tutorial "Texto e imagem como parágrafo em arquivo PDF" tem como objetivo orientar os usuários sobre como adicionar texto e imagens como parágrafos inline em um documento PDF usando o Aspose.PDF para .NET. O tutorial fornece instruções passo a passo e exemplos de código C# para demonstrar o processo.

#### P: Como este tutorial ajuda a adicionar texto e imagens como parágrafos embutidos?

R: Este tutorial ajuda os usuários a entender como usar o Aspose.PDF para .NET para incorporar texto e imagens como parágrafos inline em um documento PDF. Seguindo as etapas e exemplos de código fornecidos, os usuários podem criar arquivos PDF com layouts personalizados que combinam texto e imagens.

#### P: Quais são os pré-requisitos necessários para seguir este tutorial?

R: Antes de começar o tutorial, você deve ter um entendimento básico da linguagem de programação C#. Além disso, você precisa ter a biblioteca Aspose.PDF for .NET instalada. Você pode obtê-la no site da Aspose ou instalá-la em seu projeto usando o NuGet.

#### P: Como configuro meu projeto para seguir este tutorial?

R: Para começar, crie um novo projeto C# no seu ambiente de desenvolvimento integrado (IDE) preferido e adicione uma referência à biblioteca Aspose.PDF for .NET. Isso permite que você utilize os recursos da biblioteca para trabalhar com documentos PDF, fragmentos de texto e imagens.

#### P: Posso usar este tutorial para adicionar vários parágrafos de texto e imagem em um PDF?

R: Sim, você pode usar os exemplos de código fornecidos para adicionar várias instâncias de parágrafos de texto e imagem dentro do mesmo documento PDF. Este tutorial demonstra como criar parágrafos inline, facilitando a inclusão de diferentes combinações de texto e imagens.

#### P: Como especifico o conteúdo e a aparência dos parágrafos de texto e imagens?

 A: O tutorial demonstra como criar`TextFragment`objetos para representar parágrafos de texto e`Aspose.Pdf.Image` objetos para representar imagens. Você pode personalizar o conteúdo, as dimensões e a aparência de texto e imagens usando os exemplos de código fornecidos.

#### P: Posso ajustar o layout dos parágrafos embutidos?

 R: Sim, você pode ajustar o layout dos parágrafos inline controlando seu posicionamento, dimensões e ordem dentro da página. O tutorial mostra como definir atributos inline, como`IsInLineParagraph`, para controlar o layout de parágrafos de texto e imagem.

#### P: Como faço para salvar o documento PDF modificado?

 R: Para salvar o documento PDF modificado, você pode usar o`Save` método do`Document` objeto. O tutorial fornece exemplos de código que demonstram como salvar o documento PDF resultante.