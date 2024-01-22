---
title: Imagem e número da página na seção do rodapé do cabeçalho embutido
linktitle: Imagem e número da página na seção do rodapé do cabeçalho embutido
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como adicionar imagem e número de página no cabeçalho e rodapé usando parágrafos embutidos com Aspose.PDF para .NET.
type: docs
weight: 120
url: /pt/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section-inline/
---
Neste tutorial, iremos guiá-lo passo a passo sobre como adicionar imagem e número de página na seção de cabeçalho e rodapé de um documento PDF usando Aspose.PDF for .NET. Usaremos o código-fonte C# fornecido para criar uma página, definir cabeçalho e rodapé, adicionar imagem e texto usando parágrafos embutidos no cabeçalho do documento PDF.

## Passo 1: Configurando o ambiente

Antes de começar, certifique-se de ter o seguinte:

- Um ambiente de desenvolvimento .NET instalado.
- A biblioteca Aspose.PDF para .NET baixada e referenciada em seu projeto.

## Etapa 2: Criando o documento e a página PDF

A primeira etapa é criar um novo objeto Documento e uma página no documento PDF. Veja como:

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Crie um novo objeto Documento
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// Crie uma página no documento
Aspose.Pdf.Page page = pdf1.Pages.Add();
```

O código acima cria um novo objeto Document e uma página vazia no documento PDF.

## Etapa 3: adicionar o cabeçalho com uma imagem e texto embutido

Agora que a página foi criada, podemos adicionar uma seção de cabeçalho com imagem e texto usando parágrafos embutidos. Veja como:

```csharp
// Crie uma seção de cabeçalho
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Defina o cabeçalho da página
page. Header = header;

// Crie um objeto TextFragment para o primeiro texto embutido
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a robust component developed by");

// Especifique a cor do texto
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

// Crie um objeto Image para a imagem
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Definir caminho da imagem
image1.File = dataDir + "aspose-logo.jpg";

// Defina as dimensões da imagem
image1.FixWidth = 50;
image1.FixHeight = 20;

// Indique que o primeiro texto embutido é uma imagem
image1.IsInLineParagraph = true;

// Crie um segundo texto embutido
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;

// Adicionar itens ao cabeçalho
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);
```

O código acima cria uma seção de cabeçalho, define o cabeçalho da página com esta seção, adiciona um TextFragment com texto embutido e um objeto Image embutido.

## Passo 4: Salvando o documento PDF modificado

Depois que o cabeçalho com a imagem e o texto embutido forem adicionados, podemos salvar o documento PDF modificado. Veja como:

```csharp
// Salve o documento PDF modificado
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");
```

O código acima salva o documento PDF editado no diretório especificado.

### Exemplo de código-fonte para imagem e número de página na seção de rodapé do cabeçalho embutido usando Aspose.PDF para .NET 
```csharp

// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instancie um objeto Document chamando seu construtor vazio
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// Crie uma página no objeto PDF
Aspose.Pdf.Page page = pdf1.Pages.Add();

// Criar seção de cabeçalho do documento
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Defina o cabeçalho do arquivo PDF
page.Header = header;

// Crie um objeto Texto
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a Robust component by");

// Especifique a cor
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

// Crie um objeto de imagem na seção
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Defina o caminho do arquivo de imagem
image1.File = dataDir + "aspose-logo.jpg";

// Defina as informações da largura da imagem
image1.FixWidth = 50;
image1.FixHeight = 20;

// Indica que InlineParagraph do seg1 é uma imagem.
image1.IsInLineParagraph = true;
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);

// Salve o PDF
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");

```

## Conclusão

Parabéns! Você aprendeu como adicionar uma imagem e um número de página na seção de cabeçalho e rodapé de um documento PDF usando parágrafos embutidos com Aspose.PDF para .NET. Agora você pode personalizar o cabeçalho e o rodapé dos seus documentos PDF de maneira flexível.

### Perguntas frequentes

#### P: Qual é a vantagem de usar parágrafos embutidos para adicionar uma imagem e texto ao cabeçalho de um documento PDF?

R: O uso de parágrafos embutidos permite integrar perfeitamente imagens e texto no mesmo parágrafo, proporcionando controle preciso sobre seu posicionamento e formatação. Este método é especialmente útil para criar cabeçalhos personalizados com elementos visuais.

#### P: Como o código-fonte C# fornecido consegue parágrafos embutidos no cabeçalho de um documento PDF?

R: O código fornecido demonstra como criar um documento PDF, adicionar uma página e personalizar o cabeçalho usando parágrafos embutidos. Ele adiciona um TextFragment com texto embutido, uma imagem embutida e outro TextFragment embutido.

#### P: Como especifico a cor do texto embutido no cabeçalho?

 R: A cor do texto embutido é especificada usando o`ForegroundColor` propriedade do`TextState` do`TextFragment` objeto.

#### P: Posso ajustar as dimensões da imagem embutida no cabeçalho?

 R: Sim, você pode ajustar as dimensões da imagem embutida usando o`FixWidth` e`FixHeight` propriedades do`Image` objeto. Isso permite controlar a largura e a altura da imagem no cabeçalho.

#### P: Posso incluir elementos embutidos adicionais, como hiperlinks ou estilos de fonte diferentes, no cabeçalho?

 R: Sim, você pode incluir elementos embutidos adicionais no cabeçalho criando mais`TextFragment` ou`Image` objetos com as propriedades desejadas. Isso permite que você personalize ainda mais o cabeçalho, incluindo hiperlinks, diferentes estilos de fonte ou outros elementos visuais.

#### P: Como posso garantir que a imagem e o texto embutidos permaneçam devidamente alinhados e formatados em diferentes dispositivos e visualizadores?

R: Aspose.PDF for .NET garante que as imagens e o texto embutidos sejam alinhados e formatados corretamente, resultando em uma aparência consistente em diferentes dispositivos e visualizadores de PDF.

#### P: Posso aplicar parágrafos embutidos também à seção de rodapé?

 R: Sim, você pode aplicar a mesma técnica de usar parágrafos embutidos na seção de rodapé criando um`Footer` objeto e adicionar elementos embutidos, como texto e imagens a ele.

#### P: É possível combinar parágrafos embutidos com outros métodos de personalização de cabeçalho ou rodapé?

R: Sim, você pode combinar parágrafos embutidos com outros métodos de personalização de cabeçalho ou rodapé fornecidos pelo Aspose.PDF for .NET para criar designs de cabeçalho ou rodapé mais complexos e personalizados.

#### P: Posso remover ou limpar os elementos embutidos do cabeçalho, se necessário?

 R: Sim, você pode remover ou limpar os elementos embutidos modificando o conteúdo do`HeaderFooter` objeto e removendo os respectivos parágrafos embutidos.

#### P: Como posso aplicar parágrafos embutidos a páginas específicas do documento PDF?

 R: Para aplicar parágrafos embutidos a páginas específicas, você pode criar`HeaderFooter` objetos para cada página e atribuí-los usando o`Header` propriedade do respectivo`Aspose.Pdf.Page` objetos.