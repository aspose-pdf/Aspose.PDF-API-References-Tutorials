---
title: Ottimizza la dimensione del file
linktitle: Ottimizza la dimensione del file
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come ottimizzare la dimensione del file dei tuoi documenti PDF con Aspose.PDF per .NET utilizzando questa guida passo-passo.
type: docs
weight: 250
url: /it/net/programming-with-document/optimizefilesize/
---
Aspose.PDF per .NET è una libreria che consente agli sviluppatori di creare, modificare e manipolare file PDF nelle loro applicazioni .NET. Una delle funzionalità più utili di questa libreria è la capacità di ottimizzare le dimensioni del file di un documento PDF. In questo articolo, forniremo una guida passo passo per ottimizzare la dimensione del file di un documento PDF utilizzando Aspose.PDF per .NET.

## Passaggio 1: caricare il documento PDF

 Il primo passaggio per ottimizzare le dimensioni del file di un documento PDF consiste nel caricare il documento nell'applicazione. Puoi farlo usando il`Document`classe fornita dalla libreria Aspose.PDF per .NET. Ecco un esempio di come caricare un documento PDF:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Apri documento
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

 Assicurati di sostituire`YOUR DOCUMENT DIRECTORY` con il percorso della directory contenente il documento PDF.

## Passaggio 2: impostare le opzioni di ottimizzazione

 Dopo aver caricato il documento PDF, puoi impostare le opzioni di ottimizzazione per specificare quali parti del documento desideri ottimizzare. IL`OptimizationOptions` La classe fornita dalla libreria Aspose.PDF per .NET consente di specificare una varietà di opzioni per ottimizzare la dimensione del file del documento PDF. Ecco un esempio di come impostare alcune opzioni di ottimizzazione:

```csharp
OptimizationOptions optimizationOptions = new OptimizationOptions();
optimizationOptions.LinkDuplcateStreams = true;
optimizationOptions.RemoveUnusedObjects = true;
optimizationOptions.RemoveUnusedStreams = true;
optimizationOptions.ImageCompressionOptions.CompressImages = true;
optimizationOptions.ImageCompressionOptions.ImageQuality = 10;
```

In questo esempio, stiamo impostando le seguenti opzioni:
- `LinkDuplcateStreams`: questa opzione consente la rimozione di flussi duplicati nel documento PDF, che può aiutare a ridurre le dimensioni del file.
- `RemoveUnusedObjects`: Questa opzione consente la rimozione di qualsiasi oggetto inutilizzato nel documento PDF, che può anche aiutare a ridurre le dimensioni del file.
- `RemoveUnusedStreams`questa opzione consente la rimozione di eventuali flussi inutilizzati nel documento PDF, che possono ridurre ulteriormente le dimensioni del file.
- `CompressImages`: questa opzione abilita la compressione delle immagini nel documento PDF, che può ridurre notevolmente le dimensioni del file.
- `ImageQuality`: Questa opzione imposta la qualità delle immagini compresse. Un'impostazione di qualità inferiore risulterà in una dimensione del file inferiore, ma potrebbe anche comportare un'immagine di qualità inferiore.

## Passaggio 4: ottimizza il documento PDF

 Ora che hai impostato le opzioni di ottimizzazione, puoi ottimizzare il documento PDF utilizzando il file`OptimizeResources` metodo fornito dal`Document` classe. Ecco un esempio di come ottimizzare il documento PDF:

```csharp
// Ottimizza la dimensione del file rimuovendo gli oggetti inutilizzati
pdfDocument.OptimizeResources(optimizationOptions);
```

## Passaggio 5: salvare il documento PDF ottimizzato

Dopo aver ottimizzato il documento PDF, puoi salvare la versione ottimizzata in un nuovo file. Ecco un esempio di come salvare il documento PDF ottimizzato:

```csharp
dataDir = dataDir + "OptimizeFileSize_out.pdf";
// Salva documento di output
pdfDocument.Save(dataDir);
```

### Esempio di codice sorgente per ottimizzare la dimensione del file utilizzando Aspose.PDF per .NET

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Apri documento
	Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");

	OptimizationOptions optimizationOptions = new OptimizationOptions();
	optimizationOptions.LinkDuplcateStreams = true;
	optimizationOptions.RemoveUnusedObjects = true;
	optimizationOptions.RemoveUnusedStreams = true;
	optimizationOptions.ImageCompressionOptions.CompressImages = true;
	optimizationOptions.ImageCompressionOptions.ImageQuality = 10;
	// Ottimizza la dimensione del file rimuovendo gli oggetti inutilizzati
	pdfDocument.OptimizeResources(optimizationOptions);
	dataDir = dataDir + "OptimizeFileSize_out.pdf";
	// Salva documento di output
	pdfDocument.Save(dataDir);

```
