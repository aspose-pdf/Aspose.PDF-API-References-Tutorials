---
title: Obter janela de documento
linktitle: Obter janela de documento
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda a usar o recurso GetDocumentWindow do Aspose.PDF para .NET para recuperar informações sobre as propriedades da janela de um documento PDF.
type: docs
weight: 170
url: /pt/net/programming-with-document/getdocumentwindow/
---
Aspose.PDF para .NET é uma poderosa biblioteca de manipulação de PDF que permite aos desenvolvedores criar, editar e converter arquivos PDF em seus aplicativos .NET. Um dos recursos oferecidos por esta biblioteca é a capacidade de recuperar informações sobre as propriedades da janela de um documento. Este tutorial o guiará pelas etapas de uso do`GetDocumentWindow` recurso do Aspose.PDF para .NET para recuperar informações sobre as propriedades da janela de um documento PDF.

## Etapa 1: instalar o Aspose.PDF para .NET

 Para usar o Aspose.PDF para .NET em seus aplicativos .NET, você deve primeiro instalar a biblioteca. Você pode baixar a versão mais recente da biblioteca do[Página de download do Aspose.PDF para .NET](https://releases.aspose.com/pdf/net).

Após baixar a biblioteca, extraia o conteúdo do arquivo ZIP para uma pasta no seu computador. Você precisará então adicionar uma referência ao Aspose.PDF for .NET DLL no seu projeto .NET.

## Etapa 2: Carregue o documento PDF

 Depois de instalar o Aspose.PDF para .NET e adicionar uma referência à DLL no seu projeto .NET, você pode começar a usar o`GetDocumentWindow`recurso para recuperar informações sobre as propriedades da janela de um documento PDF.

O primeiro passo para usar esse recurso é carregar o documento PDF sobre o qual você deseja recuperar informações. Para fazer isso, você pode usar o seguinte código:

```csharp
// O caminho para o documento PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Abra o documento PDF
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");
```

 No código acima, substitua`"YOUR DOCUMENT DIRECTORY"` com o caminho para o diretório onde seu documento PDF está localizado. Este código carregará o documento PDF em um`Document` objeto, que você pode usar para recuperar informações sobre as propriedades da janela do documento.

## Etapa 3: recuperar as propriedades da janela do documento

Para recuperar informações sobre as propriedades da janela de um documento PDF, você pode usar o seguinte código:

```csharp
// Recuperar as propriedades da janela do documento
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);
Console.WriteLine("Direction : {0}", pdfDocument.Direction);
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```

No código acima, cada linha recupera uma propriedade de janela diferente do documento PDF e a envia para o console. Você pode personalizar esse código para recuperar apenas as propriedades nas quais você está interessado.

### Exemplo de código-fonte para obter janela de documento de arquivo PDF usando Aspose.PDF para .NET 

 Aqui está o código-fonte completo para recuperar as propriedades da janela de um documento PDF usando o`GetDocumentWindow` Recurso do Aspose.PDF para .NET:

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Abrir documento
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");

// Obtenha diferentes propriedades do documento
// Posição da janela do documento - Padrão: falso
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);

// Ordem de leitura predominante; determina a posição da página
// Quando exibido lado a lado - Padrão: L2R
Console.WriteLine("Direction : {0}", pdfDocument.Direction);

// Se a barra de título da janela deve exibir o título do documento
// Se falso, a barra de título exibe o nome do arquivo PDF - Padrão: falso
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);

// Se deve redimensionar a janela do documento para ajustá-la ao tamanho de
// Primeira página exibida - Padrão: falso
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);

// Se deve ocultar a barra de menu do aplicativo visualizador - Padrão: falso
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);

// Se deve ocultar a barra de ferramentas do aplicativo visualizador - Padrão: falso
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);

// Se deve ocultar elementos da IU, como barras de rolagem
// E deixando apenas o conteúdo da página exibido - Padrão: falso
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);

//Modo de página do documento. Como exibir o documento ao sair do modo de tela cheia.
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);

// O layout da página, ou seja, página única, uma coluna
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);

// Como o documento deve ser exibido quando aberto
// Ou seja, mostrar miniaturas, tela cheia, mostrar painel de anexos
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```

## Conclusão

Neste tutorial, aprendemos como usar o Aspose.PDF para .NET para recuperar informações sobre as propriedades da janela de um documento PDF. Ao carregar um documento PDF e acessar suas propriedades de janela, você pode reunir informações sobre como o documento deve ser exibido quando aberto em um aplicativo visualizador. O Aspose.PDF para .NET fornece um poderoso conjunto de recursos para trabalhar com arquivos PDF programaticamente, tornando-o uma ferramenta valiosa para manipulação de PDF em aplicativos .NET.

### Perguntas frequentes

#### P: Qual é o propósito de recuperar as propriedades da janela de um documento PDF?

A: Recuperar as propriedades da janela de um documento PDF permite que você reúna informações sobre como o documento PDF deve ser exibido quando aberto em um aplicativo visualizador. Essas propriedades controlam vários aspectos, como posição da janela, modo de exibição e visibilidade dos elementos da IU.

#### P: Como posso instalar o Aspose.PDF para .NET no meu projeto .NET?

 R: Para instalar o Aspose.PDF para .NET, você precisa baixar a biblioteca do[Página de download do Aspose.PDF para .NET](https://releases.aspose.com/pdf/net). Após o download, extraia o conteúdo do arquivo ZIP e adicione uma referência à DLL Aspose.PDF for .NET no seu projeto .NET.

#### P: Posso personalizar o código para recuperar apenas propriedades específicas da janela?

R: Sim, você pode personalizar o código para recuperar propriedades específicas da janela comentando as linhas que você não precisa. Cada linha no código corresponde a uma propriedade específica da janela, então você pode incluir ou excluir propriedades com base em seus requisitos.

#### P: Que tipos de propriedades de janela posso recuperar usando o Aspose.PDF para .NET?

R: Usando o Aspose.PDF para .NET, você pode recuperar várias propriedades de janela de um documento PDF, incluindo centralizar a janela, definir o layout da página, controlar a exibição de barras de ferramentas e barras de menu e muito mais.