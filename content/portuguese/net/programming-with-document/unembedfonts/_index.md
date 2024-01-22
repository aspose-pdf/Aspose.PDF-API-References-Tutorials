---
title: Desincorpore fontes e otimize arquivos PDF
linktitle: Desincorpore fontes e otimize arquivos PDF
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como usar Aspose.PDF for .NET para obter fontes não incorporadas e otimizar arquivos PDF. Um guia passo a passo.
type: docs
weight: 370
url: /pt/net/programming-with-document/unembedfonts/
---
Aspose.PDF for .NET é uma biblioteca poderosa que oferece uma ampla gama de recursos para trabalhar com documentos PDF. Um de seus recursos é obter fontes não incorporadas de um documento PDF. Isso pode ser útil se você precisar extrair fontes de um documento PDF e usá-las em outros aplicativos.

forneceremos um guia passo a passo para explicar o seguinte código-fonte C# do recurso de obtenção de fontes não incorporadas do Aspose.PDF para .NET.

## Passo 1: Defina o caminho para o diretório do documento

Antes de começarmos, precisamos definir o caminho para o diretório onde nosso documento PDF está localizado. Armazenaremos esse caminho em uma variável chamada “dataDir”.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Substitua "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho real para o diretório onde seu documento PDF está localizado.

## Passo 2: Abra o documento PDF

 O primeiro passo é carregar o documento PDF que você deseja fazer isso, use o`Document` classe de Aspose.PDF para .NET. O trecho de código a seguir mostra como carregar o documento PDF:

```csharp
// Abrir documento
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Etapa 3: definir a opção UnembedFonts

 Para obter fontes não incorporadas do documento PDF, você precisa definir o`UnembedFonts` opção para`true` . Esta opção está disponível no`OptimizationOptions` aula. O trecho de código a seguir mostra como definir o`UnembedFonts` opção:

```csharp
// Definir opção UnembedFonts
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

## Passo 4: Otimize o documento PDF

 Depois de definir o`UnembedFonts` opção, você pode otimizar o documento PDF usando o`OptimizeResources` método do`Document` aula. O trecho de código a seguir mostra como otimizar o documento PDF:

```csharp
// Otimize o documento PDF usando OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
```

## Etapa 5: salve o documento atualizado

 Depois que o documento PDF estiver otimizado, você poderá salvar o documento atualizado usando o`Save` método do`Document`aula. O trecho de código a seguir mostra como salvar o documento atualizado:

```csharp
// Salvar documento atualizado
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## Etapa 6: Obtenha o tamanho de arquivo original e reduzido

 Finalmente, você pode obter o tamanho de arquivo original e reduzido do documento PDF usando o`FileInfo` classe de System.IO. O trecho de código a seguir mostra como obter o tamanho do arquivo original e reduzido:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

### Exemplo de código-fonte para obter fontes não incorporadas usando Aspose.PDF para .NET

Aqui está o exemplo de código-fonte completo para obter fontes não incorporadas de um documento PDF usando Aspose.PDF para .NET:

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
// Definir opção UnembedFonts
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
Console.WriteLine("Start");
// Otimize o documento PDF usando OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
// Salvar documento atualizado
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Finished");
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

## Conclusão

Neste tutorial, demonstramos como usar Aspose.PDF for .NET para obter fontes não incorporadas de um documento PDF. Seguindo o guia passo a passo, você pode implementar facilmente esse recurso em seus aplicativos C#. Desincorporar fontes pode ser vantajoso quando você precisa trabalhar com as fontes extraídas separadamente ou garantir o uso consistente de fontes em várias plataformas.

## Perguntas frequentes

#### P: Qual é o propósito de desincorporar fontes de um documento PDF?

R: Desincorporar fontes de um documento PDF permite extrair as fontes incorporadas e usá-las em outros aplicativos. Isso pode ser útil para garantir uma renderização de fonte consistente e preservar a aparência visual do documento.

#### P: Como especifico o caminho para o diretório do documento no código C#?

 R: Para especificar o caminho para o diretório do documento, substitua`"YOUR DOCUMENT DIRECTORY"` no código com o caminho real para o diretório onde seu documento PDF está localizado.

####  P: O que o`UnembedFonts` option do, and where is it set?

 R: O`UnembedFonts` opção, disponível no`OptimizationOptions` class, ativa ou desativa a remoção de fontes do documento PDF. Para definir esta opção como`true`, use o seguinte código:

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

#### P: Posso reverter as alterações feitas durante o processo de otimização?

R: Aspose.PDF for .NET não faz alterações permanentes no documento PDF original durante a otimização. O processo de otimização é realizado em uma cópia do documento, deixando o original intacto.

#### P: Como posso verificar o tamanho do arquivo original e reduzido após a otimização?

R: Você pode usar o`FileInfo` classe de`System.IO` para obter o tamanho do arquivo original e reduzido. Aqui está um exemplo de trecho de código para conseguir isso:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```