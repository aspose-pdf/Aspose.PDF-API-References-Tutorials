---
title: Riscar palavras
linktitle: Riscar palavras
second_title: Referência da API Aspose.PDF para .NET
description: Este artigo fornece um guia passo a passo para usar o recurso Aspose.PDF for .NET Strike Out Words, incluindo guia passo a passo e explicações
type: docs
weight: 150
url: /pt/net/annotations/strikeoutwords/
---
Aspose.PDF for .NET é uma biblioteca de manipulação e processamento de documentos PDF que oferece vários recursos para criar, modificar e converter arquivos PDF. Um dos recursos úteis que o Aspose.PDF oferece é a capacidade de riscar palavras ou frases em um documento PDF usando código-fonte C#. Neste artigo, forneceremos um guia passo a passo sobre como riscar palavras usando Aspose.PDF for .NET.

## Passo 1: Carregando o documento PDF
O primeiro passo é carregar o documento PDF que deseja modificar. Neste tutorial, carregaremos um documento PDF chamado “input.pdf” da pasta “SEU DIRETÓRIO DE DOCUMENTOS”. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document(dataDir + "input.pdf");
```

## Etapa 2: pesquisando fragmentos de texto
Para riscar palavras ou frases específicas no documento PDF, primeiro você precisa procurá-las. Aspose.PDF fornece uma classe TextFragmentAbsorber que pode ser usada para pesquisar um fragmento de texto específico no documento PDF.

```csharp
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
```

No código acima, procuramos o fragmento de texto “Estoque” no documento PDF. Você pode modificar isso para pesquisar qualquer outra palavra ou frase que deseja eliminar.

## Etapa 3: riscar os fragmentos de texto
Depois de encontrar os fragmentos do texto, o próximo passo é eliminá-los. Aspose.PDF fornece uma classe StrikeOutAnnotation que pode ser usada para criar uma anotação riscada para o fragmento de texto. 

```csharp
Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle((float)textFragment.Position.XIndent, (float)textFragment.Position.YIndent, (float)textFragment.Position.XIndent + (float)textFragment.Rectangle.Width, (float)textFragment.Position.YIndent + (float)textFragment.Rectangle.Height);

StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);
strikeOut.Opacity = .80f;
strikeOut.Border = new Border(strikeOut);
strikeOut.Color = Aspose.Pdf.Color.Red;
textFragment.Page.Annotations.Add(strikeOut);
```

No código acima, estamos criando uma anotação riscada para cada fragmento de texto que encontramos. Também estamos definindo a opacidade, a borda e a cor da anotação riscada.

## Passo 4: Salvando o documento PDF modificado
Após riscar os fragmentos do texto, salve o documento modificado.

```csharp
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

### Exemplo de código-fonte para Strike Out Words usando Aspose.PDF para .NET


```csharp

// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Abrir documento
Document document = new Document(dataDir + "input.pdf");

// Crie uma instância do TextFragment Absorber para pesquisar um fragmento de texto específico
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
// Iterar pelas páginas do documento PDF
for (int i = 1; i <= document.Pages.Count; i++)
{
	// Obtenha a primeira página do documento PDF
	Page page = document.Pages[1];
	page.Accept(textFragmentAbsorber);
}

// Crie uma coleção de texto absorvido
Aspose.Pdf.Text.TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

//Iterar na coleção acima
for (int j = 1; j <= textFragmentCollection.Count; j++)
{
	Aspose.Pdf.Text.TextFragment textFragment = textFragmentCollection[j];

	// Obtenha dimensões retangulares do objeto TextFragment
	Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle(
				(float)textFragment.Position.XIndent,
				(float)textFragment.Position.YIndent,
				(float)textFragment.Position.XIndent +
				(float)textFragment.Rectangle.Width,
				(float)textFragment.Position.YIndent +
				(float)textFragment.Rectangle.Height);

	// Instanciar instância de anotação StrikeOut
	StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);
	// Definir opacidade para anotação
	strikeOut.Opacity = .80f;
	// Defina a borda para a instância de anotação
	strikeOut.Border = new Border(strikeOut);
	// Defina a cor da anotação
	strikeOut.Color = Aspose.Pdf.Color.Red;
	// Adicionar anotação à coleção de anotações de TextFragment
	textFragment.Page.Annotations.Add(strikeOut);
}
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

## Conclusão

Neste tutorial, aprendemos como usar Aspose.PDF for .NET para riscar palavras específicas em um documento PDF. Seguindo o guia passo a passo e usando o código-fonte C# fornecido, você pode facilmente carregar um documento PDF, pesquisar fragmentos de texto específicos e criar anotações riscadas para marcar e riscar visualmente essas palavras. Aspose.PDF for .NET fornece uma maneira simples e eficaz de manipular documentos PDF de forma programática, tornando-o uma ferramenta valiosa para desenvolvedores que trabalham com arquivos PDF em aplicativos .NET.

### Perguntas frequentes

#### P: O que é Aspose.PDF para .NET?

R: Aspose.PDF for .NET é uma biblioteca poderosa que permite aos desenvolvedores criar, editar e manipular documentos PDF programaticamente em aplicativos .NET. Ele oferece uma ampla gama de recursos para trabalhar com arquivos PDF, incluindo extração de texto, tratamento de anotações, preenchimento de formulários e muito mais.

#### P: Posso usar o Aspose.PDF for .NET para riscar palavras específicas em um documento PDF?

R: Sim, o Aspose.PDF for .NET fornece funcionalidade para pesquisar fragmentos de texto específicos em um documento PDF e, em seguida, criar anotações tachadas para marcar e riscar visualmente essas palavras.

#### P: Como especifico o texto que desejo riscar no documento PDF?

 R: Para especificar o texto que deseja riscar, você pode usar o`TextFragmentAbsorber` classe fornecida por Aspose.PDF para .NET. Ele permite que você pesquise um fragmento de texto específico no documento PDF com base nos critérios desejados.

#### P: Posso personalizar a aparência da anotação riscada?

R: Sim, você pode personalizar várias propriedades da anotação riscada, como opacidade, estilo de borda e cor. Isso permite personalizar a aparência da anotação riscada de acordo com seus requisitos específicos.