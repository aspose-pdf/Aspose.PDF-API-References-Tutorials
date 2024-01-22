---
title: Adicionar e pesquisar texto oculto em arquivo PDF
linktitle: Adicionar e pesquisar texto oculto em arquivo PDF
second_title: Referência da API Aspose.PDF para .NET
description: Guia passo a passo para adicionar e pesquisar texto oculto em arquivo PDF usando Aspose.PDF for .NET.
type: docs
weight: 20
url: /pt/net/programming-with-text/add-and-search-hidden-text/
---
Neste tutorial, orientaremos você sobre como adicionar e pesquisar texto oculto em arquivo PDF usando Aspose.PDF for .NET. Siga estas etapas para realizar esta operação facilmente.

## 1. Pré-requisitos

Antes de começar, certifique-se de ter o seguinte:

- Visual Studio ou qualquer outro ambiente de desenvolvimento instalado e configurado.
- Conhecimento básico da linguagem de programação C#.
- Biblioteca Aspose.PDF para .NET instalada. Você pode baixá-lo no site oficial do Aspose.

## 2. Criando o documento PDF com texto oculto

Para começar, use o código a seguir para criar um novo documento PDF contendo texto oculto:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Crie um documento
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
// Definir propriedade de texto - invisível
frag2.TextState.Invisible = true;
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
```

Certifique-se de fornecer o caminho e o nome de arquivo desejados para o documento PDF.

## 3. Procure texto no documento

A seguir, pesquisaremos o texto oculto no documento PDF. Use o seguinte código:

```csharp
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorb = new TextFragmentAbsorber();
absorb.Visit(doc.Pages[1]);
foreach(TextFragment fragment in absorber.TextFragments)
{
//Faça algo com os fragmentos
Console.WriteLine("Text '{0}' at position {1}, invisibility: {2} ",
fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

Isto irá pesquisar o texto oculto na segunda página do documento PDF e exibir as informações relevantes.

### Exemplo de código-fonte para adicionar e pesquisar texto oculto usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//Crie documento com texto oculto
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
//Definir propriedade de texto - invisível
frag2.TextState.Invisible = true;
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
//Pesquisar texto no documento
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
absorber.Visit(doc.Pages[1]);
foreach (TextFragment fragment in absorber.TextFragments)
{
	//Faça algo com fragmentos
	Console.WriteLine("Text '{0}' on pos {1} invisibility: {2} ",
	fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

## Conclusão

Parabéns! Você adicionou e encontrou com sucesso texto oculto em um documento PDF usando Aspose.PDF for .NET. Agora você pode aplicar esse método aos seus próprios projetos para manipular e pesquisar texto oculto em arquivos PDF.

### Perguntas frequentes

#### P: O que é Aspose.PDF para .NET?

R: Aspose.PDF for .NET é uma biblioteca robusta que permite aos desenvolvedores criar, manipular e transformar documentos PDF em aplicativos .NET.

#### P: O texto oculto pode ser usado para fins de marca d'água?

R: Absolutamente! O texto oculto pode servir como um meio eficaz de colocar marcas d'água em documentos PDF, adicionando uma camada extra de segurança.

#### P: É possível revelar texto oculto em um documento PDF?

R: Sim, o processo de busca e revelação de texto oculto em um documento PDF pode ser realizado usando as técnicas descritas neste tutorial.

#### P: Que outras funcionalidades o Aspose.PDF for .NET oferece?

R: Além da manipulação de texto oculto, o Aspose.PDF for .NET oferece uma ampla gama de recursos, incluindo geração de PDF, conversão, criptografia e muito mais.