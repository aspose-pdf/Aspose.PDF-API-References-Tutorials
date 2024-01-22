---
title: Remover hiperlinks após converter de HTML
linktitle: Remover hiperlinks após converter de HTML
second_title: Referência da API Aspose.PDF para .NET
description: Guia passo a passo para remover hiperlinks após converter HTML em PDF usando Aspose.PDF for .NET.
type: docs
weight: 250
url: /pt/net/document-conversion/remove-hyperlinks-after-converting-from-html/
---
Neste tutorial, orientaremos você no processo de remoção de hiperlinks de um arquivo PDF gerado a partir de um arquivo HTML usando Aspose.PDF for .NET. Hiperlinks são links clicáveis que podem redirecionar para outras páginas ou sites. Seguindo as etapas abaixo, você poderá remover hiperlinks do arquivo PDF resultante.

## Pré-requisitos
Antes de começar, certifique-se de atender aos seguintes pré-requisitos:

- Conhecimento básico da linguagem de programação C#.
- Biblioteca Aspose.PDF para .NET instalada em seu sistema.
- Um ambiente de desenvolvimento como o Visual Studio.

## Etapa 1: Carregar arquivo HTML e remover hiperlinks
Nesta etapa, carregaremos o arquivo HTML e removeremos os hiperlinks do documento PDF resultante. Use o seguinte código:

```csharp
// Caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Carregue o arquivo HTML usando as opções de carregamento de HTML
Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());

// Navegue pelas anotações da primeira página do documento
foreach(Annotation a in doc.Pages[1].Annotations)
{
     // Verifique se a anotação é um link
     if (a.AnnotationType == AnnotationType.Link)
     {
         LinkAnnotation the = (LinkAnnotation)a;
        
         // Verifique se a ação é do tipo GoToURIAction
         if (the.Action is GoToURIAction)
         {
             GoToURIAction gta = (GoToURIAction)the.Action;
             gta.URI = "";
            
             // Use um absorvedor de fragmentos de texto para encontrar fragmentos de texto correspondentes
             TextFragmentAbsorber tfa = new TextFragmentAbsorber();
             tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
             doc.Pages[a.PageIndex].Accept(tfa);
            
             // Percorrer fragmentos de texto correspondentes e remover atributos de hiperlinks
             foreach(TextFragment tf in tfa.TextFragments)
             {
                 tf.TextState.Underline = false;
                 tf.TextState.ForegroundColor = Color.Black;
             }
         }
        
         // Remover a anotação da página
         doc.Pages[a.PageIndex].Annotations.Delete(a);
     }
}
```

 Certifique-se de substituir`"YOUR DOCUMENTS DIRECTORY"` com o diretório real onde seu arquivo HTML está localizado.

## Passo 2: Salvando o arquivo PDF resultante
Por fim, salvaremos o arquivo PDF resultante sem os hiperlinks. Use o seguinte código:

```csharp
// Salve o arquivo PDF resultante
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

 O código acima salva o arquivo PDF resultante com o nome do arquivo`"RemoveHyperlinksFromText_out.pdf"`.

### Exemplo de código-fonte para remover hiperlinks após a conversão de HTML usando Aspose.PDF para .NET

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());
doc.Save(new MemoryStream());
foreach (Annotation a in doc.Pages[1].Annotations)
{
	if (a.AnnotationType == AnnotationType.Link)
	{
		LinkAnnotation la = (LinkAnnotation)a;
		if (la.Action is GoToURIAction)
		{
			GoToURIAction gta = (GoToURIAction)la.Action;
			gta.URI = "";
			TextFragmentAbsorber tfa = new TextFragmentAbsorber();
			tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
			doc.Pages[a.PageIndex].Accept(tfa);
			foreach (TextFragment tf in tfa.TextFragments)
			{
				tf.TextState.Underline = false;
				tf.TextState.ForegroundColor = Color.Black;
			}
		}
		doc.Pages[a.PageIndex].Annotations.Delete(a);
	}
}
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

## Conclusão
Neste tutorial, cobrimos o processo passo a passo de remoção de hiperlinks de um arquivo PDF gerado a partir de um arquivo HTML usando Aspose.PDF for .NET. Seguindo as instruções descritas acima, você poderá remover hiperlinks do arquivo PDF resultante.

### Perguntas frequentes

#### P: O que é Aspose.PDF para .NET?

R: Aspose.PDF for .NET é uma biblioteca poderosa que permite aos desenvolvedores trabalhar com documentos PDF em aplicativos C#. Oferece uma ampla gama de funcionalidades, incluindo a capacidade de converter arquivos HTML em PDF e manipular conteúdo PDF.

#### P: Por que eu desejaria remover hiperlinks de um arquivo PDF?

R: Existem vários motivos para remover hiperlinks de um arquivo PDF. Por exemplo, você pode querer eliminar links externos para fins de impressão ou arquivamento ou garantir que o conteúdo do PDF não seja navegável por meio de hiperlinks.

#### P: Como posso carregar um arquivo HTML e remover hiperlinks usando Aspose.PDF for .NET?

 R: Para carregar um arquivo HTML e remover hiperlinks, você pode usar Aspose.PDF para .NET`HtmlLoadOptions` aula. Itere pelas anotações das páginas PDF para encontrar anotações de link e modificar seus atributos.

#### P: Posso personalizar o nome do arquivo de saída do PDF resultante?

R: Sim, você pode personalizar o nome do arquivo de saída do arquivo PDF resultante, modificando o código que salva o documento PDF. Basta alterar o nome do arquivo desejado no`doc.Save()` método.

#### P: É possível remover hiperlinks seletivamente com base em determinados critérios?

R: Sim, você pode remover hiperlinks seletivamente com base em critérios específicos. Por exemplo, você pode optar por remover apenas links externos ou links que apontam para URLs específicos.