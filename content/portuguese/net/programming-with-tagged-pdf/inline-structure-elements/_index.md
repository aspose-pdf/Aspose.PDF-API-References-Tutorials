---
title: Elementos de estrutura em linha
linktitle: Elementos de estrutura em linha
second_title: Referência da API do Aspose.PDF para .NET
description: Guia passo a passo para usar elementos estruturais online com Aspose.PDF para .NET. Organize seus PDFs com títulos e parágrafos.
type: docs
weight: 110
url: /pt/net/programming-with-tagged-pdf/inline-structure-elements/
---
## Introdução

Criar documentos acessíveis e bem estruturados é crucial no cenário digital de hoje. Se você já se viu rolando por um PDF apenas para se perder em um mar de texto, você sabe a importância de uma boa organização. Marcar elementos em seu PDF pode melhorar a acessibilidade, tornando mais fácil para leitores de tela interpretarem o conteúdo. Neste guia, estamos mergulhando no uso do Aspose.PDF para .NET para criar documentos PDF marcados, garantindo que seu trabalho atenda aos padrões modernos em estruturação de documentos.

## Pré-requisitos

Antes de começarmos a agir, vamos garantir que você tenha tudo o que precisa para continuar:

1. Conhecimento básico de C#: familiaridade com programação em C# e noções básicas do framework .NET é essencial.
2. Visual Studio instalado: você precisará de um IDE como o Visual Studio para escrever e executar seu código.
3.  Aspose.PDF para .NET: Certifique-se de baixar e instalar o Aspose.PDF para .NET. Você pode obtê-lo do[link para download](https://releases.aspose.com/pdf/net/).
4. Uma licença temporária: é opcional, mas se você quiser avaliar todos os recursos sem limitações, considere obter uma[licença temporária](https://purchase.aspose.com/temporary-license/).

Depois de cumprir esses pré-requisitos, você estará pronto para criar seu primeiro documento PDF marcado!

## Pacotes de importação

Para começar, vamos importar os pacotes necessários. Isso permite que seu projeto aproveite os recursos da biblioteca Aspose.PDF.

1. Abra seu projeto do Visual Studio.
2. Adicione uma referência à biblioteca Aspose.PDF. Se você ainda não a adicionou, pode usar o NuGet Package Manager para instalá-la.
3. Inclua os seguintes namespaces no topo do seu arquivo C#:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Com essas importações em andamento, você está pronto para o sucesso.

## Análise de código: guia passo a passo para criar um PDF marcado

Agora que estamos todos configurados, vamos decompor o código passo a passo. Criaremos um PDF marcado com elementos estruturados, como cabeçalhos e parágrafos, permitindo melhor acessibilidade.

### Etapa 1: Defina o diretório de documentos

Primeiro, defina o caminho onde seu documento será salvo. É uma boa ideia manter uma estrutura de arquivo organizada.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Substitua pelo seu caminho atual
```

### Etapa 2: Criar uma instância de documento PDF

 Em seguida, crie uma instância do`Document` class, que servirá como contêiner para o conteúdo do seu PDF.

```csharp
Document document = new Document();
```

### Etapa 3: Acesse o conteúdo marcado

Agora, acesse o conteúdo marcado do documento. É aqui que a mágica acontece — marcando o conteúdo, melhoramos sua acessibilidade.

```csharp
ITaggedContent taggedContent = document.TaggedContent;    
```

### Etapa 4: Defina o título e o idioma

Definir um título e idioma para seu documento PDF é essencial tanto para usuários quanto para leitores de tela. Isso torna seu documento mais informativo e acessível.

```csharp
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");
```

### Etapa 5: Obtenha o elemento de estrutura raiz

Vamos começar a adicionar elementos ao seu documento. Primeiro, pegue o elemento de estrutura raiz do conteúdo marcado, que serve como base para construir a estrutura do seu documento.

```csharp
StructureElement rootElement = taggedContent.RootElement;
```

### Etapa 6: Criar elementos de cabeçalho

Agora é hora de criar elementos de cabeçalho. Isso ajudará a organizar o conteúdo em uma hierarquia. Criaremos seis níveis de cabeçalhos.

```csharp
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);
```

### Etapa 7: Acrescentar cabeçalhos ao elemento raiz

Após criar elementos de cabeçalho, anexe-os ao elemento raiz. Isso constrói a hierarquia estrutural do documento.

```csharp
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);
```

### Etapa 8: Adicione texto a cada cabeçalho

Agora, vamos adicionar algum texto a cada cabeçalho. Este é um processo direto, mas vital para tornar seu documento útil. 

```csharp
// H1
SpanElement spanH11 = taggedContent.CreateSpanElement();
spanH11.SetText("H1. ");
h1.AppendChild(spanH11);
SpanElement spanH12 = taggedContent.CreateSpanElement();
spanH12.SetText("Level 1 Header");
h1.AppendChild(spanH12);

// Repita para H2 - H6 conforme mostrado acima
```

### Etapa 9: Crie um elemento de parágrafo

Em seguida, vamos adicionar um elemento de parágrafo. Ele servirá como a área de conteúdo principal do seu PDF. 

```csharp
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P. ");
rootElement.AppendChild(p);
```

### Etapa 10: Adicionar texto ao parágrafo

Agora que temos nosso elemento de parágrafo, é hora de preenchê-lo com texto. Você pode adicionar vários spans para compor seu conteúdo.

```csharp
SpanElement span1 = taggedContent.CreateSpanElement();
span1.SetText("Lorem ipsum dolor sit amet, consectetur adipiscing elit. ");
p.AppendChild(span1);
// Continue a adicionar extensões adicionais conforme necessário
```

### Etapa 11: Salve o documento PDF marcado

Finalmente, depois de adicionar todo o seu conteúdo, você precisa salvar seu documento. Vamos finalizar!

```csharp
document.Save(dataDir + "InlineStructureElements.pdf");
```

E voilà! Agora você tem um documento PDF marcado, estruturado e acessível.

## Conclusão

Criar documentos PDF marcados pode parecer assustador, mas com o Aspose.PDF para .NET, é moleza! Seguindo este guia passo a passo, você dominou os fundamentos da estruturação de documentos. Lembre-se, marcar corretamente seu PDF melhora sua acessibilidade, garantindo que seu conteúdo valioso alcance um público mais amplo. Então, vá em frente e deixe seus PDFs não apenas bonitos, mas também fáceis de usar!

## Perguntas frequentes

### O que é um PDF marcado?
Um PDF marcado é um PDF que inclui informações sobre a estrutura do documento, tornando-o mais acessível para usuários com deficiências.

### Por que a marcação é importante em PDFs?
A marcação melhora a acessibilidade, permitindo que os leitores de tela interpretem o documento claramente, proporcionando assim uma melhor experiência para usuários com deficiências.

### Posso usar o Aspose.PDF gratuitamente?
 Sim, você pode avaliar o Aspose.PDF para .NET por meio de um[teste gratuito](https://releases.aspose.com/).

### Onde posso obter suporte para o Aspose.PDF?
 O suporte pode ser acessado através do[Fórum de suporte Aspose](https://forum.aspose.com/c/pdf/10).

### Como posso adquirir a licença do Aspose.PDF para .NET?
 Você pode comprar uma licença diretamente do[página de compra](https://purchase.aspose.com/buy).