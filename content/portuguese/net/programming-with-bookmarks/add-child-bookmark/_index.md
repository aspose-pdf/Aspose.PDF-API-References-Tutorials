---
title: Adicionar marcador filho em arquivo PDF
linktitle: Adicionar marcador filho em arquivo PDF
second_title: Referência da API Aspose.PDF para .NET
description: Adicione facilmente um marcador filho em um arquivo PDF para uma navegação mais organizada com Aspose.PDF para .NET.
type: docs
weight: 20
url: /pt/net/programming-with-bookmarks/add-child-bookmark/
---
Adicionar marcadores secundários em arquivos PDF permite uma organização e navegação mais estruturadas. Com Aspose.PDF for .NET, você pode adicionar facilmente um submarcador seguindo o seguinte código-fonte:

## Etapa 1: importar as bibliotecas necessárias

Antes de começar, você precisa importar as bibliotecas necessárias para seu projeto C#. Aqui está a diretiva de importação necessária:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## Etapa 2: definir o caminho para a pasta de documentos

 Nesta etapa, você precisa especificar o caminho para a pasta que contém o arquivo PDF ao qual deseja adicionar um submarcador. Substituir`"YOUR DOCUMENT DIRECTORY"`no código a seguir com o caminho real para sua pasta de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passo 3: Abra o documento PDF

Agora abriremos o documento PDF ao qual queremos adicionar um submarcador usando o seguinte código:

```csharp
Document pdfDocument = new Document(dataDir + "AddChildBookmark.pdf");
```

## Etapa 4: criar objeto de marcador pai

 Nesta etapa, criaremos um objeto de marcador pai usando o`OutlineItemCollection` class e defina suas propriedades como título, atributo itálico e atributo negrito. Aqui está o código correspondente:

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Parent bookmark";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
```

## Etapa 5: Criar objeto de marcador filho

Nesta etapa, criaremos um objeto de sub-bookmark novamente usando o`OutlineItemCollection` classe e definir suas propriedades. Aqui está o código correspondente:

```csharp
OutlineItemCollection pdfChildOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfChildOutline.Title = "Sub Bookmark";
pdfChildOutline. Italic = true;
pdfChildOutline. Bold = true;
```

## Etapa 6: adicionar o submarcador ao marcador pai

 Finalmente, adicionamos o subbookmark criado à coleção de subbookmarks do bookmark pai usando o comando`Add` método do objeto pai. Aqui está o código correspondente:

```csharp
pdfOutline.Add(pdfChildOutline);
```

## Etapa 7: adicionar o marcador pai à coleção de marcadores do documento

 Finalmente, adicionamos o marcador pai à coleção de marcadores do documento usando o comando`Add` método do`Outlines` propriedade. Aqui está o código correspondente:

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

### Exemplo de código-fonte para Adicionar marcador filho usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "AddChildBookmark.pdf");
// Crie um objeto de marcador pai
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Parent Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;      
// Crie um objeto de marcador filho
OutlineItemCollection pdfChildOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfChildOutline.Title = "Child Outline";
pdfChildOutline.Italic = true;
pdfChildOutline.Bold = true;
// Adicionar marcador filho na coleção de marcadores pai
pdfOutline.Add(pdfChildOutline);
// Adicione um marcador pai na coleção de estrutura de tópicos do documento.
pdfDocument.Outlines.Add(pdfOutline);
dataDir = dataDir + "AddChildBookmark_out.pdf";
// Salvar saída
pdfDocument.Save(dataDir);
Console.WriteLine("\nChild bookmark added successfully.\nFile saved at " + dataDir);
```

## Conclusão

Parabéns! Agora você tem um guia passo a passo para adicionar um submarcador com Aspose.PDF for .NET. Você pode usar este código para organizar e estruturar seus marcadores em documentos PDF.

Certifique-se de verificar a documentação oficial do Aspose.PDF para obter mais informações sobre recursos avançados de manipulação de marcadores.

### Perguntas frequentes sobre como adicionar marcador filho em arquivo PDF

#### P: O que são marcadores secundários em um arquivo PDF?

R: Os marcadores secundários, também conhecidos como submarcadores, são elementos de navegação em um documento PDF estruturados hierarquicamente em um marcador principal. Eles fornecem uma maneira de criar um índice mais organizado e detalhado para o documento.

#### P: Como importo as bibliotecas necessárias para meu projeto C#?

R: Para importar as bibliotecas necessárias para o seu projeto C#, você pode usar a seguinte diretiva de importação:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

Essas bibliotecas fornecem as classes e funções necessárias para trabalhar com documentos PDF e recursos interativos.

#### P: Como especifico o caminho para a pasta de documentos?

 R: No código-fonte fornecido, você precisa substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para a pasta que contém o arquivo PDF com o qual você deseja trabalhar. Isso garante que o código localize corretamente o arquivo PDF de destino.

#### P: Posso criar vários níveis de marcadores secundários?

R: Sim, você pode criar vários níveis de marcadores secundários estendendo o processo descrito no tutorial. Ao criar marcadores principais com submarcadores e aninhá-los ainda mais, você pode criar uma estrutura hierárquica de marcadores para documentos PDF complexos.

####  P: Qual é o propósito do`OutlineItemCollection` class?

 R: O`OutlineItemCollection` class em Aspose.PDF for .NET é usada para criar e gerenciar contornos, que são essencialmente marcadores em um documento PDF. Esta classe permite definir propriedades como título, estilo de fonte e ações para marcadores.

#### P: Como adiciono um submarcador a um marcador pai?

 R: Para adicionar um submarcador a um marcador pai, você cria um novo`OutlineItemCollection` objeto para o sub-marcador e defina suas propriedades. Então você usa o`Add` método do marcador pai`OutlineItemCollection` para adicionar o submarcador à coleção dos pais.

#### P: Posso personalizar a aparência dos favoritos secundários?

R: Sim, semelhante aos marcadores principais, você pode personalizar a aparência dos marcadores secundários definindo propriedades como título, estilo da fonte e outros atributos. Isso permite que você crie marcadores visualmente distintos e informativos.

#### P: O Aspose.PDF for .NET é compatível com outras linguagens de programação?

R: Aspose.PDF for .NET foi projetado especificamente para ambientes C# e .NET. No entanto, Aspose oferece bibliotecas semelhantes para outras linguagens de programação, como Java e Android, cada uma adaptada às suas respectivas plataformas.

#### P: Como os marcadores secundários melhoram a navegação no PDF?

R: Os marcadores secundários melhoram a navegação no PDF, fornecendo um índice mais estruturado e organizado. Os usuários podem acessar rapidamente seções específicas do documento por meio da estrutura hierárquica de marcadores.