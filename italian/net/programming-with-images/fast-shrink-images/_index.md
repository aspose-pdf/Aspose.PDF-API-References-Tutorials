---
title: Immagini a restringimento rapido
linktitle: Immagini a restringimento rapido
second_title: Aspose.PDF per riferimento API .NET
description: Riduci rapidamente le dimensioni delle immagini in un file PDF con Aspose.PDF per .NET.
type: docs
weight: 130
url: /it/net/programming-with-images/fast-shrink-images/
---

Questa guida ti guiderà passo dopo passo su come ridurre rapidamente le dimensioni delle immagini in un file PDF utilizzando Aspose.PDF per .NET. Assicurati di aver già configurato il tuo ambiente e procedi nel seguente modo:

## Passaggio 1: inizializzare l'ora

Prima di iniziare, inizializzeremo il tempo per misurare le prestazioni di compressione. Aggiungere il seguente codice per registrare l'ora di inizio:

```csharp
var time = DateTime.Now.Ticks;
```

## Passaggio 2: definire la directory dei documenti

 Assicurati di impostare la directory dei documenti corretta. Sostituire`"YOUR DOCUMENT DIRECTORY"` nel codice con il percorso della directory in cui si trova il documento PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 3: apri il documento PDF

 In questo passaggio, apriremo il documento PDF utilizzando il file`Document` classe di Aspose.PDF. Usa il`Document` costruttore e passare il percorso al documento PDF.

```csharp
Document pdfDocument = new Document(dataDir + "Shrinkimage.pdf");
```

## Passaggio 4: inizializza le opzioni di ottimizzazione

 In questo passaggio, inizializzeremo le opzioni di ottimizzazione per la compressione delle immagini. Crea un'istanza di`OptimizationOptions` e impostare le opzioni appropriate. In questo esempio, abilitiamo la compressione dell'immagine, impostiamo la qualità dell'immagine su 75 e utilizziamo la versione di compressione veloce.

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();
optimizeOptions.ImageCompressionOptions.CompressImages = true;
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;
optimizeOptions.ImageCompressionOptions.Version = Pdf.Optimization.ImageCompressionVersion.Fast;
```

## Passaggio 5: ottimizza il documento PDF

 In questo passaggio, ottimizzeremo il documento PDF utilizzando le opzioni di ottimizzazione definite in precedenza. Chiama il`OptimizeResources` metodo del`pdfDocument` oggetto e passare le opzioni di ottimizzazione.

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## Passaggio 6: salvare il documento PDF aggiornato

 Salva il documento PDF aggiornato utilizzando il file`Save` metodo del`pdfDocument` oggetto. Specificare il percorso di output per il file PDF.

```csharp
dataDir = dataDir + "FastShrinkImages_out.pdf";
pdfDocument.Save(dataDir);
```

### Esempio di codice sorgente per Fast Shrink Images utilizzando Aspose.PDF per .NET 
```csharp
// Inizializza l'ora
var time = DateTime.Now.Ticks;
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "Shrinkimage.pdf");
// Inizializza le opzioni di ottimizzazione
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();
// Imposta l'opzione CompressImages
optimizeOptions.ImageCompressionOptions.CompressImages = true;
// Imposta l'opzione Qualità immagine
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;
// Imposta la versione di compressione di Imagae su veloce
optimizeOptions.ImageCompressionOptions.Version = Pdf.Optimization.ImageCompressionVersion.Fast;
// Ottimizza il documento PDF utilizzando OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "FastShrinkImages_out.pdf";
// Salva documento aggiornato
pdfDocument.Save(dataDir);
Console.WriteLine("Ticks: {0}", DateTime.Now.Ticks - time);
Console.WriteLine("\nImage fast shrinked successfully.\nFile saved at " + dataDir);
```

## Conclusione

Congratulazioni! Hai rapidamente ridotto le dimensioni delle immagini in un PDF utilizzando Aspose.PDF per .NET. Il file PDF ottimizzato viene salvato nella directory specificata. Ora puoi utilizzare questo file PDF con immagini ridotte per esigenze di archiviazione o condivisione più efficienti.