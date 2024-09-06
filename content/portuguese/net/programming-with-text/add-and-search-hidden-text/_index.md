---
title: Adicionar e pesquisar texto oculto em arquivo PDF
linktitle: Adicionar e pesquisar texto oculto em arquivo PDF
second_title: Referência da API do Aspose.PDF para .NET
description: Guia passo a passo para adicionar e pesquisar texto oculto em arquivo PDF usando Aspose.PDF para .NET.
type: docs
weight: 20
url: /pt/net/programming-with-text/add-and-search-hidden-text/
---
Neste tutorial, mostraremos como adicionar e pesquisar texto oculto em arquivo PDF usando Aspose.PDF para .NET. Siga estas etapas para executar esta operação facilmente.

## 1. Pré-requisitos

Antes de começar, certifique-se de ter o seguinte:

- Visual Studio ou qualquer outro ambiente de desenvolvimento instalado e configurado.
- Conhecimento básico da linguagem de programação C#.
- Biblioteca Aspose.PDF para .NET instalada. Você pode baixá-la do site oficial da Aspose.

## 2. Criando o documento PDF com texto oculto

Para começar, use o seguinte código para criar um novo documento PDF contendo texto oculto:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Criar um documento
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

Certifique-se de fornecer o caminho e o nome do arquivo desejados para o documento PDF.

## 3. Pesquisar texto no documento

Em seguida, pesquisaremos o texto oculto no documento PDF. Use o seguinte código:

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

Isso pesquisará o texto oculto na segunda página do documento PDF e exibirá as informações relevantes.

### Código-fonte de exemplo para Adicionar e pesquisar texto oculto usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//Criar documento com texto oculto
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

Parabéns! Você adicionou e encontrou com sucesso texto oculto em um documento PDF usando o Aspose.PDF para .NET. Agora você pode aplicar esse método aos seus próprios projetos para manipular e pesquisar texto oculto em arquivos PDF.

### Perguntas frequentes

#### P: O que é Aspose.PDF para .NET?

R: Aspose.PDF para .NET é uma biblioteca robusta que permite aos desenvolvedores criar, manipular e transformar documentos PDF em aplicativos .NET.

#### P: Texto oculto pode ser usado para fins de marca d'água?

R: Com certeza! Texto oculto pode servir como um meio eficaz de marcar documentos PDF com marca d'água, adicionando uma camada extra de segurança.

#### P: É possível revelar texto oculto em um documento PDF?

R: Sim, o processo de pesquisar e revelar texto oculto em um documento PDF pode ser realizado usando as técnicas descritas neste tutorial.

#### P: Quais outras funcionalidades o Aspose.PDF para .NET oferece?

R: Além da manipulação de texto oculto, o Aspose.PDF para .NET oferece uma ampla gama de recursos, incluindo geração de PDF, conversão, criptografia e muito mais.