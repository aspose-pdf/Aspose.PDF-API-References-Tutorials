---
title: Herdar zoom no arquivo PDF
linktitle: Herdar zoom no arquivo PDF
second_title: Referência da API Aspose.PDF para .NET
description: Herde facilmente o zoom do marcador no arquivo PDF com Aspose.PDF para .NET.
type: docs
weight: 90
url: /pt/net/programming-with-bookmarks/inherit-zoom/
---
herança de zoom no arquivo PDF permite especificar um nível de zoom padrão para marcadores. Com Aspose.PDF for .NET, você pode herdar facilmente o zoom seguindo o seguinte código-fonte:

## Etapa 1: importar as bibliotecas necessárias

Antes de começar, você precisa importar as bibliotecas necessárias para seu projeto C#. Aqui está a diretiva de importação necessária:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## Etapa 2: definir o caminho para a pasta de documentos

 Nesta etapa, você precisa especificar o caminho para a pasta que contém o arquivo PDF do qual deseja herdar o zoom. Substituir`"YOUR DOCUMENT DIRECTORY"`no código a seguir com o caminho real para sua pasta de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passo 3: Abra o documento PDF

Agora vamos abrir o documento PDF do qual queremos herdar o zoom usando o seguinte código:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Etapa 4: obter coleção de favoritos

 Nesta etapa, obteremos a coleção de marcadores ou marcos do documento utilizando o`Outlines` propriedade do`doc` objeto. Aqui está o código correspondente:

```csharp
OutlineItemCollection item = new OutlineItemCollection(doc.Outlines);
```

## Etapa 5: definir o nível de zoom

 Agora vamos definir o nível de zoom criando um`XYZExplicitDestination` objeto com as coordenadas x, y e z especificadas. Aqui usamos as coordenadas (100, 100, 0) com zoom de 2. Aqui está o código correspondente:

```csharp
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
```

## Etapa 6: adicionar nível de zoom aos favoritos

 Nesta etapa, adicionamos o`XYZExplicitDestination` objeto como uma ação para os marcadores do`item` coleção. Aqui está o código correspondente:

```csharp
item. Action = new GoToAction(dest);
```

## Etapa 7: adicione os favoritos atualizados ao documento

 Finalmente, adicionamos os marcadores atualizados à coleção de marcadores do documento usando o`Add` método do`doc.Outlines` objeto. Aqui está o código correspondente:

```csharp
doc. Outlines. Add(item);
```

## Etapa 8: salve o arquivo atualizado

 Agora vamos salvar o arquivo PDF atualizado usando o`Save` método do`doc` objeto. Aqui está o código correspondente:

```csharp
dataDir = dataDir + "InheritZoom_out.pdf";
doc.Save(dataDir);
```

### Exemplo de código-fonte para Inherit Zoom usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document doc = new Document(dataDir + "input.pdf");
// Obtenha uma coleção de contornos/marcadores de arquivo PDF
OutlineItemCollection item = new OutlineItemCollection(doc.Outlines);
// Defina o nível de zoom como 0
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
// Adicione XYZExplicitDestination como ação para descrever a coleção de PDF
item.Action = new GoToAction(dest);
// Adicionar item à coleção de contornos do arquivo PDF
doc.Outlines.Add(item);
dataDir = dataDir + "InheritZoom_out.pdf";
// Salvar saída
doc.Save(dataDir);
Console.WriteLine("\nBookmarks updated successfully.\nFile saved at " + dataDir);
```

## Conclusão

Parabéns! Agora você tem um guia passo a passo para herdar o zoom com Aspose.PDF para .NET. Você pode usar este código para especificar um nível de zoom padrão para marcadores em seus documentos PDF.

Certifique-se de verificar a documentação oficial do Aspose.PDF para obter mais informações sobre recursos avançados de manipulação de marcadores.

### Perguntas frequentes sobre como herdar zoom em arquivo PDF

#### P: O que é herança de zoom em um arquivo PDF?

R: A herança de zoom refere-se à capacidade de especificar um nível de zoom padrão para marcadores em um documento PDF. Isso permite uma navegação consistente e fácil de usar quando os usuários interagem com os marcadores.

#### P: Por que eu desejaria herdar os níveis de zoom dos marcadores?

R: Herdar os níveis de zoom garante que os usuários tenham uma experiência de visualização consistente ao navegar pelos marcadores em um documento PDF. Pode ser particularmente útil quando você deseja fornecer uma visualização específica para diferentes seções de um documento.

#### P: Como importo as bibliotecas necessárias para meu projeto C#?

R: Para importar as bibliotecas necessárias para seu projeto C#, inclua as seguintes diretivas de importação:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

Estas diretivas permitem acessar as classes e métodos necessários para trabalhar com documentos PDF e marcadores.

#### P: Como especifico o caminho para a pasta de documentos?

 R: No código-fonte fornecido, substitua`"YOUR DOCUMENT DIRECTORY"` pelo caminho real para a pasta que contém o arquivo PDF para o qual você deseja herdar os níveis de zoom.

#### P: Como abro um documento PDF para herdar os níveis de zoom?

R: Para abrir um documento PDF para herdar níveis de zoom, use o seguinte código:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

 Substituir`"input.pdf"` com o nome real do arquivo.

#### P: Como defino o nível de zoom dos marcadores?

 R: Para definir o nível de zoom, crie um`XYZExplicitDestination` objeto com as coordenadas desejadas e fator de zoom. Aqui está um exemplo:

```csharp
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
```

Isso define o nível de zoom para 2 nas coordenadas (100, 100).

#### P: Como adiciono o nível de zoom aos favoritos?

 R: Adicione o`XYZExplicitDestination` objeto como uma ação para a coleção de marcadores:

```csharp
item.Action = new GoToAction(dest);
```

 Onde`item` é um`OutlineItemCollection` representando um marcador.

#### P: Como salvo o arquivo PDF atualizado?

 R: Salve o arquivo PDF atualizado usando o`Save` método do`doc` objeto:

```csharp
dataDir = dataDir + "InheritZoom_out.pdf";
doc.Save(dataDir);
```

#### P: Posso personalizar os níveis de zoom para diferentes marcadores?

 R: Sim, você pode personalizar os níveis de zoom para diferentes marcadores criando vários`XYZExplicitDestination` objetos com diferentes coordenadas e fatores de zoom.

#### P: Existe um limite para o número de marcadores aos quais posso aplicar a herança de zoom?

R: Normalmente não há limite estrito para o número de marcadores aos quais você pode aplicar a herança de zoom. Contudo, documentos muito grandes com um número excessivo de marcadores podem exigir um gerenciamento de memória eficiente.

#### P: Como posso confirmar se a herança de zoom foi aplicada?

R: Abra o arquivo PDF gerado para verificar se os níveis de zoom especificados foram herdados pelos marcadores.