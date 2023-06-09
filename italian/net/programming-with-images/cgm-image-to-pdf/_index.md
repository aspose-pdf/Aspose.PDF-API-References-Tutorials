---
title: Immagine CGM in PDF
linktitle: Immagine CGM in PDF
second_title: Aspose.PDF per riferimento API .NET
description: Converti facilmente l'immagine CGM in PDF con Aspose.PDF per .NET.
type: docs
weight: 40
url: /it/net/programming-with-images/cgm-image-to-pdf/
---

Questa guida dettagliata spiega come convertire un'immagine CGM in PDF utilizzando Aspose.PDF per .NET. Assicurati di aver già configurato il tuo ambiente e procedi nel seguente modo:

## Passaggio 1: definire la directory dei documenti

 Prima di iniziare, assicurati di impostare la directory corretta per i documenti. Sostituire`"YOUR DOCUMENT DIRECTORY"` nel codice con il percorso della directory in cui si trova il file CGM.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: definire il file di input e output

 Impostare il nome del file di input CGM e il nome del file di output PDF. Sostituire`"corvette.cgm"` con il nome del tuo file CGM e aggiorna`dataDir`con la directory di output desiderata e il nome del file PDF.

```csharp
string inputFile = dataDir + "corvette.cgm";
dataDir = dataDir + "CGMImageToPDF_out.pdf";
```

## Passaggio 3: converti l'immagine CGM in PDF

 Usa il`Produce` metodo di`PdfProducer` per convertire il file CGM in formato PDF utilizzando`ImportFormat.Cgm`. Specificare il file di input CGM e il file di output PDF.

```csharp
PdfProducer.Produce(inputFile, ImportFormat.Cgm, dataDir);
```

### Esempio di codice sorgente per CGMImage in PDF utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inputFile = dataDir + "corvette.cgm";
dataDir = dataDir + "CGMImageToPDF_out.pdf";
// Salva CGM in formato PDF
PdfProducer.Produce(inputFile, ImportFormat.Cgm, dataDir);
Console.WriteLine("\nCGM file converted to pdf successfully.\nFile saved at " + dataDir); 
```

## Conclusione

Congratulazioni! Hai convertito con successo un file CGM in PDF utilizzando Aspose.PDF per .NET. Ora puoi utilizzare il file PDF generato nei tuoi progetti o applicazioni.