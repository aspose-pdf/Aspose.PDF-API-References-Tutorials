---
title: Número de página no cabeçalho e rodapé usando caixa flutuante
linktitle: Número de página no cabeçalho e rodapé usando caixa flutuante
second_title: Referência da API do Aspose.PDF para .NET
description: Adicione facilmente números de página no cabeçalho e rodapé do seu PDF usando uma caixa flutuante com Aspose.PDF para .NET neste tutorial passo a passo.
type: docs
weight: 150
url: /pt/net/programming-with-stamps-and-watermarks/page-number-in-header-footer-using-floating-box/
---
## Introdução

Quando se trata de gerenciar documentos PDF programaticamente, o Aspose.PDF para .NET se destaca como uma ferramenta excepcional. Ele simplifica a maneira como criamos, editamos e manipulamos arquivos PDF em aplicativos .NET. Quer você esteja gerando faturas, relatórios ou qualquer tipo de documento, adicionar números de página elegantemente pode melhorar o profissionalismo e a organização dos seus PDFs. Neste tutorial, vamos nos aprofundar em como adicionar números de página no cabeçalho e rodapé do seu PDF usando uma caixa flutuante. Pronto para começar? Vamos lá!

## Pré-requisitos

Antes de começarmos esta emocionante jornada no reino da manipulação de PDF, há algumas coisas que você precisa ter:

### Configuração do ambiente .NET
Certifique-se de ter um ambiente de desenvolvimento .NET. Você pode usar o Visual Studio, que é uma escolha popular entre desenvolvedores para aplicativos .NET.

### Biblioteca Aspose.PDF
Instale a biblioteca Aspose.PDF. Você pode baixá-la facilmente do site:

- [Baixe Aspose.PDF para .NET](https://releases.aspose.com/pdf/net/)

### Conhecimento básico de programação C#
Uma compreensão básica de C# ajudará você a entender os conceitos e trechos de codificação apresentados neste tutorial.

### Acesso à Documentação
 É sempre benéfico ter o[Documentação Aspose.PDF](https://reference.aspose.com/pdf/net/) útil para referência e exploração mais profunda de quaisquer funcionalidades adicionais.

## Pacotes de importação

Para começar, você precisará importar os pacotes necessários no seu projeto. Isso garante que o assembly Aspose.PDF esteja acessível para uso no seu código. Veja como fazer isso:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Agora, vamos dividir o processo de adicionar números de página usando uma Caixa Flutuante em etapas gerenciáveis. Acompanhe enquanto caminhamos.

## Etapa 1: configure seu ambiente de documentos

Vamos começar especificando o diretório onde seu documento PDF será armazenado. Isso é crucial porque ele determina onde seu arquivo de saída será salvo.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Substituir`YOUR DOCUMENT DIRECTORY` com o caminho de sua escolha onde você deseja salvar o arquivo PDF de saída.

## Etapa 2: Instanciar o documento

 A próxima etapa é criar um novo documento PDF. Isso envolve usar o`Document` classe da biblioteca Aspose.PDF.

```csharp
// Instanciar instância de documento
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();
```
 Aqui, criamos uma nova instância do`Document` classe, que serve como nossa tela para manipulação.

## Etapa 3: Adicionar uma nova página

Agora, vamos adicionar uma página ao nosso documento PDF. Todo PDF precisa de pelo menos uma página, certo?

```csharp
// Adicionar uma página ao documento PDF
Aspose.Pdf.Page page = pdf.Pages.Add();
```
Este trecho de código adiciona uma nova página ao nosso documento, deixando-o pronto para receber conteúdo, incluindo nossa caixa flutuante com números de página.

## Etapa 4: Crie uma caixa flutuante

 Em seguida, é hora de criar nossa Caixa Flutuante que conterá o número da página. O`FloatingBox` classe nos permite posicionar o conteúdo livremente na página.

```csharp
// Inicializa uma nova instância da classe FloatingBox
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);
```
 Aqui, os parâmetros`(140, 80)` especifique a largura e a altura do Floating Box. Você pode ajustar esses valores com base na sua preferência de layout.

## Etapa 5: Posicionando a caixa flutuante

 O posicionamento é a chave! Você quer determinar onde o número da página aparecerá na página. Você estará trabalhando com o`Left` e`Top` propriedades para especificar a posição.

```csharp
// Valor flutuante que indica a posição esquerda do parágrafo
box1.Left = 2;
// Valor flutuante que indica a posição superior do parágrafo
box1.Top = 10;
```
Esses valores ditam o posicionamento da Caixa Flutuante na página. Sinta-se à vontade para experimentar com eles para ver o que fica melhor no seu documento.

## Etapa 6: Adicionar texto com a macro de número de página

Agora, adicionaremos uma string que mostra dinamicamente o número da página. É aqui que a mágica acontece!

```csharp
// Adicione as macros à coleção de parágrafos do FloatingBox
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));
```
 Nesse caso,`($p/ $P)`é uma macro que exibirá o número da página atual (`$p`) e o número total de páginas (`$P`). Como resultado, ele formata o texto para algo como "Página: 1/5".

## Etapa 7: adicione a caixa flutuante à página

É hora de adicionar a Caixa Flutuante, junto com o texto do número da página, à nossa página recém-criada.

```csharp
// Adicione um floatingBox à página
page.Paragraphs.Add(box1);
```
Esta linha essencialmente incorpora sua Caixa Flutuante na página, tornando-a parte do layout do documento. 

## Etapa 8: Salve seu documento

Por fim, não esqueça de salvar seu trabalho! O último passo é salvar seu documento PDF com um nome de arquivo apropriado.

```csharp
// Salvar o documento
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");
```
Certifique-se de que o caminho especificado inclua o nome do arquivo desejado. Agora, seu incrível PDF com números de página está criado! 

## Conclusão

aí está, pessoal! Adicionar números de página ao cabeçalho e rodapé do seu PDF usando o Aspose.PDF para .NET é tão simples quanto isso. Com apenas algumas linhas de código, você embarcou em uma jornada para dominar o processamento de documentos em seus aplicativos. Não hesite em experimentar diferentes layouts e formatações — afinal, a criatividade não tem limites! Pronto para gerar aquele documento profissional? Pegue seu chapéu de codificação e comece a experimentar.

## Perguntas frequentes

### Posso personalizar a aparência do texto do número da página?  
 Sim, você pode personalizar as propriedades do texto, como tamanho da fonte, cor e estilo, ajustando o`TextFragment` propriedades.

### O Aspose.PDF é gratuito?  
 Embora o Aspose.PDF ofereça um teste gratuito, ele é um produto pago para uso em produção. Você pode[compre aqui](https://purchase.aspose.com/buy).

### Onde posso encontrar documentação mais detalhada?  
 Você pode encontrar documentação abrangente sobre o[Site de documentação Aspose.PDF](https://reference.aspose.com/pdf/net/).

### Como aplico cabeçalhos e rodapés a várias páginas?  
Você pode percorrer todas as páginas do seu documento e aplicar a Caixa Flutuante a cada uma delas da mesma forma.

### E se eu precisar de suporte para recursos adicionais?  
Para quaisquer perguntas ou suporte adicionais, você pode visitar o[Fórum Aspose](https://forum.aspose.com/c/pdf/10).