---
title: Imagem e número de página na seção Cabeçalho Rodapé Inline
linktitle: Imagem e número de página na seção Cabeçalho Rodapé Inline
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda como adicionar imagem e número de página no cabeçalho e rodapé usando parágrafos embutidos com Aspose.PDF para .NET.
type: docs
weight: 120
url: /pt/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section-inline/
---
Neste tutorial, nós o guiaremos passo a passo sobre como adicionar imagem e número de página na seção de cabeçalho e rodapé do documento PDF usando Aspose.PDF para .NET. Usaremos o código-fonte C# fornecido para criar uma página, definir cabeçalho e rodapé, adicionar imagem e texto usando parágrafos inline no cabeçalho do documento PDF.

## Etapa 1: Configurando o ambiente

Antes de começar, certifique-se de ter o seguinte:

- Um ambiente de desenvolvimento .NET instalado.
- A biblioteca Aspose.PDF para .NET baixada e referenciada em seu projeto.

## Etapa 2: Criando o documento PDF e a página

O primeiro passo é criar um novo objeto Document e uma página no documento PDF. Veja como:

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Crie um novo objeto Document
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// Crie uma página no documento
Aspose.Pdf.Page page = pdf1.Pages.Add();
```

O código acima cria um novo objeto Document e uma página em branco no documento PDF.

## Etapa 3: Adicionar o cabeçalho com uma imagem e texto embutido

Agora que a página foi criada, podemos adicionar uma seção de cabeçalho com uma imagem e texto usando parágrafos inline. Veja como:

```csharp
// Criar uma seção de cabeçalho
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Defina o cabeçalho da página
page. Header = header;

// Crie um objeto TextFragment para o primeiro texto embutido
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a robust component developed by");

// Especificar cor do texto
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

// Crie um objeto Image para a imagem
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Definir caminho da imagem
image1.File = dataDir + "aspose-logo.jpg";

// Defina as dimensões da imagem
image1.FixWidth = 50;
image1.FixHeight = 20;

// Indica que o primeiro texto em linha é uma imagem
image1.IsInLineParagraph = true;

// Crie um segundo texto inline
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;

// Adicionar itens ao cabeçalho
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);
```

O código acima cria uma seção de cabeçalho, define o cabeçalho da página com esta seção, adiciona um TextFragment com texto embutido e um objeto Image embutido.

## Etapa 4: salvando o documento PDF modificado

Depois que o cabeçalho com a imagem e o texto inline for adicionado, podemos salvar o documento PDF modificado. Veja como:

```csharp
// Salvar o documento PDF modificado
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");
```

O código acima salva o documento PDF editado no diretório especificado.

### Exemplo de código-fonte para Imagem e Número de Página na seção Cabeçalho Rodapé Inline usando Aspose.PDF para .NET 
```csharp

// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instanciar um objeto Document chamando seu construtor vazio
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// Crie uma página no objeto PDF
Aspose.Pdf.Page page = pdf1.Pages.Add();

// Criar seção de cabeçalho do documento
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Defina o cabeçalho do arquivo PDF
page.Header = header;

// Criar um objeto de texto
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a Robust component by");

// Especifique a cor
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

// Crie um objeto de imagem na seção
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Defina o caminho do arquivo de imagem
image1.File = dataDir + "aspose-logo.jpg";

//Definir a largura da imagem Informações
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

// Salvar o PDF
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");

```

## Conclusão

Parabéns! Você aprendeu como adicionar uma imagem e um número de página na seção de cabeçalho e rodapé de um documento PDF usando parágrafos inline com Aspose.PDF para .NET. Agora você pode personalizar o cabeçalho e o rodapé dos seus documentos PDF de forma flexível.

### Perguntas frequentes

#### P: Qual é a vantagem de usar parágrafos embutidos para adicionar uma imagem e texto ao cabeçalho de um documento PDF?

R: Usar parágrafos inline permite que você integre perfeitamente imagens e texto dentro do mesmo parágrafo, fornecendo controle preciso sobre seu posicionamento e formatação. Este método é especialmente útil para criar cabeçalhos personalizados com elementos visuais.

#### P: Como o código-fonte C# fornecido obtém parágrafos embutidos para o cabeçalho em um documento PDF?

R: O código fornecido demonstra como criar um documento PDF, adicionar uma página e personalizar o cabeçalho usando parágrafos inline. Ele adiciona um TextFragment com texto inline, uma imagem inline e outro TextFragment inline.

#### P: Como especifico a cor do texto embutido no cabeçalho?

 A: A cor do texto embutido é especificada usando o`ForegroundColor` propriedade do`TextState` do`TextFragment` objeto.

#### P: Posso ajustar as dimensões da imagem embutida no cabeçalho?

 R: Sim, você pode ajustar as dimensões da imagem embutida usando o`FixWidth` e`FixHeight` propriedades do`Image` objeto. Isso permite que você controle a largura e a altura da imagem dentro do cabeçalho.

#### P: Posso incluir elementos embutidos adicionais, como hiperlinks ou estilos de fonte diferentes, no cabeçalho?

 R: Sim, você pode incluir elementos inline adicionais no cabeçalho criando mais`TextFragment` ou`Image` objetos com as propriedades desejadas. Isso permite que você personalize o cabeçalho ainda mais, incluindo hiperlinks, diferentes estilos de fonte ou outros elementos visuais.

#### P: Como posso garantir que a imagem e o texto embutidos permaneçam alinhados e formatados corretamente em diferentes dispositivos e visualizadores?

R: O Aspose.PDF para .NET garante que imagens e textos embutidos sejam alinhados e formatados corretamente, resultando em uma aparência consistente em diferentes dispositivos e visualizadores de PDF.

#### P: Posso aplicar parágrafos embutidos também na seção de rodapé?

 R: Sim, você pode aplicar a mesma técnica de uso de parágrafos embutidos na seção de rodapé, criando um`Footer` objeto e adicionar elementos embutidos, como texto e imagens.

#### P: É possível combinar parágrafos embutidos com outros métodos de personalização de cabeçalho ou rodapé?

R: Sim, você pode combinar parágrafos embutidos com outros métodos de personalização de cabeçalho ou rodapé fornecidos pelo Aspose.PDF para .NET para criar designs de cabeçalho ou rodapé mais complexos e personalizados.

#### P: Posso remover ou limpar os elementos embutidos do cabeçalho, se necessário?

 R: Sim, você pode remover ou limpar os elementos inline modificando o conteúdo do`HeaderFooter`objeto e removendo os respectivos parágrafos em linha.

#### P: Como posso aplicar parágrafos embutidos a páginas específicas do documento PDF?

 R: Para aplicar parágrafos inline a páginas específicas, você pode criar parágrafos separados`HeaderFooter` objetos para cada página e atribuí-los usando o`Header` propriedade do respectivo`Aspose.Pdf.Page` objetos.