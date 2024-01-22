---
title: Obtenha destinos de hiperlink em arquivo PDF
linktitle: Obtenha destinos de hiperlink em arquivo PDF
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como extrair destinos de hiperlinks em arquivos PDF usando Aspose.PDF para .NET.
type: docs
weight: 60
url: /pt/net/programming-with-links-and-actions/get-hyperlink-destinations/
---
Aspose.PDF for .NET é uma biblioteca poderosa para manipular e extrair informações em arquivos PDF usando a linguagem de programação C#. Neste tutorial, vamos nos concentrar na extração de destinos de hiperlinks de um arquivo PDF usando Aspose.PDF for .NET.

## Pré-requisitos

Antes de começar, certifique-se de ter o seguinte:

- Um ambiente de desenvolvimento integrado (IDE), como o Visual Studio.
- A biblioteca Aspose.PDF para .NET instalada em sua máquina.

## Etapa 1: Configurando o ambiente de desenvolvimento

Antes de começar a escrever código, você precisa configurar seu ambiente de desenvolvimento criando um novo projeto C# em seu IDE favorito.

## Etapa 2: importar referências Aspose.PDF

Para usar Aspose.PDF for .NET, você precisa adicionar as referências apropriadas ao seu projeto. Siga as etapas abaixo para importar as referências necessárias:

1. No seu projeto, clique com o botão direito em “Referências” e selecione “Adicionar Referência”.
2. Na janela "Adicionar referência", localize e selecione os arquivos DLL do Aspose.PDF para .NET.
3. Clique em “OK” para importar as referências para o seu projeto.

## Passo 3: Carregando o arquivo PDF

Antes de extrair destinos de hiperlinks, você deve carregar o arquivo PDF em seu aplicativo. Use o seguinte código para carregar o arquivo PDF:

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Carregue o arquivo PDF
Document document = new Document(dataDir + "input.pdf");
```

Certifique-se de especificar o caminho correto para o diretório do documento e o arquivo PDF que deseja processar.

## Passo 4: Navegando pelas páginas do documento

Agora que o arquivo PDF foi carregado, você precisa percorrer todas as páginas do documento. Isso permitirá que você obtenha

nas anotações de hiperlink presentes em cada página. Use o seguinte código para percorrer as páginas do documento:

```csharp
foreach(Aspose.Pdf.Page page in document.Pages)
{
     // Obtenha as anotações do link de uma página específica
     AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
     page. Accept(selector);
     // Crie uma lista para armazenar todos os links
     IList<Annotation> list = selector. Selected;
     // Percorra cada item da lista
     foreach(LinkAnnotation a in list)
     {
         // Imprimir URL de destino
         Console.WriteLine("\nDestination: " + (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI + "\n");
     }
}
```

Este código percorre cada página do documento e seleciona as anotações de hiperlink presentes em cada página. Em seguida, ele armazena essas anotações em uma lista e imprime a URL de destino de cada link.

## Etapa 5: Obtendo destinos de hiperlink

A última etapa é extrair os destinos do hiperlink das anotações do hiperlink. O código a seguir mostra como fazer isso:

```csharp
foreach(Aspose.Pdf.Page page in document.Pages)
{
     AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
     page. Accept(selector);
     IList<Annotation> list = selector. Selected;
     foreach(LinkAnnotation a in list)
     {
         string destination = (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI;
         // Use o destino como desejar
     }
}
```

Neste código, obtemos cada destino de hiperlink das anotações do link e armazenamos o destino em uma variável. Você pode então usar esse destino como desejar em seu aplicativo.

### Exemplo de código-fonte para obter destinos de hiperlink usando Aspose.PDF para .NET 
```csharp
try
{
	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Carregue o arquivo PDF
	Document document = new Document(dataDir + "input.pdf");
	// Percorra toda a página do PDF
	foreach (Aspose.Pdf.Page page in document.Pages)
	{
		// Obtenha as anotações do link de uma página específica
		AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
		page.Accept(selector);
		// Crie uma lista contendo todos os links
		IList<Annotation> list = selector.Selected;
		// Iterar através do item invidiaul dentro da lista
		foreach (LinkAnnotation a in list)
		{
			// Imprima o URL de destino
			Console.WriteLine("\nDestination: " + (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI + "\n");
		}
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

### Perguntas frequentes para obter destinos de hiperlinks em arquivo PDF

#### P: O que é um destino de hiperlink em um arquivo PDF?

R: Um destino de hiperlink em um arquivo PDF é um local ou destino específico para o qual um hiperlink aponta. Pode ser um URL, uma página do mesmo documento ou um documento externo.

#### P: Como a extração de destinos de hiperlinks pode beneficiar minha análise de documentos PDF?

R: A extração de destinos de hiperlinks permite identificar e catalogar todos os destinos para os quais os hiperlinks apontam em um documento PDF. Essas informações podem ser úteis para validação de conteúdo, verificação de links e análise de dados.

#### P: Como o Aspose.PDF for .NET ajuda na extração de destinos de hiperlinks?

R: Aspose.PDF for .NET fornece APIs poderosas para extrair destinos de hiperlinks com facilidade. Este tutorial demonstra passo a passo como extrair destinos de hiperlinks usando C#.

#### P: Posso extrair seletivamente destinos de hiperlinks com base em determinados critérios?

R: Sim, você pode extrair seletivamente destinos de hiperlinks iterando pelas páginas do documento PDF e filtrando as anotações de hiperlink desejadas com base em seus critérios.

#### P: É possível extrair destinos de hiperlinks de documentos PDF protegidos por senha?

R: Aspose.PDF for .NET pode extrair destinos de hiperlinks de documentos PDF protegidos por senha, desde que você forneça as credenciais de autenticação necessárias ao abrir o documento.

#### P: Como posso utilizar os destinos de hiperlink extraídos em meu aplicativo?

R: Depois de extrair os destinos dos hiperlinks, você poderá usá-los para executar diversas ações, como validar URLs de links, criar relatórios ou implementar navegação personalizada.

#### P: Há alguma limitação ao extrair destinos de hiperlinks?

R: Embora a extração de destino de hiperlink seja poderosa, é essencial considerar a estrutura do documento PDF. Hiperlinks incorporados em gráficos complexos ou conteúdo multimídia podem exigir manuseio adicional.

#### P: Posso extrair outros atributos de hiperlinks, como tipos de links ou coordenadas?

R: O tutorial se concentra na extração de destinos de hiperlinks. No entanto, você pode consultar a documentação oficial do Aspose.PDF para explorar recursos avançados, incluindo a extração de tipos de links e coordenadas.