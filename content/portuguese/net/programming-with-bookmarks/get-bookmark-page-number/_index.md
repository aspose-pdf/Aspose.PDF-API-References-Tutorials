---
title: Obtenha o número da página do marcador em arquivo PDF
linktitle: Obtenha o número da página do marcador em arquivo PDF
second_title: Referência da API Aspose.PDF para .NET
description: Obtenha facilmente o número da página do marcador em um arquivo PDF com Aspose.PDF para .NET.
type: docs
weight: 60
url: /pt/net/programming-with-bookmarks/get-bookmark-page-number/
---
Recuperar números de páginas associados a marcadores em arquivos PDF pode ser útil para navegação. Com Aspose.PDF for .NET, você pode obter facilmente o número da página dos favoritos seguindo o seguinte código-fonte:

## Etapa 1: importar as bibliotecas necessárias

Antes de começar, você precisa importar as bibliotecas necessárias para seu projeto C#. Aqui está a diretiva de importação necessária:

```csharp
using Aspose.Pdf.Facades;
```

## Etapa 2: definir o caminho para a pasta de documentos

 Nesta etapa, você precisa especificar o caminho para a pasta que contém o arquivo PDF do qual deseja extrair os números das páginas dos marcadores. Substituir`"YOUR DOCUMENT DIRECTORY"`no código a seguir com o caminho real para sua pasta de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Etapa 3: crie o editor de favoritos

 Agora vamos criar um`PdfBookmarkEditor` objeto para manipular os marcadores do documento. Use o seguinte código:

```csharp
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
```

## Passo 4: Abra o arquivo PDF

 Nesta etapa, abrimos o arquivo PDF usando o`BindPdf` método do editor de favoritos. Aqui está o código correspondente:

```csharp
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
```

## Etapa 5: Extraia os favoritos

 Agora iremos extrair os marcadores do documento usando o`ExtractBookmarks` método do editor de favoritos. Aqui está o código correspondente:

```csharp
Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
```

## Etapa 6: navegue nos favoritos e obtenha os números das páginas

 Finalmente, percorremos os marcadores extraídos e obtemos os números das páginas associados a cada marcador usando um`foreach` laço. Aqui está o código correspondente:

```csharp
foreach (Bookmark bookmark in bookmarks)
{
     string strLevelSeprator = string.Empty;
     for (int i = 1; i < bookmark.Level; i++)
     {
         strLevelSeprator += "----";
     }
     Console.WriteLine("{0}Title: {1}", strLevelSeprator, bookmark.Title);
     Console.WriteLine("{0}Page number: {1}", strLevelSeprator, bookmark.PageNumber);
     Console.WriteLine("{0}Page Action: {1}", strLevelSeprator, bookmark.Action);
}
```

### Exemplo de código-fonte para obter o número da página do marcador usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Criar PDFBookmarkEditor
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
// Abrir arquivo PDF
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
// Extrair favoritos
Aspose.Pdf.Facades.Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
foreach (Aspose.Pdf.Facades.Bookmark bookmark in bookmarks)
{
	string strLevelSeprator = string.Empty;
	for (int i = 1; i < bookmark.Level; i++)
	{
		strLevelSeprator += "----";
	}
	Console.WriteLine("{0}Title: {1}", strLevelSeprator, bookmark.Title);
	Console.WriteLine("{0}Page Number: {1}", strLevelSeprator, bookmark.PageNumber);
	Console.WriteLine("{0}Page Action: {1}", strLevelSeprator, bookmark.Action);
}
```

## Conclusão

Parabéns! Agora você tem um guia passo a passo para obter números de página de favoritos com Aspose.PDF for .NET. Você pode usar esse código para recuperar as informações de navegação associadas a cada marcador em seus documentos PDF.

Certifique-se de verificar a documentação oficial do Aspose.PDF para obter mais informações sobre recursos avançados de manipulação de marcadores.

### Perguntas frequentes para obter o número da página dos favoritos em arquivo PDF

#### P: O que são marcadores em um arquivo PDF?

R: Os marcadores em um arquivo PDF são auxílios à navegação que permitem aos usuários ir rapidamente para seções ou páginas específicas do documento. Eles melhoram a experiência do usuário, fornecendo atalhos para conteúdo relevante.

#### P: Por que eu desejaria recuperar os números das páginas dos marcadores de um arquivo PDF?

R: A recuperação dos números das páginas dos marcadores ajuda os usuários a navegar pelo documento com mais eficiência, fornecendo uma indicação clara de onde cada marcador leva. Isto é particularmente útil para documentos mais longos com múltiplas seções.

#### P: Como importo as bibliotecas necessárias para meu projeto C#?

R: Para importar a biblioteca necessária para seu projeto C#, use a seguinte diretiva de importação:

```csharp
using Aspose.Pdf.Facades;
```

Esta diretiva permite utilizar as classes e métodos fornecidos por Aspose.PDF for .NET.

#### P: Como especifico o caminho para a pasta de documentos?

 R: No código-fonte fornecido, substitua`"YOUR DOCUMENT DIRECTORY"`com o caminho real para a pasta que contém o arquivo PDF do qual você deseja extrair os números das páginas dos marcadores. Isso garante que o código possa localizar o arquivo PDF de destino.

#### P: Como faço para criar um editor de favoritos?

R: Para criar um editor de favoritos, use o seguinte código:

```csharp
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
```

#### P: Como abro um arquivo PDF para manipulação de marcadores?

R: Para abrir um arquivo PDF para extrair informações de marcadores, use o seguinte código:

```csharp
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
```

 Substituir`"GetBookmarks.pdf"` com o nome real do arquivo.

#### P: Como extraio marcadores do arquivo PDF?

 R: Para extrair marcadores do arquivo PDF, use o`ExtractBookmarks` método do editor de favoritos:

```csharp
Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
```

#### P: Como recupero e exibo os números das páginas dos favoritos?

 R: Percorra os marcadores extraídos usando um`foreach` faça um loop e acesse o`PageNumber` propriedade de cada marcador para recuperar e exibir seu número de página associado:

```csharp
foreach (Bookmark bookmark in bookmarks)
{
    Console.WriteLine("Title: " + bookmark.Title);
    Console.WriteLine("Page Number: " + bookmark.PageNumber);
    Console.WriteLine("Page Action: " + bookmark.Action);
}
```

#### P: Posso modificar as propriedades dos marcadores usando esta abordagem?

 R: Embora este tutorial se concentre na recuperação de números de páginas de marcadores, você pode modificar outras propriedades de marcadores usando o mesmo`Bookmark`objeto e propriedades associadas.

#### P: Como salvo o arquivo PDF atualizado após extrair as informações do marcador?

R: A extração de marcadores não modifica o arquivo PDF original. Se quiser salvar alguma alteração, você pode fazer isso usando outros métodos fornecidos pelo Aspose.PDF for .NET.