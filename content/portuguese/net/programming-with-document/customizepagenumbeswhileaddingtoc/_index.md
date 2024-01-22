---
title: Personalize os números das páginas ao adicionar o TOC
linktitle: Personalize os números das páginas ao adicionar o TOC
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como personalizar números de página ao adicionar um índice analítico (TOC) usando Aspose.PDF para .NET com este guia passo a passo e exemplo de código.
type: docs
weight: 100
url: /pt/net/programming-with-document/customizepagenumbeswhileaddingtoc/
---
Neste tutorial, exploraremos como personalizar os números das páginas ao adicionar um índice analítico (TOC) usando Aspose.PDF para .NET. Forneceremos orientação passo a passo, juntamente com um exemplo de código, para ajudá-lo a conseguir isso.

## Passo 1: Carregando um arquivo PDF existente

Primeiro, precisamos carregar um arquivo PDF existente. Para este tutorial, usaremos o arquivo “42824.pdf” localizado no diretório “SEU DIRETÓRIO DE DOCUMENTOS”. Substitua este caminho de diretório pelo caminho real para seu diretório de documentos.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "42824.pdf";
string outFile = dataDir + "42824_out.pdf";
Document doc = new Document(inFile);
```

## Etapa 2: adicionar uma página de sumário

 Em seguida, precisamos adicionar uma nova página no início do documento para servir como página do sumário. Podemos conseguir isso usando o`Insert()` método do`Pages` coleção do`Document` objeto.

```csharp
Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
```

## Etapa 3: Criando um objeto TOC

 Para criar um objeto TOC, primeiro precisamos criar um`TocInfo` objeto e definir suas propriedades. Neste tutorial, definiremos o título do sumário como “Índice” e o prefixo do número da página como “P”.

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocInfo.PageNumbersPrefix = "P";
tocPage.TocInfo = tocInfo;
```

## Etapa 4: Criando entradas de sumário

Para criar entradas de sumário, precisamos percorrer todas as páginas do documento, exceto a página de sumário, e criar um objeto de título para cada página. Podemos então adicionar o objeto de título à página do sumário e especificar sua página de destino.

```csharp
for (int i = 1; i < doc.Pages.Count; i++)
{
    // Criar objeto de título
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);
    // Especifique a página de destino para o objeto de título
    heading2.DestinationPage = doc.Pages[i + 1];
    // Página de destino
    heading2.Top = doc.Pages[i + 1].Rect.Height;
    // Coordenada de destino
    segment2.Text = "Page " + i.ToString();
    // Adicionar título à página que contém o sumário
    tocPage.Paragraphs.Add(heading2);
}
```

## Passo 5: Salvando o documento atualizado

Finalmente, precisamos salvar o documento atualizado em um novo arquivo. Podemos conseguir isso usando o`Save()` método do`Document` objeto.

```csharp
doc.Save(outFile);
```

### Exemplo de código-fonte para personalizar números de páginas ao adicionar sumário usando Aspose.PDF para .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "42824.pdf";
string outFile = dataDir + "42824_out.pdf";
// Carregar arquivos PDF existentes
Document doc = new Document(inFile);
// Obtenha acesso à primeira página do arquivo PDF
Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
// Crie um objeto para representar informações do TOC
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
// Defina o título do TOC
tocInfo.Title = title;
tocInfo.PageNumbersPrefix = "P";
tocPage.TocInfo = tocInfo;
for (int i = 1; i<doc.Pages.Count; i++)
{
	// Criar objeto de título
	Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
	TextSegment segment2 = new TextSegment();
	heading2.TocPage = tocPage;
	heading2.Segments.Add(segment2);
	// Especifique a página de destino para o objeto de título
	heading2.DestinationPage = doc.Pages[i + 1];
	// Página de destino
	heading2.Top = doc.Pages[i + 1].Rect.Height;
	// Coordenada de destino
	segment2.Text = "Page " + i.ToString();
	// Adicionar título à página que contém o sumário
	tocPage.Paragraphs.Add(heading2);
}

// Salve o documento atualizado
doc.Save(outFile);
```

## Conclusão

Neste tutorial, fornecemos orientação passo a passo sobre como personalizar números de página ao adicionar um sumário usando Aspose.PDF para .NET. Também fornecemos um exemplo de código que você pode usar como referência ao implementar esse recurso em seu

### Perguntas frequentes

#### P: O que é um sumário (TOC) em um documento PDF?

R: Um índice analítico (TOC) em um documento PDF é um auxílio à navegação que fornece uma lista organizada de seções ou capítulos do documento junto com seus números de página correspondentes. Ele permite que os leitores naveguem rapidamente para seções específicas do documento.

#### P:Por que eu desejaria personalizar os números das páginas em um sumário?

R: Personalizar números de página em um sumário pode ser útil quando você deseja usar um formato de numeração de página específico ou incluir informações adicionais junto com os números de página. Ele permite que você crie um índice mais personalizado e informativo.

#### P: Posso incluir hiperlinks no sumário para vincular seções ou páginas específicas do documento PDF?

R: Sim, o Aspose.PDF for .NET permite que você crie hiperlinks no sumário que direcionam para seções ou páginas específicas do documento PDF. Isso melhora a interatividade e a navegação do documento PDF.

#### P: O Aspose.PDF for .NET é compatível com os padrões PDF/A?

R: Sim, Aspose.PDF for .NET suporta padrões PDF/A, incluindo PDF/A-1, PDF/A-2 e PDF/A-3. Ele permite que você crie documentos PDF que atendam aos requisitos de arquivamento e preservação de longo prazo.

#### P: Posso adicionar mais formatação às entradas do sumário, como estilos de fonte ou cores?

R: Sim, você pode adicionar formatação adicional às entradas do sumário, como estilos de fonte, cores e tamanhos de fonte, usando Aspose.PDF para .NET. Isso permite que você personalize a aparência do sumário de acordo com suas necessidades.
