---
title: Pesquisar e obter página de texto em arquivo PDF
linktitle: Pesquisar e obter página de texto em arquivo PDF
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda como pesquisar e obter texto de uma página específica em um arquivo PDF usando o Aspose.PDF para .NET.
type: docs
weight: 430
url: /pt/net/programming-with-text/search-and-get-text-page/
---
## Introdução

Você já se viu precisando procurar por um texto específico dentro de um documento PDF e extraí-lo para uso posterior? Talvez você esteja construindo um aplicativo que processa documentos e requer extração precisa de dados, ou talvez você só precise analisar PDFs de forma eficiente. Seja qual for o seu caso, você está no lugar certo! Neste tutorial, vamos nos aprofundar em como pesquisar e obter texto de uma página em um arquivo PDF usando o Aspose.PDF para .NET. Seja você um iniciante ou um desenvolvedor experiente, este guia o guiará por cada etapa de uma maneira conversacional e envolvente. Pronto para começar? Vamos começar!

## Pré-requisitos

Antes de começarmos a codificar, vamos garantir que você tenha tudo o que precisa:

1.  Biblioteca Aspose.PDF para .NET: Você pode baixá-la em[aqui](https://releases.aspose.com/pdf/net/) ou obtenha uma versão de teste gratuita no mesmo link. Para comprar, vá para o[Loja Aspose](https://purchase.aspose.com/buy).
2. .NET Framework: você precisará de um ambiente de desenvolvimento .NET funcional, como o Visual Studio.
3. Um arquivo PDF: Você precisará de um arquivo PDF de amostra onde podemos pesquisar e extrair o texto. Para este tutorial, vamos supor que o arquivo seja chamado`SearchAndGetTextPage.pdf`.

## Pacotes de importação

Primeiro, precisamos importar os namespaces necessários para trabalhar com Aspose.PDF para .NET. Certifique-se de que eles estejam incluídos no topo do seu código.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System
```

Agora que cobrimos os pré-requisitos, vamos dividir o código passo a passo. Cada passo foi claramente delineado para facilitar o acompanhamento.

## Etapa 1: Defina o caminho para o diretório de documentos

Antes de interagir com seu PDF, você precisará definir o caminho para onde seu documento PDF está armazenado. Isso garante que o programa possa acessar o arquivo.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

-  dataDir: Este é o caminho para a pasta onde seus arquivos PDF são armazenados. Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real onde o PDF está localizado.

## Etapa 2: Carregue o documento PDF

O próximo passo é carregar o documento PDF na memória para que você possa trabalhar com ele. Veja como:

```csharp
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
```

- Documento: Esta é a classe Aspose.PDF que carrega o arquivo PDF.
- pdfDocument: A variável onde seu arquivo PDF é armazenado após ser carregado.

## Etapa 3: Crie um objeto absorvedor de texto

 O`TextFragmentAbsorber`class permite que você pesquise por texto específico dentro do PDF. Vamos criar uma instância desta classe para encontrar todas as instâncias de uma dada frase de pesquisa.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
```

- TextFragmentAbsorber: Esta classe é responsável por localizar e extrair texto do PDF.
- "Figura": substitua por qualquer texto que você deseja pesquisar no PDF.

## Etapa 4: aplique o Text Absorber em todo o PDF

Depois que o absorvedor de texto estiver configurado, você precisa dizer ao programa para pesquisar em todas as páginas do PDF.

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

- Accept(): Este método aplica o absorvedor de texto ao PDF, verificando cada página em busca do texto especificado.

## Etapa 5: recuperar e iterar pelo texto extraído

Agora que escaneamos o PDF, é hora de recuperar os resultados e exibi-los. Faremos um loop pelos fragmentos de texto extraídos.

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

- TextFragmentCollection: Esta coleção contém todas as instâncias dos fragmentos de texto encontrados pelo absorvedor de texto.

## Etapa 6: faça um loop em cada fragmento e extraia os dados

Agora faremos um loop pelo`textFragmentCollection` e extrair várias propriedades de cada segmento de texto, como sua posição, detalhes de fonte e cor.

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text : {0} ", textSegment.Text);
		Console.WriteLine("Position : {0} ", textSegment.Position);
		Console.WriteLine("XIndent : {0} ", textSegment.Position.XIndent);
		Console.WriteLine("YIndent : {0} ", textSegment.Position.YIndent);
		Console.WriteLine("Font - Name : {0}", textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible : {0} ", textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded : {0} ", textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset : {0} ", textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size : {0} ", textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color : {0} ", textSegment.TextState.ForegroundColor);
	}
}
```

- TextFragment: Cada fragmento contém partes do texto encontrado.
- TextSegment: Cada fragmento pode ter vários segmentos, representando diferentes partes do texto.
- TextState: fornece informações detalhadas sobre a fonte, o tamanho e a cor do texto.

Neste loop, imprimimos detalhes como o texto real, sua posição (coordenadas X e Y), a fonte, se a fonte está incorporada no PDF e a cor de primeiro plano do texto.

## Conclusão

E aí está! Agora você pesquisou e extraiu com sucesso o texto de um arquivo PDF usando o Aspose.PDF para .NET. É incrível quanta flexibilidade você tem com esta biblioteca. Se você precisa pesquisar um texto específico em um documento grande, extraí-lo ou analisar suas propriedades, o Aspose.PDF torna isso muito fácil. Além disso, com o código que abordamos, você está bem equipado para adaptá-lo às suas necessidades. 

## Perguntas frequentes

### Posso pesquisar várias frases de uma só vez?  
 Sim, você pode modificar o código para pesquisar várias frases criando várias`TextFragmentAbsorber` objetos.

### Como posso extrair texto de uma página específica?  
 Você pode direcionar uma página específica aplicando o`TextFragmentAbsorber` para uma única página em vez de todo o documento. Por exemplo:`pdfDocument.Pages[1].Accept(textFragmentAbsorber);`.

### O Aspose.PDF para .NET é gratuito?  
 Aspose.PDF é um produto comercial, mas você pode usá-lo com um[teste gratuito](https://releases.aspose.com/).

### Posso extrair imagens do PDF usando o Aspose.PDF?  
 Sim, o Aspose.PDF permite que você extraia imagens além de texto. Verifique o[documentação](https://reference.aspose.com/pdf/net/) para mais detalhes.

### E se eu precisar de mais ajuda ou suporte?  
 Você sempre pode obter ajuda do[Fórum de suporte Aspose](https://forum.aspose.com/c/pdf/10).