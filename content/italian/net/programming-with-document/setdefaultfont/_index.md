---
title: Imposta il font predefinito nel file PDF
linktitle: Imposta il font predefinito nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come impostare il font predefinito in un file PDF utilizzando Aspose.PDF per .NET con questa guida dettagliata.
type: docs
weight: 280
url: /it/net/programming-with-document/setdefaultfont/
---
Se lavori con documenti PDF in .NET, potresti riscontrare problemi in cui il font utilizzato nel PDF non è disponibile sul sistema in cui viene visualizzato o stampato. Ciò può causare la visualizzazione non corretta del testo o la sua assenza. Aspose.PDF per .NET fornisce una soluzione a questo problema consentendoti di impostare un font predefinito per il documento. In questo esempio, come impostare il font predefinito utilizzando Aspose.PDF per .NET.

## Passaggio 1: impostare il percorso della directory del documento

dobbiamo impostare il percorso della directory in cui si trova il nostro documento PDF. Memorizzeremo questo percorso in una variabile chiamata "dataDir".

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: caricare il documento PDF

 Inizieremo caricando un documento PDF esistente che ha font mancanti. In questo esempio, supporremo che il documento PDF si trovi nella directory specificata da`dataDir` variabile.

```csharp
string documentName = dataDir + "input.pdf";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
    // il codice va qui
}
```

## Passaggio 3: imposta il font predefinito

 Successivamente, imposteremo il font predefinito per il documento PDF utilizzando`PdfSaveOptions`classe. In questo esempio, imposteremo il font predefinito su "Arial".

```csharp
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.DefaultFontName = "Arial";
```

## Passaggio 4: salvare il documento aggiornato

Infine, salveremo il documento aggiornato in un nuovo file. In questo esempio, salveremo il documento aggiornato in un file denominato "output_out.pdf" nella stessa directory del file di input.

```csharp
document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
```

### Esempio di codice sorgente per impostare il font predefinito utilizzando Aspose.PDF per .NET

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Carica un documento PDF esistente con font mancante
string documentName = dataDir + "input.pdf";
string newName = "Arial";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
	PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
	// Specificare il nome del font predefinito
	pdfSaveOptions.DefaultFontName = newName;
	document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
}
```

## Conclusione

Impostare un font predefinito nei documenti PDF usando Aspose.PDF per .NET è un modo semplice ed efficace per garantire che il testo venga visualizzato correttamente, anche se i font originali non sono disponibili. Seguendo la guida passo passo e usando il codice sorgente C# fornito, gli sviluppatori possono facilmente impostare il font predefinito e creare PDF che offrono un'esperienza di visualizzazione coerente e affidabile in diversi ambienti. Questa funzionalità è particolarmente utile in scenari in cui i PDF verranno visualizzati o stampati su vari sistemi che potrebbero avere diversi set di font installati.

### Domande frequenti per impostare il font predefinito nel file PDF

#### D: Perché è importante impostare un font predefinito nei documenti PDF?

R: Impostare un font predefinito nei documenti PDF è importante perché assicura che il testo venga visualizzato correttamente anche se i font originali non sono disponibili sul sistema in cui il PDF viene visualizzato o stampato. Aiuta a prevenire problemi come testo mancante o distorto, garantendo un'esperienza di visualizzazione coerente e affidabile.

#### D: Posso scegliere qualsiasi font come font predefinito utilizzando Aspose.PDF per .NET?

 R: Sì, puoi scegliere qualsiasi font disponibile sul sistema come font predefinito utilizzando Aspose.PDF per .NET. Specifica semplicemente il nome del font nel`DefaultFontName` proprietà del`PdfSaveOptions` classe.

#### D: Cosa succede se il font predefinito specificato non è disponibile sul sistema?

R: Se il font predefinito specificato non è disponibile sul sistema, il visualizzatore PDF utilizzerà un font di fallback per visualizzare il testo. Si consiglia di scegliere un font comunemente disponibile come Arial o Times New Roman per garantire la compatibilità tra sistemi diversi.