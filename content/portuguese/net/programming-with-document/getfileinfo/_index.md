---
title: Obtenha informações do arquivo em arquivo PDF
linktitle: Obtenha informações do arquivo em arquivo PDF
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como usar o recurso GetFileInfo em arquivo PDF do Aspose.PDF for .NET para recuperar informações de metadados sobre um documento PDF.
type: docs
weight: 180
url: /pt/net/programming-with-document/getfileinfo/
---
 Aspose.PDF for .NET é uma biblioteca popular de manipulação de PDF que permite aos desenvolvedores criar, editar e converter arquivos PDF em seus aplicativos .NET. Um dos recursos oferecidos por esta biblioteca é a capacidade de recuperar informações sobre os metadados de um documento PDF. Este tutorial irá guiá-lo através das etapas de uso do`GetFileInfo` recurso do Aspose.PDF for .NET para recuperar informações sobre os metadados de um documento PDF.

## Etapa 1: Instale Aspose.PDF para .NET

 Para usar Aspose.PDF for .NET em seus aplicativos .NET, você deve primeiro instalar a biblioteca. Você pode baixar a versão mais recente da biblioteca no[Página de download do Aspose.PDF para .NET](https://releases.aspose.com/pdf/net).

Depois de baixar a biblioteca, extraia o conteúdo do arquivo ZIP para uma pasta no seu computador. Em seguida, você precisará adicionar uma referência à DLL Aspose.PDF para .NET em seu projeto .NET.

## Passo 2: Carregue o Documento PDF

Depois de instalar o Aspose.PDF for .NET e adicionar uma referência à DLL em seu projeto .NET, você pode começar a usar o`GetFileInfo` recurso para recuperar informações sobre os metadados de um documento PDF.

A primeira etapa para usar esse recurso é carregar o documento PDF sobre o qual deseja recuperar informações. Para fazer isso, você pode usar o seguinte código:

```csharp
// O caminho para o documento PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Abra o documento PDF
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");
```

 No código acima, substitua`"YOUR DOCUMENT DIRECTORY"` com o caminho para o diretório onde seu documento PDF está localizado. Este código carregará o documento PDF em um`Document` objeto, que você pode usar para recuperar informações sobre os metadados do documento.

## Etapa 3: recuperar os metadados do documento

Para recuperar informações sobre os metadados de um documento PDF, você pode usar o seguinte código:

```csharp
// Obtenha informações do documento
DocumentInfo docInfo = pdfDocument.Info;

// Mostrar informações do documento
Console.WriteLine("Author: {0}", docInfo.Author);
Console.WriteLine("Creation Date: {0}", docInfo.CreationDate);
Console.WriteLine("Keywords: {0}", docInfo.Keywords);
Console.WriteLine("Modify Date: {0}", docInfo.ModDate);
Console.WriteLine("Subject: {0}", docInfo.Subject);
Console.WriteLine("Title: {0}", docInfo.Title);
```

No código acima, cada linha recupera uma propriedade de metadados diferente do documento PDF e a envia para o console. Você pode personalizar esse código para recuperar apenas as propriedades de seu interesse.

### Exemplo de código-fonte para obter informações do arquivo PDF usando Aspose.PDF para .NET

 Aqui está o código-fonte completo para recuperar os metadados de um documento PDF usando o`GetFileInfo` recurso do Aspose.PDF para .NET:

```csharp
// O caminho para o documento PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Abra o documento PDF
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");

// Obtenha informações do documento
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

Neste tutorial, discutimos como usar Aspose.PDF for .NET para recuperar informações sobre os metadados de um documento PDF. Ao carregar um documento PDF e acessar suas propriedades de metadados, você pode coletar informações sobre as características e propriedades do documento. Aspose.PDF for .NET fornece uma API simples e fácil de usar para trabalhar com documentos PDF, incluindo a recuperação de informações de metadados, tornando-o uma ferramenta valiosa para manipulação de PDF em aplicativos .NET.

### Perguntas frequentes

#### P: O que são metadados em um documento PDF?

R: Os metadados em um documento PDF referem-se às informações que descrevem as propriedades e características do documento. Essas informações normalmente incluem título do documento, autor, assunto, palavras-chave, data de criação, data de modificação e muito mais.

#### P: Como posso instalar o Aspose.PDF for .NET em meu projeto .NET?

 R: Para instalar o Aspose.PDF for .NET, você precisa baixar a biblioteca do[Página de download do Aspose.PDF para .NET](https://releases.aspose.com/pdf/net). Após o download, extraia o conteúdo do arquivo ZIP e adicione uma referência à DLL Aspose.PDF para .NET em seu projeto .NET.

#### P: Posso personalizar o código para recuperar apenas propriedades de metadados específicas?

R: Sim, você pode personalizar o código para recuperar propriedades específicas de metadados comentando as linhas desnecessárias. Cada linha no código corresponde a uma propriedade de metadados específica, portanto você pode incluir ou excluir propriedades com base em seus requisitos.

#### P: Que tipos de propriedades de metadados posso recuperar usando Aspose.PDF for .NET?

R: Usando Aspose.PDF for .NET, você pode recuperar várias propriedades de metadados de um documento PDF, incluindo autor, título, assunto, palavras-chave, data de criação e data de modificação.