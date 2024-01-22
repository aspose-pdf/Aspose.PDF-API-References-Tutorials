---
title: PDF para XPS
linktitle: PDF para XPS
second_title: Referência da API Aspose.PDF para .NET
description: Guia passo a passo para converter PDF em XPS usando Aspose.PDF para .NET.
type: docs
weight: 220
url: /pt/net/document-conversion/pdf-to-xps/
---
Neste tutorial, orientaremos você no processo de conversão de um arquivo PDF para o formato XPS (XML Paper Specification) usando Aspose.PDF para .NET. O formato XPS é um formato de arquivo baseado em XML usado para representar documentos eletronicamente. Seguindo as etapas abaixo, você poderá converter um arquivo PDF para o formato XPS.

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
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 Certifique-se de substituir`"YOUR DOCUMENTS DIRECTORY"` com o diretório real onde seu arquivo PDF está localizado.

## Etapa 2: instanciar opções de salvamento XPS
Após carregar o arquivo PDF, instanciaremos as opções de salvamento do XPS. Use o seguinte código:

```csharp
// Instancie opções de salvamento XPS
Aspose.Pdf.XpsSaveOptions saveOptions = new Aspose.Pdf.XpsSaveOptions();
```

## Etapa 3: Salvar o arquivo XPS resultante
Agora salvaremos o arquivo PDF convertido no formato XPS. Use o seguinte código:

```csharp
// Salve o documento XPS
pdfDocument.Save("PDFToXPS_out.xps", saveOptions);
```

 O código acima salva o arquivo PDF convertido no formato XPS com o nome do arquivo`"PDFToXPS_out.xps"`.


### Exemplo de código-fonte para PDF para XPS usando Aspose.PDF para .NET

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Carregar documento PDF
Document pdfDocument = new Document(dataDir + "input.pdf");

// Instanciar opções de salvamento XPS
Aspose.Pdf.XpsSaveOptions saveOptions = new Aspose.Pdf.XpsSaveOptions();

// Salve o documento XPS
pdfDocument.Save("PDFToXPS_out.xps", saveOptions);
```

## Conclusão
Neste tutorial, cobrimos o processo passo a passo de conversão de um arquivo PDF para o formato XPS usando Aspose.PDF para .NET. Seguindo as instruções descritas acima, agora você poderá converter um arquivo PDF para o formato XPS. Este recurso é útil quando você deseja visualizar ou imprimir documentos PDF no formato XPS.

### Perguntas frequentes

#### P: O formato XPS é adequado para compatibilidade entre plataformas?

R: O formato XPS, sendo um formato de arquivo baseado em XML, é independente de plataforma e pode ser visualizado em vários sistemas operacionais e dispositivos. Os arquivos XPS são suportados em plataformas Windows por padrão, e alguns aplicativos e visualizadores de terceiros podem estar disponíveis para outras plataformas.

#### P: O Aspose.PDF for .NET pode lidar com arquivos PDF complexos com múltiplas páginas e imagens durante a conversão XPS?

R: Sim, o Aspose.PDF for .NET pode lidar com arquivos PDF complexos com múltiplas páginas e imagens durante a conversão XPS. Ele retém com precisão o layout, as imagens e o conteúdo textual do PDF enquanto o converte para o formato XPS.

#### P: É possível especificar configurações ou opções adicionais durante o processo de conversão de XPS?

 R: Sim, Aspose.PDF for .NET oferece várias opções e configurações que podem ser personalizadas durante o processo de conversão XPS. Você pode controlar a compactação da imagem, a incorporação de fontes e outras configurações usando o`XpsSaveOptions` aula.

#### P: Os PDFs protegidos por senha podem ser convertidos para o formato XPS usando Aspose.PDF for .NET?

 R: Sim, Aspose.PDF for .NET suporta a conversão de PDFs protegidos por senha para o formato XPS. Ao carregar um PDF protegido por senha, você pode fornecer a senha usando o`Document` construtor de classe ou definindo o`Password` propriedade antes de carregar o PDF.