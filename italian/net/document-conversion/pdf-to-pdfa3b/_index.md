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

### Esempio di codice sorgente per PDF in PDFA3b utilizzando Aspose.PDF per .NET

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

### FAQ

#### D: Che cos'è il PDF/A-3b e in cosa differisce dagli altri standard PDF/A?

R: PDF/A-3b è uno standard ISO che consente di incorporare file e dati in un documento PDF, rendendolo autonomo e garantendone la conservazione a lungo termine. A differenza di altri standard PDF/A, come PDF/A-1 e PDF/A-2, PDF/A-3b consente l'inclusione di file e dati aggiuntivi all'interno del documento PDF. Questa caratteristica lo rende adatto all'archiviazione e allo scambio di documenti complessi e interattivi.

#### D: Posso includere più file e dati in un documento PDF/A-3b?

R: Sì, uno dei principali vantaggi di PDF/A-3b è la sua capacità di includere più file e dati all'interno del documento PDF. È possibile incorporare vari tipi di file, come XML, fogli di calcolo, immagini o altri file PDF, insieme al contenuto PDF principale. Di conseguenza, il documento PDF/A-3b diventa un pacchetto autonomo contenente tutti gli elementi necessari.

#### D: Cosa succede se si verificano errori durante il processo di conversione da PDF a PDF/A-3b?

 R: Quando si converte un PDF in formato PDF/A-3b utilizzando Aspose.PDF per .NET, si ha il controllo su come vengono gestiti gli errori. IL`Convert` del metodo`ConvertErrorAction` Il parametro determina l'azione da intraprendere in caso di errori. Nell'esempio di codice fornito, il`ConvertErrorAction.Delete` viene utilizzato il parametro, il che significa che eventuali errori riscontrati durante la conversione comporteranno l'eliminazione delle pagine con errori.

#### D: Il formato PDF/A-3b è adatto alla conservazione a lungo termine dei documenti?

R: Sì, PDF/A-3b è progettato specificamente per la conservazione a lungo termine dei documenti elettronici. Incorporando file e dati aggiuntivi, garantisce che tutti i componenti necessari siano inclusi nel documento PDF stesso, riducendo il rischio di perdita di informazioni o dipendenze esterne nel tempo. Questa caratteristica lo rende adatto per l'archiviazione di documenti in modo da garantire accessibilità e coerenza a lungo termine.