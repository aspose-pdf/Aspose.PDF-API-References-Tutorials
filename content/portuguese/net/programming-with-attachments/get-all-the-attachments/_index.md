---
title: Obtenha todos os anexos em arquivo PDF
linktitle: Obtenha todos os anexos em arquivo PDF
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como obter todos os anexos em um arquivo PDF com Aspose.PDF para .NET. Guia passo a passo para fácil manuseio.
type: docs
weight: 40
url: /pt/net/programming-with-attachments/get-all-the-attachments/
---
Neste tutorial, orientaremos você através do seguinte código-fonte C#, passo a passo, para obter todos os anexos em um arquivo PDF usando Aspose.PDF para .NET.

Certifique-se de ter instalado a biblioteca Aspose.PDF e configurado seu ambiente de desenvolvimento antes de começar. Também possui conhecimentos básicos de programação C#.

### Etapa 1: configuração do diretório de documentos

No código-fonte fornecido, você precisa especificar o diretório onde está localizado o arquivo PDF do qual deseja obter os anexos. Altere a variável “dataDir” para o diretório desejado.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Passo 2: Abra o documento PDF existente

Abrimos o documento PDF existente usando o caminho especificado.

```csharp
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
```

### Passo 3: Obtendo a Coleção de Anexos

Obtemos a coleção de anexos do documento.

```csharp
EmbeddedFileCollection embeddedFiles = pdfDocument.EmbeddedFiles;
```

### Passo 4: Recuperando anexos

Percorremos a coleção para obter todos os anexos e exibir suas informações. Também salvamos anexos em arquivos individuais.

```csharp
int count = 1;
foreach(FileSpecification fileSpecification in embeddedFiles)
{
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
Console.WriteLine("MIME Type: {0}", fileSpecification.MIMEType);

// Verifique se os parâmetros do objeto contêm informações adicionais
if (fileSpecification.Params != null)
{
Console.WriteLine("CheckSum: {0}", fileSpecification.Params.CheckSum);
Console.WriteLine("Creation date: {0}", fileSpecification.Params.CreationDate);
Console.WriteLine("Modified date: {0}", fileSpecification.Params.ModDate);
Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
}

// Recupere o anexo e salve em um arquivo
byte[] fileContent = new byte[fileSpecification.Contents.Length];
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + count + "_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();

count += 1;
}
```


### Exemplo de código-fonte para obter todos os anexos usando Aspose.PDF para .NET 

```csharp

// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
// Obtenha coleção de arquivos incorporados
EmbeddedFileCollection embeddedFiles = pdfDocument.EmbeddedFiles;
// Obtenha a contagem dos arquivos incorporados
Console.WriteLine("Total files : {0}", embeddedFiles.Count);
int count = 1;
// Percorra a coleção para obter todos os anexos
foreach (FileSpecification fileSpecification in embeddedFiles)
{
	Console.WriteLine("Name: {0}", fileSpecification.Name);
	Console.WriteLine("Description: {0}",
	fileSpecification.Description);
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
	fileSpecification.Contents.Read(fileContent, 0,
	fileContent.Length);
	FileStream fileStream = new FileStream(dataDir + count + "_out" + ".txt",
	FileMode.Create);
	fileStream.Write(fileContent, 0, fileContent.Length);
	fileStream.Close();
	count+=1;
}

```

## Conclusão

Neste tutorial, explicamos como obter todos os anexos de um arquivo PDF usando Aspose.PDF for .NET. Agora você pode usar esse conhecimento para extrair e manipular anexos de seus arquivos PDF.

## Perguntas frequentes para obter todos os anexos em arquivo PDF

#### P: Por que eu precisaria recuperar todos os anexos de um documento PDF?

R: A recuperação de anexos permite acessar e manipular arquivos adicionais incorporados em um PDF, o que pode ser útil para arquivamento, compartilhamento ou processamento posterior.

#### P: Que tipos de arquivos podem ser anexados a um documento PDF?

R: Os documentos PDF podem conter uma ampla variedade de arquivos anexados, incluindo imagens, documentos, planilhas, arquivos de áudio e muito mais.

#### P: Como este tutorial me ajuda a recuperar anexos de um PDF usando Aspose.PDF for .NET?

R: Este tutorial fornece instruções passo a passo e código-fonte C# para acessar e recuperar todos os anexos de um documento PDF.

#### P: Posso recuperar anexos específicos em vez de todos os anexos usando este tutorial?

R: Sim, você pode modificar o código fornecido para recuperar anexos seletivamente com base em seus requisitos.

#### P: Que informações sobre cada anexo posso obter usando este tutorial?

R: Este tutorial demonstra como recuperar e exibir detalhes como nome do anexo, descrição, tipo MIME, data de criação, data de modificação e tamanho.

#### P: Como os anexos recuperados são salvos usando este tutorial?

R: O tutorial orienta você no salvamento de cada anexo recuperado como um arquivo separado no diretório especificado.

#### P: Posso usar esse conhecimento para extrair anexos de arquivos PDF protegidos por senha?

R: Sim, você pode aplicar princípios semelhantes para recuperar anexos de arquivos PDF protegidos por senha usando Aspose.PDF for .NET.

#### P: Como o Aspose.PDF for .NET facilita a recuperação de anexos?

R: Aspose.PDF for .NET fornece uma API intuitiva que permite acessar e manipular anexos em documentos PDF facilmente.

#### P: Existem cenários específicos em que a recuperação de anexos é recomendada?

R: A recuperação de anexos é útil quando você precisa acessar arquivos incorporados em um PDF, como extrair imagens, arquivos de áudio ou documentos adicionais.