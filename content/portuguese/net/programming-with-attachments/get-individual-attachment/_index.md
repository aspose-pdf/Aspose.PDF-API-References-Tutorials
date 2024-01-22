---
title: Obtenha anexo individual em arquivo PDF
linktitle: Obtenha anexo individual em arquivo PDF
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como obter um anexo individual em arquivo PDF com Aspose.PDF para .NET.
type: docs
weight: 60
url: /pt/net/programming-with-attachments/get-individual-attachment/
---
Neste tutorial, orientaremos você passo a passo no seguinte código-fonte C# para obter um anexo individual de um arquivo PDF usando Aspose.PDF para .NET.

Certifique-se de ter instalado a biblioteca Aspose.PDF e configurado seu ambiente de desenvolvimento antes de começar. Também possui conhecimentos básicos de programação C#.

### Etapa 1: configuração do diretório de documentos

No código-fonte fornecido, você precisa especificar o diretório onde está localizado o arquivo PDF do qual deseja obter o anexo individual. Altere a variável “dataDir” para o diretório desejado.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Passo 2: Abra o documento PDF existente

Abrimos o documento PDF existente usando o caminho especificado.

```csharp
Document pdfDocument = new Document(dataDir + "GetIndividualAttachment.pdf");
```

### Passo 3: Obtendo um Anexo Específico

Recuperamos um anexo específico da coleção de anexos do documento. Neste exemplo, obtemos o primeiro anexo usando o índice 1.

```csharp
FileSpecification fileSpecification = pdfDocument.EmbeddedFiles[1];
```

### Etapa 4: obter propriedades do arquivo

Exibimos propriedades do anexo, como nome, descrição, tipo MIME, hash de controle, data de criação, data de modificação e tamanho.

```csharp
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
Console.WriteLine("MIME Type: {0}", fileSpecification.MIMEType);

// Verifique se os parâmetros do objeto contêm informações adicionais
if (fileSpecification.Params != null)
{
Console.WriteLine("Check Hash: {0}", fileSpecification.Params.CheckSum);
Console.WriteLine("Creation date: {0}", fileSpecification.Params.CreationDate);
Console.WriteLine("Modified date: {0}", fileSpecification.Params.ModDate);
Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
}
```

### Etapa 5: recuperar o anexo e salvar em arquivo

Recuperamos o conteúdo do anexo e o salvamos em um arquivo de texto. Neste exemplo, o arquivo é salvo com o nome "test_out.txt".

```csharp
byte[] fileContent = new byte[fileSpecification.Contents.Length];
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + "test_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();
```

### Exemplo de código-fonte para obter anexo individual usando Aspose.PDF para .NET 

```csharp

// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "GetIndividualAttachment.pdf");
// Obtenha um arquivo incorporado específico
FileSpecification fileSpecification = pdfDocument.EmbeddedFiles[1];
// Obtenha as propriedades do arquivo
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
Console.WriteLine("Mime Type: {0}", fileSpecification.MIMEType);
//Verifique se o objeto de parâmetro contém os parâmetros
if (fileSpecification.Params != null)
{
	Console.WriteLine("CheckSum: {0}",
	fileSpecification.Params.CheckSum);
	Console.WriteLine("Creation Date: {0}",
	fileSpecification.Params.CreationDate);
	Console.WriteLine("Modification Date: {0}",
	fileSpecification.Params.ModDate);
	Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
}
// Obtenha o anexo e grave no arquivo ou stream
byte[] fileContent = new byte[fileSpecification.Contents.Length];
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + "test_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();

```

## Conclusão

Neste tutorial, explicamos como obter um anexo individual de um arquivo PDF usando Aspose.PDF for .NET. Agora você pode usar esse conhecimento para extrair e salvar anexos de seus arquivos PDF.

### Perguntas frequentes para obter anexo individual em arquivo PDF

#### P: Qual é o propósito de obter um anexo individual de um documento PDF?

R: Obter um anexo individual permite extrair e salvar um arquivo incorporado específico em um PDF, o que pode ser útil para análise ou manipulação posterior.

#### P: Como posso me beneficiar deste tutorial em minhas tarefas relacionadas a PDF?

R: Este tutorial fornece instruções passo a passo e código-fonte C# para recuperar e salvar um anexo específico de um documento PDF usando Aspose.PDF for .NET.

#### P: Quais propriedades de anexo posso acessar usando este tutorial?

R: Você pode acessar propriedades do anexo, como nome, descrição, tipo MIME, hash de controle, data de criação, data de modificação e tamanho do anexo específico.

#### P: Posso modificar o código para obter anexos diferentes do primeiro?

 R: Com certeza, você pode ajustar o índice (por exemplo,`pdfDocument.EmbeddedFiles[1]`) para recuperar anexos em diferentes índices no PDF.

#### P: Como salvo o anexo recuperado em um arquivo?

R: Este tutorial fornece código para recuperar o conteúdo do anexo e salvá-lo em um arquivo de texto com um nome especificado.

#### P: Qual é o significado da propriedade "Check Hash" nas informações do anexo?

R: A propriedade "Check Hash" representa o valor do hash de controle do anexo, que pode ser usado para verificar a integridade do anexo.

#### P: Posso ampliar esse conhecimento para extrair anexos com critérios específicos, como tipo de arquivo?

R: Sim, você pode aprimorar o código para filtrar anexos com base em critérios específicos, como tipo de arquivo ou outras propriedades.

#### P: Como o Aspose.PDF for .NET simplifica o processo de extração de anexos individuais?

R: Aspose.PDF for .NET fornece uma API amigável que facilita a extração e manipulação de anexos em documentos PDF.

#### P: Este tutorial também é relevante para arquivos PDF protegidos por senha?

R: Sim, você pode adaptar técnicas semelhantes para recuperar anexos individuais de arquivos PDF protegidos por senha usando Aspose.PDF for .NET.
