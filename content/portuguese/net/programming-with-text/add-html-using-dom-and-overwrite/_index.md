---
title: Adicionar HTML usando DOM e substituição de PDF
linktitle: Adicionar HTML usando DOM e substituir
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como adicionar conteúdo HTML usando DOM e substituição de PDF em Aspose.PDF for .NET.
type: docs
weight: 50
url: /pt/net/programming-with-text/add-html-using-dom-and-overwrite/
---
Este tutorial irá guiá-lo através do processo de adição de conteúdo HTML usando DOM (Document Object Model) em Aspose.PDF para .NET. Além disso, você aprenderá como substituir estilos do conteúdo HTML. O código-fonte C# fornecido demonstra as etapas necessárias.

## Requisitos
Antes de começar, certifique-se de ter o seguinte:

- Visual Studio ou qualquer outro compilador C# instalado em sua máquina.
- Biblioteca Aspose.PDF para .NET. Você pode baixá-lo do site oficial do Aspose ou usar um gerenciador de pacotes como o NuGet para instalá-lo.

## Etapa 1: configurar o projeto
1. Crie um novo projeto C# em seu ambiente de desenvolvimento preferido.
2. Adicione uma referência à biblioteca Aspose.PDF para .NET.

## Etapa 2: importar namespaces necessários
No arquivo de código onde você deseja adicionar o conteúdo HTML, adicione o seguinte usando diretivas na parte superior do arquivo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Etapa 3: definir o diretório do documento e o caminho do arquivo de saída
 No código, localize a linha que diz`string dataDir = "YOUR DOCUMENT DIRECTORY";` e substitua`"YOUR DOCUMENT DIRECTORY"` com o caminho para o diretório onde seus documentos estão armazenados.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Etapa 4: crie um novo objeto Documento
 Instanciar um novo`Document` objeto adicionando a seguinte linha de código:

```csharp
Document doc = new Document();
```

## Etapa 5: adicione uma página ao documento
 Adicione uma nova página ao documento usando o`Add` método do`Pages`coleção. No código fornecido, a nova página é atribuída à variável`page`.

```csharp
Page page = doc.Pages.Add();
```

## Etapa 6: crie um HtmlFragment com o conteúdo HTML
 Instanciar um`HtmlFragment` objeto e forneça o conteúdo HTML desejado. No código fornecido, o conteúdo HTML é atribuído à variável`title`. Você pode modificar o conteúdo HTML conforme necessário.

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

## Etapa 7: substituir os estilos do conteúdo HTML
 Para substituir os estilos do conteúdo HTML, você pode modificar o`TextState` propriedades do`HtmlFragment` objeto. No código fornecido, a família da fonte é alterada para “Arial” e o tamanho da fonte é definido como 20.

```csharp
title. TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

## Passo 8: Definir informações de margem
Ajuste as margens inferior e superior do fragmento HTML, se necessário. No código fornecido, a margem inferior é definida como 10 e a margem superior como 400.

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 400;
```

## Etapa 9: adicione o HtmlFragment à página
 Adicione o`HtmlFragment` objeto à coleção de parágrafos da página.

```csharp
page.Paragraphs.Add(title);
```

## Passo 10: Salve o documento PDF
 Salve o documento PDF usando o`Save` método do`Document` objeto. Especifique o caminho do arquivo de saída definido na Etapa 3.

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

### Exemplo de código-fonte para adicionar HTML usando DOM e substituir usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instanciar objeto Document
Document doc = new Document();
// Adicionar uma página à coleção de páginas do arquivo PDF
Page page = doc.Pages.Add();
// Instancie HtmlFragment com conteúdos HTML
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
//A família de fontes de 'Verdana' será redefinida para 'Arial'
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
// Definir informações da margem inferior
title.Margin.Bottom = 10;
// Definir informações de margem superior
title.Margin.Top = 400;
// Adicionar fragmento HTML à coleção de parágrafos da página
page.Paragraphs.Add(title);
// Salvar arquivo PDF
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
// Salvar arquivo PDF
doc.Save(dataDir);
```

## Conclusão
Você adicionou com êxito conteúdo HTML usando DOM em Aspose.PDF para .NET e substituiu os estilos do conteúdo HTML. O arquivo PDF resultante agora pode ser encontrado no caminho do arquivo de saída especificado.

### Perguntas frequentes

#### P: Qual é o foco deste tutorial?

R: Este tutorial foi desenvolvido para orientá-lo no processo de adição de conteúdo HTML a um documento PDF usando o Document Object Model (DOM) no Aspose.PDF for .NET. Além disso, você aprenderá como substituir estilos do conteúdo HTML, permitindo personalizar sua aparência. O tutorial fornece trechos de código-fonte C# para demonstrar as etapas necessárias.

#### P: Quais namespaces preciso importar para este tutorial?

R: No arquivo de código onde você pretende adicionar conteúdo HTML, importe os seguintes namespaces no início do arquivo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### P: Como especifico o diretório do documento e o caminho do arquivo de saída?

 R: No código, localize a linha`string dataDir = "YOUR DOCUMENT DIRECTORY";` e substitua`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório do seu documento.

#### P: Como posso criar um objeto Document?

 R: Na Etapa 4, você instanciará um novo`Document` objeto usando a seguinte linha de código:

```csharp
Document doc = new Document();
```

#### P: Como adiciono uma página ao documento?

 R: Na Etapa 5, você adicionará uma nova página ao documento usando o`Add` método do`Pages` coleção:

```csharp
Page page = doc.Pages.Add();
```

#### P: Como posso definir conteúdo HTML usando o DOM?

 R: Na Etapa 6, você criará um`HtmlFragment` objeto e atribua o conteúdo HTML desejado a ele. O conteúdo HTML é atribuído à variável`title`:

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

#### P: Como posso substituir os estilos do conteúdo HTML?

 R: Na Etapa 7, você substituirá os estilos do conteúdo HTML modificando o`TextState` propriedades do`HtmlFragment` objeto. Por exemplo, você pode alterar a família da fonte para “Arial” e definir o tamanho da fonte para 20:

```csharp
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

#### P: Posso ajustar a margem do conteúdo HTML?

R: Sim, na Etapa 8, você pode ajustar as margens inferior e superior do fragmento HTML conforme necessário:

```csharp
title.Margin.Bottom = 10;
title.Margin.Top = 400;
```

#### P: Como adiciono o HtmlFragment ao documento PDF?

 R: Na Etapa 9, você adicionará o`HtmlFragment` objeto (`title`) para a coleção de parágrafos da página:

```csharp
page.Paragraphs.Add(title);
```

#### P: Como salvo o documento PDF resultante?

 R: Depois de adicionar o conteúdo HTML e personalizar seus estilos, use o`Save` método do`Document` objeto para salvar o documento PDF:

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

#### P: Qual é a principal conclusão deste tutorial?

R: Seguindo este tutorial, você aprendeu com sucesso como incorporar conteúdo HTML usando o Document Object Model (DOM) no Aspose.PDF for .NET. Além disso, você ganhou a capacidade de substituir estilos para personalizar a aparência do conteúdo HTML no documento PDF resultante.