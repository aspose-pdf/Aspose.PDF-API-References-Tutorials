---
title: Número de página no cabeçalho e rodapé usando caixa flutuante
linktitle: Número de página no cabeçalho e rodapé usando caixa flutuante
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda como adicionar o número da página no cabeçalho e rodapé de um documento PDF com o Aspose.PDF para .NET.
type: docs
weight: 150
url: /pt/net/programming-with-stamps-and-watermarks/page-number-in-header-footer-using-floating-box/
---
Neste tutorial, nós o guiaremos passo a passo sobre como adicionar número de página no cabeçalho e rodapé de um documento PDF usando FloatingBox com Aspose.PDF para .NET. Usaremos o código-fonte C# fornecido para criar um documento PDF, adicionar uma página, criar um FloatingBox, definir sua posição e adicionar o número de página a ele, então salvar o documento PDF modificado.

## Etapa 1: Configurando o ambiente

Antes de começar, certifique-se de ter o seguinte:

- Um ambiente de desenvolvimento .NET instalado.
- A biblioteca Aspose.PDF para .NET baixada e referenciada em seu projeto.

## Etapa 2: Criando o documento PDF e adicionando uma página

O primeiro passo é criar uma instância do documento PDF e adicionar uma página a ele. Veja como:

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Instanciar o documento PDF
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

// Adicionar uma página ao documento PDF
Aspose.Pdf.Page page = pdf.Pages.Add();
```

Certifique-se de substituir "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho real para o diretório onde você deseja salvar o documento PDF.

## Etapa 3: Criando o FloatingBox e adicionando o número da página

Agora que a página foi adicionada ao documento PDF, podemos criar um FloatingBox, definir sua posição e adicionar o número da página a ele. Veja como:

```csharp
// Crie uma FloatingBox com largura de 140 e altura de 80
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

// Defina a posição esquerda do parágrafo
box1. Left = 2;

// Defina a posição superior do parágrafo
box1. Top = 10;

// Adicione o número da página ao FloatingBox
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

// Adicione o FloatingBox à página
page.Paragraphs.Add(box1);
```

O código acima cria um FloatingBox com uma largura de 140 e uma altura de 80. Em seguida, definimos sua posição especificando os valores left e top. Finalmente, adicionamos o número da página ao FloatingBox usando um TextFragment contendo a sintaxe "($p/ $P )" que será substituído pelo número da página atual e o número total de páginas.

## Etapa 4: salvando o documento PDF modificado

Depois que o número da página for adicionado ao cabeçalho ou rodapé usando o FloatingBox, podemos salvar o documento PDF modificado. Veja como:

```csharp
// Salvar o documento PDF modificado
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");
```

O código acima salva o documento PDF editado no diretório especificado.

### Exemplo de código-fonte para Page Numberin Header Footer usando caixa flutuante usando Aspose.PDF para .NET 
```csharp

// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instanciar instância de documento
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

// Adicionar uma página ao documento PDF
Aspose.Pdf.Page page = pdf.Pages.Add();

// Inicializa uma nova instância da classe FloatingBox
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

// Valor flutuante que indica a posição esquerda do parágrafo
box1.Left = 2;

// Valor flutuante que indica a posição superior do parágrafo
box1.Top = 10;

// Adicione as macros à coleção de parágrafos do FloatingBox
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

// Adicione um floatingBox à página
page.Paragraphs.Add(box1);

// Salvar o documento
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");

```

## Conclusão

Parabéns! Você aprendeu como adicionar número de página no cabeçalho e rodapé de um documento PDF usando FloatingBox com Aspose.PDF para .NET. Agora você pode personalizar seus cabeçalhos e rodapés adicionando informações dinâmicas, como número de página.

### Perguntas frequentes

#### P: O que é um FloatingBox e como ele é usado para adicionar números de página no cabeçalho ou rodapé de um documento PDF?

R: Um FloatingBox é um elemento de layout versátil no Aspose.PDF que pode conter vários conteúdos, incluindo texto e imagens. Neste tutorial, ele é usado para criar um contêiner para o número da página, permitindo que você insira dinamicamente o número da página atual e a contagem total de páginas no cabeçalho ou rodapé.

#### P: Como o código-fonte C# fornecido consegue adicionar números de página usando um FloatingBox?

R: O snippet de código demonstra como criar um documento PDF, adicionar uma página, criar um FloatingBox, definir sua posição dentro da página e inserir o número da página usando um TextFragment. A sintaxe "($p/ $P )" no TextFragment é substituída pelo número da página atual e pela contagem total de páginas.

#### P: Posso personalizar a aparência e a formatação do número de página adicionado usando o FloatingBox?

R: Sim, você pode personalizar a aparência do número da página modificando as propriedades do TextFragment dentro do FloatingBox. Você pode alterar o tamanho da fonte, cor, estilo, alinhamento e outras opções de formatação.

#### P: É possível adicionar diferentes elementos dinâmicos, como data e hora, ao cabeçalho ou rodapé usando uma abordagem semelhante?

R: Com certeza, você pode adicionar diferentes elementos dinâmicos como data, hora, metadados do documento ou texto personalizado modificando o conteúdo do TextFragment dentro do FloatingBox. Você pode usar macros como "($p/ $P )" para números de página ou "($date)" para a data atual.

#### P: Como especifico a posição do FloatingBox na seção de cabeçalho ou rodapé?
 R: O código fornecido define a posição do FloatingBox usando o`Left` e`Top` propriedades. Você pode ajustar esses valores para posicionar o FloatingBox conforme desejado dentro da seção de cabeçalho ou rodapé.

#### P: Posso usar uma fonte ou estilo diferente para o número de página no cabeçalho ou rodapé?

R: Sim, você pode personalizar a fonte, o estilo e outras propriedades de formatação do texto do número da página modificando as propriedades TextFragment dentro do FloatingBox.

#### P: O que acontece se o conteúdo no FloatingBox exceder suas dimensões?

R: Se o conteúdo dentro do FloatingBox exceder suas dimensões, ele pode ser cortado ou podem surgir problemas de layout. Certifique-se de que as dimensões do FloatingBox sejam adequadas para acomodar o conteúdo e considere ajustar o layout da página, se necessário.

#### P: É possível adicionar vários FloatingBoxes com conteúdo diferente ao cabeçalho ou rodapé da mesma página?

R: Sim, você pode adicionar vários FloatingBoxes com conteúdo diferente ao cabeçalho ou rodapé da mesma página criando instâncias FloatingBox separadas e adicionando-as à coleção Paragraphs da página.

#### P: Posso usar a abordagem FloatingBox para adicionar conteúdo a outras seções do documento PDF, como o corpo ou as margens?

R: Embora FloatingBoxes sejam comumente usados para cabeçalhos e rodapés, você também pode usá-los para adicionar conteúdo a outras seções do documento PDF, como o corpo ou as margens, posicionando-os adequadamente na página.