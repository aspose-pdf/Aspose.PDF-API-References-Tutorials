---
title: Atualizar marcadores filhos em arquivo PDF
linktitle: Atualizar marcadores filhos em arquivo PDF
second_title: Referência da API Aspose.PDF para .NET
description: Atualize facilmente os favoritos secundários em um arquivo PDF com Aspose.PDF para .NET.
type: docs
weight: 110
url: /pt/net/programming-with-bookmarks/update-child-bookmarks/
---
A atualização de marcadores secundários em um arquivo PDF permite modificar as propriedades de marcadores específicos em um marcador principal. Com Aspose.PDF for .NET, você pode atualizar facilmente os favoritos filhos seguindo o seguinte código-fonte:

## Etapa 1: importar as bibliotecas necessárias

Antes de começar, você precisa importar as bibliotecas necessárias para seu projeto C#. Aqui está a diretiva de importação necessária:

```csharp
using Aspose.Pdf;
```

## Etapa 2: definir o caminho para a pasta de documentos

 Nesta etapa, você precisa especificar o caminho para a pasta que contém o arquivo PDF que deseja atualizar. Substituir`"YOUR DOCUMENT DIRECTORY"`no código a seguir com o caminho real para sua pasta de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passo 3: Abra o documento PDF

Agora abriremos o documento PDF que queremos atualizar usando o seguinte código:

```csharp
Document pdfDocument = new Document(dataDir + "UpdateChildBookmarks.pdf");
```

## Etapa 4: obter o objeto de marcador pai

Nesta etapa, obteremos o objeto de marcador pai específico a partir do qual queremos atualizar os marcadores filhos. No exemplo abaixo, recuperamos o marcador pai no índice 1 (o segundo marcador na coleção de marcadores). Você pode ajustar o índice de acordo com suas necessidades. Aqui está o código correspondente:

```csharp
OutlineItemCollection pdfOutline = pdfDocument.Outlines[1];
```

## Etapa 5: obter o objeto de marcador filho

Agora vamos obter o objeto de marcador filho específico que queremos atualizar. No exemplo abaixo, recuperamos o marcador filho no índice 1 (o segundo marcador filho na coleção de marcadores filhos do marcador pai). Você pode ajustar o índice de acordo com suas necessidades. Aqui está o código correspondente:

```csharp
OutlineItemCollection childOutline = pdfOutline[1];
```

## Etapa 6: atualizar as propriedades dos favoritos secundários

Agora vamos atualizar as propriedades do marcador filho, como título, estilo itálico e estilo negrito. Você pode ajustar essas propriedades de acordo com suas necessidades. Aqui está o código correspondente:

```csharp
childOutline.Title = "Updated Outline";
childOutline. Italic = true;
childOutline. Bold = true;
```

## Etapa 7: salve o arquivo atualizado

 Agora vamos salvar o arquivo PDF atualizado usando o`Save` método do`pdfDocument` objeto. Aqui está o código correspondente:

```csharp
dataDir = dataDir + "UpdateChildBookmarks_out.pdf";
pdfDocument.Save(dataDir);
```

### Exemplo de código-fonte para atualizar marcadores filhos usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "UpdateChildBookmarks.pdf");
// Obtenha um objeto de marcador
OutlineItemCollection pdfOutline = pdfDocument.Outlines[1];
//Obter objeto de marcador filho
OutlineItemCollection childOutline = pdfOutline[1];
childOutline.Title = "Updated Outline";
childOutline.Italic = true;
childOutline.Bold = true;
dataDir = dataDir + "UpdateChildBookmarks_out.pdf";            
// Salvar saída
pdfDocument.Save(dataDir);
Console.WriteLine("\nChild bookmarks updated successfully.\nFile saved at " + dataDir);
```

## Conclusão

Parabéns! Agora você tem um guia passo a passo para atualizar marcadores filhos com Aspose.PDF for .NET. Você pode usar esse código para modificar as propriedades dos marcadores secundários em seus documentos PDF.

Certifique-se de verificar a documentação oficial do Aspose.PDF para obter mais informações sobre recursos avançados de manipulação de marcadores.

### Perguntas frequentes para atualizar marcadores secundários em arquivo PDF

#### P: O que são marcadores secundários em um arquivo PDF?

R: Marcadores filhos são marcadores aninhados em um marcador pai. Eles permitem criar uma estrutura hierárquica para navegar pelo conteúdo de um documento PDF.

#### P: Por que eu precisaria atualizar os favoritos secundários?

R: A atualização de marcadores secundários é útil quando você deseja modificar as propriedades, os títulos ou os estilos de marcadores específicos em um marcador principal. Isso ajuda a personalizar a estrutura de navegação do documento.

#### P: Como importo as bibliotecas necessárias para meu projeto C#?

R: Para importar as bibliotecas necessárias para o seu projeto C#, inclua a seguinte diretiva de importação:

```csharp
using Aspose.Pdf;
```

Esta diretiva permite acessar as classes e métodos necessários para trabalhar com documentos PDF e marcadores.

#### P: Como especifico o caminho para a pasta de documentos?

 R: Substitua`"YOUR DOCUMENT DIRECTORY"` no código-fonte fornecido com o caminho real para a pasta que contém o arquivo PDF que você deseja atualizar.

#### P: Como abro um documento PDF para atualizar marcadores secundários?

R: Para abrir um documento PDF para atualizar marcadores secundários, use o seguinte código:

```csharp
Document pdfDocument = new Document(dataDir + "UpdateChildBookmarks.pdf");
```

 Substituir`"UpdateChildBookmarks.pdf"` com o nome real do arquivo.

#### P: Como obtenho o objeto de marcador pai do qual desejo atualizar os marcadores secundários?

 R: Para recuperar um marcador pai específico para atualizar marcadores filhos, acesse o`Outlines` propriedade do`pdfDocument` objeto. No exemplo abaixo, recuperamos o marcador pai no índice 1:

```csharp
OutlineItemCollection pdfOutline = pdfDocument.Outlines[1];
```

#### P: Como obtenho o objeto de marcador filho que desejo atualizar?

 R: Para recuperar um marcador filho específico para atualização, acesse o`OutlineItemCollection` do marcador pai. No exemplo abaixo, recuperamos o marcador filho no índice 1:

```csharp
OutlineItemCollection childOutline = pdfOutline[1];
```

#### P: Quais propriedades de favoritos secundários posso atualizar?

R: Você pode atualizar diversas propriedades de um marcador filho, como título, estilo em itálico e estilo em negrito. Personalize essas propriedades de acordo com suas necessidades:

```csharp
childOutline.Title = "Updated Outline";
childOutline.Italic = true;
childOutline.Bold = true;
```

#### P: Posso atualizar vários marcadores secundários usando este método?

R: Sim, você pode repetir as etapas 4 a 7 para cada marcador filho que deseja atualizar. Modifique o índice pai e o índice filho conforme necessário.

#### P: Como salvo o arquivo PDF atualizado?

 R: Salve o arquivo PDF atualizado usando o`Save` método do`pdfDocument` objeto:

```csharp
dataDir = dataDir + "UpdateChildBookmarks_out.pdf";
pdfDocument.Save(dataDir);
```