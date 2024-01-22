---
title: Paradas de tabulação personalizadas em arquivo PDF
linktitle: Paradas de tabulação personalizadas em arquivo PDF
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como criar paradas de tabulação personalizadas em arquivo PDF usando Aspose.PDF para .NET.
type: docs
weight: 120
url: /pt/net/programming-with-text/custom-tab-stops/
---

Este tutorial irá guiá-lo através do processo de criação de paradas de tabulação personalizadas em arquivo PDF usando Aspose.PDF para .NET. O código-fonte C# fornecido demonstra as etapas necessárias.

## Requisitos
Antes de começar, certifique-se de ter o seguinte:

- Visual Studio ou qualquer outro compilador C# instalado em sua máquina.
- Biblioteca Aspose.PDF para .NET. Você pode baixá-lo do site oficial do Aspose ou usar um gerenciador de pacotes como o NuGet para instalá-lo.

## Etapa 1: configurar o projeto
1. Crie um novo projeto C# em seu ambiente de desenvolvimento preferido.
2. Adicione uma referência à biblioteca Aspose.PDF para .NET.

## Etapa 2: importar namespaces necessários
No arquivo de código onde você deseja criar paradas de tabulação personalizadas, adicione o seguinte usando diretivas na parte superior do arquivo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Etapa 3: definir o diretório do documento
 No código, localize a linha que diz`string dataDir = "YOUR DOCUMENT DIRECTORY";` e substitua`"YOUR DOCUMENT DIRECTORY"` com o caminho para o diretório onde seus documentos estão armazenados.

## Etapa 4: crie uma nova instância de documento
 Instanciar um novo`Document` objeto adicionando a seguinte linha de código:

```csharp
Document _pdfdocument = new Document();
```

## Etapa 5: adicione uma página ao documento
 Adicione uma nova página ao documento usando o`Add` método do`Pages`coleção. No código fornecido, a nova página é atribuída à variável`page`.

```csharp
Page page = _pdfdocument.Pages.Add();
```

## Etapa 6: criar paradas de tabulação personalizadas
 Criar uma`TabStops` objeto e adicionar paradas de tabulação personalizadas a ele. Defina o tipo de alinhamento e o tipo de linha de chamada para cada parada de tabulação.

```csharp
TabStops ts = new TabStops();
TabStop ts1 = ts.Add(100);
ts1.AlignmentType = TabAlignmentType.Right;
ts1.LeaderType = TabLeaderType.Solid;

TabStop ts2 = ts.Add(200);
ts2.AlignmentType = TabAlignmentType.Center;
ts2.LeaderType = TabLeaderType.Dash;

TabStop ts3 = ts.Add(300);
ts3.AlignmentType = TabAlignmentType.Left;
ts3.LeaderType = TabLeaderType.Dot;
```

## Etapa 7: crie fragmentos de texto com tabulações
 Criar`TextFragment` objetos e passar as paradas de tabulação personalizadas para eles. Use os caracteres especiais`#$TAB` para indicar as paradas de tabulação no texto.

```csharp
TextFragment header = new TextFragment("This is an example of forming a table with TAB stops", ts);
TextFragment text0 = new TextFragment("#$TABHead1 #$TABHead2 #$TABHead3", ts);
TextFragment text1 = new TextFragment("#$TABdata11 #$TABdata12 #$TABdata13", ts);
TextFragment text2 = new TextFragment("#$TABdata21 ", ts);
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data22 "));
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data23"));

page.Paragraphs.Add(header);
page.Paragraphs.Add(text0);
page.Paragraphs.Add(text1);
page.Paragraphs.Add(text2);
```

## Passo 8: Salve o documento PDF
 Salve o documento PDF usando o`Save` método do`Document` objeto.

```csharp
_pdfdocument.Save(dataDir);
Console.WriteLine("\nCustom tab stops setup successfully.\nFile saved at " + dataDir);
```

### Exemplo de código-fonte para paradas de tabulação personalizadas usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document _pdfdocument = new Document();
Page page = _pdfdocument.Pages.Add();
Aspose.Pdf.Text.TabStops ts = new Aspose.Pdf.Text.TabStops();
Aspose.Pdf.Text.TabStop ts1 = ts.Add(100);
ts1.AlignmentType = TabAlignmentType.Right;
ts1.LeaderType = TabLeaderType.Solid;
Aspose.Pdf.Text.TabStop ts2 = ts.Add(200);
ts2.AlignmentType = TabAlignmentType.Center;
ts2.LeaderType = TabLeaderType.Dash;
Aspose.Pdf.Text.TabStop ts3 = ts.Add(300);
ts3.AlignmentType = TabAlignmentType.Left;
ts3.LeaderType = TabLeaderType.Dot;
TextFragment header = new TextFragment("This is a example of forming table with TAB stops", ts);
TextFragment text0 = new TextFragment("#$TABHead1 #$TABHead2 #$TABHead3", ts);
TextFragment text1 = new TextFragment("#$TABdata11 #$TABdata12 #$TABdata13", ts);
TextFragment text2 = new TextFragment("#$TABdata21 ", ts);
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data22 "));
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data23"));
page.Paragraphs.Add(header);
page.Paragraphs.Add(text0);
page.Paragraphs.Add(text1);
page.Paragraphs.Add(text2);
dataDir = dataDir + "CustomTabStops_out.pdf";
_pdfdocument.Save(dataDir);
Console.WriteLine("\nCustom tab stops setup successfully.\nFile saved at " + dataDir);
```

## Conclusão
Você criou com sucesso um documento PDF com tabulações personalizadas usando Aspose.PDF para .NET. O arquivo PDF resultante agora pode ser encontrado no caminho do arquivo de saída especificado.

### Perguntas frequentes

#### P: Qual é o foco deste tutorial?

R: Este tutorial se concentra em orientá-lo no processo de criação de paradas de tabulação personalizadas em um arquivo PDF usando a biblioteca Aspose.PDF para .NET. O código-fonte C# fornecido demonstra as etapas necessárias para conseguir isso.

#### P: Quais namespaces devo importar para este tutorial?

R: No arquivo de código onde você deseja criar paradas de tabulação personalizadas, importe os seguintes namespaces no início do arquivo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### P: Como especifico o diretório do documento?

 R: No código, encontre a linha`string dataDir = "YOUR DOCUMENT DIRECTORY";` e substitua`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório do seu documento.

#### P: Como posso criar uma nova instância de Documento?

 R: Na Etapa 4, você instanciará um novo`Document` objeto usando o código fornecido.

#### P: Como adiciono uma página ao documento?

 R: Na Etapa 5, você adicionará uma nova página ao documento usando o`Add` método do`Pages` coleção.

#### P: Como posso criar paradas de tabulação personalizadas?

 R: Na Etapa 6, você criará um`TabStops` objeto e adicionar paradas de tabulação personalizadas a ele. Você também definirá o alinhamento e os tipos de linha de chamada para cada parada de tabulação.

#### P: Como posso criar fragmentos de texto com tabulações?

 R: Na Etapa 7, você criará`TextFragment` objetos e passar as paradas de tabulação personalizadas para eles. Você usará os caracteres especiais`#$TAB` para indicar as paradas de tabulação no texto.

#### P: Como faço para salvar o documento PDF?

 R: Na Etapa 8, você salvará o documento PDF usando o`Save` método do`Document` objeto.

#### P: Qual é a principal conclusão deste tutorial?

R: Seguindo este tutorial, você aprendeu como criar um documento PDF com tabulações personalizadas usando Aspose.PDF para .NET. Isso pode ser útil para organizar e alinhar texto de maneira estruturada.