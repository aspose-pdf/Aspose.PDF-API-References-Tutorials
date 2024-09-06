---
title: Adicionar recuo de linhas subsequentes em arquivo PDF
linktitle: Adicionar recuo de linhas subsequentes em arquivo PDF
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda como adicionar recuo de linhas subsequentes ao texto em um arquivo PDF usando o Aspose.PDF para .NET.
type: docs
weight: 60
url: /pt/net/programming-with-text/add-subsequent-lines-indent/
---
Este tutorial guiará você pelo processo de adicionar recuo de linhas subsequentes ao texto em um arquivo PDF usando Aspose.PDF para .NET. O código-fonte C# fornecido demonstra as etapas necessárias.

## Requisitos
Antes de começar, certifique-se de ter o seguinte:

- Visual Studio ou qualquer outro compilador C# instalado em sua máquina.
- Biblioteca Aspose.PDF para .NET. Você pode baixá-la do site oficial do Aspose ou usar um gerenciador de pacotes como o NuGet para instalá-la.

## Etapa 1: Configurar o projeto
1. Crie um novo projeto C# no seu ambiente de desenvolvimento preferido.
2. Adicione uma referência à biblioteca Aspose.PDF para .NET.

## Etapa 2: Importar os namespaces necessários
No arquivo de código onde você deseja adicionar recuo às linhas subsequentes, adicione a seguinte diretiva using no topo do arquivo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Etapa 3: Defina o diretório do documento
 No código, localize a linha que diz`string dataDir = "YOUR DOCUMENT DIRECTORY";` e substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho para o diretório onde seus documentos estão armazenados.

## Etapa 4: Crie um novo objeto Documento
 Instanciar um novo`Document` objeto adicionando a seguinte linha de código:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

## Etapa 5: Adicionar uma página ao documento
 Adicione uma nova página ao documento usando o`Add` método do`Pages`coleção. No código fornecido, a nova página é atribuída à variável`page`.

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

## Etapa 6: Crie um TextFragment com recuo nas linhas subsequentes
 Instanciar um`TextFragment` objeto e fornecer o texto desejado. No código fornecido, o texto é atribuído à variável`text` . Então, inicialize`TextFormattingOptions` para o`TextFragment` especificar o`SubsequentLinesIndent` valor.

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog." );
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
     SubsequentLinesIndent = 20
};
```

## Etapa 7: adicione o TextFragment à página
 Adicione o`TextFragment` objetar à coleção de parágrafos da página.

```csharp
page.Paragraphs.Add(text);
```

## Etapa 8: Repita as etapas 6 e 7 para linhas adicionais
Para adicionar linhas subsequentes com o mesmo recuo, repita as etapas 6 e 7 para cada linha. Atualize o conteúdo do texto conforme necessário.

```csharp
text = new Aspose.Pdf.Text.TextFragment("Line2");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line3");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line4");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line5");
page.Paragraphs.Add(text);
```

## Etapa 9: Salve o documento PDF
 Salve o documento PDF usando o`Save` método do`Document` objeto. Especifique o caminho do arquivo de saída.

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### Código-fonte de exemplo para Adicionar recuo de linhas subsequentes usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Criar novo objeto de documento
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = document.Pages.Add();
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog.");
// Inicie TextFormattingOptions para o fragmento de texto e especifique o valor SubsequentLinesIndent
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
	SubsequentLinesIndent = 20
};
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line2");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line3");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line4");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line5");
page.Paragraphs.Add(text);
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

## Conclusão
Você adicionou com sucesso o recuo de linhas subsequentes ao texto usando Aspose.PDF para .NET. O arquivo PDF resultante agora pode ser encontrado no caminho do arquivo de saída especificado.

### Perguntas frequentes

#### P: Qual é o foco deste tutorial?

R: Este tutorial fornece um guia abrangente sobre como adicionar recuo de linhas subsequentes ao texto em um arquivo PDF usando a biblioteca Aspose.PDF para .NET. Ele inclui exemplos de código-fonte C# para ilustrar as etapas necessárias para atingir isso.

#### P: Quais namespaces preciso importar para este tutorial?

R: No arquivo de código onde você pretende adicionar recuo às linhas subsequentes, importe os seguintes namespaces no início do arquivo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### P: Como especifico o diretório do documento?

 A: No código, localize a linha`string dataDir = "YOUR DOCUMENT DIRECTORY";` e substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório do seu documento.

#### P: Como crio um objeto Documento?

 R: Na Etapa 4, você instanciará um novo`Document` objeto usando a seguinte linha de código:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

#### P: Como adiciono uma página ao documento?

 R: Na Etapa 5, você adicionará uma nova página ao documento usando o`Add` método do`Pages` coleção:

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

#### P: Como posso adicionar recuo de linhas subsequentes ao texto?

 A: Na Etapa 6, você criará um`TextFragment` objeto e atribuir o texto desejado a ele. Então, você inicializará`TextFormattingOptions` para o`TextFragment` especificar o`SubsequentLinesIndent` valor:

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("Your text here");
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
    SubsequentLinesIndent = 20
};
```

#### P: Como adiciono o TextFragment ao documento PDF?

 A: Na Etapa 7, você adicionará o`TextFragment` objeto (`text`) para a coleção de parágrafos da página:

```csharp
page.Paragraphs.Add(text);
```

#### P: Posso repetir o processo para linhas adicionais?

 R: Sim, na Etapa 8, você pode repetir o processo para linhas adicionais com o mesmo recuo, criando novas`TextFragment` objetos e adicioná-los à coleção de parágrafos da página.

#### P: Como faço para salvar o documento PDF resultante?

 A: Após adicionar o texto com recuo de linhas subsequentes, use o`Save` método do`Document` objeto para salvar o documento PDF:

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

#### P: Qual é a principal lição deste tutorial?

R: Ao seguir este tutorial, você aprendeu com sucesso como melhorar a legibilidade do texto em um documento PDF adicionando recuo de linhas subsequentes usando Aspose.PDF para .NET. Esta técnica pode ser útil para vários tipos de documentos e relatórios.