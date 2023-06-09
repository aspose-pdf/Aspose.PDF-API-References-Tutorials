---
title: Aggiungi allegato
linktitle: Aggiungi allegato
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come aggiungere allegati ai tuoi file PDF utilizzando Aspose.PDF per .NET. Guida passo passo per una facile gestione.
type: docs
weight: 10
url: /it/net/programming-with-attachments/add-attachment/
---

In questo tutorial, ti guideremo attraverso il seguente codice sorgente C# passo dopo passo per aggiungere un allegato a un file PDF usando Aspose.PDF per .NET.

Assicurati di aver installato la libreria Aspose.PDF e di configurare il tuo ambiente di sviluppo prima di iniziare. Avere anche una conoscenza di base della programmazione C#.

### Passaggio 1: impostazione della directory dei documenti

Nel codice sorgente fornito, è necessario specificare la directory in cui si trova il file PDF a cui si desidera aggiungere l'allegato. Modificare la variabile "dataDir" nella directory desiderata.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Passaggio 2: aprire il documento PDF esistente

Apriamo il documento PDF esistente utilizzando il percorso specificato.

```csharp
Document pdfDocument = new Document(dataDir + "AddAttachment.pdf");
```

### Passaggio 3: impostazione del nuovo file da aggiungere come allegato

Configuriamo il nuovo file che vogliamo aggiungere come allegato. In questo esempio, aggiungiamo un file di testo con il nome "test.txt" e una descrizione "File di testo di esempio".

```csharp
FileSpecification fileSpecification = new FileSpecification(dataDir + "test.txt", "Sample text file");
```

### Passaggio 4: aggiunta dell'allegato alla raccolta degli allegati del documento

Aggiungiamo l'allegato alla raccolta di allegati del documento.

```csharp
pdfDocument.EmbeddedFiles.Add(fileSpecification);
```

### Passaggio 5: salvare il nuovo file di output

Infine, salviamo il nuovo file PDF risultante con il nome "AddAttachment_out.pdf" nella directory specificata.

```csharp
pdfDocument.Save(dataDir + "AddAttachment_out.pdf");
```

### Esempio di codice sorgente per Aggiungi allegato utilizzando Aspose.PDF per .NET
 
```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "AddAttachment.pdf");
// Imposta il nuovo file da aggiungere come allegato
FileSpecification fileSpecification = new FileSpecification(dataDir + "test.txt", "Sample text file");
// Aggiungi allegato alla raccolta di allegati del documento
pdfDocument.EmbeddedFiles.Add(fileSpecification);
dataDir = dataDir + "AddAttachment_out.pdf";
// Salva nuovo output
pdfDocument.Save(dataDir);
Console.WriteLine("\nSample text file attached successfully.\nFile saved at " + dataDir);

```

## Conclusione

In questo tutorial, abbiamo spiegato come aggiungere un allegato a un file PDF utilizzando Aspose.PDF per .NET. Ora puoi utilizzare questa conoscenza per aggiungere ulteriori file come allegati ai tuoi documenti PDF.
