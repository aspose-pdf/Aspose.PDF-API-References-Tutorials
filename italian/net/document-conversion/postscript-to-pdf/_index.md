---
title: Post scriptum in PDF
linktitle: Post scriptum in PDF
second_title: Aspose.PDF per riferimento API .NET
description: Guida passo passo per convertire PostScript in PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 230
url: /it/net/document-conversion/postscript-to-pdf/
---

In questo tutorial, ti guideremo attraverso il processo di conversione di un file PostScript (PS) in formato PDF utilizzando Aspose.PDF per .NET. Il formato PostScript è un linguaggio di descrizione della pagina utilizzato per descrivere l'aspetto grafico dei documenti. Seguendo i passaggi seguenti, sarai in grado di convertire un file PostScript in formato PDF.

## Prerequisiti
Prima di iniziare, assicurati di soddisfare i seguenti prerequisiti:

- Conoscenza base del linguaggio di programmazione C#.
- Libreria Aspose.PDF per .NET installata sul tuo sistema.
- Un ambiente di sviluppo come Visual Studio.

## Passaggio 1: caricamento del documento PostScript
In questo passaggio caricheremo il file PostScript di origine utilizzando Aspose.PDF per .NET. Segui il codice qui sotto:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Crea una nuova istanza di PsLoadOptions
LoadOptions options = new PsLoadOptions();

// Apri il documento .ps con le opzioni di caricamento create
Document pdfDocument = new Document(dataDir + "input.ps", options);
```

 Assicurati di sostituire`"YOUR DOCUMENTS DIRECTORY"` con la directory effettiva in cui si trova il file PostScript.

## Passaggio 2: salvare il file PDF risultante
Infine, salveremo il file PostScript convertito in PDF. Usa il seguente codice:

```csharp
// Salva il documento
pdfDocument.Save(dataDir + "PSToPDF.pdf");
```

 Il codice precedente salva il file PostScript convertito in formato PDF con il nome del file`"PSToPDF.pdf"`.

### Esempio di codice sorgente per Postscript in PDF utilizzando Aspose.Words per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crea una nuova istanza di PsLoadOptions
LoadOptions options = new PsLoadOptions();
//Apri il documento .ps con le opzioni di caricamento create
Document pdfDocument = new Document(dataDir + "input.ps", options);
// Salva documento
pdfDocument.Save(dataDir + "PSToPDF.pdf");
```

## Conclusione
In questo tutorial, abbiamo coperto il processo passo-passo di conversione di un file PostScript in formato PDF utilizzando Aspose.PDF per .NET. Seguendo le istruzioni sopra descritte, ora dovresti essere in grado di convertire un file PostScript in formato PDF. Questa funzione è utile quando si desidera convertire i file PostScript in formato PDF per un uso più comune e una migliore compatibilità.