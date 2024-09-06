---
title: Incorporar fonte durante a criação de documento PDF
linktitle: Incorporar fonte durante a criação de documento PDF
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda como incorporar fontes em documentos PDF usando Aspose.PDF para .NET com este guia passo a passo. Melhore a aparência do seu PDF.
type: docs
weight: 140
url: /pt/net/programming-with-document/embedfontwhiledoccreation/
---
## Introdução

Criar documentos PDF com aparência profissional e polida é essencial no mundo digital de hoje. Um dos principais aspectos para obter essa aparência polida é garantir que as fontes usadas no seu PDF sejam incorporadas corretamente. Isso não apenas preserva a aparência do seu documento em diferentes dispositivos, mas também melhora a legibilidade. Neste tutorial, vamos nos aprofundar em como incorporar fontes ao criar documentos PDF usando o Aspose.PDF para .NET. 

## Pré-requisitos

Antes de começarmos o código, vamos garantir que você tenha tudo o que precisa para começar:

1.  Aspose.PDF para .NET: Você precisará ter a biblioteca Aspose.PDF instalada. Você pode baixá-la do[site](https://releases.aspose.com/pdf/net/).
2. Visual Studio: um ambiente de desenvolvimento onde você pode escrever e testar seu código.
3. Conhecimento básico de C#: A familiaridade com a programação em C# ajudará você a entender melhor os trechos de código.

## Pacotes de importação

Para usar Aspose.PDF no seu projeto, você precisa importar os namespaces necessários. Veja como você pode fazer isso:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

Esses namespaces darão acesso às classes e métodos necessários para criar e manipular documentos PDF.

Agora que resolvemos nossos pré-requisitos, vamos dividir o processo de incorporação de fontes em um documento PDF em etapas gerenciáveis.

## Etapa 1: configure seu diretório de documentos

Primeiro, você precisa definir o caminho onde seu documento PDF será salvo. Isso é crucial porque diz ao seu aplicativo onde armazenar o arquivo de saída.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Substituir`"YOUR DOCUMENT DIRECTORY"`com o caminho real no seu sistema onde você deseja salvar o PDF.

## Etapa 2: Instanciar o documento PDF

 Em seguida, você criará uma instância do`Document` classe. Esta classe representa seu documento PDF.

```csharp
// Instanciar objeto PDF chamando seu construtor vazio
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

Ao chamar o construtor vazio, você está criando um novo documento PDF em branco, pronto para conteúdo.

## Etapa 3: Crie uma página no documento PDF

Agora, vamos adicionar uma página ao seu documento PDF. Todo PDF precisa de pelo menos uma página, então esta etapa é essencial.

```csharp
// Crie uma seção no objeto PDF
Aspose.Pdf.Page page = doc.Pages.Add();
```

Esta linha de código adiciona uma nova página ao seu documento, permitindo que você comece a adicionar conteúdo.

## Etapa 4: Crie um fragmento de texto

 Para adicionar texto ao seu PDF, você precisará criar um`TextFragment`. Este objeto conterá o texto que você deseja exibir.

```csharp
Aspose.Pdf.Text.TextFragment fragment = new Aspose.Pdf.Text.TextFragment("");
```

 Aqui, estamos inicializando um novo`TextFragment`. Você pode pensar nisso como um contêiner para seu texto.

## Etapa 5: Adicionar segmentos de texto

Agora, vamos criar um segmento de texto que contém o texto real que você quer exibir. É aqui que você pode personalizar seu texto.

```csharp
Aspose.Pdf.Text.TextSegment segment = new Aspose.Pdf.Text.TextSegment("This is a sample text using Custom font.");
```

Sinta-se à vontade para mudar o texto para o que quiser. Este é o seu conteúdo!

## Etapa 6: Definir estado do texto e incorporar fonte

 Para garantir que sua fonte seja incorporada ao PDF, você precisa definir as propriedades da fonte no`TextState` objeto.

```csharp
Aspose.Pdf.Text.TextState ts = new Aspose.Pdf.Text.TextState();
ts.Font = FontRepository.FindFont("Arial");
ts.Font.IsEmbedded = true;
segment.TextState = ts;
```

Neste código, estamos especificando que queremos usar a fonte Arial e que ela deve ser incorporada no PDF. Este é um passo crucial para garantir que seu documento tenha a mesma aparência em todos os dispositivos.

## Etapa 7: Adicione o segmento ao fragmento

Agora que você tem seu segmento de texto pronto, é hora de adicioná-lo ao fragmento de texto.

```csharp
fragment.Segments.Add(segment);
```

Esta linha adiciona o segmento ao fragmento, tornando-o parte do texto que será exibido na página.

## Etapa 8: Adicione o fragmento à página

Em seguida, você precisará adicionar o fragmento de texto à página criada anteriormente.

```csharp
page.Paragraphs.Add(fragment);
```

Esta etapa garante que seu texto apareça na página do documento PDF.

## Etapa 9: Salve o documento PDF

Finalmente, é hora de salvar seu documento PDF. Você especificará o caminho onde deseja salvá-lo.

```csharp
dataDir = dataDir + "EmbedFontWhileDocCreation_out.pdf";
// Salvar documento PDF
doc.Save(dataDir);
```

Este código concatena o nome do arquivo de saída ao caminho do diretório do documento e salva o PDF. 

## Conclusão

E aí está! Você criou com sucesso um documento PDF com fontes incorporadas usando o Aspose.PDF para .NET. Esse processo não só melhora o apelo visual dos seus documentos, mas também garante que eles mantenham sua formatação em diferentes plataformas. 

## Perguntas frequentes

### O que é Aspose.PDF para .NET?
Aspose.PDF para .NET é uma biblioteca poderosa que permite aos desenvolvedores criar, manipular e converter documentos PDF programaticamente.

### Por que devo incorporar fontes no meu PDF?
A incorporação de fontes garante que seu documento tenha a mesma aparência em todos os dispositivos, mantendo o design e a legibilidade pretendidos.

### Posso usar fontes personalizadas com o Aspose.PDF?
Sim, você pode usar fontes personalizadas, desde que elas estejam disponíveis no seu sistema e sejam devidamente referenciadas no seu código.

### Existe uma versão de avaliação gratuita disponível para o Aspose.PDF?
 Sim, você pode baixar uma versão de teste gratuita no[Site Aspose](https://releases.aspose.com/).

### Onde posso encontrar suporte para o Aspose.PDF?
 Você pode encontrar suporte e fazer perguntas no[Fórum Aspose](https://forum.aspose.com/c/pdf/10).