---
title: MHT para PDF
linktitle: MHT para PDF
second_title: Referência da API Aspose.PDF para .NET
description: Guia passo a passo para converter MHT em PDF usando Aspose.PDF para .NET.
type: docs
weight: 70
url: /pt/net/document-conversion/mht-to-pdf/
---
Neste tutorial, iremos guiá-lo através do processo de conversão de um arquivo MHT em PDF usando Aspose.PDF for .NET. MHT (MIME HTML) é um formato usado para salvar uma página da web completa, incluindo imagens e conteúdo associado. Seguindo as etapas abaixo, você poderá converter arquivos MHT para o formato PDF.

## Pré-requisitos
Antes de começar, certifique-se de atender aos seguintes pré-requisitos:

- Conhecimento básico da linguagem de programação C#.
- Biblioteca Aspose.PDF para .NET instalada em seu sistema.
- Um ambiente de desenvolvimento como o Visual Studio.

## Passo 1: Carregando o arquivo MHT
Nesta etapa carregaremos o arquivo MHT usando Aspose.PDF para .NET. Siga o código abaixo:

```csharp
// Caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

MhtLoadOptions options = new MhtLoadOptions();

// Carregue o documento
Document document = new Document(dataDir + "test.mht", options);
```

 Certifique-se de substituir`"YOUR DOCUMENTS DIRECTORY"` com o diretório real onde seu arquivo MHT está localizado.

## Passo 2: Conversão de MHT para PDF
Após carregar o arquivo MHT, podemos prosseguir com a conversão para PDF. Use o seguinte código:

```csharp
// Salve a saída como um documento PDF
document.Save(dataDir + "MHTToPDF_out.pdf");
```

 O código acima converte o arquivo MHT para o formato PDF e salva-o como o nome do arquivo`"MHTToPDF_out.pdf"`.

### Exemplo de código-fonte de MHT para PDF usando Aspose.PDF para .NET

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
MhtLoadOptions options = new MhtLoadOptions();
// Carregar documento
Document document = new Document(dataDir  + "test.mht", options);
// Salve a saída como documento PDF
document.Save(dataDir + "MHTToPDF_out.pdf");
```

## Conclusão
Neste tutorial, cobrimos o processo passo a passo de conversão de um arquivo MHT em PDF usando Aspose.PDF para .NET. Seguindo as instruções descritas acima, agora você poderá converter arquivos MHT para o formato PDF. Este recurso pode ser útil quando você precisa converter páginas inteiras da web em documentos PDF.

### Perguntas frequentes

#### P: O Aspose.PDF for .NET oferece suporte à conversão de arquivos MHT com imagens incorporadas em PDF?

R: Sim, Aspose.PDF for .NET suporta a conversão de arquivos MHT com imagens incorporadas em PDF. A biblioteca pode lidar com o conteúdo completo da página da web, incluindo imagens e recursos associados, e convertê-lo em um documento PDF.

#### P: Posso personalizar a saída do PDF durante o processo de conversão de MHT para PDF?

R: Sim, Aspose.PDF for .NET oferece várias opções para personalizar a saída do PDF durante o processo de conversão de MHT para PDF. Você pode definir propriedades como tamanho da página, orientação, margens e muito mais para controlar a aparência do documento PDF resultante.

#### P: O Aspose.PDF for .NET preserva hiperlinks e formatação do arquivo MHT original na saída PDF?

R: Sim, o Aspose.PDF for .NET preserva hiperlinks e formatação do arquivo MHT original na saída PDF. A biblioteca garante que o PDF convertido mantenha o mesmo layout e conteúdo do arquivo MHT de origem.

#### P: Posso converter vários arquivos MHT em documentos PDF separados usando Aspose.PDF for .NET?

R: Sim, você pode converter vários arquivos MHT em documentos PDF separados usando Aspose.PDF for .NET. Basta carregar cada arquivo MHT e salvá-lo como um documento PDF separado com um nome de arquivo exclusivo.