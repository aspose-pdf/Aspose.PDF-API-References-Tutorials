---
title: Da EPUB a PDF
linktitle: Da EPUB a PDF
second_title: Aspose.PDF per riferimento API .NET
description: Guida passo passo per convertire EPUB in PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 30
url: /it/net/document-conversion/epub-to-pdf/
---

In questo tutorial, ti guideremo attraverso il processo di conversione di un file EPUB in PDF utilizzando la libreria Aspose.PDF per .NET. EPUB (Electronic Publication) è un formato ampiamente utilizzato per i libri elettronici, mentre PDF (Portable Document Format) è uno standard per lo scambio di documenti. Seguendo i passaggi indicati di seguito, sarai in grado di convertire i file EPUB in formato PDF senza sforzo.

## Prerequisiti
Prima di iniziare, assicurati di soddisfare i seguenti prerequisiti:

- Conoscenza base del linguaggio di programmazione C#.
- Libreria Aspose.PDF per .NET installata sul tuo sistema.
- Un ambiente di sviluppo come Visual Studio.

## Passaggio 1: carica il file EPUB
A questo punto, caricheremo il file EPUB utilizzando Aspose.PDF per .NET. Segui il codice qui sotto:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Crea un'istanza dell'oggetto LoadOption utilizzando l'opzione di caricamento EPUB
EpubLoadOptions epubload = new EpubLoadOptions();

// Creare un oggetto documento
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document(dataDir + "EPUBToPDF.epub", epubload);
```

 Assicurati di sostituire`"YOUR DOCUMENTS DIRECTORY"` con la directory effettiva in cui si trova il tuo file EPUB.

## Passaggio 2: conversione da EPUB a PDF
Ora che abbiamo caricato il file EPUB, possiamo procedere con la conversione in PDF. Usa il seguente codice:

```csharp
// Salva il documento PDF risultante
pdf. Save(dataDir + "EPUBToPDF_out.pdf");
```

 Il codice precedente converte il file EP EPUB caricato in formato PDF e lo salva come nome file`"EPUBToPDF_out.pdf"`. Assicurati di fornire il percorso e il nome file corretti per il file PDF di output.


 Sostituire`"YOUR DOCUMENTS DIRECTORY"` con la directory desiderata in cui si desidera salvare il file PDF di output.

### Esempio di codice sorgente per EPUB in PDF utilizzando Aspose.Words per .NET

```csharp
try
{
	
	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Crea un'istanza dell'oggetto LoadOption utilizzando l'opzione di caricamento EPUB
	EpubLoadOptions epubload = new EpubLoadOptions();

	// Crea oggetto documento
	Aspose.Pdf.Document pdf = new Aspose.Pdf.Document(dataDir + "EPUBToPDF.epub", epubload);

	// Salva il documento PDF risultante
	pdf.Save(dataDir + "EPUBToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}

```

## Conclusione
In questo tutorial, abbiamo coperto il processo passo-passo di conversione di un file EPUB in PDF utilizzando la libreria Aspose.PDF per .NET. Seguendo le istruzioni sopra descritte, ora dovresti essere in grado di convertire i file EPUB in formato PDF senza sforzo. Questa conversione apre possibilità di condivisione, stampa e archiviazione dei tuoi documenti.

