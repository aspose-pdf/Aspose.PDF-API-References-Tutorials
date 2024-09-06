---
title: Disincorpora i font e ottimizza i file PDF
linktitle: Disincorpora i font e ottimizza i file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come usare Aspose.PDF per .NET per ottenere font Unembed e ottimizzare i file PDF. Una guida passo-passo.
type: docs
weight: 370
url: /it/net/programming-with-document/unembedfonts/
---
Aspose.PDF per .NET è una potente libreria che fornisce un'ampia gamma di funzionalità per lavorare con documenti PDF. Una delle sue funzionalità è quella di ottenere font non incorporati da un documento PDF. Ciò può essere utile se hai bisogno di estrarre font da un documento PDF e usarli in altre applicazioni.

forniremo una guida passo passo per spiegare il seguente codice sorgente C# della funzionalità di estrazione dei font incorporati di Aspose.PDF per .NET.

## Passaggio 1: impostare il percorso della directory del documento

Prima di iniziare, dobbiamo impostare il percorso della directory in cui si trova il nostro documento PDF. Memorizzeremo questo percorso in una variabile chiamata "dataDir".

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Sostituisci "DIRECTORY DEI TUOI DOCUMENTI" con il percorso effettivo della directory in cui si trova il tuo documento PDF.

## Passaggio 2: aprire il documento PDF

 Il primo passo è caricare il documento PDF che si desidera fare, utilizzare il`Document` classe di Aspose.PDF per .NET. Il seguente frammento di codice mostra come caricare il documento PDF:

```csharp
// Apri documento
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Passaggio 3: impostare l'opzione UnembedFonts

 Per ottenere i font non incorporati dal documento PDF, è necessario impostare`UnembedFonts` opzione per`true` Questa opzione è disponibile in`OptimizationOptions` classe. Il seguente frammento di codice mostra come impostare la`UnembedFonts` opzione:

```csharp
// Imposta l'opzione UnembedFonts
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

## Passaggio 4: Ottimizza il documento PDF

 Dopo aver impostato il`UnembedFonts` opzione, puoi ottimizzare il documento PDF utilizzando l'`OptimizeResources` metodo del`Document` classe. Il seguente frammento di codice mostra come ottimizzare il documento PDF:

```csharp
// Ottimizza il documento PDF utilizzando OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
```

## Passaggio 5: Salvare il documento aggiornato

 Una volta ottimizzato il documento PDF, è possibile salvare il documento aggiornato utilizzando`Save` metodo del`Document`classe. Il seguente frammento di codice mostra come salvare il documento aggiornato:

```csharp
// Salva il documento aggiornato
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## Passaggio 6: Ottieni la dimensione originale e ridotta del file

 Infine, è possibile ottenere la dimensione originale e ridotta del file del documento PDF utilizzando`FileInfo` classe di System.IO. Il seguente frammento di codice mostra come ottenere la dimensione originale e ridotta del file:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

### Esempio di codice sorgente per ottenere font non incorporati utilizzando Aspose.PDF per .NET

Ecco il codice sorgente di esempio completo per ottenere font non incorporati da un documento PDF utilizzando Aspose.PDF per .NET:

```csharp
// Percorso verso la directory dei documenti.
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
// Salva il documento aggiornato
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Finished");
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

## Conclusione

In questo tutorial, abbiamo dimostrato come usare Aspose.PDF per .NET per ottenere font non incorporati da un documento PDF. Seguendo la guida passo passo, puoi implementare facilmente questa funzionalità nelle tue applicazioni C#. L'unembedding dei font può essere vantaggioso quando devi lavorare con i font estratti separatamente o garantire un utilizzo coerente dei font su diverse piattaforme.

## Domande frequenti

#### D: Qual è lo scopo di estrarre i font da un documento PDF?

R: L'estrazione dei font da un documento PDF consente di estrarre i font incorporati e di utilizzarli in altre applicazioni. Ciò può essere utile per garantire un rendering coerente dei font e preservare l'aspetto visivo del documento.

#### D: Come faccio a specificare il percorso della directory del documento nel codice C#?

 A: Per specificare il percorso alla directory del documento, sostituire`"YOUR DOCUMENT DIRECTORY"` nel codice con il percorso effettivo della directory in cui si trova il documento PDF.

####  D: Cosa significa?`UnembedFonts` option do, and where is it set?

 A: Il`UnembedFonts` opzione, disponibile in`OptimizationOptions` classe, abilita o disabilita l'unembedding dei font dal documento PDF. Per impostare questa opzione su`true`, utilizzare il seguente codice:

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

#### D: Posso annullare le modifiche apportate durante il processo di ottimizzazione?

R: Aspose.PDF per .NET non apporta modifiche permanenti al documento PDF originale durante l'ottimizzazione. Il processo di ottimizzazione viene eseguito su una copia del documento, lasciando intatto l'originale.

#### D: Come posso controllare le dimensioni originali e ridotte del file dopo l'ottimizzazione?

 A: Puoi usare il`FileInfo` classe di`System.IO` per ottenere la dimensione originale e quella ridotta del file. Ecco un frammento di codice di esempio per ottenere questo risultato:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```