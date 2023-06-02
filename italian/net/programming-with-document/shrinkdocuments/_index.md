---
title: Riduci i documenti
linktitle: Riduci i documenti
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come utilizzare Aspose.PDF per .NET per ridurre i documenti PDF con questa guida dettagliata.
type: docs
weight: 350
url: /it/net/programming-with-document/shrinkdocuments/
---
Aspose.PDF per .NET è una potente libreria che consente agli sviluppatori di creare, manipolare e ottimizzare documenti PDF utilizzando C#. In questo tutorial, esamineremo un esempio di come utilizzare Aspose.PDF per ridurre un documento PDF.

## Passaggio 1: caricamento del documento PDF

 Per ridurre un documento PDF, dobbiamo prima caricarlo nella nostra applicazione C# utilizzando Aspose.PDF. Nel codice seguente, specifichiamo il percorso del nostro documento PDF e creiamo una nuova istanza del file`Document` classe.

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "ShrinkDocument.pdf");
```

## Passaggio 2: riduzione del documento PDF

 Una volta caricato il documento PDF, possiamo utilizzare il file`OptimizeResources` metodo del`Document` class per ottimizzare il documento e potenzialmente ridurne le dimensioni. Si noti che questo metodo non può garantire la riduzione del documento, poiché alcuni documenti PDF potrebbero già essere altamente ottimizzati.

```csharp
// Ottimizza il documento PDF. Si noti, tuttavia, che questo metodo non può garantire la riduzione del documento
pdfDocument.OptimizeResources();
```

## Passaggio 3: salvataggio del documento PDF aggiornato

Dopo aver ottimizzato il documento PDF, possiamo salvare la versione aggiornata in un nuovo file utilizzando il formato`Save` metodo del`Document` classe. Nel codice seguente, specifichiamo il percorso e il nome file del file di output.

```csharp
// Specificare il percorso del file di output
string outputFilePath = dataDir + "ShrinkDocument_out.pdf";
// Salva documento aggiornato
pdfDocument.Save(outputFilePath);
```

### Esempio di codice sorgente per ridurre i documenti utilizzando Aspose.PDF per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "ShrinkDocument.pdf");
// Ottimizza il documento PDF. Si noti, tuttavia, che questo metodo non può garantire la riduzione del documento
pdfDocument.OptimizeResources();
dataDir = dataDir + "ShrinkDocument_out.pdf";
// Salva documento aggiornato
pdfDocument.Save(dataDir);
```
