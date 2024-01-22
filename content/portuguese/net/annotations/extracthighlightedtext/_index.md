---
title: Extraia texto destacado em arquivo PDF
linktitle: Extraia texto destacado em arquivo PDF
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como extrair texto destacado em arquivo PDF usando Aspose.PDF for .NET com este guia passo a passo.
type: docs
weight: 60
url: /pt/net/annotations/extracthighlightedtext/
---
Para extrair o texto destacado em um arquivo PDF, você pode usar a API Aspose.PDF for .NET. Esta API fornece uma maneira simples de recuperar todo o texto destacado em um documento.

## Passo 1: Carregue o documento PDF

 A primeira etapa para extrair o texto destacado em um arquivo PDF é carregar o documento usando a API Aspose.PDF for .NET. Você pode fazer isso criando uma nova instância do`Document` class e passando o caminho para o documento PDF como parâmetro. 

```csharp
// O caminho para o diretório de documentos.
string dataDir ="YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");
```

## Etapa 2: percorrer todas as anotações

 A próxima etapa é percorrer todas as anotações no documento PDF. Você pode fazer isso usando um`foreach` loop, assim:

```csharp
foreach (Annotation annotation in doc.Pages[1].Annotations)
{
	// O código vai aqui
}
```

## Etapa 3: filtrar anotações de marcação de texto

 Dentro de`foreach` loop, você precisará filtrar todas as anotações que não sejam anotações de marcação de texto. Você pode fazer isso verificando se a anotação é uma instância do`TextMarkupAnnotation` aula.

```csharp
if (annotation is TextMarkupAnnotation)
{
	// O código vai aqui
}
```

## Etapa 4: recuperar fragmentos de texto destacados

 Depois de filtrar todas as anotações de marcação de texto, você poderá recuperar os fragmentos de texto destacados para cada anotação. Você pode fazer isso ligando para o`GetMarkedTextFragments()` método no`TextMarkupAnnotation` objeto.

```csharp
TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
```

## Etapa 5: exibir o texto destacado

 Finalmente, você pode exibir o texto destacado para o usuário. Você pode fazer isso percorrendo cada`TextFragment` objeto no`TextFragmentCollection` e ligando para o`Text` propriedade.

```csharp
foreach (TextFragment tf in collection)
{
	Console.WriteLine(tf.Text);
}
```

### Exemplo de código-fonte para extrair texto destacado usando Aspose.PDF para .NET

```csharp
// O caminho para o diretório de documentos.
string dataDir ="YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");

foreach (Annotation annotation in doc.Pages[1].Annotations)
{
	if (annotation is TextMarkupAnnotation)
	{
		TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
		TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
		foreach (TextFragment tf in collection)
		{
			Console.WriteLine(tf.Text);
		}
	}
}
```

## Conclusão

Neste tutorial, exploramos como extrair texto destacado de um documento PDF usando Aspose.PDF for .NET. Seguindo o guia passo a passo e usando o código-fonte C# fornecido, os desenvolvedores podem extrair e gerenciar facilmente o texto destacado em seus documentos PDF.

### Perguntas frequentes para extrair texto destacado em arquivo PDF

#### P: O que são anotações de marcação de texto em um documento PDF?

R: As anotações de marcação de texto são anotações que destacam ou marcam um texto específico em um documento PDF. Exemplos de anotações de marcação de texto incluem destaques, sublinhados e tachados.

#### P: Posso extrair texto de outros tipos de anotações usando Aspose.PDF for .NET?

R: Sim, o Aspose.PDF for .NET fornece vários métodos para extrair texto de diferentes tipos de anotações, incluindo anotações de marcação de texto, anotações de texto livre e muito mais.

#### P: O Aspose.PDF for .NET oferece suporte à extração de texto de arquivos PDF protegidos por senha?

 R: Sim, Aspose.PDF for .NET suporta a extração de texto de arquivos PDF protegidos por senha. Você precisa fornecer a senha correta ao carregar o documento PDF usando o`Document` aula.

#### P: Posso filtrar o texto destacado com base em outros critérios, como cor ou autor?

R: Sim, você pode filtrar o texto destacado com base em outros critérios, como cor, autor ou data de criação. Aspose.PDF for .NET fornece métodos para acessar e filtrar anotações com base em suas propriedades.

#### P: É possível salvar o texto destacado extraído em um arquivo separado?

R: Sim, você pode salvar o texto destacado extraído em um arquivo separado ou armazená-lo em uma estrutura de dados para processamento ou análise posterior.
