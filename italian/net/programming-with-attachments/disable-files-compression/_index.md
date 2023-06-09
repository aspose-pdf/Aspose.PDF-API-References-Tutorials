---
title: Disabilita la compressione dei file
linktitle: Disabilita la compressione dei file
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come disabilitare la compressione dei file in un file PDF con Aspose.PDF per .NET. Guida passo passo per una facile gestione.
type: docs
weight: 30
url: /it/net/programming-with-attachments/disable-files-compression/
---
In questo tutorial, ti guideremo attraverso il seguente codice sorgente C# passo dopo passo per disabilitare la compressione dei file in un PDF usando Aspose.PDF per .NET.

Assicurati di aver installato la libreria Aspose.PDF e di configurare il tuo ambiente di sviluppo prima di iniziare. Avere anche una conoscenza di base della programmazione C#.

### Passaggio 1: impostazione della directory dei documenti

Nel codice sorgente fornito, è necessario specificare la directory in cui si trova il file PDF che si desidera disabilitare la compressione del file. Modificare la variabile "dataDir" nella directory desiderata.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Passaggio 2: aprire il documento PDF esistente

Apriamo il documento PDF esistente utilizzando il percorso specificato.

```csharp
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
```

### Passaggio 3: impostazione del nuovo file da aggiungere come allegato

Configuriamo il nuovo file che vogliamo aggiungere come allegato. In questo esempio, aggiungiamo un file di testo con il nome "test_out.txt" e una descrizione "Example text file".

```csharp
FileSpecification fileSpecification = new FileSpecification("test_out.txt", "Sample text file");
```

### Passaggio 4: disabilitare la compressione dei file

Disabilitiamo la compressione dei file impostando la proprietà Encoding dell'oggetto FileSpecification su FileEncoding.None.

```csharp
fileSpecification.Encoding = FileEncoding.None;
```

### Passaggio 5: aggiunta dell'allegato alla raccolta degli allegati del documento

Aggiungiamo l'allegato alla raccolta di allegati del documento.

```csharp
pdfDocument.EmbeddedFiles.Add(fileSpecification);
```

### Passaggio 6: salva il nuovo file di output

Infine, salviamo il nuovo file PDF risultante con il nome "DisableFilesCompression_out.pdf" nella directory specificata.

```csharp
pdfDocument.Save(dataDir + "DisableFilesCompression_out.pdf");
```


### Codice sorgente di esempio per disabilitare la compressione dei file utilizzando Aspose.PDF per .NET 

```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
// Imposta il nuovo file da aggiungere come allegato
FileSpecification fileSpecification = new FileSpecification("test_out.txt", "Sample text file");
// Specifica Encoding proparty impostandolo su FileEncoding.None
fileSpecification.Encoding = FileEncoding.None;
// Aggiungi allegato alla raccolta di allegati del documento
pdfDocument.EmbeddedFiles.Add(fileSpecification);
dataDir = dataDir + "DisableFilesCompression_out.pdf";
// Salva nuovo output
pdfDocument.Save(dataDir);
Console.WriteLine("\nFile compression disabled successfully.\nFile saved at " + dataDir);

```

## Conclusione

In questo tutorial, abbiamo spiegato come disabilitare la compressione dei file in un PDF utilizzando Aspose.PDF per .NET. È ora possibile utilizzare questa conoscenza per mantenere l'integrità dei file allegati senza compressione.