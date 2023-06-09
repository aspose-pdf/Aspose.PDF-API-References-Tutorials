---
title: Ottieni allegato individuale
linktitle: Ottieni allegato individuale
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come ottenere un singolo allegato in un file PDF con Aspose.PDF per .NET.
type: docs
weight: 60
url: /it/net/programming-with-attachments/get-individual-attachment/
---
In questo tutorial, ti guideremo attraverso il seguente codice sorgente C# passo dopo passo per ottenere un singolo allegato di un file PDF utilizzando Aspose.PDF per .NET.

Assicurati di aver installato la libreria Aspose.PDF e di configurare il tuo ambiente di sviluppo prima di iniziare. Avere anche una conoscenza di base della programmazione C#.

### Passaggio 1: impostazione della directory dei documenti

Nel codice sorgente fornito, è necessario specificare la directory in cui si trova il file PDF da cui si desidera ottenere il singolo allegato. Modificare la variabile "dataDir" nella directory desiderata.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Passaggio 2: aprire il documento PDF esistente

Apriamo il documento PDF esistente utilizzando il percorso specificato.

```csharp
Document pdfDocument = new Document(dataDir + "GetIndividualAttachment.pdf");
```

### Passaggio 3: ottenere un allegato specifico

Recuperiamo un allegato specifico dalla raccolta di allegati del documento. In questo esempio, otteniamo il primo allegato utilizzando l'indice 1.

```csharp
FileSpecification fileSpecification = pdfDocument.EmbeddedFiles[1];
```

### Passaggio 4: ottieni le proprietà del file

Visualizziamo le proprietà degli allegati come nome, descrizione, tipo MIME, hash di controllo, data di creazione, data di modifica e dimensione.

```csharp
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
Console.WriteLine("MIME Type: {0}", fileSpecification.MIMEType);

// Verificare se i parametri dell'oggetto contengono informazioni aggiuntive
if (fileSpecification.Params != null)
{
Console.WriteLine("Check Hash: {0}", fileSpecification.Params.CheckSum);
Console.WriteLine("Creation date: {0}", fileSpecification.Params.CreationDate);
Console.WriteLine("Modified date: {0}", fileSpecification.Params.ModDate);
Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
}
```

### Passaggio 5: recuperare l'allegato e salvarlo in un file

Recuperiamo il contenuto dell'allegato e lo salviamo in un file di testo. In questo esempio, il file viene salvato con il nome "test_out.txt".

```csharp
byte[] fileContent = new byte[fileSpecification.Contents.Length];
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + "test_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();
```

### Esempio di codice sorgente per Ottieni allegato individuale utilizzando Aspose.PDF per .NET 

```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "GetIndividualAttachment.pdf");
// Ottieni un particolare file incorporato
FileSpecification fileSpecification = pdfDocument.EmbeddedFiles[1];
// Ottieni le proprietà del file
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
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
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + "test_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();

```

## Conclusione

In questo tutorial, abbiamo spiegato come ottenere un singolo allegato da un file PDF utilizzando Aspose.PDF per .NET. Ora puoi utilizzare questa conoscenza per estrarre e salvare gli allegati dai tuoi file PDF.
