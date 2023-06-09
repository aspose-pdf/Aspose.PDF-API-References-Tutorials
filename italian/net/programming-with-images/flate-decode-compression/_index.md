---
title: Flate Decodifica Compressione
linktitle: Flate Decodifica Compressione
second_title: Aspose.PDF per riferimento API .NET
description: Comprimi in modo efficiente le immagini in un PDF utilizzando la compressione Flate Decode con Aspose.PDF per .NET.
type: docs
weight: 140
url: /it/net/programming-with-images/flate-decode-compression/
---

Questa guida ti guiderà passo dopo passo su come comprimere le immagini utilizzando la compressione Flate Decode in un file PDF utilizzando Aspose.PDF per .NET. Assicurati di aver già configurato il tuo ambiente e procedi nel seguente modo:

## Passaggio 1: definire la directory dei documenti

 Assicurati di impostare la directory dei documenti corretta. Sostituire`"YOUR DOCUMENT DIRECTORY"` nel codice con il percorso della directory in cui si trova il documento PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: apri il documento PDF

 In questo passaggio, apriremo il documento PDF utilizzando il file`Document` classe di Aspose.PDF. Usa il`Document` costruttore e passare il percorso al documento PDF.

```csharp
Document doc = new Document(dataDir + "AddImage.pdf");
```

## Passaggio 3: Inizializza le opzioni di ottimizzazione

 In questo passaggio, inizializzeremo le opzioni di ottimizzazione per la compressione delle immagini. Crea un'istanza di`OptimizationOptions` e impostare le opzioni appropriate. In questo esempio, stiamo usando la compressione Flate Decode per ottimizzare le immagini.

```csharp
var optimizationOptions = new Aspose.Pdf.Optimization.OptimizationOptions();
optimizationOptions.ImageCompressionOptions.Encoding = ImageEncoding.Flate;
```

## Passaggio 4: ottimizza il documento PDF

 In questo passaggio, ottimizzeremo il documento PDF utilizzando le opzioni di ottimizzazione definite in precedenza. Chiama il`OptimizeResources` metodo del`doc` oggetto e passare le opzioni di ottimizzazione.

```csharp
doc.OptimizeResources(optimizationOptions);
```

## Passaggio 5: salvare il documento PDF aggiornato

 Salva il documento PDF aggiornato utilizzando il file`Save` metodo del`doc` oggetto. Specificare il percorso di output per il file PDF.

```csharp
doc.Save(dataDir + "FlateDecodeCompression.pdf");
```

### Esempio di codice sorgente per Flate Decode Compression utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document doc = new Document(dataDir + "AddImage.pdf");
// Inizializza le opzioni di ottimizzazione
var optimizationOptions = new Aspose.Pdf.Optimization.OptimizationOptions();
//Per ottimizzare l'immagine utilizzando FlateDecode Compression, impostare le opzioni di ottimizzazione su Flate
optimizationOptions.ImageCompressionOptions.Encoding = ImageEncoding.Flate;
// Imposta le opzioni di ottimizzazione
doc.OptimizeResources(optimizationOptions);
// Salva documento
doc.Save(dataDir + "FlateDecodeCompression.pdf");
```

## Conclusione

Congratulazioni! Hai compresso correttamente le immagini in un PDF utilizzando la compressione Flate Decode con Aspose.PDF per .NET. Il file PDF ottimizzato viene salvato nella directory specificata. Ora puoi utilizzare questo file PDF per esigenze di archiviazione o condivisione più efficienti.