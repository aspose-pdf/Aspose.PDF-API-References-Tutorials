---
title: Criar PDF com várias colunas
linktitle: Criar PDF com várias colunas
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda a criar um PDF com várias colunas usando o Aspose.PDF para .NET.
type: docs
weight: 110
url: /pt/net/programming-with-text/create-multi-column-pdf/
---
Este tutorial guiará você pelo processo de criação de um PDF multicoluna usando Aspose.PDF para .NET. O código-fonte C# fornecido demonstra as etapas necessárias.

## Requisitos
Antes de começar, certifique-se de ter o seguinte:

- Visual Studio ou qualquer outro compilador C# instalado em sua máquina.
- Biblioteca Aspose.PDF para .NET. Você pode baixá-la do site oficial do Aspose ou usar um gerenciador de pacotes como o NuGet para instalá-la.

## Etapa 1: Configurar o projeto
1. Crie um novo projeto C# no seu ambiente de desenvolvimento preferido.
2. Adicione uma referência à biblioteca Aspose.PDF para .NET.

## Etapa 2: Importar os namespaces necessários
No arquivo de código onde você deseja criar um PDF com várias colunas, adicione as seguintes diretivas using no topo do arquivo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

## Etapa 3: Defina o diretório do documento
 No código, localize a linha que diz`string dataDir = "YOUR DOCUMENT DIRECTORY";` e substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho para o diretório onde seus documentos estão armazenados.

## Etapa 4: Crie uma nova instância de Documento
 Instanciar um novo`Document` objeto adicionando a seguinte linha de código:

```csharp
Document doc = new Document();
```

## Etapa 5: Defina as margens da página
 Especifique as informações de margem esquerda e direita para o arquivo PDF usando o`PageInfo.Margin` propriedade do`Document`.

```csharp
doc.PageInfo.Margin.Left = 40;
doc.PageInfo.Margin.Right = 40;
```

## Etapa 6: Adicionar uma página ao documento
 Adicione uma nova página ao documento usando o`Add` método do`Pages`coleção. No código fornecido, a nova página é atribuída à variável`page`.

```csharp
Page page = doc.Pages.Add();
```

## Etapa 7: Crie um objeto Graph e adicione uma linha
 Criar um novo`Graph` objeto com dimensões específicas e adicione uma linha a ele. Em seguida, adicione o`Graph` objetar ao`Paragraphs` coleção da página.

```csharp
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500, 2);
float[] backPos = new float[] { 1, 2, 500, 2 };
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
page.Paragraphs.Add(graph1);
```

## Etapa 8: adicione texto de título com formatação HTML
 Criar um`HtmlFragment` objeto e defina seu conteúdo para o texto HTML desejado. Em seguida, adicione o fragmento ao`Paragraphs` coleção da página.

```csharp
string s = "<font face=\"Times New Roman\" size=4>" +
     "<strong>How to Steer Clear of money scams</<strong>" +
     "</font>";
HtmlFragment heading_text = new HtmlFragment(s);
page.Paragraphs.Add(heading_text);
```

## Etapa 9: Crie um FloatingBox com várias colunas
 Criar um`FloatingBox` objeto e defina o número de colunas e o espaçamento entre colunas. Em seguida, adicione fragmentos de texto e uma linha ao`Paragraphs` coleção do`FloatingBox`.

```csharp
Aspose.Pdf.FloatingBox box = new Aspose.Pdf.FloatingBox();
box. ColumnInfo. ColumnCount = 2;
box.ColumnInfo.ColumnSpacing = "5";
box.ColumnInfo.ColumnWidths = "105 105";

TextFragment text1 = new TextFragment("By A Googling (The Official Google Blog)");
text1.TextState.FontSize = 8;
text1.TextState.LineSpacing = 2;
box.Paragraphs.Add(text1);

TextFragment text2 = new TextFragment("Sed augue tortor, sodales id, luctus et, pulvinar ut, eros. Suspendisse vel dolor. Sed quam. Curabitur ut massa vitae eros euismod aliquam...");
box.Paragraphs.Add(text2);

Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50, 10);
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
box.Paragraphs.Add(graph2);

page.Paragraphs.Add(box);
```

## Etapa 10: Salve o documento PDF
 Salve o documento PDF usando o`Save` método do`Document` objeto.

```csharp
doc.Save(dataDir);
```

### Código-fonte de exemplo para criar PDF com várias colunas usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
//Especifique as informações da margem esquerda do arquivo PDF
doc.PageInfo.Margin.Left = 40;
// Especifique as informações da margem direita para o arquivo PDF
doc.PageInfo.Margin.Right = 40;
Page page = doc.Pages.Add();
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500, 2);
// Adicione a linha à coleção de paráfrases do objeto de seção
page.Paragraphs.Add(graph1);
// Especifique as coordenadas para a linha
float[] posArr = new float[] { 1, 2, 500, 2 };
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
// Crie variáveis de string com texto contendo tags HTML
string s = "<font face=\"Times New Roman\" size=4>" +
"<strong> How to Steer Clear of money scams</<strong> "
+ "</font>";
// Crie parágrafos de texto contendo texto HTML
HtmlFragment heading_text = new HtmlFragment(s);
page.Paragraphs.Add(heading_text);
Aspose.Pdf.FloatingBox box = new Aspose.Pdf.FloatingBox();
// Adicione quatro colunas na seção
box.ColumnInfo.ColumnCount = 2;
// Defina o espaçamento entre as colunas
box.ColumnInfo.ColumnSpacing = "5";
box.ColumnInfo.ColumnWidths = "105 105";
TextFragment text1 = new TextFragment("By A Googler (The Official Google Blog)");
text1.TextState.FontSize = 8;
text1.TextState.LineSpacing = 2;
box.Paragraphs.Add(text1);
text1.TextState.FontSize = 10;
text1.TextState.FontStyle = FontStyles.Italic;
// Crie um objeto de gráfico para desenhar uma linha
Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50, 10);
// Especifique as coordenadas para a linha
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
// Adicione a linha à coleção de parágrafos do objeto de seção
box.Paragraphs.Add(graph2);
TextFragment text2 = new TextFragment(@"Sed augue tortor, sodales id, luctus et, pulvinar ut, eros. Suspendisse vel dolor. Sed quam. Curabitur ut massa vitae eros euismod aliquam. Pellentesque sit amet elit. Vestibulum interdum pellentesque augue. Cras mollis arcu sit amet purus. Donec augue. Nam mollis tortor a elit. Nulla viverra nisl vel mauris. Vivamus sapien. nascetur ridiculus mus. Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et,nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et, semper sed, enim nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Sed urna. . Duis convallis ultrices nisi. Maecenas non ligula. Nunc nibh est, tincidunt in, placerat sit amet, vestibulum a, nulla. Praesent porttitor turpis eleifend ante. Morbi sodales.nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Sed urna. . Duis convallis ultrices nisi. Maecenas non ligula. Nunc nibh est, tincidunt in, placerat sit amet, vestibulum a, nulla. Praesent porttitor turpis eleifend ante. Morbi sodales.");
box.Paragraphs.Add(text2);
page.Paragraphs.Add(box);
dataDir = dataDir + "CreateMultiColumnPdf_out.pdf";
// Salvar arquivo PDF
doc.Save(dataDir);
Console.WriteLine("\nMulti column pdf file created successfully.\nFile saved at " + dataDir);
```

## Conclusão
Você criou com sucesso um PDF multicoluna usando Aspose.PDF para .NET. O arquivo PDF resultante agora pode ser encontrado no caminho de arquivo de saída especificado.

### Perguntas frequentes

#### P: Qual é o foco deste tutorial?

Este tutorial é focado em guiar você pelo processo de criação de um PDF multicoluna usando a biblioteca Aspose.PDF for .NET. O código-fonte C# fornecido demonstra as etapas necessárias para atingir isso.

#### P: Quais namespaces devo importar para este tutorial?

R: No arquivo de código onde você deseja criar um PDF com várias colunas, importe os seguintes namespaces no início do arquivo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

#### P: Como especifico o diretório do documento?

 A: No código, encontre a linha`string dataDir = "YOUR DOCUMENT DIRECTORY";` e substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório do seu documento.

#### P: Como crio uma nova instância de Documento?

 R: Na Etapa 4, você instanciará um novo`Document` objeto usando o código fornecido.

#### P: Como defino as margens da página?

 A: Na Etapa 5, você usará o`PageInfo.Margin` propriedade do`Document` para especificar as informações de margem esquerda e direita do arquivo PDF.

#### P: Como adiciono uma página ao documento?

 R: Na Etapa 6, você adicionará uma nova página ao documento usando o`Add` método do`Pages` coleção.

#### P: Como crio um objeto Graph e adiciono uma linha?

 R: Na Etapa 7, você criará um novo`Graph` objeto, adicione uma linha a ele e, em seguida, adicione o`Graph` objetar ao`Paragraphs` coleção da página.

#### P: Como adiciono texto de título com formatação HTML?

 R: Na Etapa 8, você criará um`HtmlFragment` objeto e defina seu conteúdo para o texto HTML desejado e, em seguida, adicione o fragmento ao`Paragraphs` coleção da página.

#### P: Como posso criar um FloatingBox com várias colunas?

 A: Na Etapa 9, você criará um`FloatingBox` objeto com várias colunas e espaçamento entre colunas, em seguida, adicione fragmentos de texto e uma linha ao`Paragraphs` coleção do`FloatingBox`.

#### P: Como faço para salvar o documento PDF?

 R: Na Etapa 10, você salvará o documento PDF usando o`Save` método do`Document` objeto.

#### P: Qual é o principal aprendizado deste tutorial?

R: Ao seguir este tutorial, você aprendeu a criar um documento PDF com várias colunas usando o Aspose.PDF para .NET. Isso pode ser útil para exibir conteúdo em um layout estruturado e organizado.