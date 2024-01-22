---
title: Definir nome de fonte padrão
linktitle: Definir nome de fonte padrão
second_title: Referência da API Aspose.PDF para .NET
description: Guia passo a passo para definir o nome da fonte padrão em um arquivo PDF usando Aspose.PDF para .NET.
type: docs
weight: 270
url: /pt/net/document-conversion/set-default-font-name/
---
Neste tutorial, mostraremos como definir o nome da fonte padrão em um arquivo PDF usando Aspose.PDF for .NET. Às vezes, ao extrair imagens de um arquivo PDF, você pode encontrar problemas de fonte ausente. Ao especificar um nome de fonte padrão, você pode garantir que o texto extraído será exibido corretamente. Siga as etapas abaixo para definir o nome da fonte padrão em um arquivo PDF.

## Pré-requisitos
Antes de começar, certifique-se de atender aos seguintes pré-requisitos:

- Conhecimento básico da linguagem de programação C#.
- Biblioteca Aspose.PDF para .NET instalada em seu sistema.
- Um ambiente de desenvolvimento como o Visual Studio.

## Passo 1: Carregando o documento PDF
 O primeiro passo é carregar o documento PDF em um`Document` objeto. Use o seguinte código:

```csharp
// Caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
     // Código para adicionar
}
```

 Certifique-se de substituir`"YOUR DOCUMENTS DIRECTORY"` com o diretório real onde seu arquivo PDF está localizado.

## Etapa 2: definir o nome da fonte padrão
 A seguir, definiremos o nome da fonte padrão usando o`DefaultFontName` opção do`RenderingOptions` objeto. Use o seguinte código:

```csharp
using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
     using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
     {
         Resolution resolution = new Resolution(300);
         PngDevice pngDevice = new PngDevice(resolution);
         RenderingOptions ro = new RenderingOptions();
         ro.DefaultFontName = "Arial";
         pngDevice.RenderingOptions = ro;
        
         // Código para adicionar
     }
}
```

 Certifique-se de substituir`"Arial"` com o nome da fonte desejada.

## Etapa 3: extração de imagem
A seguir, extrairemos a imagem da página especificada do documento PDF. Use o seguinte código:

```csharp
pngDevice.Process(pdfDocument.Pages[1], imageStream);
```

 Certifique-se de especificar o número de página correto em`pdfDocument.Pages[1]`.

### Exemplo de código-fonte para definir nome de fonte padrão usando Aspose.PDF para .NET

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
	using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
	{
		Resolution resolution = new Resolution(300);
		PngDevice pngDevice = new PngDevice(resolution);
		RenderingOptions ro = new RenderingOptions();
		ro.DefaultFontName = "Arial";
		pngDevice.RenderingOptions = ro;
		pngDevice.Process(pdfDocument.Pages[1], imageStream);
	}
}
```

## Conclusão
Neste tutorial, aprendemos como definir o nome da fonte padrão em um arquivo PDF usando Aspose.PDF for .NET. Ao especificar um nome de fonte padrão, você pode garantir que o texto extraído será exibido corretamente. Use este método para resolver problemas de fonte ausente ao extrair imagens de arquivos PDF.

### Perguntas frequentes

#### P: O que é Aspose.PDF para .NET?

R: Aspose.PDF for .NET é uma biblioteca poderosa que permite aos desenvolvedores trabalhar com documentos PDF em aplicativos C#. Oferece várias funcionalidades, incluindo definir o nome da fonte padrão em um arquivo PDF.

#### P: Por que eu precisaria definir o nome da fonte padrão em um arquivo PDF?

R: Definir o nome da fonte padrão é útil ao extrair texto de um documento PDF. Se o PDF contiver texto com fontes que não estão disponíveis na máquina de extração, a especificação de um nome de fonte padrão garante a exibição correta do texto.

#### P: Como posso carregar um documento PDF e definir o nome da fonte padrão usando Aspose.PDF for .NET?

 R: Para carregar um documento PDF e definir o nome da fonte padrão, você pode usar o`Document`class para carregar o arquivo PDF e o`RenderingOptions.DefaultFontName` propriedade para especificar o nome da fonte padrão desejada.

#### P: Posso escolher qualquer fonte como nome de fonte padrão?

R:Sim, você pode escolher qualquer fonte disponível na máquina de extração como nome de fonte padrão. Use uma fonte que corresponda às fontes ausentes no PDF original para garantir uma renderização precisa do texto.

#### P: Definir o nome da fonte padrão é uma alteração permanente no arquivo PDF?

R: Não, definir o nome da fonte padrão usando Aspose.PDF for .NET é uma alteração temporária feita durante a extração de texto. Não modifica o arquivo PDF original.