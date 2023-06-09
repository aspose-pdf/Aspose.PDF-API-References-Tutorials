---
title: Ottieni tutti gli allegati
linktitle: Ottieni tutti gli allegati
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come ottenere tutti gli allegati da un file PDF con Aspose.PDF per .NET. Guida passo passo per una facile gestione.
type: docs
weight: 40
url: /it/net/programming-with-attachments/get-all-the-attachments/
---
In questo tutorial, ti guideremo attraverso il seguente codice sorgente C# passo dopo passo per ottenere tutti gli allegati da un file PDF usando Aspose.PDF per .NET.

Assicurati di aver installato la libreria Aspose.PDF e di configurare il tuo ambiente di sviluppo prima di iniziare. Avere anche una conoscenza di base della programmazione C#.

### Passaggio 1: impostazione della directory dei documenti

Nel codice sorgente fornito, è necessario specificare la directory in cui si trova il file PDF da cui si desidera ottenere gli allegati. Modificare la variabile "dataDir" nella directory desiderata.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Passaggio 2: aprire il documento PDF esistente

Apriamo il documento PDF esistente utilizzando il percorso specificato.

```csharp
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
```

### Passaggio 3: ottenere la raccolta degli allegati

Otteniamo la raccolta di allegati dal documento.

```csharp
EmbeddedFileCollection embeddedFiles = pdfDocument.EmbeddedFiles;
```

### Passaggio 4: recupero degli allegati

Esaminiamo la raccolta per ottenere tutti gli allegati e visualizzare le loro informazioni. Salviamo anche gli allegati in singoli file.

```csharp
int count = 1;
foreach(FileSpecification fileSpecification in embeddedFiles)
{
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
Console.WriteLine("MIME Type: {0}", fileSpecification.MIMEType);

// Verificare se i parametri dell'oggetto contengono informazioni aggiuntive
if (fileSpecification.Params != null)
{
Console.WriteLine("CheckSum: {0}", fileSpecification.Params.CheckSum);
Console.WriteLine("Creation date: {0}", fileSpecification.Params.CreationDate);
Console.WriteLine("Modified date: {0}", fileSpecification.Params.ModDate);
Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
}

// Recuperare l'allegato e salvarlo in un file
byte[] fileContent = new byte[fileSpecification.Contents.Length];
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + count + "_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();

count += 1;
}
```


### Esempio di codice sorgente per Ottieni tutti gli allegati utilizzando Aspose.PDF per .NET 

```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
// Ottieni la raccolta di file incorporati
EmbeddedFileCollection embeddedFiles = pdfDocument.EmbeddedFiles;
// Ottieni il conteggio dei file incorporati
Console.WriteLine("Total files : {0}", embeddedFiles.Count);
int count = 1;
// Scorri la raccolta per ottenere tutti gli allegati
foreach (FileSpecification fileSpecification in embeddedFiles)
{
	Console.WriteLine("Name: {0}", fileSpecification.Name);
	Console.WriteLine("Description: {0}",
	fileSpecification.Description);
	Console.WriteLine("Mime Type: {0}", fileSpecification.MIMEType);
	// Controlla se l'oggetto parametro contiene i parametri
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
	// Ottieni l'allegato e scrivi su file o stream
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

## Conclusione

In questo tutorial, abbiamo spiegato come ottenere tutti gli allegati da un file PDF utilizzando Aspose.PDF per .NET. Ora puoi utilizzare questa conoscenza per estrarre e manipolare gli allegati dai tuoi file PDF.