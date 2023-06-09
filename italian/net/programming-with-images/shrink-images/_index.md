---
title: Riduci immagini
linktitle: Riduci immagini
second_title: Aspose.PDF per riferimento API .NET
description: Guida dettagliata per ridurre le dimensioni delle immagini in un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 280
url: /it/net/programming-with-images/shrink-images/
---

In questo tutorial, ti diremo come ridurre le dimensioni delle immagini in un documento PDF utilizzando Aspose.PDF per .NET. Segui questi passaggi per eseguire facilmente questa operazione.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

- Visual Studio o qualsiasi altro ambiente di sviluppo installato e configurato.
- Conoscenza di base del linguaggio di programmazione C#.
- Libreria Aspose.PDF per .NET installata. Puoi scaricarlo dal sito ufficiale di Aspose.

## Passaggio 1: caricamento del documento PDF

Per iniziare, utilizza il seguente codice per caricare il documento PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Apri il documento
Document pdfDocument = new Document(dataDir + "Shrinkimage.pdf");
```

Assicurati di fornire il percorso corretto al tuo documento PDF.

## Passaggio 2: inizializzazione delle opzioni di ottimizzazione

Successivamente, inizializzeremo le opzioni di ottimizzazione per ridurre le dimensioni delle immagini. Usa il seguente codice:

```csharp
// Inizializza le opzioni di ottimizzazione
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();

// Attiva l'opzione CompressImages
optimizeOptions.ImageCompressionOptions.CompressImages = true;

// Imposta la qualità dell'immagine
optimizeOptions.ImageCompressionOptions.ImageQuality = 50;
```

È possibile regolare le impostazioni di ottimizzazione in base alle proprie esigenze.

## Fase 3: Ottimizzazione del documento PDF

Ora ottimizzeremo il documento PDF riducendo le dimensioni delle immagini. Usa il seguente codice:

```csharp
// Ottimizza il documento PDF utilizzando OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);

dataDir = dataDir + "Shrinkimage_out.pdf";
// Salva il documento aggiornato
pdfDocument.Save(dataDir);
Console.WriteLine("\nImages successfully reduced.\nFile saved as: " + dataDir);
```

Assicurati di fornire il percorso e il nome file desiderati per il documento PDF aggiornato.

### Esempio di codice sorgente per Shrink Images utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "Shrinkimage.pdf");
// Inizializza le opzioni di ottimizzazione
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();
// Imposta l'opzione CompressImages
optimizeOptions.ImageCompressionOptions.CompressImages = true;
// Imposta l'opzione Qualità immagine
optimizeOptions.ImageCompressionOptions.ImageQuality = 50;
// Ottimizza il documento PDF utilizzando OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "Shrinkimage_out.pdf";
// Salva documento aggiornato
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage shrinked successfully.\nFile saved at " + dataDir);
```

## Conclusione

Congratulazioni! Hai ridotto con successo la dimensione delle immagini in un documento PDF utilizzando Aspose.PDF per .NET. Ora puoi applicare questo metodo ai tuoi progetti per ottimizzare la dimensione delle immagini nei file PDF.