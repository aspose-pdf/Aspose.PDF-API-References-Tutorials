---
title: Pesquisar texto e adicionar hiperlink
linktitle: Pesquisar texto e adicionar hiperlink
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda a pesquisar texto em um PDF, adicionar hiperlinks ao texto encontrado e salvar o documento modificado usando o Aspose.PDF para .NET.
type: docs
weight: 450
url: /pt/net/programming-with-text/search-text-and-add-hyperlink/
---
Este tutorial explica como usar o Aspose.PDF for .NET para pesquisar texto específico em um documento PDF, adicionar um hiperlink ao texto encontrado e salvar o documento modificado. O código-fonte C# fornecido demonstra o processo passo a passo.

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
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Text;
```

## Etapa 3: Defina o caminho para o diretório do documento

 Defina o caminho para o diretório do seu documento usando o`dataDir` variável:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório do seu documento.

## Etapa 4: Crie um TextFragmentAbsorber

 Criar um`TextFragmentAbsorber` objeto para encontrar todas as instâncias da frase de pesquisa de entrada:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
```

 Substituir`"\\d{4}-\\d{4}"` com o padrão de expressão regular desejado.

## Etapa 5: Habilitar pesquisa de expressão regular

 Habilite a pesquisa de expressão regular definindo o`TextSearchOptions` propriedade do absorvedor:

```csharp
absorber.TextSearchOptions = new TextSearchOptions(true);
```

## Etapa 6: Abra e encaderne o documento PDF

 Criar um`PdfContentEditor` objeto e vinculá-lo ao arquivo PDF de origem:

```csharp
PdfContentEditor editor = new PdfContentEditor();
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
```

 Substituir`"SearchRegularExpressionPage.pdf"` com o nome real do seu arquivo PDF.

## Etapa 7: Aceite o absorvedor para a página

Aceite o absorvedor para a página desejada do documento:

```csharp
editor.Document.Pages[1].Accept(absorber);
```

 Substituir`1` com o número de página desejado.

## Etapa 8: adicione hiperlinks ao texto encontrado

Percorra os fragmentos de texto recuperados e adicione hiperlinks a eles:

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
    // Crie um retângulo com base na posição do fragmento de texto
    System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
        (int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
        (int)Math.Round(textFragment.Rectangle.Height + 1));
    //Adicione um link da web ao retângulo
    editor.CreateWebLink(rect, "http://www.aspose.com", 1, System.Drawing.Color.Blue);
}
```

 Substituir`"http://www.aspose.com"` com o URL do hiperlink desejado.

## Etapa 9: Salve e feche o documento modificado

Salve o documento modificado e feche o editor:

```csharp
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

 Certifique-se de substituir`"SearchTextAndAddHyperlink_out.pdf"` com o nome do arquivo de saída desejado.

### Código-fonte de exemplo para Pesquisar texto e adicionar hiperlink usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crie um objeto absorvedor para encontrar todas as instâncias da frase de pesquisa de entrada
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
// Habilitar pesquisa de expressão regular
absorber.TextSearchOptions = new TextSearchOptions(true);
// Abrir documento
PdfContentEditor editor = new PdfContentEditor();
// Vincular arquivo PDF de origem
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
// Aceite o absorvedor para a página
editor.Document.Pages[1].Accept(absorber);
int[] dashArray = { };
String[] LEArray = { };
System.Drawing.Color blue = System.Drawing.Color.Blue;
// Percorrer os fragmentos
foreach (TextFragment textFragment in absorber.TextFragments)
{
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
		(int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
		(int)Math.Round(textFragment.Rectangle.Height + 1));
	Enum[] actionName = new Enum[2] { Aspose.Pdf.Annotations.PredefinedAction.Document_AttachFile, Aspose.Pdf.Annotations.PredefinedAction.Document_ExtractPages };
	editor.CreateWebLink(rect, "http:// Www.aspose.com", 1, azul, actionName);
	editor.CreateLine(rect, "", (float)textFragment.Rectangle.LLX + 1, (float)textFragment.Rectangle.LLY - 1,
		(float)textFragment.Rectangle.URX, (float)textFragment.Rectangle.LLY - 1, 1, 1, blue, "S", dashArray, LEArray);
}
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

## Conclusão

Parabéns! Você aprendeu com sucesso como pesquisar texto específico em um documento PDF, adicionar hiperlinks ao texto encontrado e salvar o documento modificado usando o Aspose.PDF para .NET. Este tutorial forneceu um guia passo a passo, desde a configuração do projeto até a execução das ações necessárias. Agora você pode incorporar este código em seus próprios projetos C# para manipular texto e adicionar hiperlinks em arquivos PDF.

### Perguntas frequentes

#### P: Qual é o objetivo do tutorial "Pesquisar texto e adicionar hiperlink"?

R: O tutorial "Pesquisar texto e adicionar hiperlink" tem como objetivo demonstrar como usar a biblioteca Aspose.PDF para .NET para pesquisar texto específico em um documento PDF, adicionar hiperlinks ao texto encontrado e salvar o documento modificado. O tutorial fornece um guia abrangente e exemplos de código C# para ilustrar o processo passo a passo.

#### P: Como este tutorial ajuda a adicionar hiperlinks para texto específico em um documento PDF?

R: Este tutorial o guia pelo processo de uso da biblioteca Aspose.PDF para localizar texto específico em um documento PDF, aplicar um hiperlink ao texto identificado e salvar o PDF modificado. Ele abrange etapas essenciais, como configurar o projeto, carregar o documento, habilitar a pesquisa de expressão regular e adicionar hiperlinks ao texto encontrado.

#### P: Quais são os pré-requisitos necessários para seguir este tutorial?

R: Antes de começar, você deve ter um entendimento básico da linguagem de programação C#. Além disso, você precisa ter a biblioteca Aspose.PDF for .NET instalada, que pode ser obtida no site da Aspose ou instalada usando o NuGet no seu projeto.

#### P: Como configuro meu projeto para seguir este tutorial?

R: Comece criando um novo projeto C# no seu ambiente de desenvolvimento integrado (IDE) preferido. Em seguida, adicione uma referência à biblioteca Aspose.PDF for .NET, o que permitirá que você utilize os recursos da biblioteca no seu projeto.

#### P: Posso adicionar hiperlinks para um texto específico usando este tutorial?

R: Sim, este tutorial foca especificamente em adicionar hiperlinks para texto específico em um documento PDF. Ele demonstra como encontrar e extrair o texto desejado usando expressões regulares, criar hiperlinks associados aos fragmentos de texto e salvar o PDF modificado.

#### P: Como defino o texto que desejo pesquisar e adiciono um hiperlink?

 R: Para especificar o texto que você deseja pesquisar e adicionar um hiperlink, crie um`TextFragmentAbsorber` objeto e definir seu padrão usando o`Text` parâmetro. Substitua o padrão padrão`"\\d{4}-\\d{4}"` no código do tutorial com o padrão de expressão regular desejado.

#### P: Como posso habilitar a pesquisa de expressão regular para texto?

 A: A pesquisa de expressão regular é habilitada pela criação de um`TextSearchOptions` objeto e definindo seu valor para`true` . Atribua este objeto ao`TextSearchOptions` propriedade do`TextFragmentAbsorber` instância. Isso garante que o padrão de expressão regular seja aplicado durante a pesquisa de texto.

#### P: Como adiciono hiperlinks ao texto encontrado?

 A: Após identificar os fragmentos de texto usando o`TextFragmentAbsorber` , o tutorial fornece um loop para iterar por esses fragmentos. Para cada fragmento de texto, o tutorial demonstra como definir a cor do texto para azul e criar um hiperlink usando o`CreateWebLink` método.

#### P: Quais são as etapas para salvar o PDF modificado com hiperlinks?

 A: Após adicionar hiperlinks aos fragmentos de texto desejados, use o`PdfContentEditor` class para salvar o documento modificado. O código de exemplo do tutorial mostra como salvar o PDF editado, fechar o editor e exibir uma mensagem de sucesso.