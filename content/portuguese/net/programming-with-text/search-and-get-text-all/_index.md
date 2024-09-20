---
title: Pesquisar e obter texto tudo
linktitle: Pesquisar e obter texto tudo
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda a pesquisar e obter texto de todas as páginas de um documento PDF usando o Aspose.PDF para .NET.
type: docs
weight: 420
url: /pt/net/programming-with-text/search-and-get-text-all/
---
## Introdução

Você já precisou extrair texto específico de um PDF, mas achou complicado? Às vezes, os PDFs podem parecer contêineres bloqueados, dificultando a obtenção das informações necessárias. Mas aqui estão as boas notícias: com o Aspose.PDF para .NET, você pode pesquisar e recuperar texto facilmente de qualquer PDF. Esta biblioteca poderosa fornece tudo o que você precisa para trabalhar com PDFs em seus aplicativos .NET, tornando a extração de texto muito fácil. Neste tutorial, mostraremos o processo de pesquisa e extração de texto de um arquivo PDF usando o Aspose.PDF para .NET. Quer você esteja criando uma ferramenta de análise de texto ou apenas precise automatizar a extração de dados de relatórios em PDF, você está no lugar certo!

## Pré-requisitos

Antes de começarmos o código, vamos garantir que você tenha tudo configurado:

1. Aspose.PDF para .NET: Você precisará baixar e instalar o Aspose.PDF para .NET. Você pode obtê-lo na página de download[aqui](https://releases.aspose.com/pdf/net/).
2. Ambiente .NET: certifique-se de ter o .NET Framework ou o .NET Core configurado na sua máquina de desenvolvimento.
3. Conhecimento básico de C##: Recomenda-se alguma familiaridade com C# e trabalho com projetos .NET.
4.  Documento PDF: Um arquivo PDF de amostra do qual extrairemos o texto. Neste exemplo, usaremos`SearchAndGetTextFromAll.pdf`.

## Pacotes de importação

Antes de escrever qualquer código, você precisa importar os namespaces necessários para seu projeto para trabalhar com o Aspose.PDF.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

Esses namespaces fornecem acesso ao modelo de objeto do documento do PDF e nos permitem manipular o texto dentro do arquivo.

Vamos dividir o processo em etapas simples para que você possa acompanhar com facilidade.

## Etapa 1: Defina o diretório de documentos

Primeiro, você precisa especificar o caminho para o diretório onde seu PDF está localizado. Isso ajuda o aplicativo a localizar o arquivo do qual você extrairá o texto.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

-  O`dataDir` variável deve apontar para o diretório onde seu`SearchAndGetTextFromAll.pdf` o arquivo é armazenado.
-  Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real na sua máquina.

## Etapa 2: Abra o documento PDF

Em seguida, abriremos o documento PDF usando o Aspose.PDF`Document` objeto.

```csharp
// Abrir documento
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

-  Criamos uma nova instância do`Document` classe passando o caminho completo do arquivo PDF.
- Isso carregará o PDF na memória, deixando-o pronto para processamento.

## Etapa 3: Crie um absorvedor de texto

 O`TextFragmentAbsorber` objeto é usado para procurar por texto específico dentro do PDF. Neste caso, procuraremos pela palavra “texto”.

```csharp
// Crie um objeto TextAbsorber para encontrar todas as instâncias da frase de pesquisa de entrada
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

-  O`TextFragmentAbsorber` é inicializado com a string`"text"`. Isso significa que ele procurará por qualquer ocorrência da palavra “texto” dentro do documento PDF.

## Etapa 4: aceitar o absorvedor para todas as páginas

Agora, instruiremos o documento PDF a aceitar o absorvedor e procurar o texto em todas as suas páginas.

```csharp
// Aceite o absorvedor para todas as páginas
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

-  O`Accept` método é aplicado às páginas do documento. Isso pesquisará todas as páginas em busca do texto especificado.

## Etapa 5: Extrair fragmentos de texto

Depois que o absorvedor escaneia o documento, podemos recuperar os fragmentos de texto extraídos.

```csharp
// Obtenha os fragmentos de texto extraídos
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

-  O`TextFragments` propriedade do`TextFragmentAbsorber` retorna uma coleção de todos os fragmentos de texto que correspondem ao termo de pesquisa.

## Etapa 6: faça um loop pelos fragmentos de texto

Agora que temos a coleção de fragmentos de texto, vamos percorrê-los e extrair os detalhes.

```csharp
// Percorrer os fragmentos
foreach (TextFragment textFragment in textFragmentCollection)
{
    Console.WriteLine("Text : {0} ", textFragment.Text);
    Console.WriteLine("Position : {0} ", textFragment.Position);
    Console.WriteLine("XIndent : {0} ", textFragment.Position.XIndent);
    Console.WriteLine("YIndent : {0} ", textFragment.Position.YIndent);
    Console.WriteLine("Font - Name : {0}", textFragment.TextState.Font.FontName);
    Console.WriteLine("Font - IsAccessible : {0} ", textFragment.TextState.Font.IsAccessible);
    Console.WriteLine("Font - IsEmbedded : {0} ", textFragment.TextState.Font.IsEmbedded);
    Console.WriteLine("Font - IsSubset : {0} ", textFragment.TextState.Font.IsSubset);
    Console.WriteLine("Font Size : {0} ", textFragment.TextState.FontSize);
    Console.WriteLine("Foreground Color : {0} ", textFragment.TextState.ForegroundColor);
}
```

-  O`foreach` o loop itera por cada`TextFragment` na coleção.
- Imprimimos várias propriedades de cada fragmento, como o texto real, sua posição na página, detalhes da fonte e tamanho da fonte.
-  O`XIndent` e`YIndent` propriedades fornecem as coordenadas exatas do fragmento de texto dentro do PDF.

## Conclusão

E aí está! Com apenas algumas linhas de código, pesquisamos e extraímos com sucesso texto de um PDF usando o Aspose.PDF para .NET. A flexibilidade do Aspose.PDF permite que você manipule PDFs de várias maneiras, tornando-o uma excelente escolha para desenvolvedores que precisam de soluções robustas de PDF em ambientes .NET. Você pode facilmente estender este exemplo para pesquisar outras palavras, extrair mais detalhes ou até mesmo manipular o conteúdo do PDF com base em suas necessidades. Espero que este guia tenha lhe dado uma abordagem clara e direta para trabalhar com PDFs. Vá em frente e tente com seus próprios PDFs!

## Perguntas frequentes

### Posso pesquisar várias palavras de uma só vez?  
 Sim, você pode modificar o`TextFragmentAbsorber` para pesquisar várias frases ajustando a sequência de pesquisa adequadamente.

### E se o texto abranger várias linhas?  
Aspose.PDF ainda reconhecerá e extrairá texto mesmo que ele ocupe várias linhas. Você pode manipular esses fragmentos individualmente.

### Como faço para salvar o texto extraído em um arquivo?  
 Você pode gravar o texto extraído em um arquivo usando operações de E/S de arquivo C# padrão, como`StreamWriter`.

### O Aspose.PDF suporta extração de texto de PDFs digitalizados?  
Aspose.PDF não suporta OCR. Para PDFs escaneados, você precisaria de uma ferramenta de OCR para reconhecer o texto.

### Como lidar com PDFs criptografados?  
Se o seu PDF for protegido por senha, você poderá desbloqueá-lo usando o Aspose.PDF fornecendo a senha ao carregar o documento.