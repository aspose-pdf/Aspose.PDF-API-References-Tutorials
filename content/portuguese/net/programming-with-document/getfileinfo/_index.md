---
title: Obter informações do arquivo em arquivo PDF
linktitle: Obter informações do arquivo em arquivo PDF
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda a usar o recurso GetFileInfo em arquivo PDF do Aspose.PDF para .NET para recuperar informações de metadados sobre um documento PDF.
type: docs
weight: 180
url: /pt/net/programming-with-document/getfileinfo/
---
 Aspose.PDF para .NET é uma biblioteca popular de manipulação de PDF que permite aos desenvolvedores criar, editar e converter arquivos PDF em seus aplicativos .NET. Um dos recursos oferecidos por esta biblioteca é a capacidade de recuperar informações sobre os metadados de um documento PDF. Este tutorial o guiará pelas etapas de uso do`GetFileInfo` recurso do Aspose.PDF para .NET para recuperar informações sobre os metadados de um documento PDF.

## Etapa 1: instalar o Aspose.PDF para .NET

 Para usar o Aspose.PDF para .NET em seus aplicativos .NET, você deve primeiro instalar a biblioteca. Você pode baixar a versão mais recente da biblioteca do[Página de download do Aspose.PDF para .NET](https://releases.aspose.com/pdf/net).

Após baixar a biblioteca, extraia o conteúdo do arquivo ZIP para uma pasta no seu computador. Você precisará então adicionar uma referência ao Aspose.PDF for .NET DLL no seu projeto .NET.

## Etapa 2: Carregue o documento PDF

 Depois de instalar o Aspose.PDF para .NET e adicionar uma referência à DLL no seu projeto .NET, você pode começar a usar o`GetFileInfo` recurso para recuperar informações sobre os metadados de um documento PDF.

O primeiro passo para usar esse recurso é carregar o documento PDF sobre o qual você deseja recuperar informações. Para fazer isso, você pode usar o seguinte código:

```csharp
// O caminho para o documento PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Abra o documento PDF
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");
```

 No código acima, substitua`"YOUR DOCUMENT DIRECTORY"` com o caminho para o diretório onde seu documento PDF está localizado. Este código carregará o documento PDF em um`Document` objeto, que você pode usar para recuperar informações sobre os metadados do documento.

## Etapa 3: recuperar os metadados do documento

Para recuperar informações sobre os metadados de um documento PDF, você pode usar o seguinte código:

```csharp
// Obter informações do documento
DocumentInfo docInfo = pdfDocument.Info;

// Mostrar informações do documento
Console.WriteLine("Author: {0}", docInfo.Author);
Console.WriteLine("Creation Date: {0}", docInfo.CreationDate);
Console.WriteLine("Keywords: {0}", docInfo.Keywords);
Console.WriteLine("Modify Date: {0}", docInfo.ModDate);
Console.WriteLine("Subject: {0}", docInfo.Subject);
Console.WriteLine("Title: {0}", docInfo.Title);
```

No código acima, cada linha recupera uma propriedade de metadados diferente do documento PDF e a envia para o console. Você pode personalizar esse código para recuperar apenas as propriedades nas quais você está interessado.

### Exemplo de código-fonte para obter informações do arquivo PDF usando Aspose.PDF para .NET

 Aqui está o código-fonte completo para recuperar os metadados de um documento PDF usando o`GetFileInfo` Recurso do Aspose.PDF para .NET:

```csharp
// O caminho para o documento PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Abra o documento PDF
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");

// Obter informações do documento
DocumentInfo docInfo = pdfDocument.Info;

// Mostrar informações do documento
Console.WriteLine("Author: {0}", docInfo.Author);
Console.WriteLine("Creation Date: {0}", docInfo.CreationDate);
Console.WriteLine("Keywords: {0}", docInfo.Keywords);
Console.WriteLine("Modify Date: {0}", docInfo.ModDate);
Console.WriteLine("Subject: {0}", docInfo.Subject);
Console.WriteLine("Title: {0}", docInfo.Title);
```

## Conclusão

Neste tutorial, discutimos como usar o Aspose.PDF para .NET para recuperar informações sobre os metadados de um documento PDF. Ao carregar um documento PDF e acessar suas propriedades de metadados, você pode reunir informações sobre as características e propriedades do documento. O Aspose.PDF para .NET fornece uma API simples e fácil de usar para trabalhar com documentos PDF, incluindo a recuperação de informações de metadados, tornando-o uma ferramenta valiosa para manipulação de PDF em aplicativos .NET.

### Perguntas frequentes

#### P: O que são metadados em um documento PDF?

R: Metadados em um documento PDF referem-se às informações que descrevem as propriedades e características do documento. Essas informações geralmente incluem o título do documento, autor, assunto, palavras-chave, data de criação, data de modificação e mais.

#### P: Como posso instalar o Aspose.PDF para .NET no meu projeto .NET?

 R: Para instalar o Aspose.PDF para .NET, você precisa baixar a biblioteca do[Página de download do Aspose.PDF para .NET](https://releases.aspose.com/pdf/net). Após o download, extraia o conteúdo do arquivo ZIP e adicione uma referência à DLL Aspose.PDF for .NET no seu projeto .NET.

#### P: Posso personalizar o código para recuperar apenas propriedades de metadados específicas?

R: Sim, você pode personalizar o código para recuperar propriedades de metadados específicas comentando as linhas que você não precisa. Cada linha no código corresponde a uma propriedade de metadados específica, então você pode incluir ou excluir propriedades com base em seus requisitos.

#### P: Que tipos de propriedades de metadados posso recuperar usando o Aspose.PDF para .NET?

R: Usando o Aspose.PDF para .NET, você pode recuperar várias propriedades de metadados de um documento PDF, incluindo autor, título, assunto, palavras-chave, data de criação e data de modificação.