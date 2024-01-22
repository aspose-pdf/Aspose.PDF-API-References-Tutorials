---
title: Expandir marcadores em arquivo PDF
linktitle: Expandir marcadores em arquivo PDF
second_title: Referência da API Aspose.PDF para .NET
description: Expanda facilmente os favoritos no arquivo PDF para melhorar a navegação com Aspose.PDF for .NET.
type: docs
weight: 50
url: /pt/net/programming-with-bookmarks/expand-bookmarks/
---
A expansão dos marcadores no arquivo PDF exibirá todos os marcadores abertos por padrão. Com Aspose.PDF for .NET, você pode expandir facilmente os favoritos seguindo o seguinte código-fonte:

## Etapa 1: importar as bibliotecas necessárias

Antes de começar, você precisa importar as bibliotecas necessárias para seu projeto C#. Aqui está a diretiva de importação necessária:

```csharp
using Aspose.Pdf;
```

## Etapa 2: definir o caminho para a pasta de documentos

 Nesta etapa, você precisa especificar o caminho para a pasta que contém o arquivo PDF cujos marcadores deseja expandir. Substituir`"YOUR DOCUMENT DIRECTORY"`no código a seguir com o caminho real para sua pasta de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passo 3: Abra o documento PDF

Agora abriremos o documento PDF cujos favoritos queremos expandir usando o seguinte código:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Etapa 4: definir o modo de exibição da página

Nesta etapa, definiremos o modo de exibição da página para mostrar os favoritos por padrão. Nós usamos o`PageMode` propriedade do`doc` objeto para definir o modo de página desejado. Aqui está o código correspondente:

```csharp
doc.PageMode = PageMode.UseOutlines;
```

## Etapa 5: navegue pelos favoritos e expanda-os

 Agora percorreremos cada item de marcador na coleção de marcadores do documento e definiremos o estado aberto de cada item como`true` para expandi-los por padrão. Aqui está o código correspondente:

```csharp
foreach(OutlineItemCollection item in doc.Outlines)
{
     item. Open = true;
}
```

## Etapa 6: salve o arquivo atualizado

 Finalmente, salvamos o arquivo PDF atualizado usando o`Save` método do`doc` objeto. Aqui está o código correspondente:

```csharp
dataDir = dataDir + "ExpandBookmarks_out.pdf";
doc.Save(dataDir);
```

### Exemplo de código-fonte para expandir marcadores usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document doc = new Document(dataDir + "input.pdf");
// Defina o modo de visualização de página, ou seja, mostrar miniaturas, tela inteira, mostrar painel de anexos
doc.PageMode = PageMode.UseOutlines;
// Percorra cada item do Ouline na coleção de contornos do arquivo PDF
foreach (OutlineItemCollection item in doc.Outlines)
{
	// Definir status aberto para item de estrutura de tópicos
	item.Open = true;
}
dataDir = dataDir + "ExpandBookmarks_out.pdf";
// Salvar saída
doc.Save(dataDir);
Console.WriteLine("\nBookmarks expanded successfully.\nFile saved at " + dataDir);
```

## Conclusão

Parabéns! Agora você tem um guia passo a passo para desenvolver marcadores com Aspose.PDF for .NET. Você pode usar este código para mostrar todos os marcadores padrão em seus documentos PDF.

Certifique-se de verificar a documentação oficial do Aspose.PDF para obter mais informações sobre recursos avançados de manipulação de marcadores.

### Perguntas frequentes para expandir marcadores em arquivo PDF

#### P: O que são marcadores em um arquivo PDF?

R: Os marcadores em um arquivo PDF são auxílios à navegação que permitem aos usuários ir rapidamente para seções ou páginas específicas do documento. Eles fornecem uma maneira conveniente de acessar diferentes partes de um documento.

#### P: Por que eu desejaria expandir os marcadores em um arquivo PDF?

R: A expansão de marcadores pode melhorar a experiência do usuário, exibindo todos os marcadores em estado expandido por padrão. Isso dá aos usuários uma visão geral clara da estrutura do documento e permite navegar facilmente para diferentes seções.

#### P: Como importo as bibliotecas necessárias para meu projeto C#?

R: Para importar a biblioteca necessária para seu projeto C#, use a seguinte diretiva de importação:

```csharp
using Aspose.Pdf;
```

Esta diretiva permite utilizar as classes e métodos fornecidos por Aspose.PDF for .NET.

#### P: Como especifico o caminho para a pasta de documentos?

 R: No código-fonte fornecido, substitua`"YOUR DOCUMENT DIRECTORY"` com o caminho real para a pasta que contém o arquivo PDF com o qual você deseja trabalhar. Isso garante que o código possa localizar o arquivo PDF de destino.

#### P: Como abro um documento PDF para expandir seus marcadores?

R: Para abrir um documento PDF para expandir marcadores, use o seguinte código:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

 Substituir`"input.pdf"` com o nome real do arquivo.

#### P: Como configuro o modo de exibição da página para mostrar marcadores por padrão?

R: Para definir o modo de exibição de página para mostrar marcadores por padrão, use o`PageMode` propriedade do`doc` objeto:

```csharp
doc.PageMode = PageMode.UseOutlines;
```

#### P: Como posso expandir todos os marcadores no documento PDF?

 R: Para expandir todos os marcadores, percorra cada item de marcador na coleção de contornos do documento e defina o`Open` propriedade para`true`:

```csharp
foreach (OutlineItemCollection item in doc.Outlines)
{
    item.Open = true;
}
```

#### P: O que acontece se um marcador tiver marcadores secundários aninhados?

R: Se um marcador tiver marcadores secundários aninhados, a expansão do marcador pai também expandirá seus marcadores secundários, proporcionando uma visão abrangente da estrutura do documento.

#### P: Como salvo o arquivo PDF atualizado após expandir os favoritos?

R: Para salvar o arquivo PDF atualizado após expandir os marcadores, use o seguinte código:

```csharp
dataDir = dataDir + "ExpandBookmarks_out.pdf";
doc.Save(dataDir);
```

#### P: Posso personalizar a aparência dos marcadores expandidos?

R: Embora este tutorial se concentre na expansão de marcadores por padrão, você pode personalizar a aparência dos marcadores usando outros recursos e propriedades do Aspose.PDF.