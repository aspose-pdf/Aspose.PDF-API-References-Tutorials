---
title: Pesquisar texto e desenhar retângulo
linktitle: Pesquisar texto e desenhar retângulo
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda a pesquisar texto em um PDF, desenhar retângulos ao redor do texto encontrado e salvar o documento modificado usando o Aspose.PDF para .NET.
type: docs
weight: 460
url: /pt/net/programming-with-text/search-text-and-draw-rectangle/
---
Este tutorial explica como usar o Aspose.PDF for .NET para pesquisar texto específico em um documento PDF, desenhar um retângulo ao redor do texto encontrado e salvar o documento modificado. O código-fonte C# fornecido demonstra o processo passo a passo.

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
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
```

## Etapa 3: Defina o caminho para o diretório do documento

 Defina o caminho para o diretório do seu documento usando o`dataDir` variável:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório do seu documento.

## Etapa 4: Carregue o documento PDF

 Carregue o documento PDF usando o`Document` aula:

```csharp
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 Substituir`"SearchAndGetTextFromAll.pdf"` com o nome real do seu arquivo PDF.

## Etapa 5: Crie um TextFragmentAbsorber

 Criar um`TextFragmentAbsorber` objeto para encontrar todas as instâncias da frase de pesquisa de entrada:

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

 Substituir`@"[\S]+"` com o padrão de expressão regular desejado.

## Etapa 6: Habilitar pesquisa de expressão regular

 Habilite a pesquisa de expressão regular definindo o`TextSearchOptions` propriedade do absorvedor:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

## Etapa 7: Pesquisar em todas as páginas

Aceite o absorvedor para todas as páginas do documento:

```csharp
document.Pages.Accept(textAbsorber);
```

## Etapa 8: desenhe um retângulo ao redor do texto encontrado

 Criar um`PdfContentEditor` objeto e percorrer os fragmentos de texto recuperados, desenhando um retângulo ao redor de cada segmento de texto:

```csharp
var editor = new PdfContentEditor(document);
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
    foreach (TextSegment textSegment in textFragment.Segments)
    {
        DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
    }
}
```

## Etapa 9: Salve o documento modificado

Salve o documento modificado:

```csharp
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
```

 Certifique-se de substituir`"SearchTextAndDrawRectangle_out.pdf"` com o nome do arquivo de saída desejado.

### Código-fonte de exemplo para Pesquisar texto e desenhar retângulo usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
//Crie um objeto TextAbsorber para encontrar todas as frases que correspondem à expressão regular
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
document.Pages.Accept(textAbsorber); 
var editor = new PdfContentEditor(document); 
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
			DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
	}
}
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
Console.WriteLine("\nRectangle drawn successfully on searched text.\nFile saved at " + dataDir);
```

## Conclusão

Parabéns! Você aprendeu com sucesso como pesquisar texto específico em um documento PDF, desenhar um retângulo ao redor do texto encontrado e salvar o documento modificado usando o Aspose.PDF para .NET. Este tutorial forneceu um guia passo a passo, desde a configuração do projeto até a execução das ações necessárias. Agora você pode incorporar este código em seus próprios projetos C# para manipular texto e desenhar retângulos em arquivos PDF.

### Perguntas frequentes

#### P: Qual é o objetivo do tutorial "Pesquisar texto e desenhar retângulo"?

R: O tutorial "Search Text And Draw Rectangle" tem como objetivo guiar os usuários pelo processo de uso da biblioteca Aspose.PDF para .NET para pesquisar texto específico em um documento PDF, desenhar retângulos ao redor dos segmentos de texto encontrados e salvar o documento modificado. O tutorial fornece instruções detalhadas e exemplos de código C# para ilustrar cada etapa do processo.

#### P: Como este tutorial ajuda a desenhar retângulos ao redor de um texto específico em um documento PDF?

R: Este tutorial fornece um guia abrangente sobre como localizar e desenhar retângulos ao redor de segmentos de texto específicos dentro de um documento PDF. Ele demonstra o processo de configuração de um projeto, carregamento de um documento PDF, habilitação de pesquisa de expressão regular, desenho de retângulos ao redor de segmentos de texto encontrados e salvamento do PDF modificado.

#### P: Quais são os pré-requisitos necessários para seguir este tutorial?

R: Antes de começar o tutorial, você deve ter um entendimento básico da linguagem de programação C#. Além disso, você precisa ter a biblioteca Aspose.PDF for .NET instalada. Você pode obtê-la no site da Aspose ou instalá-la em seu projeto usando o NuGet.

#### P: Como configuro meu projeto para seguir este tutorial?

R: Comece criando um novo projeto C# no seu ambiente de desenvolvimento integrado (IDE) preferido. Em seguida, adicione uma referência à biblioteca Aspose.PDF for .NET ao seu projeto. Isso permitirá que você use a funcionalidade da biblioteca para manipular documentos PDF.

#### P: Posso desenhar retângulos ao redor de um texto específico usando este tutorial?

R: Sim, o tutorial foca em desenhar retângulos ao redor de segmentos de texto específicos dentro de um documento PDF. Ele demonstra como localizar o texto desejado usando expressões regulares, criar retângulos ao redor dos segmentos de texto identificados e salvar o PDF modificado.

#### P: Como posso especificar o texto que desejo pesquisar e desenhar retângulos ao redor?

 R: Para especificar o texto que você deseja pesquisar e desenhar retângulos ao redor, crie um`TextFragmentAbsorber` objeto e definir seu padrão usando o`Text` parâmetro. Substitua o padrão padrão`@"[\S]+"` no código do tutorial com o padrão de expressão regular desejado.

#### P: Como habilito a pesquisa de expressão regular para texto?

 A: A pesquisa de expressão regular é habilitada pela criação de um`TextSearchOptions` objeto e definindo seu valor para`true` . Atribua este objeto ao`TextSearchOptions` propriedade do`TextFragmentAbsorber` instância. Isso garante que o padrão de expressão regular seja usado durante a pesquisa de texto.

#### P: Como desenho retângulos ao redor do texto encontrado?

 A: Após identificar os segmentos de texto usando o`TextFragmentAbsorber` , o tutorial fornece um loop para iterar por esses segmentos. Para cada segmento de texto, o tutorial demonstra como criar um retângulo ao redor dele usando o`DrawBox` método e especifique a aparência do retângulo.

#### P: Quais são as etapas para salvar o PDF modificado com retângulos desenhados?

A: Depois de desenhar retângulos ao redor dos segmentos de texto desejados, use o`Document` classe`Save` método para salvar o documento modificado. O código de exemplo do tutorial mostra como salvar o PDF editado e exibir uma mensagem de sucesso.

#### P: Posso personalizar a aparência dos retângulos desenhados?

 R: Sim, você pode personalizar a aparência dos retângulos desenhados. No código de exemplo do tutorial, o`DrawBox` O método é usado para criar retângulos. Você pode modificar propriedades como cor, estilo e espessura para personalizar a aparência dos retângulos desenhados.