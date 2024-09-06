---
title: Obter metadados XMP
linktitle: Obter metadados XMP
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda a usar o recurso GetXmpMetadata do Aspose.PDF para .NET para extrair metadados XMP de um documento PDF usando código-fonte C#.
type: docs
weight: 200
url: /pt/net/programming-with-document/getxmpmetadata/
---
 Aspose.PDF para .NET é uma biblioteca popular de manipulação de PDF que permite aos desenvolvedores criar, editar e converter arquivos PDF em seus aplicativos .NET. Um dos recursos oferecidos por esta biblioteca é a capacidade de extrair metadados XMP de um documento PDF. Este tutorial o guiará pelas etapas de uso do`GetXmpMetadata` recurso do Aspose.PDF para .NET para extrair metadados XMP de um documento PDF.

## Etapa 1: instalar o Aspose.PDF para .NET

 Para usar o Aspose.PDF para .NET em seus aplicativos .NET, você deve primeiro instalar a biblioteca. Você pode baixar a versão mais recente da biblioteca do[Página de download do Aspose.PDF para .NET](https://releases.aspose.com/pdf/net).

Após baixar a biblioteca, extraia o conteúdo do arquivo ZIP para uma pasta no seu computador. Você precisará então adicionar uma referência ao Aspose.PDF for .NET DLL no seu projeto .NET.

## Etapa 2: Carregue o documento PDF

 Depois de instalar o Aspose.PDF para .NET e adicionar uma referência à DLL no seu projeto .NET, você pode começar a usar o`GetXmpMetadata` recurso para extrair metadados XMP de um documento PDF.

O primeiro passo para usar esse recurso é carregar o documento PDF do qual você deseja extrair metadados XMP. Para fazer isso, você pode usar o seguinte código:

```csharp
// O caminho para o documento PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Abra o documento PDF
Document pdfDocument = new Document(dataDir + "GetXMPMetadata.pdf");
```

 No código acima, substitua`"YOUR DOCUMENT DIRECTORY"` com o caminho para o diretório onde seu documento PDF está localizado. Este código carregará o documento PDF em um`Document` objeto, que você pode usar para extrair metadados XMP.

## Etapa 3: Extrair metadados XMP

Para extrair metadados XMP de um documento PDF, você pode usar o seguinte código:

```csharp
Console.WriteLine(pdfDocument.Metadata["xmp:CreateDate"]);
Console.WriteLine(pdfDocument.Metadata["xmp:Nickname"]);
Console.WriteLine(pdfDocument.Metadata["xmp:CustomProperty"]);
```

 No código acima,`xmp:CreateDate`, `xmp:Nickname` , e`xmp:CustomProperty` são exemplos de propriedades de metadados XMP que você pode extrair de um documento PDF. Você pode substituir esses nomes de propriedade pelos nomes de quaisquer outras propriedades de metadados XMP que você queira extrair.

### Exemplo de código-fonte para obter metadados XMP usando Aspose.PDF para .NET

 Aqui está o código-fonte completo para extrair metadados XMP de um documento PDF usando o`GetXmpMetadata` Recurso do Aspose.PDF para .NET:

```csharp
// O caminho para o documento PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Abra o documento PDF
Document pdfDocument = new Document(dataDir + "GetXMPMetadata.pdf");

// Extrair metadados XMP
Console.WriteLine(pdfDocument.Metadata["xmp:CreateDate"]);
Console.WriteLine(pdfDocument.Metadata["xmp:Nickname"]);
Console.WriteLine(pdfDocument.Metadata["xmp:CustomProperty"]);
```

 No código acima, substitua`"YOUR DOCUMENT DIRECTORY"` com o caminho para o diretório onde seu documento PDF está localizado. Este código extrairá metadados XMP do documento PDF e os enviará para o console.

## Conclusão

Neste tutorial, discutimos como usar o Aspose.PDF para .NET para extrair metadados XMP de um documento PDF. Os metadados XMP fornecem informações valiosas sobre um documento, e o Aspose.PDF para .NET permite que os desenvolvedores acessem essas informações e as usem em seus aplicativos conforme necessário. Ao extrair metadados XMP, os desenvolvedores podem obter insights sobre a data de criação de um documento, autor e outros dados descritivos. Essas informações podem ser usadas para aprimorar a funcionalidade e a experiência do usuário de aplicativos PDF. O Aspose.PDF para .NET fornece uma API simples e direta para acessar metadados XMP, facilitando a integração desse recurso em aplicativos .NET.

### Perguntas frequentes

#### P: O que são metadados XMP em um documento PDF?

A: Os metadados XMP em um documento PDF referem-se às informações da Plataforma de Metadados Extensíveis (XMP) que são incorporadas ao documento. Os metadados XMP fornecem uma maneira padrão de armazenar informações sobre o documento, como autor, data de criação, palavras-chave e outros dados descritivos. Eles permitem fácil recuperação e troca de metadados entre diferentes sistemas e aplicativos.

#### P: Que tipo de informação pode ser extraída usando o recurso GetXmpMetadata?

 A: O recurso GetXmpMetadata permite que os desenvolvedores extraiam várias propriedades de metadados XMP de um documento PDF. Alguns exemplos de propriedades de metadados XMP que podem ser extraídas são`xmp:CreateDate`, `xmp:Nickname` , e`xmp:CustomProperty`. Os desenvolvedores podem acessar essas propriedades e usá-las em seus aplicativos conforme necessário.

#### P: Posso extrair propriedades de metadados XMP personalizadas usando Aspose.PDF para .NET?

R: Sim, você pode extrair propriedades de metadados XMP personalizadas usando Aspose.PDF para .NET. Propriedades de metadados XMP personalizadas podem ser incluídas em um documento PDF para armazenar informações adicionais específicas para seu aplicativo ou requisitos. Você pode extrair e usar essas propriedades personalizadas conforme necessário.

#### P: O Aspose.PDF para .NET é capaz de extrair outras informações de metadados de um documento PDF?

R: Sim, o Aspose.PDF para .NET fornece vários recursos para extrair informações de metadados de um documento PDF. Além dos metadados XMP, você também pode extrair informações como Informações do Documento (título, autor, assunto, palavras-chave), versão do PDF, detalhes de criptografia e muito mais.