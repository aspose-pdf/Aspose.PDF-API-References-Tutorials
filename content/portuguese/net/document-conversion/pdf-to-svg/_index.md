---
title: PDF para SVG
linktitle: PDF para SVG
second_title: Referência da API Aspose.PDF para .NET
description: Guia passo a passo para converter PDF em SVG usando Aspose.PDF para .NET.
type: docs
weight: 180
url: /pt/net/document-conversion/pdf-to-svg/
---
Neste tutorial, orientaremos você no processo de conversão de um formato PDF para SVG usando Aspose.PDF para .NET. SVG (Scalable Vector Graphics) é um formato de imagem vetorial que ajuda a manter a qualidade e o dimensionamento dos gráficos. Seguindo as etapas abaixo, você poderá converter um arquivo PDF para o formato SVG.

## Pré-requisitos
Antes de começar, certifique-se de atender aos seguintes pré-requisitos:

- Conhecimento básico da linguagem de programação C#.
- Biblioteca Aspose.PDF para .NET instalada em seu sistema.
- Um ambiente de desenvolvimento como o Visual Studio.

## Passo 1: Carregando o documento PDF
Nesta etapa, carregaremos o arquivo PDF de origem usando Aspose.PDF for .NET. Siga o código abaixo:

```csharp
// Caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Carregue o documento PDF
Document doc = new Document(dataDir + "input.pdf");
```

 Certifique-se de substituir`"YOUR DOCUMENTS DIRECTORY"` com o diretório real onde seu arquivo PDF está localizado.

## Etapa 2: instanciação das opções de salvamento SVG
Após carregar o arquivo PDF, instanciaremos as opções de salvamento do SVG. Use o seguinte código:

```csharp
// Instanciar um objeto SvgSaveOptions
SvgSaveOptions saveOptions = new SvgSaveOptions();
// Não compacte a imagem SVG em um arquivo Zip
saveOptions.CompressOutputToZipArchive = false;
```

## Etapa 3: Salvar o arquivo SVG resultante
Agora vamos salvar o arquivo PDF convertido no formato SVG. Use o seguinte código:

```csharp
// Salve a saída em arquivos SVG
doc.Save(dataDir + "PDFToSVG_out.svg", saveOptions);
```

 O código acima salva o PDF convertido para o formato SVG com o nome do arquivo`"PDFToSVG_out.svg"`.

### Exemplo de código-fonte de PDF para SVG usando Aspose.PDF para .NET

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Carregar documento PDF
Document doc = new Document(dataDir + "input.pdf");
// Instanciar um objeto de SvgSaveOptions
SvgSaveOptions saveOptions = new SvgSaveOptions();
// Não compactar imagem SVG em arquivo Zip
saveOptions.CompressOutputToZipArchive = false;
// Salve a saída em arquivos SVG
doc.Save(dataDir + "PDFToSVG_out.svg", saveOptions);
```

## Conclusão
Neste tutorial, cobrimos o processo passo a passo de conversão de um arquivo PDF para o formato SVG usando Aspose.PDF para .NET. Seguindo as instruções descritas acima, agora você poderá converter um arquivo PDF para o formato SVG. Este recurso é útil quando você deseja manter a qualidade e o dimensionamento dos gráficos ao converter para imagens vetoriais.

### Perguntas frequentes

#### P: Posso controlar a resolução ou o tamanho dos arquivos SVG resultantes durante a conversão de PDF para SVG?

 R: Sim, você pode controlar a resolução ou o tamanho dos arquivos SVG resultantes durante a conversão de PDF para SVG usando Aspose.PDF for .NET. O`SvgSaveOptions` classe fornece propriedades como`PageSavingCallback` e`SaveFormat` que permitem definir a resolução, tamanho da página ou outros parâmetros relacionados à saída SVG. Você pode personalizar essas opções de acordo com suas necessidades para controlar a qualidade e o tamanho dos arquivos SVG.

#### P: O Aspose.PDF for .NET oferece suporte à conversão de PDFs criptografados ou protegidos por senha para SVG?

R: Sim, Aspose.PDF for .NET suporta a conversão de PDFs criptografados ou protegidos por senha para o formato SVG. Ao carregar um PDF protegido por senha, você pode fornecer a senha usando o`Document` construtor de classe ou definindo o`Password` propriedade antes de carregar o PDF. Aspose.PDF for .NET cuidará da descriptografia durante o processo de conversão de PDF em SVG.

#### P: Posso converter apenas páginas específicas do PDF para SVG em vez do documento inteiro?

R: Sim, você pode converter apenas páginas específicas do PDF para SVG em vez do documento inteiro usando Aspose.PDF for .NET. Antes de salvar a saída como arquivos SVG, você pode selecionar as páginas que deseja converter especificando seus números ou intervalos de páginas. Desta forma, você pode extrair e converter apenas as páginas desejadas do formato PDF para SVG.

#### P: O Aspose.PDF for .NET é compatível com todas as versões do SVG?

R: Aspose.PDF para .NET foi projetado para ser compatível com a especificação SVG 1.1 (Scalable Vector Graphics). Suporta a geração de arquivos SVG de acordo com o padrão SVG 1.1. No entanto, observe que o SVG 2.0 foi introduzido como a versão mais recente da especificação SVG. Embora o Aspose.PDF for .NET ainda possa funcionar bem com SVG 2.0 em muitos casos, é recomendável verificar a compatibilidade e possíveis limitações com os recursos SVG específicos que você pretende usar.