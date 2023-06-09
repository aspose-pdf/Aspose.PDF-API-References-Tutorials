---
title: Ridimensiona le immagini
linktitle: Ridimensiona le immagini
second_title: Aspose.PDF per riferimento API .NET
description: Guida passo passo per ridimensionare le immagini in un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 250
url: /it/net/programming-with-images/resize-images/
---

In questo tutorial, ti illustreremo come ridimensionare le immagini in un documento PDF utilizzando Aspose.PDF per .NET. Segui questi passaggi per eseguire facilmente questa operazione.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

- Visual Studio o qualsiasi altro ambiente di sviluppo installato e configurato.
- Conoscenza di base del linguaggio di programmazione C#.
- Libreria Aspose.PDF per .NET installata. Puoi scaricarlo dal sito ufficiale di Aspose.

## Passaggio 1: caricamento del documento PDF

Per iniziare, utilizza il seguente codice per caricare il documento PDF:

```csharp
// Inizializza l'ora
var time = DateTime.Now.Ticks;

string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Apri il documento
Document pdfDocument = new Document(dataDir + "ResizeImage.pdf");
```

Assicurati di fornire il percorso corretto al tuo documento PDF.

## Passaggio 2: inizializzazione delle opzioni di ottimizzazione

Prima di ridimensionare le immagini, dobbiamo inizializzare le opzioni di ottimizzazione. Usa il seguente codice:

```csharp
// Inizializza le opzioni di ottimizzazione
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();

// Attiva l'opzione CompressImages
optimizeOptions.ImageCompressionOptions.CompressImages = true;

// Imposta la qualità dell'immagine
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;

// Attiva l'opzione ResizeImages
optimizeOptions.ImageCompressionOptions.ResizeImages = true;

// Imposta la risoluzione massima
optimizeOptions.ImageCompressionOptions.MaxResolution = 300;
```

È possibile regolare le impostazioni di ottimizzazione in base alle proprie esigenze.

## Fase 3: Ottimizzazione del documento PDF

Ora ottimizzeremo il documento PDF utilizzando le opzioni di ottimizzazione che abbiamo definito. Usa il seguente codice:

```csharp
// Ottimizza il documento PDF utilizzando OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);

dataDir = dataDir + "ResizeImages_out.pdf";
// Salva il documento aggiornato
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage resized successfully.\nFile saved as: " + dataDir);
```

Assicurati di fornire il percorso e il nome file desiderati per il documento PDF aggiornato.

### Esempio di codice sorgente per ridimensionare le immagini utilizzando Aspose.PDF per .NET 
```csharp
// Inizializza l'ora
var time = DateTime.Now.Ticks;
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "ResizeImage.pdf");
// Inizializza le opzioni di ottimizzazione
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();            
// Imposta l'opzione CompressImages
optimizeOptions.ImageCompressionOptions.CompressImages = true;            
// Imposta l'opzione Qualità immagine
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;            
// Imposta l'opzione Ridimensiona immagine
optimizeOptions.ImageCompressionOptions.ResizeImages = true;            
// Imposta l'opzione MaxResolution
optimizeOptions.ImageCompressionOptions.MaxResolution = 300;
// Ottimizza il documento PDF utilizzando OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "ResizeImages_out.pdf";
// Salva documento aggiornato
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage resized successfully.\nFile saved at " + dataDir);
```

## Conclusione

Congratulazioni! Hai ridimensionato correttamente le immagini in un documento PDF utilizzando Aspose.PDF per .NET. Ora puoi applicare questo metodo ai tuoi progetti per modificare la dimensione delle immagini nei file PDF.