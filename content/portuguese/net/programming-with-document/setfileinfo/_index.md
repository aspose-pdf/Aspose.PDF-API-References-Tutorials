---
title: Definir informações do arquivo em arquivo PDF
linktitle: Definir informações do arquivo em arquivo PDF
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como usar Aspose.PDF for .NET para definir informações de arquivo em arquivo PDF com este guia passo a passo.
type: docs
weight: 310
url: /pt/net/programming-with-document/setfileinfo/
---
Se você estiver trabalhando em um projeto que requer o gerenciamento de arquivos PDF usando Aspose.PDF for .NET, um dos recursos que você pode querer utilizar é a capacidade de definir informações de arquivo para um documento PDF. As informações do arquivo incluem vários detalhes, como autor, data de criação, palavras-chave, data de modificação, assunto e título. Este guia orientará você no processo de configuração de informações de arquivo para um documento PDF usando código-fonte C# com Aspose.PDF para .NET.

## Guia passo a passo para definir informações de arquivo usando Aspose.PDF para .NET

1. Crie um novo projeto C# em seu IDE do Visual Studio.
2. Adicione uma referência à biblioteca Aspose.PDF for .NET em seu projeto.
3. Crie um novo objeto de documento PDF fornecendo o caminho para o arquivo PDF cujas informações você deseja modificar.

## Passo 1: Defina o caminho para o diretório de documentos.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passo 2: Abra o documento PDF

```csharp
// Abrir documento
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");
```

## Etapa 3: Use o objeto DocumentInfo para acessar as informações do arquivo do documento PDF.

```csharp
DocumentInfo docInfo = new DocumentInfo(pdfDocument);
```

## Etapa 4: Defina os valores desejados das informações do arquivo usando as propriedades do objeto DocumentInfo.

```csharp
docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";
```

## Etapa 5: salve o documento PDF atualizado no local especificado.

```csharp
dataDir = dataDir + "SetFileInfo_out.pdf";
pdfDocument.Save(dataDir);
```

## Etapa 6: verifique se as informações do arquivo foram atualizadas com sucesso.

```csharp
Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

Você definiu com sucesso as informações do arquivo para um documento PDF usando Aspose.PDF para .NET.

### Exemplo de código-fonte para definir informações do arquivo usando Aspose.PDF para .NET


```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Abrir documento
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");

// Especifique as informações do documento
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

Concluindo, Aspose.PDF for .NET fornece uma maneira simples e eficaz de definir informações de arquivo para documentos PDF. Seguindo as etapas mencionadas acima, você pode definir facilmente os valores de informações de arquivo desejados para seus documentos PDF usando o código-fonte C#.

### Perguntas frequentes sobre como definir informações de arquivo em arquivo PDF

#### P: Posso definir propriedades adicionais de informações de arquivo não mencionadas no exemplo?

 R: Sim, você pode definir propriedades adicionais de informações de arquivo usando o`DocumentInfo` objeto em Aspose.PDF para .NET. O`DocumentInfo`classe fornece várias propriedades que permitem definir informações adicionais, como produtor, versão e propriedades personalizadas.

#### P: É possível recuperar as informações do arquivo de um documento PDF existente?

 R: Sim, você pode recuperar as informações do arquivo de um documento PDF existente usando Aspose.PDF for .NET. Para fazer isso, você pode usar o`DocumentInfo` objeto para acessar as propriedades das informações do arquivo e ler as informações armazenadas no documento PDF.

#### P: A configuração das informações do arquivo modifica o documento PDF original?

R: Não, definir as informações do arquivo usando Aspose.PDF for .NET não modifica o documento PDF original. Em vez disso, ele cria um novo documento PDF com as informações atualizadas do arquivo. O documento PDF original permanece inalterado.