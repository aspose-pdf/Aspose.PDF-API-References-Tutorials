---
title: Imposta carattere predefinito
linktitle: Imposta carattere predefinito
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come impostare il carattere predefinito per un documento PDF utilizzando Aspose.PDF per .NET con questa guida dettagliata.
type: docs
weight: 280
url: /it/net/programming-with-document/setdefaultfont/
---
Se stai lavorando con documenti PDF in .NET, potresti riscontrare problemi in cui il carattere utilizzato nel PDF non è disponibile sul sistema in cui viene visualizzato o stampato. Ciò può comportare che il testo appaia in modo errato o non appaia affatto. Aspose.PDF per .NET fornisce una soluzione a questo problema consentendo di impostare un carattere predefinito per il documento. In questo esempio, come impostare il carattere predefinito utilizzando Aspose.PDF per .NET.

## Passaggio 1: impostare il percorso della directory dei documenti

dobbiamo impostare il percorso della directory in cui si trova il nostro documento PDF. Memorizzeremo questo percorso in una variabile chiamata "dataDir".

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: caricare il documento PDF

 Inizieremo caricando un documento PDF esistente a cui mancano i caratteri. In questo esempio, supponiamo che il documento PDF si trovi nella directory specificata dal file`dataDir` variabile.

```csharp
string documentName = dataDir + "input.pdf";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
    // il codice va qui
}
```

## Passaggio 3: imposta il carattere predefinito

 Successivamente, imposteremo il carattere predefinito per il documento PDF utilizzando il file`PdfSaveOptions`classe. In questo esempio, imposteremo il carattere predefinito su "Arial".

```csharp
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.DefaultFontName = "Arial";
```

## Passaggio 4: salvare il documento aggiornato

Infine, salveremo il documento aggiornato in un nuovo file. In questo esempio, salveremo il documento aggiornato in un file denominato "output_out.pdf" nella stessa directory del file di input.

```csharp
document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
```

### Esempio di codice sorgente per impostare il carattere predefinito utilizzando Aspose.PDF per .NET

```csharp
	
	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Carica un documento PDF esistente con font mancante
	string documentName = dataDir + "input.pdf";
	string newName = "Arial";
	using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
	using (Document document = new Document(fs))
	{
		PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
		// Specifica il nome del carattere predefinito
		pdfSaveOptions.DefaultFontName = newName;
		document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
	}
	
```
