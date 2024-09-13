---
title: Criar hiperlink local em arquivo PDF
linktitle: Criar hiperlink local em arquivo PDF
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda a criar hiperlinks locais em arquivos PDF usando o Aspose.PDF para .NET sem esforço com nosso guia passo a passo.
type: docs
weight: 40
url: /pt/net/programming-with-links-and-actions/create-local-hyperlink/
---
## Introdução

Neste guia, nós o guiaremos pelo processo de criação de hiperlinks locais em um arquivo PDF usando o Aspose.PDF para .NET. Nós detalharemos cada etapa claramente, garantindo que mesmo se você for novo no mundo da manipulação de PDF, você será capaz de acompanhar sem esforço.

## Pré-requisitos

Antes de mergulhar de cabeça no código, vamos garantir que você tenha tudo o que precisa:

1.  Visual Studio: Você precisará disto para desenvolver seus aplicativos .NET. Baixe-o do[site](https://visualstudio.microsoft.com/).
2.  Aspose.PDF para .NET: Você pode baixar esta biblioteca através do[link para download aqui](https://releases.aspose.com/pdf/net/). Ele vem com um rico conjunto de recursos para manipulação de PDF.
3. Conhecimento básico de C#: Um pouco de familiaridade com programação em C# ajudará, mas não se preocupe; analisaremos o código linha por linha.
4.  .NET Framework: Certifique-se de ter o .NET Framework instalado em sua máquina. Você pode verificar os requisitos no Aspose.PDF[documentação](https://reference.aspose.com/pdf/net/).

Com esses pré-requisitos configurados, você está pronto para aprender a criar hiperlinks locais em seus documentos PDF!

## Pacotes de importação

Agora que você está preparado, é hora de importar os pacotes necessários no seu projeto C#. A biblioteca Aspose.PDF contém todas as classes que precisamos. Veja como fazer isso:

### Abra seu projeto

Abra seu projeto .NET existente ou crie um novo no Visual Studio. Se estiver começando do zero, selecione “Criar um novo projeto” na tela de inicialização.

### Adicionar referência ao Aspose.PDF

 Clique com o botão direito em "Dependencies" na pasta do seu projeto no Solution Explorer. Selecione "Manage NuGet Packages" e pesquise por`Aspose.PDF`. Instale a versão mais recente disponível. Isso trará todas as ferramentas que você precisa para criar e manipular PDFs.

### Importar namespaces

No topo do seu arquivo .cs, adicione diretivas using para a biblioteca Aspose.PDF como esta:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

Dessa forma, você poderá acessar os recursos da biblioteca.

Vamos dividir o processo de criação de hyperlinks locais em etapas simples. Cada etapa será explicada de forma abrangente para ajudar você a entender a lógica por trás dela.

## Etapa 1: Configurar instância do documento

Nesta etapa, você criará uma nova instância da classe Document, que representa o arquivo PDF com o qual você trabalhará.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Defina seu diretório de documentos
Document doc = new Document(); // Criar instância de documento
```
 O`dataDir` variável é onde seu PDF recém-criado residirá. Você precisará substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real em seu sistema. O`Document` A classe cria um novo documento PDF onde podemos adicionar páginas e links.

## Etapa 2: Adicionar uma página ao documento

Em seguida, você adicionará uma página ao seu documento PDF. 

```csharp
Page page = doc.Pages.Add(); // Adicionar página à coleção de páginas
```
 O`Pages.Add()` O método adiciona uma nova página ao documento. É aqui que todo o seu conteúdo ficará.

## Etapa 3: Crie um fragmento de texto

Agora, vamos criar um pedaço de texto que funcionará como um link clicável.

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("link page number test to page 7");
```
 O`TextFragment` representa um segmento de texto no PDF. Aqui, estamos criando um link que informa aos usuários que ele os levará para a página 7.

## Etapa 4: Criar hiperlink local

É aqui que a mágica acontece! Você precisa criar um hyperlink local que dirá ao fragmento de texto para onde apontar.

```csharp
Aspose.Pdf.LocalHyperlink link = new Aspose.Pdf.LocalHyperlink(); // Criar hiperlink local
link.TargetPageNumber = 7; //Definir página de destino para instância de link
text.Hyperlink = link; // Definir hiperlink TextFragment
```
 O`LocalHyperlink` classe é o que nos permite apontar para outras páginas no mesmo documento. Ao definir`TargetPageNumber` para 7, você diz ao hiperlink para pular para aquela página específica quando clicado.

## Etapa 5: adicione o fragmento de texto à página

Depois de configurar o hiperlink, é hora de adicionar nosso fragmento de texto à página que criamos.

```csharp
page.Paragraphs.Add(text); // Adicionar texto à coleção de parágrafos da página
```
Esta linha adiciona seu texto clicável ao conjunto de parágrafos da página.

## Etapa 6: Crie outro fragmento de texto (opcional)

Vamos adicionar outro hiperlink para navegar de volta à página 1.

```csharp
text = new TextFragment("link page number test to page 1"); // Criar novo TextFragment
text.IsInNewPage = true; // Adicione-o a uma nova página
```
 Criando um novo`TextFragment` para o segundo link, definimos`IsInNewPage` para verdadeiro, indicando que este texto irá para uma nova página.

## Etapa 7: Configurar o segundo hiperlink local

Assim como antes, você criará outro hiperlink local para a página 1.

```csharp
link = new LocalHyperlink(); // Crie outra instância de hiperlink local
link.TargetPageNumber = 1; //Definir página de destino para o segundo hiperlink
text.Hyperlink = link; // Definir link para o segundo TextFragment
```
Este hiperlink direciona para a página 1, permitindo que os usuários voltem quando chegarem à segunda página.

## Etapa 8: Adicione o segundo fragmento de texto à nova página

Agora, vamos adicionar este texto à sua página.

```csharp
page.Paragraphs.Add(text); // Adicionar texto à coleção de parágrafos do objeto de página
```
Semelhante à etapa 5, esta linha adiciona o novo texto do hiperlink à página recém-criada.

## Etapa 9: Salve o documento

Finalmente, é hora de salvar seu trabalho duro! 

```csharp
dataDir = dataDir + "CreateLocalHyperlink_out.pdf"; // Especificar nome do arquivo de saída
doc.Save(dataDir); // Salvar documento atualizado
Console.WriteLine("\nLocal hyperlink created successfully.\nFile saved at " + dataDir);
```
 Isso combina o caminho do seu diretório com o nome do arquivo. O`Save()` O método salva seu documento e uma mensagem de confirmação informa que tudo ocorreu sem problemas!

## Conclusão

Criar hiperlinks locais em arquivos PDF usando o Aspose.PDF para .NET não é apenas um truque legal; é um recurso prático que aprimora a navegação e a experiência do usuário. Agora você está equipado com o conhecimento para direcionar seus leitores diretamente para as informações de que precisam. Basta pensar novamente em nossa analogia inicial — chega de almas perdidas vagando por páginas infinitas.

## Perguntas frequentes

### O que é Aspose.PDF para .NET?
Aspose.PDF para .NET é uma biblioteca que permite aos desenvolvedores criar, manipular e converter documentos PDF programaticamente usando o .NET framework.

### Posso criar hiperlinks para páginas da web externas?
Sim, o Aspose.PDF também suporta a criação de hiperlinks para URLs externas, além de hiperlinks locais dentro do PDF.

### Existe uma versão de avaliação gratuita do Aspose.PDF?
 Com certeza! Você pode acessar o teste gratuito no[site](https://releases.aspose.com/).

### Quais linguagens de programação o Aspose suporta?
Aspose oferece bibliotecas para várias linguagens de programação, incluindo Java, C++, e Python, entre outros.

### Como obtenho suporte para produtos Aspose?
 Você pode buscar suporte através do[Fórum Aspose](https://forum.aspose.com/c/pdf/10).