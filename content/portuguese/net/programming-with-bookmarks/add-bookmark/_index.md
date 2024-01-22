---
title: Adicionar marcador em arquivo PDF
linktitle: Adicionar marcador em arquivo PDF
second_title: Referência da API Aspose.PDF para .NET
description: Adicione facilmente marcadores em arquivos PDF para melhorar a navegação com Aspose.PDF para .NET.
type: docs
weight: 10
url: /pt/net/programming-with-bookmarks/add-bookmark/
---
Adicionar marcadores em um arquivo PDF permite uma navegação fácil e rápida. Com Aspose.PDF for .NET, você pode facilmente adicionar um marcador em um arquivo PDF seguindo o seguinte código-fonte:

## Etapa 1: importar as bibliotecas necessárias

Antes de começar, você precisa importar as bibliotecas necessárias para seu projeto C#. Aqui está a diretiva de importação necessária:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## Etapa 2: definir o caminho para a pasta de documentos

 Nesta etapa, você precisa especificar o caminho para a pasta que contém o arquivo PDF ao qual deseja adicionar um marcador. Substituir`"YOUR DOCUMENT DIRECTORY"`no código a seguir com o caminho real para sua pasta de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passo 3: Abra o documento PDF

Agora abriremos o documento PDF ao qual queremos adicionar um marcador usando o seguinte código:

```csharp
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
```

## Etapa 4: criar objeto de marcador

 Nesta etapa, criaremos um objeto marcador usando`OutlineItemCollection` classe e definir suas propriedades como título, atributo itálico, atributo negrito e ação a ser executada quando clicado. Aqui está o código correspondente:

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
```

## Etapa 5: adicionar marcador ao documento

 Finalmente, adicionamos o marcador criado à coleção de marcadores do documento usando o`Add` método do`Outlines` propriedade. Aqui está o código correspondente:

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

### Exemplo de código-fonte para Adicionar marcador usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
// Crie um objeto de marcador
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;
// Defina o número da página de destino
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
// Adicione um marcador na coleção de estrutura de tópicos do documento.
pdfDocument.Outlines.Add(pdfOutline);
dataDir = dataDir + "AddBookmark_out.pdf";
// Salvar saída
pdfDocument.Save(dataDir);
Console.WriteLine("\nBookmark added successfully.\nFile saved at " + dataDir);
```

## Conclusão

Parabéns! Agora você tem um guia passo a passo para adicionar um marcador usando Aspose.PDF for .NET. Você pode usar este código para melhorar a navegação em seus documentos PDF adicionando marcadores personalizados.

Certifique-se de verificar a documentação oficial do Aspose.PDF para obter mais informações sobre recursos avançados de manipulação de marcadores.


### Perguntas frequentes sobre como adicionar um marcador em um arquivo PDF

#### P: O que são marcadores em um arquivo PDF?

R: Os marcadores, também conhecidos como contornos, são elementos interativos que fornecem navegação e estrutura em um documento PDF. Eles permitem que os usuários pulem rapidamente para seções ou páginas específicas.

#### P: Por que eu precisaria adicionar marcadores a um arquivo PDF?

R: Adicionar marcadores a um arquivo PDF melhora a experiência do usuário e facilita a navegação dos leitores pelo conteúdo do documento. Os marcadores podem servir como índice ou fornecer acesso rápido a seções importantes.

#### P: Como importo as bibliotecas necessárias para meu projeto C#?

R: Para importar as bibliotecas necessárias para o seu projeto C#, inclua as seguintes diretivas de importação:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

Estas diretivas permitem acessar as classes e métodos necessários para trabalhar com documentos PDF e marcadores.

#### P: Como especifico o caminho para a pasta de documentos?

 R: Substitua`"YOUR DOCUMENT DIRECTORY"` no código-fonte fornecido com o caminho real para a pasta que contém o arquivo PDF ao qual deseja adicionar um marcador.

#### P: Como abro um documento PDF para adicionar marcadores?

R: Para abrir um documento PDF para adicionar marcadores, use o seguinte código:

```csharp
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
```

 Substituir`"AddBookmark.pdf"` com o nome real do arquivo.

#### P: Como posso criar um objeto de marcador?

 R: Para criar um objeto de marcador, use o`OutlineItemCollection` aula. Personalize suas propriedades, como título, estilo em itálico, estilo em negrito e ação a ser executada quando clicado.

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
```

####  P: Qual é o propósito do`Action` property in a bookmark?

 R: O`Action` propriedade especifica a ação a ser executada quando o marcador é clicado. Neste exemplo, usamos o`GoToAction`class para navegar para uma página específica (página 2 neste caso).

#### P: Como adiciono o marcador ao documento?

 R: Use o`Add` método do`Outlines` propriedade para adicionar o marcador criado à coleção de marcadores do documento.

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

#### P: Posso adicionar vários marcadores usando este método?

R: Sim, você pode repetir as etapas 4 a 8 para adicionar vários marcadores ao documento. Personalize as propriedades e ações de cada marcador conforme necessário.

#### P: Como salvo o arquivo PDF atualizado?

 R: Salve o arquivo PDF atualizado usando o`Save` método do`pdfDocument` objeto:

```csharp
dataDir = dataDir + "AddBookmark_out.pdf";
pdfDocument.Save(dataDir);
```

#### P: Como posso confirmar se os favoritos foram adicionados?

R: Abra o arquivo PDF gerado para verificar se os marcadores especificados foram adicionados ao documento.

#### P: Existe um limite para o número de marcadores que posso adicionar?

R: Geralmente não há limite estrito para o número de marcadores que você pode adicionar, mas considere o tamanho e a complexidade do documento para obter o desempenho ideal.

#### P: Posso personalizar a aparência dos favoritos?

R: Sim, você pode personalizar ainda mais a aparência, cor, estilo e outros atributos do marcador usando os recursos do Aspose.PDF.