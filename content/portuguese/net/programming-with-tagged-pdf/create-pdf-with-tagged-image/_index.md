---
title: Criar PDF com imagem marcada
linktitle: Criar PDF com imagem marcada
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda a criar um PDF marcado com imagens usando o Aspose.PDF para .NET. Siga nosso guia passo a passo para criação de documentos acessíveis e profissionais.
type: docs
weight: 40
url: /pt/net/programming-with-tagged-pdf/create-pdf-with-tagged-image/
---
## Introdução

Criar PDFs pode ser uma tarefa complexa, mas não precisa ser! Hoje, vamos mergulhar em como criar um documento PDF com uma imagem marcada usando o Aspose.PDF para .NET. Se você está curioso sobre como incorporar imagens em seus PDFs e garantir que eles sejam acessíveis, você veio ao lugar certo. Vamos desvendar esse processo passo a passo para que você possa criar PDFs profissionais e acessíveis com facilidade.

## Pré-requisitos

Antes de começar a criar seu PDF com imagens marcadas, há algumas coisas que você precisa:

1. Aspose.PDF para .NET: Esta biblioteca poderosa é essencial para lidar com documentos PDF em aplicativos .NET. Você pode encontrar a biblioteca aqui:[Aspose.PDF para .NET Baixar](https://releases.aspose.com/pdf/net/).
2. .NET Framework ou .NET Core: Certifique-se de ter uma versão compatível do .NET Framework ou .NET Core em sua máquina. Esta biblioteca suporta ambos.
3. Arquivo de imagem: Você precisará de um arquivo de imagem para incorporar ao seu PDF. Em nosso exemplo, usaremos o 'aspose-logo.png'. Certifique-se de tê-lo pronto no seu diretório de documentos. 

Ao garantir que esses pré-requisitos estejam resolvidos, você estará pronto para começar!

## Pacotes de importação

Para dar início à nossa aventura de codificação, precisamos configurar nosso espaço de trabalho importando os namespaces Aspose.PDF necessários. Veja como você pode fazer isso:

### Criar um novo projeto

- Abra seu IDE preferido (Visual Studio, por exemplo).
- Crie um novo projeto Console Application. Por que um Console Application? É simplista e perfeito para tutoriais!

### Adicionar referência Aspose.PDF

- Clique com o botão direito do mouse no seu projeto no Solution Explorer e selecione Gerenciar pacotes NuGet.
- Procure por "Aspose.PDF" e instale-o. 
- Isso adicionará todos os pacotes necessários ao seu projeto, permitindo que você acesse as funcionalidades necessárias para manipulação de PDF.

### Importe os namespaces necessários

 No topo do seu arquivo de programa principal (como`Program.cs`), importe os seguintes namespaces:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Ao importar esses pacotes, você está informando ao seu aplicativo para trazer as funcionalidades do Aspose.PDF que utilizaremos.

Agora que configuramos tudo, vamos criar nosso PDF com uma imagem marcada passo a passo.

## Etapa 1: Inicializar o documento

Primeiro, precisamos criar um novo documento PDF:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Defina o caminho para seu diretório
Document document = new Document();
```

-  O que está acontecendo aqui? Estamos instanciando um novo`Document` objeto que representa nosso PDF. Pense nele como uma tela em branco esperando por suas obras-primas!

## Etapa 2: Configurar o conteúdo marcado

Em seguida, configuraremos o conteúdo marcado:

```csharp
ITaggedContent taggedContent = document.TaggedContent;
```

- Por que usar Tagged Content? PDFs marcados são essenciais para acessibilidade, permitindo que leitores de tela entendam a estrutura do documento.

## Etapa 3: Configurar metadados

Agora, vamos adicionar alguns metadados que descrevem nosso PDF:

```csharp
taggedContent.SetTitle("CreatePDFwithTaggedImage");
taggedContent.SetLanguage("en-US");
```

- Meta o quê? Adicionar um título e idioma é como colocar uma etiqueta de nome na sua criação — ajuda os outros a entender do que se trata!

## Etapa 4: Crie um elemento de ilustração

Precisamos criar o elemento que irá conter nossa imagem:

```csharp
IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
```

-  Simples assim?! Sim! O`CreateFigureElement` O método nos permite criar uma nova ilustração e anexá-la ao elemento raiz do nosso conteúdo marcado.

## Etapa 5: Definir propriedades da imagem

Em seguida, vamos definir as propriedades da imagem:

```csharp
figure1.AlternativeText = "Aspose Logo";
figure1.Title = "Image 1";
figure1.SetTag("Fig");
```

- Por que todas essas propriedades? O texto alternativo descreve a imagem para aqueles que não conseguem vê-la, enquanto o título e a tag categorizam a imagem para melhor acessibilidade.

## Etapa 6: adicione a imagem

Agora, é hora de adicionar a imagem real ao nosso PDF:

```csharp
figure1.SetImage(dataDir + @"aspose-logo.png"); // Certifique-se de que o caminho da sua imagem esteja correto!
```

- É aqui que a mágica acontece! Você está incorporando a imagem diretamente no seu PDF. 

## Etapa 7: Salve o documento PDF

Por fim, vamos salvar nossa criação em um arquivo:

```csharp
document.Save(dataDir + "PDFwithTaggedImage.pdf");
```

- grand finale! Após executar esta linha, você encontrará seu novo PDF no diretório especificado.

## Conclusão

Criar PDFs com imagens marcadas usando o Aspose.PDF para .NET é moleza quando você divide em etapas gerenciáveis. Ao seguir este guia, você aprendeu não apenas a criar um PDF, mas também a melhorar sua acessibilidade com conteúdo marcado. Quer você esteja preparando documentos para um público maior ou simplesmente polindo suas criações em PDF, esse conhecimento será útil.

## Perguntas frequentes

### O que é um PDF marcado?
Um PDF marcado é projetado para ser acessível. Ele inclui metadados que permitem que tecnologias assistivas leiam e naveguem nele adequadamente.

### Posso adicionar várias imagens usando o Aspose.PDF?
 Com certeza! Basta repetir os passos para criar novos`IllustrationElement` instâncias no seu documento.

### Onde posso encontrar mais documentação sobre o Aspose.PDF?
 Confira a documentação[aqui](https://reference.aspose.com/pdf/net/).

### Existe uma versão de avaliação gratuita disponível para o Aspose.PDF?
 Sim! Você pode acessar um teste gratuito[aqui](https://releases.aspose.com/).

### Como posso obter suporte para o Aspose.PDF?
 Você pode obter suporte visitando o[Fóruns Aspose](https://forum.aspose.com/c/pdf/10).