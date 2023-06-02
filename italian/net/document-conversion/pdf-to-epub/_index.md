---
title: Da PDF a EPUB
linktitle: Da PDF a EPUB
second_title: Aspose.PDF per riferimento API .NET
description: Guida passo passo per convertire PDF in EPUB utilizzando Aspose.PDF per .NET.
type: docs
weight: 120
url: /it/net/document-conversion/pdf-to-epub/
---

In questo tutorial, ti guideremo attraverso il processo di conversione di un file PDF in formato EPUB utilizzando Aspose.PDF per .NET. Il formato PDF è comunemente utilizzato per visualizzare i documenti, mentre il formato EPUB è appositamente progettato per gli e-book. Seguendo i passaggi seguenti, sarai in grado di convertire i file PDF in formato EPUB.

## Prerequisiti
Prima di iniziare, assicurati di soddisfare i seguenti prerequisiti:

- Conoscenza base del linguaggio di programmazione C#.
- Libreria Aspose.PDF per .NET installata sul tuo sistema.
- Un ambiente di sviluppo come Visual Studio.

## Passaggio 1: caricamento del documento PDF
In questo passaggio, caricheremo il file PDF utilizzando Aspose.PDF per .NET. Segui il codice qui sotto:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Carica il documento PDF
Document pdfDocument = new Document(dataDir + "PDFToEPUB.pdf");
```

 Assicurati di sostituire`"YOUR DOCUMENTS DIRECTORY"` con la directory effettiva in cui si trova il file PDF.

## Passaggio 2: creazione di un'istanza delle opzioni di salvataggio di EPUB
Dopo aver caricato il documento PDF, creeremo un'istanza delle opzioni di salvataggio per il formato EPUB. Usa il seguente codice:

```csharp
// Crea un'istanza delle opzioni di backup EPUB
EpubSaveOptions options = new EpubSaveOptions();
```

## Passaggio 3: Specifica del layout del contenuto
Ora specificheremo il layout dei contenuti del libro EPUB. Usa il seguente codice:

```csharp
// Specifica del layout per i contenuti
options.ContentRecognitionMode = EpubSaveOptions.RecognitionMode.Flow;
```

## Passaggio 4: salvare il documento EPUB
Dopo aver configurato le opzioni di salvataggio, ora possiamo salvare il file EPUB risultante. Ecco l'ultimo passo:

```csharp
// Salva il documento EPUB
pdfDocument.Save(dataDir + "PDFToEPUB_out.epub", options);
```

 Sostituire`"YOUR DOCUMENTS DIRECTORY"` con la directory desiderata in cui si desidera salvare il file EPUB di output.

### Esempio di codice sorgente per PDF in EPUB utilizzando Aspose.Words per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Carica documento PDF
Document pdfDocument = new Document(dataDir + "PDFToEPUB.pdf");

// Opzioni di salvataggio di un'istanza di Epub
EpubSaveOptions options = new EpubSaveOptions();

// Specificare il layout per i contenuti
options.ContentRecognitionMode = EpubSaveOptions.RecognitionMode.Flow;

// Salva il documento ePUB
pdfDocument.Save(dataDir + "PDFToEPUB_out.epub", options);
```

## Conclusione
In questo tutorial, abbiamo coperto il processo passo-passo di conversione di un file PDF in formato EPUB utilizzando Aspose.PDF per .NET. Seguendo le istruzioni sopra, puoi convertire facilmente i file PDF in formato EPUB. Questa funzione è particolarmente utile per convertire documenti PDF in e-book leggibili su diversi dispositivi.