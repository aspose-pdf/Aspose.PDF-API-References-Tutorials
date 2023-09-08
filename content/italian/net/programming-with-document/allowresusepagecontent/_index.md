---
title: Consenti riutilizzo del contenuto della pagina
linktitle: Consenti riutilizzo del contenuto della pagina
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come ottimizzare i PDF abilitando la funzione "Consenti riutilizzo contenuto pagina" utilizzando Aspose.PDF per .NET. Riduci le dimensioni del file e migliora le prestazioni.
type: docs
weight: 50
url: /it/net/programming-with-document/allowresusepagecontent/
---
In questo tutorial, spiegheremo come abilitare la funzione "Consenti riutilizzo contenuto pagina" utilizzando Aspose.PDF per .NET. Questa funzionalità ottimizza il documento PDF riutilizzando il contenuto della pagina, riducendo le dimensioni del file e migliorando le prestazioni. Segui la guida passo passo di seguito:

## Passaggio 1: carica il documento PDF

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Passaggio 2: imposta l'opzione ConsentiReusePageContent

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    AllowReusePageContent = true
};
```

## Passaggio 3: ottimizza il documento PDF

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## Passaggio 4: salva il documento aggiornato

```csharp
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## Passaggio 5: controlla la riduzione delle dimensioni del file

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

Congratulazioni! Hai consentito con successo il riutilizzo del contenuto della pagina nel tuo documento PDF.

### Codice sorgente di esempio per consentire il riutilizzo del contenuto della pagina utilizzando Aspose.PDF per .NET:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Apri documento
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");

// Imposta l'opzione ConsentiReusePageContent
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    AllowReusePageContent = true
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

Console.WriteLine("\nAllowed reuse of page content successfully.\nFile saved at " + dataDir);
```

Ora puoi ottimizzare in modo efficace i tuoi documenti PDF consentendo il riutilizzo del contenuto della pagina.

## Conclusione

In questo tutorial, abbiamo spiegato come abilitare la funzione "Consenti riutilizzo contenuto pagina" utilizzando Aspose.PDF per .NET. Seguendo la guida passo passo fornita e utilizzando il codice sorgente C#, puoi ottimizzare in modo efficace i tuoi documenti PDF consentendo il riutilizzo del contenuto della pagina. Questa ottimizzazione si traduce in file PDF più piccoli, che possono portare a tempi di caricamento più rapidi e prestazioni migliorate quando si gestiscono documenti PDF di grandi dimensioni. Aspose.PDF per .NET fornisce una soluzione robusta e intuitiva per l'ottimizzazione dei PDF, consentendo di creare facilmente file PDF efficienti e di alta qualità.

### Domande frequenti

#### D: Qual è lo scopo di abilitare la funzione "Consenti riutilizzo contenuto pagina" in un documento PDF?

R: L'attivazione della funzione "Consenti riutilizzo del contenuto della pagina" in un documento PDF ottimizza il file riutilizzando il contenuto della pagina, riducendo le dimensioni del file e migliorando le prestazioni generali. Questa ottimizzazione si traduce in file PDF più piccoli senza compromettere la qualità del contenuto.

#### D: Come funziona la funzione "Consenti riutilizzo del contenuto della pagina"?

R: Quando la funzione "Consenti riutilizzo contenuto pagina" è abilitata, gli oggetti di pagina identici all'interno del documento PDF vengono condivisi e riutilizzati, invece di essere duplicati per ogni occorrenza. Questa condivisione del contenuto della pagina riduce significativamente la dimensione complessiva del file.

#### D: Posso annullare l'ottimizzazione e ripristinare il documento originale?

R: No, una volta eseguita l'ottimizzazione con "Consenti riutilizzo contenuto pagina" e salvato il documento PDF, le modifiche sono permanenti. Si consiglia di conservare un backup del documento originale prima di eseguire qualsiasi ottimizzazione.

#### D: L'attivazione di questa funzionalità influirà sull'aspetto visivo o sul contenuto del documento PDF?

R: L'attivazione della funzione "Consenti riutilizzo contenuto pagina" non influisce sull'aspetto visivo o sul contenuto del documento PDF. Ottimizza esclusivamente la struttura interna del file per ridurre la ridondanza e migliorare l'efficienza.

#### D: Aspose.PDF per .NET è una soluzione affidabile per l'ottimizzazione e la manipolazione dei PDF?

R: Sì, Aspose.PDF per .NET è una libreria affidabile e ricca di funzionalità per l'ottimizzazione e la manipolazione dei PDF. Offre ampie opzioni per ottimizzare i file PDF, inclusa la riduzione delle dimensioni del file, la rimozione delle risorse inutilizzate e il miglioramento delle prestazioni generali.