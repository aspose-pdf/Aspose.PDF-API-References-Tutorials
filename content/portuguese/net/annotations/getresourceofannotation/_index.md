---
title: Obtenha recurso de anotação
linktitle: Obtenha recurso de anotação
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como recuperar o recurso de uma anotação usando Aspose.PDF for .NET com este guia passo a passo.
type: docs
weight: 90
url: /pt/net/annotations/getresourceofannotation/
---
exemplo mostra como obter recurso de anotação com Aspose.PDF for .NET. Para obter o recurso de uma anotação usando Aspose.PDF for .NET, siga estas etapas:

## Passo 1: Defina o caminho do diretório onde o documento está localizado.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passo 2: Abra o documento PDF que contém a anotação cujo recurso você deseja obter.

```csharp
Document doc = new Document(dataDir + "AddAnnotation.pdf");
```

## Etapa 3: crie uma anotação.

```csharp
ScreenAnnotation sa = new ScreenAnnotation(doc.Pages[1], new Rectangle(100, 400, 300, 600), dataDir + "AddSwfFileAsAnnotation.swf");
```

## Etapa 4: adicione a anotação a uma página do documento.

```csharp
doc.Pages[1].Annotations.Add(sa);
```

## Etapa 5: salve o documento.

```csharp
doc.Save(dataDir + "GetResourceOfAnnotation_Out.pdf");
```

## Etapa 6: Abra o documento modificado.

```csharp
Document doc1 = new Document(dataDir + "GetResourceOfAnnotation_Out.pdf");
```

## Etapa 7: Obtenha a ação da anotação.

```csharp
RenditionAction action = (doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction;
```

## Etapa 7: Obtenha a representação da ação.

```csharp
Rendition rendition = ((doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction).Rendition;
```

## Etapa 8: Obtenha o clipe de mídia.

```csharp
MediaClip clip = (rendition as MediaRendition).MediaClip;
```

## Etapa 9: Obtenha a especificação do arquivo.

```csharp
FileSpecification data = (clip as MediaClipData).Data;
```

## Etapa 10: Leia os dados da mídia.

```csharp
MemoryStream ms = new MemoryStream();
byte[] buffer = new byte[1024];
int read = 0;
Stream source = data.Contents;
while ((read = source.Read(buffer, 0, buffer.Length)) > 0)
{
   ms.Write(buffer, 0, read);
}
```

## Etapa 11: Imprima o nome da representação e da operação de representação.

```csharp
Console.WriteLine(rendition.Name);
Console.WriteLine(action.RenditionOperation);
```

Seguindo essas etapas, você pode facilmente obter o recurso de uma anotação em um documento PDF usando Aspose.PDF for .NET.

### Exemplo de código-fonte para obter recurso de anotação usando Aspose.PDF para .NET:

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Abrir documento
Document doc = new Document(dataDir + "AddAnnotation.pdf");
//Criar anotação
ScreenAnnotation sa = new ScreenAnnotation(doc.Pages[1], new Rectangle(100, 400, 300, 600), dataDir + "AddSwfFileAsAnnotation.swf");
doc.Pages[1].Annotations.Add(sa);
// Salvar documento
doc.Save(dataDir + "GetResourceOfAnnotation_Out.pdf");
// Abrir documento
Document doc1 = new Document(dataDir + "GetResourceOfAnnotation_Out.pdf");
//Obter ação da anotação
RenditionAction action = (doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction;
//Obtenha a representação da ação de representação
Rendition rendition = ((doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction).Rendition;
// Clipe de mídia
MediaClip clip = (rendition as MediaRendition).MediaClip;
FileSpecification data = (clip as MediaClipData).Data;
MemoryStream ms = new MemoryStream();
byte[] buffer = new byte[1024];
int read = 0;
//Os dados da mídia estão acessíveis em FileSpecification.Contents
Stream source = data.Contents;
while ((read = source.Read(buffer, 0, buffer.Length)) > 0)
{
ms.Write(buffer, 0, read);
}
Console.WriteLine(rendition.Name);
Console.WriteLine(action.RenditionOperation);
```

## Conclusão

Neste tutorial, exploramos como obter o recurso de uma anotação específica de um documento PDF usando Aspose.PDF for .NET. Seguindo o guia passo a passo e usando o código-fonte C# fornecido, os desenvolvedores podem acessar e gerenciar facilmente anotações, incluindo anotações de representação, em seus documentos PDF.

### Perguntas frequentes

#### P: O que é uma representação no contexto de anotações em PDF?

R: No contexto das anotações em PDF, uma representação é uma apresentação de conteúdo multimídia. Ele permite incorporar multimídia, como áudio ou vídeo, no documento PDF. A anotação de representação especifica a mídia a ser apresentada e como ela deve ser reproduzida.

#### P: Posso obter o nome do arquivo de mídia associado a uma anotação de representação?

R: Sim, você pode obter o nome do arquivo de mídia associado a uma anotação de representação usando Aspose.PDF for .NET. O nome do arquivo de mídia pode ser acessado através do`FileSpecification` do`MediaClip` objeto.

#### P: O Aspose.PDF for .NET pode extrair arquivos de mídia de uma anotação de representação?

R: Sim, o Aspose.PDF for .NET pode extrair os dados de mídia de uma anotação de representação, que inclui conteúdo de áudio ou vídeo, e salvá-los como um arquivo separado.

#### P: Como posso acessar os dados de mídia de uma anotação de representação?

 R: Os dados de mídia de uma anotação de representação podem ser acessados através do`FileSpecification.Contents` propriedade do`MediaClipData` objeto.

#### P: Posso modificar a mídia associada a uma anotação de representação usando Aspose.PDF for .NET?

R: Aspose.PDF for .NET fornece métodos para acessar e modificar os dados de mídia associados a uma anotação de representação. Você pode atualizar ou substituir o arquivo de mídia usado por uma anotação de representação.