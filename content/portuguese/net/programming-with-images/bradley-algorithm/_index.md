---
title: Algoritmo de Bradley
linktitle: Algoritmo de Bradley
second_title: Referência da API Aspose.PDF para .NET
description: Converta um documento PDF usando o algoritmo Bradley com Aspose.PDF for .NET.
type: docs
weight: 30
url: /pt/net/programming-with-images/bradley-algorithm/
---
Este guia passo a passo explica como usar o algoritmo Bradley com Aspose.PDF para .NET. Certifique-se de já ter configurado seu ambiente e siga as etapas abaixo:

## Passo 1: Defina o diretório do documento

 Antes de começar, certifique-se de definir o diretório correto para os documentos. Substituir`"YOUR DOCUMENT DIRECTORY"` no código com o caminho para o diretório onde seu documento PDF está localizado.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passo 2: Abra o documento

Nesta etapa, abriremos o documento PDF usando o`Document` classe de Aspose.PDF. Use o`Document` construtor e passe o caminho para o documento PDF.

```csharp
Document pdfDocument = new Document(dataDir + "PageToTIFF.pdf");
```

## Passo 3: Definir arquivos de saída

 Defina os nomes dos arquivos de saída para a imagem resultante e a imagem binária. Substituir`"resultant_out.tif"` e`"37116-bin_out.tif"` com os nomes desejados para os arquivos de saída.

```csharp
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
```

## Etapa 4: Crie o objeto Resolução

 Criar uma`Resolution`objeto para definir a resolução da imagem TIFF. Neste exemplo, estamos usando uma resolução de 300 dpi.

```csharp
Resolution resolution = new Resolution(300);
```

## Etapa 5: crie o objeto TiffSettings

 Criar uma`TiffSettings`objeto para especificar configurações para o arquivo TIFF de saída. Neste exemplo, estamos usando compactação LZW e profundidade de cor de 1 bit por pixel (formato de 1 bpp).

```csharp
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.LZW;
tiffSettings.Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp;
```

## Etapa 6: Crie o dispositivo TIFF

 Crie um dispositivo TIFF usando o`TiffDevice` objeto, especificando a resolução e as configurações TIFF.

```csharp
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
```

## Etapa 7: converta a página específica e salve a imagem

 Use o`Process` método do dispositivo TIFF para converter uma página específica do documento PDF e salvar a imagem em um arquivo TIFF. Especifique o caminho de saída do arquivo.

```csharp
tiffDevice.Process(pdfDocument, outputImageFile);
```

## Etapa 8: binarize a imagem usando o algoritmo de Bradley

 Use o`BinarizeBradley` método do dispositivo TIFF para binarizar a imagem usando o algoritmo de Bradley. Este método utiliza um fluxo de entrada da imagem original e um fluxo de saída da imagem binária. Especifique o limite de binarização (0,1 neste exemplo).

```csharp
using (FileStream

  inStream = new FileStream(outputImageFile, FileMode.Open))
{
using (FileStream outStream = new FileStream(outputBinImageFile, FileMode.Create))
{
tiffDevice. Binarize Bradley(inStream, outStream, 0.1);
}
}
```

### Exemplo de código-fonte para algoritmo Bradley usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir+ "PageToTIFF.pdf");
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
// Criar objeto de resolução
Resolution resolution = new Resolution(300);
// Criar objeto TiffSettings
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.LZW;
tiffSettings.Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp;
// Criar dispositivo TIFF
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
//Converta uma página específica e salve a imagem para transmitir
tiffDevice.Process(pdfDocument, outputImageFile);
using (FileStream inStream = new FileStream(outputImageFile, FileMode.Open))
{
	using (FileStream outStream = new FileStream(outputBinImageFile, FileMode.Create))
	{
		tiffDevice.BinarizeBradley(inStream, outStream, 0.1);
	}
}
System.Console.WriteLine("Conversion using bradley algorithm performed successfully!");
```

## Conclusão

Parabéns! Você concluiu com êxito a conversão usando o algoritmo Bradley com Aspose.PDF para .NET. Agora você pode usar as imagens resultantes em seus projetos ou aplicativos.

### Perguntas frequentes

#### P: O que é o algoritmo Bradley e como ele se relaciona com o Aspose.PDF para .NET?

R: O Algoritmo Bradley é uma técnica de processamento de imagem usada para melhorar a qualidade e clareza da imagem. Aspose.PDF for .NET fornece uma maneira conveniente de aplicar o Algoritmo Bradley a documentos PDF, resultando em imagens aprimoradas.

#### P: Como configuro meu ambiente para usar o Algoritmo Bradley com Aspose.PDF para .NET?

R: Antes de começar, certifique-se de ter o Aspose.PDF for .NET instalado corretamente e seu ambiente de desenvolvimento configurado.

#### P: Qual é a importância de definir o diretório de documentos no processo do Algoritmo Bradley?

R: Especificar o diretório correto do documento é crucial para garantir que o documento PDF esteja localizado no caminho correto para processamento.

#### P: Como abro um documento PDF usando Aspose.PDF for .NET no Algoritmo Bradley?

 R: Use o`Document` class para abrir o documento PDF, que serve de entrada para o processo do Algoritmo Bradley.

#### P: Qual é o propósito de definir nomes de arquivos de saída para a imagem e a imagem binária no processo do Algoritmo Bradley?

R: Definir nomes de arquivos de saída permite especificar onde a imagem resultante e a imagem binária serão salvas após a aplicação do algoritmo de Bradley.

#### P: Como a configuração da resolução afeta a qualidade da imagem TIFF no processo do Algoritmo Bradley?

R: A configuração de resolução determina o nível de detalhe e clareza na imagem TIFF resultante após a aplicação do Algoritmo Bradley.

#### P: Quais configurações posso personalizar para a imagem TIFF de saída no processo do Algoritmo Bradley?
R: Você pode personalizar configurações como tipo de compactação e profundidade de cor para obter a saída desejada para a imagem TIFF.

#### P: Como o dispositivo TIFF contribui para o processo do Algoritmo Bradley?

R: O dispositivo TIFF atua como uma ferramenta para processamento de imagens e aplicação do Algoritmo Bradley, resultando em melhor qualidade de imagem.

#### P: Como faço para converter uma página específica de um documento PDF em uma imagem TIFF no processo do Algoritmo Bradley?

 R: Utilize o`Process` método do dispositivo TIFF para converter uma página específica do documento PDF em uma imagem TIFF, que pode então ser processada usando o algoritmo de Bradley.