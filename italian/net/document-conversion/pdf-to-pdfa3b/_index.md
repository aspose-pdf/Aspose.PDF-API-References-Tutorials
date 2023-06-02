---
title: Da PDF a PDFA3b
linktitle: Da PDF a PDFA3b
second_title: Aspose.PDF per riferimento API .NET
description: Guida passo passo per convertire PDF in PDF/A-3b utilizzando Aspose.PDF per .NET.
type: docs
weight: 150
url: /it/net/document-conversion/pdf-to-pdfa3b/
---

In questo tutorial, ti guideremo attraverso il processo di conversione di un file PDF in formato PDF/A-3b utilizzando Aspose.PDF per .NET. PDF/A-3b è uno standard ISO per incorporare file e dati in un documento PDF. Seguendo i passaggi seguenti, sarai in grado di convertire i file PDF in formato PDF/A-3b.

## Prerequisiti
Prima di iniziare, assicurati di soddisfare i seguenti prerequisiti:

- Conoscenza base del linguaggio di programmazione C#.
- Libreria Aspose.PDF per .NET installata sul tuo sistema.
- Un ambiente di sviluppo come Visual Studio.

## Passaggio 1: apertura del documento PDF di origine
In questo passaggio, apriremo il file PDF di origine utilizzando Aspose.PDF per .NET. Segui il codice qui sotto:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Apri il documento PDF di origine
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 Assicurati di sostituire`"YOUR DOCUMENTS DIRECTORY"` con la directory effettiva in cui si trova il file PDF.

## Passaggio 2: convertire in PDF/A-3b
Dopo aver aperto il file PDF, possiamo procedere con la conversione in formato PDF/A-3b. Usa il seguente codice:

```csharp
// Converti in formato PDF/A-3b
pdfDocument.Convert(new MemoryStream(), PdfFormat.PDF_A_3B, ConvertErrorAction.Delete);
```

Il codice precedente converte il file PDF in formato PDF/A-3b e rimuove eventuali errori di conversione.

## Passaggio 3: salvare il file PDF/A-3b risultante
Al termine della conversione, dobbiamo salvare il file PDF/A-3b risultante. Ecco l'ultimo passo:

```csharp
dataDir = dataDir + "PDFToPDFA3b_out.pdf";
// Salva il documento di output
pdfDocument.Save(dataDir);
```

 Sostituire`"YOUR DOCUMENTS DIRECTORY"` con la directory desiderata in cui si desidera salvare il file PDF/A-3b di output.

### Esempio di codice sorgente per PDF in PDFA3b utilizzando Aspose.Words per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Apri documento
Document pdfDocument = new Document(dataDir + "input.pdf");            

pdfDocument.Convert(new MemoryStream(), PdfFormat.PDF_A_3B, ConvertErrorAction.Delete);

dataDir = dataDir + "PDFToPDFA3b_out.pdf";
// Salva documento di output
pdfDocument.Save(dataDir);

Console.WriteLine("\nPDF file converted to PDF/A-3B format.\nFile saved at " + dataDir);
```

## Conclusione
In questo tutorial, abbiamo coperto il processo passo-passo di conversione di un file PDF in formato PDF/A-3b utilizzando Aspose.PDF per .NET. Seguendo le istruzioni sopra descritte, ora dovresti essere in grado di convertire i file PDF in formato PDF/A-3b. Questa funzione è utile quando si desidera incorporare file e dati aggiuntivi in un documento PDF conforme allo standard PDF/A-3b.