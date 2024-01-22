---
title: Adicionar marcadores filhos a PDFs
linktitle: Adicionar marcadores filhos a PDFs
second_title: API de processamento de PDF Java Aspose.PDF
description: Aprenda como aprimorar documentos PDF com marcadores secundários usando Aspose.PDF para Java. Guia passo a passo com exemplos de código para melhor navegação e organização.
type: docs
weight: 11
url: /pt/java/pdf-bookmarks/add-child-bookmarks-pdfs/
---

## Introdução à adição de marcadores filhos a PDFs

Neste artigo, exploraremos como adicionar marcadores secundários a documentos PDF usando Aspose.PDF para Java. Os marcadores secundários são uma forma conveniente de organizar e navegar pelo conteúdo de um documento PDF, tornando mais fácil para os usuários encontrar seções ou tópicos específicos no documento.

## Pré-requisitos

Antes de mergulharmos na implementação, certifique-se de ter os seguintes pré-requisitos em vigor:

- Ambiente de desenvolvimento Java instalado em seu sistema.
-  Aspose.PDF para biblioteca Java. Você pode baixá-lo em[aqui](https://releases.aspose.com/pdf/java/).

## Configurando o Ambiente

1. Baixe a biblioteca Aspose.PDF para Java no link fornecido.
2. Adicione a biblioteca ao seu projeto Java.

Agora, vamos começar criando um novo documento PDF e adicionando marcadores secundários a ele, passo a passo.

## Criando um novo documento PDF

Para começar, precisamos inicializar um documento PDF e adicionar páginas a ele. Aqui está o trecho de código para começar:

```java
// Inicialize um documento PDF
Document pdfDocument = new Document();

// Adicione páginas ao PDF
pdfDocument.getPages().add();
pdfDocument.getPages().add();
```

Neste exemplo, criamos um novo documento PDF e adicionamos duas páginas a ele.

## Adicionando marcadores principais

Os marcadores principais servem como seções ou categorias principais em seu documento PDF. Vamos criar alguns marcadores principais:

```java
// Crie marcadores principais
OutlineItemCollection outline = pdfDocument.getOutlines();
OutlineItemCollection parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 1");
outline.add(parentBookmark);

parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 2");
outline.add(parentBookmark);
```

Adicionamos dois marcadores principais, "Marcador pai 1" e "Marcador pai 2".

## Adicionando marcadores filhos

Agora é hora de adicionar marcadores filhos aos marcadores pais que criamos anteriormente. Os marcadores secundários representam tópicos ou subseções específicas em cada marcador principal. Veja como você pode fazer isso:

```java
// Adicionar marcadores filhos ao marcador pai 1
OutlineItemCollection childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.1");
parentBookmark.add(childBookmark);

childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.2");
parentBookmark.add(childBookmark);

//Adicionar marcadores filhos ao marcador pai 2
childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 2.1");
parentBookmark.add(childBookmark);
```

Adicionamos marcadores filhos ao "Marcador pai 1" e ao "Marcador pai 2".

## Personalizando a aparência do marcador

Você pode personalizar a aparência dos marcadores alterando seu texto e estilo. Além disso, você pode adicionar ícones aos favoritos para melhor representação visual. Aqui está um exemplo de como fazer isso:

```java
// Personalize a aparência do marcador
parentBookmark.setItalic(true);
childBookmark.setForegroundColor(Color.getGreen());
childBookmark.setIcon(OutlineItemCollection.getItalicIcon());
```

Neste exemplo, colocamos o marcador pai em itálico, alteramos a cor do texto do marcador filho para verde e adicionamos um ícone em itálico ao marcador filho.

## Tratamento de eventos

Os marcadores também podem ter ações associadas a eles. Por exemplo, você pode adicionar ações que são acionadas quando um usuário clica em um marcador. Veja como você pode lidar com eventos de clique em favoritos:

```java
// Adicionar uma ação a um marcador
GoToAction action = new GoToAction(pdfDocument.getPages().get_Item(1));
childBookmark.setAction(action);
```

Neste código, adicionamos uma ação “GoTo” a um marcador filho que levará o usuário para a segunda página do PDF quando clicado.

## Salvando o PDF

Depois de adicionar todos os marcadores necessários e personalizar sua aparência e ações, você poderá salvar o documento PDF modificado:

```java
// Salve o documento PDF
pdfDocument.save("output.pdf");
```

Seu documento PDF com marcadores secundários está pronto.

## Código fonte completo

Aqui está o código-fonte completo para adicionar marcadores filhos a um documento PDF usando Aspose.PDF para Java:

```java
// Inicialize um documento PDF
Document pdfDocument = new Document();

// Adicione páginas ao PDF
pdfDocument.getPages().add();
pdfDocument.getPages().add();

// Crie marcadores principais
OutlineItemCollection outline = pdfDocument.getOutlines();
OutlineItemCollection parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 1");
outline.add(parentBookmark);

parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 2");
outline.add(parentBookmark);

// Adicionar marcadores filhos ao marcador pai 1
OutlineItemCollection childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.1");
parentBookmark.add(childBookmark);

childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.2");
parentBookmark.add(childBookmark);

//Adicionar marcadores filhos ao marcador pai 2
childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 2.1");
parentBookmark.add(childBookmark);

// Personalize a aparência do marcador
parentBookmark.setItalic(true);
childBookmark.setForegroundColor(Color.getGreen());
childBookmark.setIcon(OutlineItemCollection.getItalicIcon());

// Adicionar uma ação a um marcador
GoToAction action = new GoToAction(pdfDocument.getPages().get_Item(1));
childBookmark.setAction(action);

// Salve o documento PDF
pdfDocument.save("output.pdf");
```

## Conclusão

Adicionar marcadores secundários a PDFs usando Aspose.PDF for Java é um recurso poderoso que aprimora a navegação e organização de seus documentos. Seguindo as etapas descritas neste artigo, você pode criar PDFs bem estruturados com marcadores principais e secundários, personalizar sua aparência e até mesmo adicionar ações para aprimorar a experiência do usuário.

## Perguntas frequentes

### Como posso baixar Aspose.PDF para Java?

 Você pode baixar Aspose.PDF para Java no site[aqui](https://releases.aspose.com/pdf/java/).

### Os marcadores secundários são suportados em todos os visualizadores de PDF?

Sim, os marcadores secundários são suportados na maioria dos visualizadores de PDF modernos e fornecem uma experiência de usuário aprimorada para navegar pelos documentos PDF.

### Posso personalizar ainda mais a aparência dos favoritos?

Sim, você pode personalizar a aparência dos marcadores ajustando estilos de texto, cores e ícones de acordo com o design do seu documento.

### Que outras ações posso adicionar aos favoritos?

Além das ações "GoTo", você pode adicionar ações como ações "URI" para abrir links da web ou ações "JavaScript" para executar scripts personalizados quando um marcador é clicado.

### O Aspose.PDF for Java é adequado para projetos comerciais?

Sim, Aspose.PDF for Java é adequado para projetos pessoais e comerciais e oferece uma ampla gama de recursos para manipulação e geração de PDF.