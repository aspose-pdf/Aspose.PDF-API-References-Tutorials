---
title: Adicionar elemento de estrutura ao elemento
linktitle: Adicionar elemento de estrutura ao elemento
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda como adicionar elementos de estrutura de acessibilidade em PDFs usando o Aspose.PDF para .NET neste tutorial abrangente passo a passo.
type: docs
weight: 20
url: /pt/net/programming-with-tagged-pdf/add-structure-element-into-element/
---
## Introdução

No mundo digital de hoje, a acessibilidade é essencial. Todos devem ter acesso igual à informação, e fornecê-la em um formato que todos os indivíduos possam navegar facilmente é crucial. Neste tutorial, estamos mergulhando em como aprimorar a acessibilidade do PDF adicionando elementos de estrutura usando o Aspose.PDF para .NET. Esta biblioteca poderosa permite que os desenvolvedores trabalhem perfeitamente com documentos PDF, permitindo que eles criem PDFs marcados que são compatíveis com os padrões de acessibilidade.

## Pré-requisitos

Antes de começarmos nossa jornada no mundo dos elementos de estrutura de PDF, vamos garantir que você tenha tudo o que precisa:

1.  Estúdio Visual: Este é o seu IDE onde você escreverá e executará seu código C#. Você pode baixá-lo de[Visual Studio](https://visualstudio.microsoft.com/) se você ainda não o fez.
2.  Biblioteca Aspose.PDF para .NET: Você precisará da biblioteca para manipular PDFs. Baixe a versão mais recente do[Site Aspose](https://releases.aspose.com/pdf/net/). Esta biblioteca é essencial para o nosso projeto.
3. Conhecimento básico de C#: Familiaridade com a sintaxe C# e programação orientada a objetos será benéfica. Se você consegue escrever algumas linhas de C# sem problemas, está pronto para começar!
4. Um diretório de documentos PDF: crie um diretório no seu sistema onde você manterá os arquivos PDF de entrada e saída para este tutorial.

Agora que temos nossas ferramentas e conhecimento alinhados, vamos trazer os pacotes necessários para começar!

## Pacotes de importação

Primeiro, vamos importar os namespaces necessários. Certifique-se de que você tenha o seguinte no topo do seu arquivo C#:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
```

Esses namespaces dão a você acesso às classes e métodos necessários para trabalhar com seus documentos PDF e criar conteúdo marcado. Agora, vamos ao cerne da questão e começar a codificar!

## Etapa 1: configure seu diretório de documentos

Antes de qualquer codificação acontecer, precisamos estabelecer onde salvaremos nossos arquivos. Isso é crucial para que nosso script rode sem problemas.

```csharp
// Defina o caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
```

 Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real onde você gostaria de manter seus arquivos PDF. Isso pode ser algo como`C:\\PDFs\\`.

## Etapa 2: Crie um novo documento PDF

Agora que definimos nosso diretório, vamos criar um documento PDF onde adicionaremos nossos elementos de estrutura.

```csharp
Document document = new Document();
```

 Esta linha inicializa uma nova instância do`Document` classe, permitindo-nos começar a trabalhar com nosso conteúdo em PDF.

## Etapa 3: acesse e configure o conteúdo marcado

Quando seu documento estiver pronto, é hora de configurar o conteúdo marcado, o que é essencial para acessibilidade.

### Inicializar conteúdo marcado

```csharp
ITaggedContent taggedContent = document.TaggedContent;
```

Esta linha fornece acesso ao conteúdo marcado do seu PDF. O conteúdo marcado é necessário para que leitores de tela interpretem seu documento com precisão.

### Definir metadados do documento

Você vai querer dar um título apropriado ao seu documento e definir o idioma.

```csharp
taggedContent.SetTitle("Text Elements Example");
taggedContent.SetLanguage("en-US");
```

Isso aprimora os metadados do documento e melhora sua acessibilidade.

## Etapa 4: Criar e anexar elementos de estrutura

Vamos adicionar alguma estrutura! Isso envolve criar parágrafos e elementos span para criar um documento devidamente formatado e marcado.

### Criar elemento de estrutura raiz

```csharp
StructureElement rootElement = taggedContent.RootElement;
```

Agora, criaremos nosso primeiro conjunto de parágrafos e elementos de extensão.

### Criar o primeiro elemento do parágrafo

```csharp
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
```

Aqui, inicializamos um novo elemento de parágrafo e o anexamos ao elemento de estrutura raiz. Este é o ponto de partida do seu conteúdo!

### Adicionar elementos de span ao parágrafo

```csharp
SpanElement span11 = taggedContent.CreateSpanElement();
span11.SetText("Span_11");
SpanElement span12 = taggedContent.CreateSpanElement();
span12.SetText(" and Span_12.");
```

 O`span` elementos são como miniparágrafos dentro do nosso parágrafo maior. Eles permitem um controle mais fino sobre a formatação do texto.

### Combine tudo

Agora vamos construir o parágrafo completo com todos os elementos juntos:

```csharp
p1.SetText("Paragraph with ");
p1.AppendChild(span11);
p1.AppendChild(span12);
```

### Repita para parágrafos adicionais

Você repetirá esse processo para parágrafos adicionais:

```csharp
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
SpanElement span21 = taggedContent.CreateSpanElement();
span21.SetText("Span_21");
SpanElement span22 = taggedContent.CreateSpanElement();
span22.SetText("Span_22.");
p2.AppendChild(span21);
p2.SetText(" and ");
p2.AppendChild(span22);
```

 Continue criando`ParagraphElement` areia`SpanElement` s, anexando-os ao`rootElement` da mesma forma que mostrado acima para`p1`.

## Etapa 5: Salve seu documento

Com todos os elementos estruturais prontos, é hora de salvar seu documento PDF.

### Especificar caminho do arquivo de saída

```csharp
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
```

### Salvar o documento

```csharp
document.Save(outFile);
```

É aqui que a mágica acontece! Seu documento é salvo no caminho de arquivo de saída especificado.

## Etapa 6: Validar a conformidade com PDF/UA

última etapa envolve verificar se o seu documento está em conformidade com os padrões PDF/UA para acessibilidade.

Para verificar a conformidade, use o seguinte código:

```csharp
document = new Document(outFile);
string logFile = dataDir + "46144_log.xml";
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));
```

Isso informará se o seu documento está em conformidade com os padrões PDF/UA, o que é essencial para acessibilidade.

## Conclusão

E aí está! Você acabou de aprender como adicionar elementos de estrutura em um documento PDF usando o Aspose.PDF para .NET. Seguindo essas etapas, você pode transformar qualquer PDF em um formato acessível que segue os padrões, garantindo que todos possam ter acesso igual às informações. 

## Perguntas frequentes

### O que é Aspose.PDF para .NET?
Aspose.PDF para .NET é uma biblioteca que permite aos desenvolvedores criar, manipular e converter documentos PDF programaticamente.

### Como posso verificar se meu PDF está acessível?
Você pode validar seu PDF em relação aos padrões PDF/UA usando a biblioteca Aspose.PDF para garantir que ele atenda às diretrizes de acessibilidade.

### Posso usar o Aspose.PDF gratuitamente?
 Sim, o Aspose oferece uma versão de teste gratuita, permitindo que você explore seus recursos sem nenhum custo. Você pode baixá-lo[aqui](https://releases.aspose.com/).

### Onde posso encontrar a documentação do Aspose.PDF?
Você pode encontrar documentação abrangente para Aspose.PDF[aqui](https://reference.aspose.com/pdf/net/).

### Como faço para comprar uma licença para o Aspose.PDF?
 Você pode comprar uma licença diretamente do site da Aspose[aqui](https://purchase.aspose.com/buy).