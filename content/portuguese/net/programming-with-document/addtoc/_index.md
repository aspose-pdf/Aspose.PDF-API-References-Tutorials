---
title: Adicionar sumário ao arquivo PDF
linktitle: Adicionar sumário ao arquivo PDF
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como adicionar um índice a um arquivo PDF usando Aspose.PDF for .NET. Guia passo a passo com exemplo de código-fonte. Aumente a navegação de documentos!
type: docs
weight: 40
url: /pt/net/programming-with-document/addtoc/
---
Neste tutorial, exploraremos como usar o recurso Adicionar TOC (Índice) ao arquivo PDF do Aspose.PDF for .NET para adicionar um índice a documentos PDF. Forneceremos um guia passo a passo e explicaremos o código-fonte C# necessário para conseguir isso. Ao final deste tutorial, você será capaz de gerar um documento PDF com um índice usando Aspose.PDF for .NET.


## Passo 1: Carregue o arquivo PDF existente

 Para começar, precisamos carregar um arquivo PDF existente. Substituir`"YOUR DOCUMENT DIRECTORY"` no código a seguir com o caminho real para o seu arquivo PDF:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "AddTOC.pdf");
```

## Etapa 2: crie uma nova página para o índice

Criaremos uma nova página para conter o índice. O código a seguir insere uma nova página no índice 1:

```csharp
Page tocPage = doc.Pages.Insert(1);
```

## Etapa 3: definir as informações do índice

Em seguida, precisamos definir as informações do índice. Definiremos o título e outras propriedades do índice analítico. Adicione o seguinte código:

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;

tocInfo.Title = title;
tocPage.TocInfo = tocInfo;
```

## Etapa 4: criar elementos do sumário

Agora, criaremos os elementos do índice analítico. Neste tutorial, criaremos quatro elementos TOC correspondentes a páginas diferentes. Modifique o seguinte código de acordo com seus requisitos:

```csharp
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";

for (int i = 0; i < 2; i++)
{
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);

    heading2.DestinationPage = doc.Pages[i + 2];
    heading2.Top = doc.Pages[i + 2].Rect.Height;

    segment2.Text = titles[i];
    tocPage.Paragraphs.Add(heading2);
}
```

## Etapa 5: salve o documento atualizado

 Finalmente, precisamos salvar o documento modificado com o índice analítico. Substituir`"YOUR DOCUMENT DIRECTORY"` no código abaixo com o caminho do arquivo de saída desejado:

```csharp
dataDir = dataDir + "TOC_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

### Exemplo de código-fonte para adicionar sumário a documentos PDF usando Aspose.PDF para .NET

```csharp

// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Carregar arquivos PDF existentes
Document doc = new Document(dataDir + "AddTOC.pdf");

// Obtenha acesso à primeira página do arquivo PDF
Page tocPage = doc.Pages.Insert(1);

// Crie um objeto para representar informações do TOC
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;

// Defina o título do TOC
tocInfo.Title = title;
tocPage.TocInfo = tocInfo;

//Crie objetos string que serão usados como elementos TOC
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";
for (int i = 0; i < 2; i++)
{
	// Criar objeto de título
	Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
	TextSegment segment2 = new TextSegment();
	heading2.TocPage = tocPage;
	heading2.Segments.Add(segment2);

	// Especifique a página de destino para o objeto de título
	heading2.DestinationPage = doc.Pages[i + 2];

	// Página de destino
	heading2.Top = doc.Pages[i + 2].Rect.Height;

	// Coordenada de destino
	segment2.Text = titles[i];

	// Adicionar título à página que contém o sumário
	tocPage.Paragraphs.Add(heading2);
}
dataDir = dataDir + "TOC_out.pdf";
// Salve o documento atualizado
doc.Save(dataDir);

Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

## Conclusão

Neste tutorial, exploramos como adicionar um índice analítico (TOC) a documentos PDF usando Aspose.PDF for .NET. Seguindo o guia passo a passo e utilizando o código-fonte C# fornecido, você pode gerar facilmente um documento PDF com um índice analítico. O sumário melhora a usabilidade do documento, permitindo que os usuários naveguem para seções ou páginas específicas com mais eficiência. Aspose.PDF for .NET fornece uma solução robusta e fácil de usar para trabalhar com arquivos PDF em aplicativos .NET, permitindo criar documentos PDF dinâmicos e interativos com facilidade.

### Perguntas frequentes sobre como adicionar sumário ao arquivo PDF

#### P: O que é Aspose.PDF para .NET?

R: Aspose.PDF for .NET é uma biblioteca poderosa que permite aos desenvolvedores trabalhar com arquivos PDF em aplicativos .NET de maneira eficaz. Ele fornece uma ampla gama de recursos para criar, manipular e gerenciar documentos PDF de forma programática.

#### P: Qual é o propósito de adicionar um sumário (TOC) a um documento PDF?

R: O sumário (TOC) fornece um auxílio à navegação para os usuários, permitindo que eles pulem rapidamente para seções ou páginas específicas do documento PDF. Melhora a usabilidade do documento e a experiência do usuário.

#### P: Como adiciono um índice a um documento PDF usando Aspose.PDF for .NET?

R: Para adicionar um índice a um documento PDF usando Aspose.PDF for .NET, você precisa criar uma nova página para conter o índice, definir as informações do índice e, em seguida, criar elementos do índice que correspondam a páginas específicas ou seções do documento.

#### P: Posso personalizar a aparência do índice?

R: Sim, você pode personalizar a aparência do índice definindo várias propriedades dos elementos do sumário, como tamanho da fonte, estilo da fonte e alinhamento. Aspose.PDF for .NET oferece flexibilidade no design do TOC para combinar com a aparência desejada.

#### P: O Aspose.PDF for .NET é adequado para adicionar recursos avançados a documentos PDF?

R: Com certeza, Aspose.PDF for .NET é uma biblioteca rica em recursos que permite adicionar funcionalidades avançadas a documentos PDF, incluindo elementos interativos, campos de formulário, assinaturas digitais e muito mais.