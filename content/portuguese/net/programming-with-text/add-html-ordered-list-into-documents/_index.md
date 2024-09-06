---
title: Adicionar lista ordenada HTML em documentos
linktitle: Adicionar lista HTMLOrdered em documentos
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda como adicionar uma lista ordenada em HTML a um documento usando o Aspose.PDF para .NET.
type: docs
weight: 30
url: /pt/net/programming-with-text/add-html-ordered-list-into-documents/
---
Neste tutorial, você aprenderá como usar a biblioteca Aspose.PDF for .NET para adicionar uma lista HTML ordenada em um documento. O código fornecido demonstra as etapas necessárias para realizar essa tarefa.

## Requisitos
Antes de começar, certifique-se de ter o seguinte:

- Visual Studio ou qualquer outro compilador C# instalado em sua máquina.
- Biblioteca Aspose.PDF para .NET. Você pode baixá-la do site oficial do Aspose ou usar um gerenciador de pacotes como o NuGet para instalá-la.

## Etapa 1: Configurar o projeto
1. Crie um novo projeto C# no seu ambiente de desenvolvimento preferido.
2. Adicione uma referência à biblioteca Aspose.PDF para .NET.

## Etapa 2: Importar os namespaces necessários
No arquivo de código onde você deseja adicionar a lista ordenada HTML, adicione as seguintes diretivas using no topo do arquivo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Etapa 3: Defina o diretório do documento e o caminho do arquivo de saída
 No código, localize a linha que diz`string dataDir = "YOUR DOCUMENT DIRECTORY";` e substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho para o diretório onde seus documentos estão armazenados.

 Em seguida, localize a linha que diz`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` e substituir`"AddHTMLOrderedListIntoDocuments_out.pdf"` com o nome desejado para o arquivo PDF de saída.

## Etapa 4: Crie um novo objeto Documento
 Instanciar um novo`Document` objeto adicionando a seguinte linha de código:

```csharp
Document doc = new Document();
```

## Etapa 5: Crie um objeto HtmlFragment com o conteúdo HTML
 Instanciar um`HtmlFragment` objeto com o conteúdo HTML que você deseja adicionar ao documento. No código fornecido, o conteúdo HTML é atribuído à variável`t`. Você pode modificar o conteúdo HTML conforme necessário.

```csharp
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li >Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
```

## Etapa 6: Adicionar uma página ao documento
 Adicione uma nova página ao documento usando o`Add` método do`Pages`coleção. No código fornecido, a nova página é atribuída à variável`page`.

```csharp
Page page = doc.Pages.Add();
```

## Etapa 7: adicione o HtmlFragment à página
 Adicione o`HtmlFragment` objetar à página usando o`Add` método do`Paragraphs` coleção.

```csharp
page.Paragraphs.Add(t);
```

## Etapa 8: Salve o documento PDF
 Salve o arquivo PDF resultante usando o`Save` método do`Document` objeto. Especifique o caminho do arquivo de saída que você definiu na Etapa 3.

```csharp
doc.Save(outFile);
```

### Código-fonte de exemplo para Adicionar lista HTMLOrdered em documentos usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// O caminho para o documento de saída.
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
// Instanciar objeto Document
Document doc = new Document();
// Instanciar objeto HtmlFragment com fragmento HTML correspondente
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
// Adicionar página na coleção de páginas
Page page = doc.Pages.Add();
// Adicionar HtmlFragment dentro da página
page.Paragraphs.Add(t);
// Salvar arquivo PDF resultante
doc.Save(outFile);
```

## Conclusão
Você adicionou com sucesso uma lista HTML ordenada em um documento usando Aspose.PDF para .NET. O arquivo PDF resultante agora pode ser encontrado no caminho do arquivo de saída especificado.

Lembre-se de personalizar o conteúdo HTML e ajustar o código de acordo com suas necessidades específicas.

### Perguntas frequentes

#### P: Qual é o propósito deste tutorial?

R: Este tutorial tem como objetivo guiá-lo pelo processo de adicionar uma lista ordenada HTML em um documento usando a biblioteca Aspose.PDF for .NET. Ele fornece instruções passo a passo e trechos de código para ajudar você a realizar essa tarefa.

#### P: Quais namespaces preciso importar para este tutorial?

R: Você precisa importar os seguintes namespaces no topo do seu arquivo de código:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### P: Como especifico o diretório do documento e o caminho do arquivo de saída?

 A: No código, localize a linha`string dataDir = "YOUR DOCUMENT DIRECTORY";` e substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório do seu documento. Além disso, encontre a linha`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` e substituir`"AddHTMLOrderedListIntoDocuments_out.pdf"` com o nome do arquivo PDF de saída desejado.

#### P: Posso personalizar o conteúdo HTML que está sendo adicionado ao documento?

 R: Com certeza! Na Etapa 5, você criará um`HtmlFragment` objeto nomeado`t` que contém o conteúdo HTML. Você pode modificar o conteúdo HTML dentro dos backticks para atender às suas necessidades.

#### P: Como adiciono a lista ordenada HTML a uma página no documento?

 A: Na Etapa 7, você adicionará o`HtmlFragment` objeto (`t` ) para a página usando o`Add` método do`Paragraphs`coleção. Isso integrará perfeitamente a lista ordenada HTML no documento.

#### P: Como faço para salvar o documento PDF resultante?

 R: Depois de adicionar o conteúdo HTML e organizá-lo em uma página, você pode salvar o documento PDF usando o`Save` método do`Document` objeto. Certifique-se de fornecer o caminho correto do arquivo de saída que você definiu anteriormente.

#### P: Você pode fornecer um resumo do código-fonte de exemplo para referência?

A: Certamente! Aqui está uma versão resumida do código-fonte de exemplo fornecido neste tutorial:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
Document doc = new Document();
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
Page page = doc.Pages.Add();
page.Paragraphs.Add(t);
doc.Save(outFile);
```

#### P: Qual é a principal lição deste tutorial?

R: Ao seguir este tutorial, você aprendeu com sucesso como aproveitar a biblioteca Aspose.PDF for .NET para incorporar uma lista ordenada HTML em um documento. Este novo conhecimento pode ser aplicado para aprimorar seus processos de criação e manipulação de documentos.