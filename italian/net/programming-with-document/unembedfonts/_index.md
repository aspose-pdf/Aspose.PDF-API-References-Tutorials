---
title: Disincorpora i caratteri
linktitle: Disincorpora i caratteri
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come utilizzare Aspose.PDF per .NET per ottenere font Unembed e ottimizzare i file PDF. Una guida passo passo.
type: docs
weight: 370
url: /it/net/programming-with-document/unembedfonts/
---
Aspose.PDF per .NET è una potente libreria che offre un'ampia gamma di funzionalità per lavorare con i documenti PDF. Una delle sue caratteristiche è quella di ottenere caratteri non incorporati da un documento PDF. Ciò può essere utile se è necessario estrarre i caratteri da un documento PDF e utilizzarli in altre applicazioni.

forniremo una guida passo-passo per spiegare il seguente codice sorgente C# della funzionalità di estrazione dei caratteri incorporati di Aspose.PDF per .NET.

## Passaggio 1: impostare il percorso della directory dei documenti

Prima di iniziare, dobbiamo impostare il percorso della directory in cui si trova il nostro documento PDF. Memorizzeremo questo percorso in una variabile chiamata "dataDir".

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Sostituisci "YOUR DOCUMENT DIRECTORY" con il percorso effettivo della directory in cui si trova il tuo documento PDF.

## Passaggio 2: apri il documento PDF

Il primo passo è caricare il documento PDF che vuoi fare, usa il file`Document` classe di Aspose.PDF per .NET. Il seguente frammento di codice mostra come caricare il documento PDF:

```csharp
// Apri documento
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Passaggio 3: impostare l'opzione UnembedFonts

 Per ottenere caratteri non incorporati dal documento PDF, è necessario impostare l'estensione`UnembedFonts` opzione a`true` . Questa opzione è disponibile nel`OptimizationOptions` classe. Il seguente frammento di codice mostra come impostare il`UnembedFonts` opzione:

```csharp
// Imposta l'opzione UnembedFonts
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

## Passaggio 4: ottimizza il documento PDF

 Dopo aver impostato il`UnembedFonts` opzione, è possibile ottimizzare il documento PDF utilizzando l'`OptimizeResources` metodo del`Document` classe. Il seguente frammento di codice mostra come ottimizzare il documento PDF:

```csharp
// Ottimizza il documento PDF utilizzando OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
```

## Passaggio 5: salvare il documento aggiornato

 Una volta ottimizzato il documento PDF, è possibile salvare il documento aggiornato utilizzando il file`Save` metodo del`Document` classe. Il seguente frammento di codice mostra come salvare il documento aggiornato:

```csharp
// Salva documento aggiornato
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## Passaggio 6: ottieni la dimensione del file originale e ridotta

 Infine, puoi ottenere la dimensione del file originale e ridotta del documento PDF utilizzando il file`FileInfo`classe di System.IO. Il seguente frammento di codice mostra come ottenere la dimensione del file originale e ridotta:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

### Codice sorgente di esempio per ottenere caratteri non incorporati utilizzando Aspose.PDF per .NET

Ecco il codice sorgente di esempio completo per ottenere caratteri non incorporati da un documento PDF utilizzando Aspose.PDF per .NET:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
// Imposta l'opzione UnembedFonts
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
Console.WriteLine("Start");
// Ottimizza il documento PDF utilizzando OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
// Salva documento aggiornato
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Finished");
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```
