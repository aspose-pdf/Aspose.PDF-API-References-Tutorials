---
title: Definir informações do arquivo em arquivo PDF
linktitle: Definir informações do arquivo em arquivo PDF
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda como usar o Aspose.PDF para .NET para definir informações de arquivo em um arquivo PDF com este guia passo a passo.
type: docs
weight: 310
url: /pt/net/programming-with-document/setfileinfo/
---
Se você estiver trabalhando em um projeto que exija o gerenciamento de arquivos PDF usando o Aspose.PDF para .NET, um dos recursos que você pode querer utilizar é a capacidade de definir informações de arquivo para um documento PDF. As informações do arquivo incluem vários detalhes, como autor, data de criação, palavras-chave, data de modificação, assunto e título. Este guia o guiará pelo processo de configuração de informações de arquivo para um documento PDF usando o código-fonte C# com o Aspose.PDF para .NET.

## Guia passo a passo para definir informações de arquivo usando Aspose.PDF para .NET

1. Crie um novo projeto C# no seu IDE do Visual Studio.
2. Adicione uma referência à biblioteca Aspose.PDF para .NET no seu projeto.
3. Crie um novo objeto de documento PDF fornecendo o caminho para o arquivo PDF cujas informações você deseja modificar.

## Etapa 1: defina o caminho para o diretório de documentos.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Etapa 2: Abra o documento PDF

```csharp
// Abrir documento
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");
```

## Etapa 3: use o objeto DocumentInfo para acessar as informações do arquivo do documento PDF.

```csharp
DocumentInfo docInfo = new DocumentInfo(pdfDocument);
```

## Etapa 4: defina os valores de informações de arquivo desejados usando as propriedades do objeto DocumentInfo.

```csharp
docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";
```

## Etapa 5: Salve o documento PDF atualizado no local especificado.

```csharp
dataDir = dataDir + "SetFileInfo_out.pdf";
pdfDocument.Save(dataDir);
```

## Etapa 6: verifique se as informações do arquivo foram atualizadas com sucesso.

```csharp
Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

Você definiu com sucesso as informações do arquivo para um documento PDF usando o Aspose.PDF para .NET.

### Exemplo de código-fonte para Definir informações de arquivo usando Aspose.PDF para .NET


```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Abrir documento
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");

// Especificar informações do documento
DocumentInfo docInfo = new DocumentInfo(pdfDocument);

docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";

dataDir = dataDir + "SetFileInfo_out.pdf";
// Salvar documento de saída
pdfDocument.Save(dataDir);

Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

## Conclusão

Concluindo, o Aspose.PDF para .NET fornece uma maneira simples e eficaz de definir informações de arquivo para documentos PDF. Seguindo os passos acima mencionados, você pode facilmente definir os valores de informações de arquivo desejados para seus documentos PDF usando o código-fonte C#.

### Perguntas frequentes sobre informações de arquivo definidas em arquivo PDF

#### P: Posso definir propriedades adicionais de informações de arquivo não mencionadas no exemplo?

 R: Sim, você pode definir propriedades adicionais de informações de arquivo usando o`DocumentInfo` objeto em Aspose.PDF para .NET. O`DocumentInfo` classe fornece várias propriedades que permitem definir informações adicionais, como o produtor, a versão e propriedades personalizadas.

#### P: É possível recuperar as informações do arquivo de um documento PDF existente?

 R: Sim, você pode recuperar as informações do arquivo de um documento PDF existente usando o Aspose.PDF para .NET. Para fazer isso, você pode usar o`DocumentInfo` objeto para acessar as propriedades das informações do arquivo e ler as informações armazenadas no documento PDF.

#### P: A definição das informações do arquivo modifica o documento PDF original?

R: Não, definir as informações do arquivo usando o Aspose.PDF para .NET não modifica o documento PDF original. Em vez disso, ele cria um novo documento PDF com as informações atualizadas do arquivo. O documento PDF original permanece inalterado.