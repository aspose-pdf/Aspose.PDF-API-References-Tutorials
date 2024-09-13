---
title: Imagem e número de página na seção Cabeçalho Rodapé Inline
linktitle: Imagem e número de página na seção Cabeçalho Rodapé Inline
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda como adicionar uma imagem e um número de página em linha na seção de cabeçalho de um PDF usando o Aspose.PDF para .NET com este guia passo a passo.
type: docs
weight: 120
url: /pt/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section-inline/
---
## Introdução

Aspose.PDF para .NET é uma ferramenta poderosa que fornece recursos extensivos para manipular e gerar arquivos PDF. Se você precisa adicionar imagens, personalizar cabeçalhos e rodapés ou gerenciar texto, o Aspose.PDF tem tudo o que você precisa. Neste tutorial, exploraremos como adicionar uma imagem e um número de página em linha no cabeçalho ou rodapé de um documento PDF. Vamos mergulhar de cabeça e dividir o processo passo a passo.

## Pré-requisitos

Antes de começarmos o código, vamos garantir que você tenha tudo pronto para seguir em frente:

-  Aspose.PDF para .NET: Baixe a versão mais recente do[Página de download do Aspose PDF](https://releases.aspose.com/pdf/net/).
- Ambiente de desenvolvimento: você precisará de um IDE C#, como o Visual Studio.
-  Licença: Se você ainda não tem uma licença, você pode obter uma[licença temporária aqui](https://purchase.aspose.com/temporary-license/) ou compre um completo no[Loja Aspose](https://purchase.aspose.com/buy).

Agora que você tem os pré-requisitos prontos, vamos começar.

## Pacotes de importação

Antes de começar a codificar, certifique-se de importar os namespaces necessários:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Esses pacotes permitem que você trabalhe com arquivos PDF e manipulação de texto.

## Etapa 1: Configurar o diretório de documentos

A primeira coisa que precisamos fazer é definir o caminho para o diretório onde nosso arquivo PDF será salvo. Esse caminho pode ser personalizado para a pasta do seu projeto ou qualquer local na sua máquina.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Esta variável contém o local onde seu documento será armazenado. Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real.

## Etapa 2: Instanciar o documento PDF

 Nesta etapa, criamos uma nova instância do`Aspose.Pdf.Document` objeto. Este objeto servirá como a espinha dorsal do seu arquivo PDF.

```csharp
// Instanciar um objeto Document chamando seu construtor vazio
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

Aqui, estamos criando um arquivo PDF em branco que podemos preencher com conteúdo posteriormente.

## Etapa 3: Adicionar uma página ao PDF

Seu PDF precisa de pelo menos uma página onde você pode adicionar cabeçalhos, rodapés e conteúdo. Vamos adicionar uma página em branco ao nosso documento.

```csharp
// Crie uma página no objeto PDF
Aspose.Pdf.Page page = pdf1.Pages.Add();
```

 Ao ligar`pdf1.Pages.Add()`uma nova página é adicionada ao documento, pronta para personalização de cabeçalho e rodapé.

## Etapa 4: Crie e defina o cabeçalho

Agora é hora de criar o cabeçalho para o documento. É aqui que adicionaremos o texto, a imagem e o número da página.

```csharp
// Criar seção de cabeçalho do documento
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();
// Defina o cabeçalho do arquivo PDF
page.Header = header;
```

 Nós criamos um`HeaderFooter` objeto e atribuí-lo ao`Header` propriedade da página, garantindo que tudo o que adicionarmos ao cabeçalho aparecerá no topo da página.

## Etapa 5: adicione texto embutido ao cabeçalho

 Adicionar texto é tão simples quanto criar um`TextFragment` e especificando suas propriedades. Vamos adicionar algum texto colorido ao nosso cabeçalho.

```csharp
// Criar um objeto de texto
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a Robust component by");
// Especifique a cor
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;
```

 Nesta etapa, criamos um`TextFragment` com o conteúdo "Aspose.Pdf é um componente Robust by" e defina sua cor para azul. O`IsInLineParagraph` propriedade garante que o texto esteja embutido, o que significa que ele aparecerá na mesma linha que os outros elementos (como a imagem e o texto adicional).

## Etapa 6: Insira uma imagem embutida no cabeçalho

Para tornar seu cabeçalho visualmente atraente, você pode adicionar uma imagem inline com o texto. Pode ser o logotipo da sua empresa ou qualquer outro gráfico.

```csharp
// Crie um objeto de imagem na seção
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
// Defina o caminho do arquivo de imagem
image1.File = dataDir + "aspose-logo.jpg";
// Definir a largura da imagem Informações
image1.FixWidth = 50;
image1.FixHeight = 20;
// Indica que InlineParagraph do seg1 é uma imagem.
image1.IsInLineParagraph = true;
```

 Aqui, adicionamos uma imagem ao cabeçalho criando um`Image` objeto, definindo seu caminho e ajustando a largura e a altura. O`IsInLineParagraph` garante que a imagem esteja alinhada com o texto.

## Etapa 7: adicione texto adicional em linha para completar o cabeçalho

Vamos adicionar mais texto para completar o cabeçalho embutido.

```csharp
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);
```

 Nesta parte, criamos outra`TextFragment` com o conteúdo "Pty Ltd." e defina sua cor para marrom. Fragmentos de texto e a imagem são adicionados ao cabeçalho.

## Etapa 8: Salve o PDF

Depois de configurar o cabeçalho, é hora de salvar o PDF.

```csharp
// Salvar o PDF
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");
```

 O`Save` O método grava o arquivo PDF final no local especificado.

## Conclusão

Parabéns! Você adicionou com sucesso uma imagem e texto ao cabeçalho de um documento PDF usando o Aspose.PDF para .NET. Este tutorial o guiou pelas etapas essenciais, incluindo a criação de um documento, adição de páginas, inserção de cabeçalhos e inserção de conteúdo inline, como texto e imagens. O Aspose.PDF oferece flexibilidade incrível para gerenciar seus PDFs, seja manipulando cabeçalhos, rodapés ou conteúdo complexo. 

## Perguntas frequentes

### Posso adicionar um número de página ao cabeçalho também?
 Sim! Você pode facilmente adicionar um número de página usando o`TextFragment` class e formatá-lo conforme necessário. Basta inseri-lo na seção de cabeçalho como conteúdo inline.

### Como defino uma imagem de fundo no cabeçalho?
 Você pode usar o`BackgroundImage` propriedade do`HeaderFooter` class para definir uma imagem de fundo. No entanto, isso não é conteúdo inline e cobrirá toda a área do cabeçalho.

### É possível usar outros formatos de imagem além de JPEG?
Absolutamente! Aspose.PDF suporta vários formatos de imagem, como PNG, BMP e GIF.

### Posso personalizar a fonte do texto no cabeçalho?
 Sim, você pode usar o`TextState`objeto para alterar a fonte, o tamanho e o estilo do texto.

### Preciso de uma licença para usar o Aspose.PDF para .NET?
 Sim, o Aspose.PDF requer uma licença para uso em produção, mas você pode começar com uma[teste gratuito aqui](https://releases.aspose.com/).