---
title: Imposta carattere predefinito nel file PDF
linktitle: Imposta carattere predefinito nel file PDF
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come impostare il carattere predefinito in un file PDF utilizzando Aspose.PDF per .NET con questa guida dettagliata.
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

 Successivamente, imposteremo il carattere predefinito per il documento PDF utilizzando il file`PdfSaveOptions` classe. In questo esempio, imposteremo il carattere predefinito su "Arial".

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

## Conclusione

L'impostazione di un carattere predefinito nei documenti PDF utilizzando Aspose.PDF per .NET è un modo semplice ed efficace per garantire che il testo venga visualizzato correttamente, anche se i caratteri originali non sono disponibili. Seguendo la guida dettagliata e utilizzando il codice sorgente C# fornito, gli sviluppatori possono facilmente impostare il carattere predefinito e creare PDF che offrono un'esperienza di visualizzazione coerente e affidabile in diversi ambienti. Questa funzione è particolarmente utile negli scenari in cui i PDF verranno visualizzati o stampati su vari sistemi che potrebbero avere diversi set di caratteri installati.

### Domande frequenti per impostare il carattere predefinito nel file PDF

#### D: Perché l'impostazione di un carattere predefinito è importante nei documenti PDF?

R: L'impostazione di un carattere predefinito nei documenti PDF è importante perché garantisce che il testo venga visualizzato correttamente anche se i caratteri originali non sono disponibili sul sistema in cui il PDF viene visualizzato o stampato. Aiuta a prevenire problemi come testo mancante o confuso, garantendo un'esperienza visiva coerente e affidabile.

#### D: Posso scegliere qualsiasi carattere come carattere predefinito utilizzando Aspose.PDF per .NET?

 R: Sì, puoi scegliere qualsiasi carattere disponibile sul sistema come carattere predefinito utilizzando Aspose.PDF per .NET. Basta specificare il nome del carattere nel file`DefaultFontName` proprietà del`PdfSaveOptions` classe.

#### D: Cosa succede se il carattere predefinito specificato non è disponibile nel sistema?

R: Se il font predefinito specificato non è disponibile sul sistema, il visualizzatore PDF utilizzerà un font di fallback per visualizzare il testo. Si consiglia di scegliere un font comunemente disponibile come Arial o Times New Roman per garantire la compatibilità tra diversi sistemi.