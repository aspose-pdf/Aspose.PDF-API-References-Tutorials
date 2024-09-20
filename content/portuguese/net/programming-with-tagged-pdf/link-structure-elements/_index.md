---
title: Elementos da estrutura do link
linktitle: Elementos da estrutura do link
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda a criar elementos de estrutura de links em um PDF usando Aspose.PDF para .NET. Guia passo a passo para adicionar links acessíveis, imagens e validação de conformidade.
type: docs
weight: 120
url: /pt/net/programming-with-tagged-pdf/link-structure-elements/
---
## Introdução

Criar e gerenciar elementos de estrutura de link dentro de um PDF pode ser crucial para documentos que exigem acessibilidade e navegação suave. Neste tutorial, mostraremos como fazer isso usando o Aspose.PDF para .NET. Se você é novo no Aspose.PDF ou na manipulação de PDF em geral, não se preocupe. Explicarei cada etapa em detalhes para que você possa acompanhar facilmente!

## Pré-requisitos  

Antes de mergulharmos na codificação, vamos esclarecer algumas coisas primeiro. Esses são os requisitos básicos para garantir uma experiência de desenvolvimento tranquila.

1.  Aspose.PDF para .NET: Você pode baixar a versão mais recente[aqui](https://releases.aspose.com/pdf/net/).
2. Ambiente de desenvolvimento .NET: seja o Visual Studio ou qualquer IDE compatível com .NET, tenha-o instalado e pronto.
3.  Licença Aspose: Você pode usar a versão de teste gratuita do Aspose.PDF[aqui](https://releases.aspose.com/) ou adquirir um[licença temporária](https://purchase.aspose.com/temporary-license/).
4. Conhecimento básico de C#: Trabalharemos com algum código C#, então entender os fundamentos tornará as coisas muito mais fáceis.

## Pacotes de importação

Você precisará importar alguns pacotes antes de escrever o código para elementos de estrutura de link. Comece referenciando as bibliotecas Aspose.PDF necessárias em seu projeto:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Essas importações nos permitem trabalhar com documentos PDF, adicionar tags e gerenciar elementos de estrutura.

Agora criaremos um documento PDF com diferentes tipos de estruturas de links, e cada etapa será detalhada para ajudar você a entender o processo completamente.

## Etapa 1: Inicializar o documento  

Vamos começar criando um novo documento PDF e configurando o conteúdo marcado para acessibilidade.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";

// Criar um novo documento PDF
Document document = new Document(); 

// Recuperar a interface TaggedContent
ITaggedContent taggedContent = document.TaggedContent;
```
  
 Aqui, estamos inicializando o`Document` objeto, que representa nosso arquivo PDF. Também recuperamos o`TaggedContent` interface, permitindo-nos adicionar elementos de estrutura como parágrafos, links e imagens.

## Etapa 2: Defina o título e o idioma  

Cada PDF deve ter um título e uma configuração de idioma, especialmente se você deseja estar em conformidade com os padrões PDF/UA.

```csharp
// Defina o título e o idioma do documento
taggedContent.SetTitle("Link Elements Example");
taggedContent.SetLanguage("en-US");
```
  
Esta etapa garante que seu PDF tenha um título significativo e defina o idioma como inglês (`en-US`). Isso é essencial para acessibilidade e garante que leitores de tela ou outras tecnologias assistivas possam interpretar seu documento corretamente.

## Etapa 3: Criar e anexar parágrafos  

Nesta etapa, adicionaremos parágrafos para conter nossos elementos de link.

```csharp
// Crie o elemento raiz
StructureElement rootElement = taggedContent.RootElement;

// Crie um parágrafo e adicione-o ao elemento raiz
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
```
  
Criamos um elemento de estrutura raiz, que é essencialmente o contêiner de nível superior para todos os outros elementos. Em seguida, criamos um parágrafo (`p1`) e anexá-lo ao elemento raiz.

## Etapa 4: adicione um link simples  

Agora vamos adicionar um hiperlink básico que aponta para o Google.

```csharp
// Crie um elemento de link e adicione-o ao parágrafo
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);

// Definir hiperlink e texto para o link
link1.Hyperlink = new WebHyperlink("http://google.com");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";
```
  
Nesta etapa, criamos um elemento de link, definimos seu hiperlink como "http://google.com" e fornecemos texto ("Google") para o link. Também adicionamos uma descrição alternativa para garantir acessibilidade.

## Etapa 5: Adicionando um link com spans  

Também podemos criar links com diferentes extensões de texto.

```csharp
// Crie outro parágrafo
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);

// Crie um link com um elemento span
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://google.com");

SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);

link2.AlternateDescriptions = "Link to Google";
```
  
Aqui, usamos um elemento span para incluir parte do texto dentro do link, permitindo-nos personalizar como certas partes do link aparecem.

## Etapa 6: Link multilinha  

E se o texto do seu link for muito longo? Não se preocupe, você pode dividi-lo em várias linhas.

```csharp
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);

LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://google.com");
link4.SetText("The multiline link: Google Google Google Google Google...");
link4.AlternateDescriptions = "Link to Google (multiline)";
```
  
Nesse caso, criamos um link multilinha simplesmente definindo um valor de texto longo, e o texto será automaticamente quebrado em várias linhas.

## Etapa 7: Adicione uma imagem ao link  

Por fim, você também pode adicionar imagens dentro de um link.

```csharp
// Crie um novo parágrafo e elemento de link
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);

LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://google.com");

// Adicione uma imagem ao link
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
link5.AppendChild(figure5);

link5.AlternateDescriptions = "Link to Google";
```
  
Esta etapa demonstra como você pode aprimorar seus links com uma imagem. Neste caso, adicionamos um ícone do Google dentro do link. Também garantimos a acessibilidade definindo texto alternativo para a imagem.

## Etapa 8: Validar PDF para conformidade  

Se você deseja obter conformidade com PDF/UA (um padrão de acessibilidade), é uma boa prática validar seu documento.

```csharp
// Salvar o documento PDF
document.Save(outFile);

// Validar o documento para conformidade com PDF/UA
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```
  
Salvamos o documento e o validamos de acordo com o padrão PDF/UA, o que garante que o PDF atenda aos requisitos de acessibilidade.

## Conclusão  

Neste tutorial, abordamos como criar documentos PDF estruturados usando Aspose.PDF para .NET. Desde adicionar hiperlinks básicos até estruturas mais complexas como spans, links multilinha e até imagens, este guia fornece uma base sólida para manipular elementos de link em seus PDFs. Com o benefício adicional da conformidade com PDF/UA, agora você está equipado para criar PDFs acessíveis e navegáveis.

## Perguntas frequentes

### Posso adicionar estruturas mais complexas, como tabelas, dentro de links?  
Não, os links são principalmente para texto e imagens, mas você pode incorporar elementos complexos nas proximidades.

### A validação de PDF/UA é obrigatória?  
Nem sempre, mas é altamente recomendado se você estiver preocupado com acessibilidade.

### O que acontece se o caminho do arquivo de imagem estiver incorreto?  
O documento não exibirá a imagem e poderá gerar um erro durante a renderização.

### Posso estilizar o texto dentro do link?  
Sim, você pode aplicar estilos de texto usando os elementos span.

### É possível criar links internos para documentos?  
Absolutamente! Você pode vincular a seções específicas dentro do mesmo documento.