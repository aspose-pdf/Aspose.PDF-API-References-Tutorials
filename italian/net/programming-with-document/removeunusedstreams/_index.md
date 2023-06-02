---
title: Rimuovi flussi inutilizzati
linktitle: Rimuovi flussi inutilizzati
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come rimuovere i flussi inutilizzati dai file PDF utilizzando Aspose.PDF per .NET. La nostra guida passo dopo passo.
type: docs
weight: 270
url: /it/net/programming-with-document/removeunusedstreams/
---
In questo esempio, discuteremo come rimuovere i flussi inutilizzati dai documenti PDF utilizzando Aspose.PDF per .NET. Forniremo una guida dettagliata su come eseguire questa operazione, incluso il codice sorgente completo con le spiegazioni.

## Passaggio 1: il percorso della directory dei documenti

La prima riga del codice imposta il percorso della directory in cui si trova il documento PDF. Assicurati di sostituire "YOUR DOCUMENT DIRECTORY" con il percorso effettivo della directory.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: apri il documento

La riga di codice successiva apre il documento PDF utilizzando la libreria Aspose.PDF per .NET.

```csharp
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Passaggio 3: impostare l'opzione RemoveUnusedStreams

Il passaggio successivo consiste nell'impostare l'opzione RemoveUnusedStreams su true. Questo rimuoverà tutti i flussi inutilizzati dal documento PDF.

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	RemoveUnusedStreams = true
};
```

## Passaggio 4: ottimizza il documento PDF utilizzando OptimizationOptions

Ora che abbiamo impostato le opzioni di ottimizzazione, possiamo ottimizzare il documento PDF utilizzando la seguente riga di codice.

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## Passaggio 5: salva il documento aggiornato

Infine, possiamo salvare il documento aggiornato utilizzando il metodo Save della classe Document.

```csharp
dataDir = dataDir + "OptimizeDocument_out.pdf";
pdfDocument.Save(dataDir);
```

### Esempio di codice sorgente per Rimuovi flussi inutilizzati utilizzando Aspose.PDF per .NET

Di seguito è riportato il codice sorgente di esempio per la rimozione di flussi inutilizzati utilizzando Aspose.PDF per .NET.

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
// Imposta l'opzione RemoveUsedStreams
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	RemoveUnusedStreams = true
};
// Ottimizza il documento PDF utilizzando OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "OptimizeDocument_out.pdf";
// Salva documento aggiornato
pdfDocument.Save(dataDir);
```
