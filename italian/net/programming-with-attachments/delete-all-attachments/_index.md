---
title: Elimina tutti gli allegati
linktitle: Elimina tutti gli allegati
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come rimuovere tutti gli allegati da un file PDF utilizzando Aspose.PDF per .NET. Guida passo passo per una facile gestione.
type: docs
weight: 20
url: /it/net/programming-with-attachments/delete-all-attachments/
---
In questo tutorial, ti guideremo attraverso il seguente codice sorgente C# passo dopo passo per rimuovere tutti gli allegati da un file PDF usando Aspose.PDF per .NET.

Assicurati di aver installato la libreria Aspose.PDF e di configurare il tuo ambiente di sviluppo prima di iniziare. Avere anche una conoscenza di base della programmazione C#.

### Passaggio 1: impostazione della directory dei documenti

Nel codice sorgente fornito, è necessario specificare la directory in cui si trova il file PDF da cui si desidera rimuovere gli allegati. Modificare la variabile "dataDir" nella directory desiderata.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Passaggio 2: aprire il documento PDF esistente

Apriamo il documento PDF esistente utilizzando il percorso specificato.

```csharp
Document pdfDocument = new Document(dataDir + "DeleteAllAttachments.pdf");
```

### Passaggio 3: rimuovere tutti gli allegati

Rimuoviamo tutti gli allegati dal documento.

```csharp
pdfDocument.EmbeddedFiles.Delete();
```

### Passaggio 4: salvare il file aggiornato

Infine, salviamo il file PDF aggiornato con il nome "DeleteAllAttachments_out.pdf" nella directory specificata.

```csharp
pdfDocument.Save(dataDir + "DeleteAllAttachments_out.pdf");
```

### Esempio di codice sorgente per Elimina tutti gli allegati utilizzando Aspose.PDF per .NET 

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "DeleteAllAttachments.pdf");
// Elimina tutti gli allegati
pdfDocument.EmbeddedFiles.Delete();
dataDir = dataDir + "DeleteAllAttachments_out.pdf";
// Salva file aggiornato
pdfDocument.Save(dataDir);
Console.WriteLine("\nAll attachments deleted successfully.\nFile saved at " + dataDir);

```

## Conclusione

In questo tutorial, abbiamo spiegato come rimuovere tutti gli allegati da un file PDF utilizzando Aspose.PDF per .NET. Ora puoi utilizzare questa conoscenza per ripulire i tuoi documenti PDF rimuovendo tutti gli allegati indesiderati.
