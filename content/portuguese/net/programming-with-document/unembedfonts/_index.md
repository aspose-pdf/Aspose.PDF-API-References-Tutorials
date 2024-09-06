---
title: Desincorpore fontes e otimize arquivos PDF
linktitle: Desincorpore fontes e otimize arquivos PDF
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda como usar o Aspose.PDF para .NET para obter Unembed Fonts e otimizar arquivos PDF. Um guia passo a passo.
type: docs
weight: 370
url: /pt/net/programming-with-document/unembedfonts/
---
Aspose.PDF para .NET é uma biblioteca poderosa que fornece uma ampla gama de recursos para trabalhar com documentos PDF. Um de seus recursos é obter fontes não incorporadas de um documento PDF. Isso pode ser útil se você precisar extrair fontes de um documento PDF e usá-las em outros aplicativos.

forneceremos um guia passo a passo para explicar o seguinte código-fonte C# do recurso obter fontes não incorporadas do Aspose.PDF para .NET.

## Etapa 1: Defina o caminho para o diretório do documento

Antes de começarmos, precisamos definir o caminho para o diretório onde nosso documento PDF está localizado. Armazenaremos esse caminho em uma variável chamada "dataDir".

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Substitua "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho real para o diretório onde seu documento PDF está localizado.

## Etapa 2: Abra o documento PDF

 O primeiro passo é carregar o documento PDF que você deseja fazer isso, use o`Document` classe de Aspose.PDF para .NET. O seguinte trecho de código mostra como carregar o documento PDF:

```csharp
// Abrir documento
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Etapa 3: Defina a opção UnembedFonts

 Para obter fontes não incorporadas do documento PDF, você precisa definir o`UnembedFonts` opção para`true` . Esta opção está disponível no`OptimizationOptions` classe. O trecho de código a seguir mostra como definir o`UnembedFonts` opção:

```csharp
// Definir opção UnembedFonts
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

## Etapa 4: Otimize o documento PDF

 Depois de definir o`UnembedFonts` opção, você pode otimizar o documento PDF usando o`OptimizeResources` método do`Document` classe. O seguinte trecho de código mostra como otimizar o documento PDF:

```csharp
// Otimizar documento PDF usando OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
```

## Etapa 5: Salve o documento atualizado

 Depois que o documento PDF for otimizado, você pode salvar o documento atualizado usando o`Save` método do`Document`classe. O seguinte trecho de código mostra como salvar o documento atualizado:

```csharp
// Salvar documento atualizado
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## Etapa 6: Obtenha o tamanho do arquivo original e reduzido

 Por fim, você pode obter o tamanho original e reduzido do arquivo PDF usando o`FileInfo` classe de System.IO. O seguinte trecho de código mostra como obter o tamanho original e reduzido do arquivo:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

### Exemplo de código-fonte para obter fontes não incorporadas usando Aspose.PDF para .NET

Aqui está o código-fonte de exemplo completo para obter fontes não incorporadas de um documento PDF usando Aspose.PDF para .NET:

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
// Otimizar documento PDF usando OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
// Salvar documento atualizado
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Finished");
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

## Conclusão

Neste tutorial, demonstramos como usar o Aspose.PDF para .NET para obter fontes não incorporadas de um documento PDF. Seguindo o guia passo a passo, você pode implementar facilmente esse recurso em seus aplicativos C#. Não incorporar fontes pode ser vantajoso quando você precisa trabalhar com as fontes extraídas separadamente ou garantir o uso consistente de fontes em várias plataformas.

## Perguntas frequentes

#### P: Qual é o propósito de desincorporar fontes de um documento PDF?

R: Desincorporar fontes de um documento PDF permite que você extraia as fontes incorporadas e as use em outros aplicativos. Isso pode ser útil para garantir renderização de fonte consistente e preservar a aparência visual do documento.

#### P: Como especifico o caminho para o diretório do documento no código C#?

 A: Para especificar o caminho para o diretório do documento, substitua`"YOUR DOCUMENT DIRECTORY"` no código com o caminho real para o diretório onde seu documento PDF está localizado.

####  P: O que o`UnembedFonts` option do, and where is it set?

 A: O`UnembedFonts` opção, disponível no`OptimizationOptions` classe, habilita ou desabilita a desincorporação de fontes do documento PDF. Para definir esta opção para`true`, use o seguinte código:

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

#### P: Posso reverter as alterações feitas durante o processo de otimização?

A: O Aspose.PDF para .NET não faz alterações permanentes no documento PDF original durante a otimização. O processo de otimização é realizado em uma cópia do documento, deixando o original intacto.

#### P: Como posso verificar o tamanho do arquivo original e reduzido após a otimização?

 A: Você pode usar o`FileInfo` classe de`System.IO` para obter o tamanho original e reduzido do arquivo. Aqui está um trecho de código de exemplo para conseguir isso:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```