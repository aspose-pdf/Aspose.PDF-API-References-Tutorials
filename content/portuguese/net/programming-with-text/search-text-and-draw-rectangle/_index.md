---
title: Pesquisar texto e desenhar retângulo
linktitle: Pesquisar texto e desenhar retângulo
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda a pesquisar texto em PDFs e destacá-lo com retângulos usando Aspose.PDF para .NET! Tutorial passo a passo fácil para habilidades aprimoradas de manipulação de PDF.
type: docs
weight: 460
url: /pt/net/programming-with-text/search-text-and-draw-rectangle/
---
## Introdução

Você está procurando aprimorar suas habilidades de manipulação de PDF? Quer aprender como pesquisar texto específico em arquivos PDF e destacá-lo com um retângulo? Você encontrou o guia perfeito! Hoje, vou mostrar como usar o Aspose.PDF para .NET para pesquisar texto em um documento PDF e desenhar retângulos ao redor dele. Este artigo fornecerá um tutorial passo a passo projetado com clareza e utilidade em mente, garantindo que você possa acompanhar e aplicar essas técnicas aos seus projetos. 

## Pré-requisitos

Antes de mergulhar no tutorial, vamos preparar o que você precisa para garantir um fluxo de trabalho tranquilo:

1. Noções básicas de .NET: você deve estar familiarizado com programação em C# e o framework .NET para seguir este tutorial com eficiência.
   
2. Visual Studio instalado: Você precisará de um ambiente de desenvolvimento integrado (IDE) para escrever e testar seu código. O Visual Studio Community é uma ótima opção, e é gratuito.
   
3. Aspose.PDF para .NET: Você precisa ter a biblioteca Aspose.PDF instalada em seu projeto. Você pode baixá-la[aqui](https://releases.aspose.com/pdf/net/) ou considere um[licença temporária](https://purchase.aspose.com/temporary-license/) para recursos estendidos.
   
4.  Documento PDF de amostra: para este tutorial, você precisará de um arquivo PDF de amostra chamado`SearchAndGetTextFromAll.pdf` armazenado no diretório do seu projeto. 

## Pacotes de importação

Para começar, você primeiro precisará importar os pacotes necessários para seu projeto .NET. Siga estas etapas:

### Abra o Visual Studio

Inicie o Visual Studio e crie um novo aplicativo de console ou use um existente no qual você deseja implementar as funcionalidades do PDF.

### Adicione Aspose.PDF ao seu projeto

1. Clique com o botão direito do mouse no seu projeto no Solution Explorer.
2. Selecione "Gerenciar pacotes NuGet".
3.  Procurar`Aspose.PDF` e instale a versão mais recente.

Ao fazer isso, você estará preparando o terreno para todas as incríveis manipulações de PDF que você está prestes a realizar.

## Importar namespaces

Na parte superior do seu arquivo de programa, você deve importar os namespaces relevantes da biblioteca Aspose:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
using Aspose.Pdf.Facades;
```

Isso facilita o acesso a classes e métodos dentro da biblioteca Aspose.PDF para suas tarefas.


Agora que você configurou tudo, vamos dividir o processo de busca de texto em um PDF e desenhar um retângulo ao redor dele em etapas mais fáceis de gerenciar.

## Etapa 1: Defina o caminho para o seu documento

 Primeiro, defina o caminho para o seu arquivo PDF. Certifique-se de substituir`YOUR DOCUMENT DIRECTORY` com o caminho real onde seu`SearchAndGetTextFromAll.pdf` é armazenado.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Etapa 2: Abra o documento PDF

 Em seguida, crie uma instância do`Document` classe para carregar seu PDF:

```csharp
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

Esta linha de código abre o arquivo PDF especificado, permitindo que você o manipule posteriormente.

## Etapa 3: Crie um absorvedor de texto

 Agora, você precisará de uma maneira de pesquisar texto dentro desse documento. Para isso, usamos o`TextFragmentAbsorber`:

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

 A expressão regular`@"[\S]+"` foi projetado para corresponder a qualquer sequência de caracteres que não seja espaço em branco no PDF. 

## Etapa 4: Configurar opções de pesquisa de texto

Em seguida, você deve configurar as opções de pesquisa de texto:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

 Aqui, o`true` parâmetro significa que a pesquisa fará distinção entre maiúsculas e minúsculas. Você pode defini-lo como`false` se você quiser uma pesquisa que não diferencie maiúsculas de minúsculas.

## Etapa 5: Aceite o Text Absorber no documento

 Com o seu`TextFragmentAbsorber` e opções de pesquisa prontas, é hora de absorver o texto do documento:

```csharp
document.Pages.Accept(textAbsorber);
```

Este método examina cada página do seu PDF para encontrar fragmentos de texto que correspondam ao padrão especificado.

## Etapa 6: Crie um PdfContentEditor

 Para desenhar formas no documento, você precisará do`PdfContentEditor`:

```csharp
var editor = new PdfContentEditor(document);
```

Este editor permite que você manipule e edite o conteúdo do PDF facilmente.

## Etapa 7: Percorra os fragmentos de texto encontrados

Agora, você vai querer percorrer os fragmentos de texto encontrados para desenhar retângulos ao redor deles:

```csharp
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
    foreach (TextSegment textSegment in textFragment.Segments)
    {
        DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
    }
}
```

 Este loop itera sobre cada fragmento de texto e seus segmentos, chamando um`DrawBox` método para desenho de retângulos.

## Etapa 8: Defina o método DrawBox

 Você precisa definir o`DrawBox` método, que manipulará a lógica de desenho do retângulo. Aqui está uma implementação simples:

```csharp
private static void DrawBox(PdfContentEditor editor, int pageNumber, TextSegment textSegment, System.Drawing.Color color)
{
    // Calcular as dimensões do retângulo com base no segmento de texto
    float x = textSegment.Rectangle.LLX;
    float y = textSegment.Rectangle.LLY;
    float width = textSegment.Rectangle.Width;
    float height = textSegment.Rectangle.Height;

    // Desenhe um retângulo usando os valores calculados
    editor.DrawRectangle(pageNumber, x, y, width, height, color, 1);
}
```

Este método determina a posição e o tamanho do retângulo com base no retângulo delimitador do segmento e usa o editor para desenhá-lo.

## Etapa 9: Salve o documento modificado

Depois de desenhar os retângulos ao redor do texto encontrado, você pode salvar o documento modificado:

```csharp
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
```

Certifique-se de que seu novo arquivo seja salvo com um nome diferente para evitar sobrescrever o documento original.

## Etapa 10: Mensagem de confirmação

Por fim, imprima uma mensagem de confirmação no console para informar que a operação foi bem-sucedida:

```csharp
Console.WriteLine("\nRectangle drawn successfully on searched text.\nFile saved at " + dataDir);
```

E aí está! Você criou com sucesso um script para procurar texto em um PDF e destacá-lo com retângulos.

## Conclusão

Parabéns! Você acabou de desbloquear uma habilidade poderosa que pode melhorar muito suas habilidades de manipulação de PDF usando o Aspose.PDF para .NET. Com apenas alguns passos simples, você pode procurar qualquer texto em seu documento e destacá-lo visualmente, tornando seus documentos PDF mais interativos e gerenciáveis. Não hesite em experimentar diferentes padrões de regex e opções de cores para realmente tornar esta ferramenta sua!

## Perguntas frequentes

### O que é Aspose.PDF para .NET?
Aspose.PDF para .NET é uma biblioteca que fornece uma maneira abrangente de criar, manipular e converter documentos PDF programaticamente.

### Posso usar o Aspose.PDF gratuitamente?
Sim, o Aspose oferece um teste gratuito que você pode usar para testar as funcionalidades da biblioteca. Confira[aqui](https://releases.aspose.com/).

### Qual linguagem de programação preciso usar com o Aspose.PDF para .NET?
O Aspose.PDF para .NET foi projetado para ser usado com C# e outras linguagens .NET.

### Como obtenho ajuda com o Aspose.PDF?
 Você pode visitar o fórum de suporte do Aspose para obter ajuda sobre qualquer problema ou dúvida que você possa ter. Encontre suporte[aqui](https://forum.aspose.com/c/pdf/10).

### Onde posso baixar o Aspose.PDF para .NET?
 Você pode baixar a biblioteca do site da Aspose,[aqui](https://releases.aspose.com/pdf/net/).