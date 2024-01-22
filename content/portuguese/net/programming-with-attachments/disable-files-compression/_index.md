---
title: Desativar compactação de arquivos em arquivo PDF
linktitle: Desativar compactação de arquivos em arquivo PDF
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como desabilitar a compactação de arquivos em arquivos PDF com Aspose.PDF para .NET. Guia passo a passo para fácil manuseio.
type: docs
weight: 30
url: /pt/net/programming-with-attachments/disable-files-compression/
---
Neste tutorial, orientaremos você passo a passo no seguinte código-fonte C# para desabilitar a compactação de arquivos em PDF usando Aspose.PDF para .NET.

Certifique-se de ter instalado a biblioteca Aspose.PDF e configurado seu ambiente de desenvolvimento antes de começar. Também possui conhecimentos básicos de programação C#.

### Etapa 1: configuração do diretório de documentos

No código-fonte fornecido, você precisa especificar o diretório onde o arquivo PDF está localizado e deseja desativar a compactação do arquivo. Altere a variável “dataDir” para o diretório desejado.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Passo 2: Abra o documento PDF existente

Abrimos o documento PDF existente usando o caminho especificado.

```csharp
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
```

### Etapa 3: configurar o novo arquivo para adicionar como anexo

Configuramos o novo arquivo que queremos adicionar como anexo. Neste exemplo, adicionamos um arquivo de texto com o nome "test_out.txt" e uma descrição "Arquivo de texto de exemplo".

```csharp
FileSpecification fileSpecification = new FileSpecification("test_out.txt", "Sample text file");
```

### Etapa 4: desative a compactação de arquivos

Desativamos a compactação de arquivos definindo a propriedade Encoding do objeto FileSpecification como FileEncoding.None.

```csharp
fileSpecification.Encoding = FileEncoding.None;
```

### Etapa 5: Adicionar o anexo à coleção de anexos do documento

Adicionamos o anexo à coleção de anexos do documento.

```csharp
pdfDocument.EmbeddedFiles.Add(fileSpecification);
```

### Etapa 6: salve o novo arquivo de saída

Finalmente, salvamos o novo arquivo PDF resultante com o nome "DisableFilesCompression_out.pdf" no diretório especificado.

```csharp
pdfDocument.Save(dataDir + "DisableFilesCompression_out.pdf");
```


### Exemplo de código-fonte para desabilitar compactação de arquivos usando Aspose.PDF para .NET 

```csharp

// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
// Configure novo arquivo para ser adicionado como anexo
FileSpecification fileSpecification = new FileSpecification("test_out.txt", "Sample text file");
// Especifique a propriedade de codificação configurando-a como FileEncoding.None
fileSpecification.Encoding = FileEncoding.None;
//Adicionar anexo à coleção de anexos do documento
pdfDocument.EmbeddedFiles.Add(fileSpecification);
dataDir = dataDir + "DisableFilesCompression_out.pdf";
// Salvar nova saída
pdfDocument.Save(dataDir);
Console.WriteLine("\nFile compression disabled successfully.\nFile saved at " + dataDir);

```

## Conclusão

Neste tutorial, explicamos como desabilitar a compactação de arquivos em um PDF usando Aspose.PDF for .NET. Agora você pode usar esse conhecimento para manter a integridade dos arquivos anexados sem compactação.

## Perguntas frequentes sobre como desativar a compactação de arquivos em arquivos PDF

#### P: Por que eu desejaria desabilitar a compactação de arquivos em um documento PDF?

R: Desativar a compactação de arquivos garante que os arquivos anexados em um documento PDF permaneçam descompactados, preservando sua qualidade e conteúdo originais.

#### P: Como a desativação da compactação de arquivos beneficia os anexos PDF?

R: Desativar a compactação evita qualquer perda de dados ou de qualidade que possa ocorrer durante o processo de compactação, garantindo que os arquivos anexados sejam apresentados como estão.

#### P: Posso desabilitar seletivamente a compactação para anexos específicos usando este tutorial?

R: Sim, este tutorial orienta você na desativação da compactação de arquivos para anexos individuais em um documento PDF, fornecendo controle refinado.

#### P: Para quais tipos de anexos posso desabilitar a compactação?

R: Você pode desativar a compactação para qualquer tipo de anexo, como imagens, documentos, planilhas e muito mais, garantindo que sua integridade seja mantida.

#### P: A desativação da compactação afeta o tamanho geral do arquivo do documento PDF?

R: Desativar a compactação para anexos pode levar a um ligeiro aumento no tamanho geral do arquivo do documento PDF, pois os arquivos descompactados ocupam mais espaço.

#### P: Como o Aspose.PDF for .NET facilita o processo de desativação da compactação de arquivos?

R: Aspose.PDF for .NET fornece uma API fácil de usar que permite desabilitar a compactação de arquivos para anexos, conforme demonstrado no código-fonte fornecido.

#### P: Posso reativar a compactação de anexos posteriormente, se necessário?

R: Sim, você pode modificar as configurações do anexo para ativar a compactação novamente, se necessário.

#### P: O que acontece se eu abrir o PDF em um dispositivo ou software compatível com compactação?

R: Se você abrir o PDF em um dispositivo ou software compatível com compactação, o anexo poderá ser exibido descompactado, afetando potencialmente o tamanho do arquivo e o desempenho de renderização.

#### P: Existem cenários específicos em que a desativação da compactação é recomendada?

R: A desativação da compactação é recomendada para anexos onde a manutenção da qualidade original e da integridade dos dados é uma prioridade, como imagens de alta resolução ou documentos confidenciais.