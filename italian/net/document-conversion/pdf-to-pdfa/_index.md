---
title: Da PDF a PDFA
linktitle: Da PDF a PDFA
second_title: Aspose.PDF per riferimento API .NET
description: Guida passo passo per convertire PDF in PDFA utilizzando Aspose.PDF per .NET.
type: docs
weight: 140
url: /it/net/document-conversion/pdf-to-pdfa/
---

In questo tutorial, ti guideremo attraverso il processo di conversione di un file PDF in formato PDF/A utilizzando Aspose.PDF per .NET. Il formato PDF/A è uno standard ISO che garantisce la conservazione a lungo termine dei documenti elettronici. Seguendo i passaggi seguenti, sarai in grado di convertire i file PDF in formato PDF/A.

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
Document pdfDocument = new Document(dataDir + "PDFToPDFA.pdf");
```

 Assicurati di sostituire`"YOUR DOCUMENTS DIRECTORY"` con la directory effettiva in cui si trova il file PDF.

## Passaggio 2: conversione in formato PDF/A
Dopo aver aperto il file PDF, possiamo procedere con la conversione in formato PDF/A. Usa il seguente codice:

```csharp
// Converti in documento conforme a PDF/A
// Durante il processo di conversione, viene eseguita anche la convalida
pdfDocument.Convert(dataDir + "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);
```

 Il codice precedente converte il file PDF in formato PDF/A-1b ed esegue anche la convalida durante il processo di conversione. Eventuali errori vengono registrati nel file`"log.xml"` file.

## Passaggio 3: salvare il file PDF/A risultante
Al termine della conversione, dobbiamo salvare il file PDF/A risultante. Ecco l'ultimo passaggio:

```csharp
dataDir = dataDir + "PDFToPDFA_out.pdf";
// Salva il documento di output
pdfDocument.Save(dataDir);
```

 Sostituire`"YOUR DOCUMENTS DIRECTORY"` con la directory desiderata in cui si desidera salvare il file PDF/A di output.

### Esempio di codice sorgente per PDF in HTML utilizzando Aspose.Words per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Apri documento
Document pdfDocument = new Document(dataDir + "PDFToPDFA.pdf");

// Converti in documento conforme a PDF/A
// Durante il processo di conversione, viene eseguita anche la convalida
pdfDocument.Convert(dataDir + "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);

dataDir = dataDir + "PDFToPDFA_out.pdf";
// Salva documento di output
pdfDocument.Save(dataDir);

Console.WriteLine("\nPDF file converted to PDF/A-1b compliant PDF.\nFile saved at " + dataDir);
```

## Conclusione
In questo tutorial, abbiamo coperto il processo passo-passo di conversione di un file PDF in formato PDF/A utilizzando Aspose.PDF per .NET. Seguendo le istruzioni sopra descritte, ora dovresti essere in grado di convertire i file PDF in formato PDF/A. Questa funzione è utile quando si desidera garantire la conformità a lungo termine dei propri documenti elettronici.