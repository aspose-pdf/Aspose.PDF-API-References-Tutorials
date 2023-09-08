---
title: Elimina i caratteri e ottimizza i file PDF
linktitle: Elimina i caratteri e ottimizza i file PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come utilizzare Aspose.PDF per .NET per ottenere caratteri non incorporati e ottimizzare i file PDF. Una guida passo passo.
type: docs
weight: 370
url: /it/net/programming-with-document/unembedfonts/
---
Aspose.PDF per .NET è una potente libreria che fornisce un'ampia gamma di funzionalità per lavorare con documenti PDF. Una delle sue funzionalità è ottenere caratteri non incorporati da un documento PDF. Questo può essere utile se devi estrarre caratteri da un documento PDF e utilizzarli in altre applicazioni.

forniremo una guida passo passo per spiegare il seguente codice sorgente C# della funzionalità di acquisizione dei caratteri non incorporati di Aspose.PDF per .NET.

## Passaggio 1: impostare il percorso della directory dei documenti

Prima di iniziare, dobbiamo impostare il percorso della directory in cui si trova il nostro documento PDF. Memorizzeremo questo percorso in una variabile chiamata "dataDir".

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Sostituisci "LA TUA DIRECTORY DOCUMENTI" con il percorso effettivo della directory in cui si trova il tuo documento PDF.

## Passaggio 2: apri il documento PDF

 Il primo passo è caricare il documento PDF che desideri, utilizzare il file`Document` classe di Aspose.PDF per .NET. Il seguente frammento di codice mostra come caricare il documento PDF:

```csharp
// Apri documento
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Passaggio 3: imposta l'opzione UnembedFonts

 Per ottenere caratteri non incorporati dal documento PDF, è necessario impostare il file`UnembedFonts` opzione a`true` . Questa opzione è disponibile in`OptimizationOptions` classe. Il seguente frammento di codice mostra come impostare il file`UnembedFonts` opzione:

```csharp
// Imposta l'opzione UnembedFonts
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

## Passaggio 4: ottimizza il documento PDF

 Dopo aver impostato il`UnembedFonts` opzione, puoi ottimizzare il documento PDF utilizzando l'opzione`OptimizeResources` metodo del`Document` classe. Il seguente frammento di codice mostra come ottimizzare il documento PDF:

```csharp
// Ottimizza il documento PDF utilizzando le opzioni di ottimizzazione
pdfDocument.OptimizeResources(optimizeOptions);
```

## Passaggio 5: salva il documento aggiornato

 Una volta ottimizzato il documento PDF, puoi salvare il documento aggiornato utilizzando il file`Save` metodo del`Document`classe. Il seguente frammento di codice mostra come salvare il documento aggiornato:

```csharp
// Salva documento aggiornato
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## Passaggio 6: ottieni la dimensione del file originale e ridotta

 Infine, puoi ottenere la dimensione del file originale e ridotta del documento PDF utilizzando il file`FileInfo` classe di System.IO. Il seguente frammento di codice mostra come ottenere la dimensione del file originale e ridotta:

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
// Ottimizza il documento PDF utilizzando le opzioni di ottimizzazione
pdfDocument.OptimizeResources(optimizeOptions);
// Salva documento aggiornato
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Finished");
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

## Conclusione

In questo tutorial, abbiamo dimostrato come utilizzare Aspose.PDF per .NET per ottenere caratteri non incorporati da un documento PDF. Seguendo la guida passo passo, puoi facilmente implementare questa funzionalità nelle tue applicazioni C#. L'eliminazione dell'incorporamento dei caratteri può essere vantaggiosa quando è necessario lavorare separatamente con i caratteri estratti o garantire un utilizzo coerente dei caratteri su varie piattaforme.

## Domande frequenti

#### D: Qual è lo scopo di rimuovere i caratteri da un documento PDF?

R: L'annullamento dell'incorporamento dei caratteri da un documento PDF consente di estrarre i caratteri incorporati e utilizzarli in altre applicazioni. Ciò può essere utile per garantire un rendering coerente dei caratteri e preservare l'aspetto visivo del documento.

#### D: Come posso specificare il percorso della directory dei documenti nel codice C#?

 R: Per specificare il percorso della directory dei documenti, sostituire`"YOUR DOCUMENT DIRECTORY"` nel codice con il percorso effettivo della directory in cui si trova il documento PDF.

####  D: Cosa significa`UnembedFonts` option do, and where is it set?

 R: Il`UnembedFonts` opzione, disponibile in`OptimizationOptions` classe, abilita o disabilita l'incorporamento dei caratteri dal documento PDF. Per impostare questa opzione su`true`, utilizzare il seguente codice:

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

#### D: Posso annullare le modifiche apportate durante il processo di ottimizzazione?

R: Aspose.PDF per .NET non apporta modifiche permanenti al documento PDF originale durante l'ottimizzazione. Il processo di ottimizzazione viene eseguito su una copia del documento, lasciando intatto l'originale.

#### D: Come posso verificare la dimensione del file originale e ridotta dopo l'ottimizzazione?

R: Puoi usare il`FileInfo` classe di`System.IO` per ottenere la dimensione del file originale e ridotta. Ecco uno snippet di codice di esempio per raggiungere questo obiettivo:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```