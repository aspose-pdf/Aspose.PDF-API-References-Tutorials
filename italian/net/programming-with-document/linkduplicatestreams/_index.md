---
title: Collega flussi duplicati
linktitle: Collega flussi duplicati
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come utilizzare Aspose.PDF per la funzione .NET Link Duplicate Streams per ottimizzare i tuoi documenti PDF con questa guida dettagliata.
type: docs
weight: 230
url: /it/net/programming-with-document/linkduplicatestreams/
---
Aspose.PDF per .NET è una libreria completa e potente che fornisce una varietà di funzionalità per lavorare con i file PDF. Una delle sue caratteristiche principali è la capacità di ottimizzare i file PDF. In questo articolo, spiegheremo come utilizzare la funzionalità Link Duplicate Streams di Aspose.PDF per .NET per ottimizzare i file PDF. Forniremo istruzioni dettagliate e includeremo un esempio completo di codice sorgente per facilitare il seguito degli sviluppatori.

## Passaggio 1: apertura del documento PDF

Per aprire il documento PDF utilizzando Aspose.PDF per .NET, attenersi alla seguente procedura:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

Nel codice sopra, sostituisci "YOUR DOCUMENT DIRECTORY" con il percorso della directory del tuo progetto.

## Passaggio 2: impostazione dell'opzione LinkDuplicateStreams

Per impostare l'opzione LinkDuplicateStreams, attenersi alla seguente procedura:

```csharp
// Imposta l'opzione LinkDuplcateStreams
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    LinkDuplcateStreams = true
};
```

Nel codice sopra, abbiamo creato una nuova istanza di OptimizationOptions e impostato l'opzione LinkDuplicateStreams su true.

## Passaggio 3: ottimizzazione del documento PDF

Per ottimizzare il documento PDF, attenersi alla seguente procedura:

```csharp
// Ottimizza il documento PDF utilizzando OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
```

Nel codice sopra, abbiamo usato il metodo OptimizeResources dell'oggetto pdfDocument per ottimizzare il documento PDF usando OptimizationOptions che abbiamo creato in precedenza.

## Passaggio 4: salvataggio del documento aggiornato

Per salvare il documento aggiornato, attenersi alla seguente procedura:

```csharp
dataDir = dataDir + "OptimizeDocument_out.pdf";
// Salva documento aggiornato
pdfDocument.Save(dataDir);
```

Nel codice precedente, abbiamo utilizzato il metodo Save dell'oggetto pdfDocument per salvare il documento aggiornato in un nuovo file denominato "OptimizeDocument_out.pdf" nella directory del progetto.

### Esempio di codice sorgente per collegare flussi duplicati utilizzando Aspose.PDF per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
// Imposta l'opzione LinkDuplcateStreams
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	LinkDuplcateStreams = true
};
// Ottimizza il documento PDF utilizzando OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "OptimizeDocument_out.pdf";
// Salva documento aggiornato
pdfDocument.Save(dataDir);
```
