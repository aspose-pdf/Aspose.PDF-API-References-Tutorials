---
title: Imposta il carattere predefinito nel file PDF
linktitle: Imposta il carattere predefinito nel file PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come impostare il carattere predefinito in un file PDF utilizzando Aspose.PDF per .NET con questa guida passo passo.
type: docs
weight: 280
url: /it/net/programming-with-document/setdefaultfont/
---
Se lavori con documenti PDF in .NET, potresti riscontrare problemi in cui il carattere utilizzato nel PDF non è disponibile nel sistema in cui viene visualizzato o stampato. Ciò può far sì che il testo venga visualizzato in modo errato o non venga visualizzato affatto. Aspose.PDF per .NET fornisce una soluzione a questo problema consentendo di impostare un carattere predefinito per il documento. In questo esempio, come impostare il carattere predefinito utilizzando Aspose.PDF per .NET.

## Passaggio 1: impostare il percorso della directory dei documenti

dobbiamo impostare il percorso della directory in cui si trova il nostro documento PDF. Memorizzeremo questo percorso in una variabile chiamata "dataDir".

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: carica il documento PDF

 Inizieremo caricando un documento PDF esistente a cui mancano i caratteri. In questo esempio, supponiamo che il documento PDF si trovi nella directory specificata da`dataDir` variabile.

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

## Passaggio 4: salva il documento aggiornato

Infine, salveremo il documento aggiornato in un nuovo file. In questo esempio, salveremo il documento aggiornato in un file denominato "output_out.pdf" nella stessa directory del file di input.

```csharp
document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
```

### Esempio di codice sorgente per impostare il carattere predefinito utilizzando Aspose.PDF per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Carica un documento PDF esistente con carattere mancante
string documentName = dataDir + "input.pdf";
string newName = "Arial";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
	PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
	// Specificare il nome del carattere predefinito
	pdfSaveOptions.DefaultFontName = newName;
	document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
}
```

## Conclusione

L'impostazione di un carattere predefinito nei documenti PDF utilizzando Aspose.PDF per .NET è un modo semplice ed efficace per garantire che il testo venga visualizzato correttamente, anche se i caratteri originali non sono disponibili. Seguendo la guida passo passo e utilizzando il codice sorgente C# fornito, gli sviluppatori possono facilmente impostare il carattere predefinito e creare PDF che offrono un'esperienza di visualizzazione coerente e affidabile in diversi ambienti. Questa funzionalità è particolarmente utile negli scenari in cui i PDF verranno visualizzati o stampati su vari sistemi che potrebbero avere diversi set di caratteri installati.

### Domande frequenti per impostare il carattere predefinito nel file PDF

#### D: Perché è importante impostare un carattere predefinito nei documenti PDF?

R: L'impostazione di un carattere predefinito nei documenti PDF è importante perché garantisce che il testo venga visualizzato correttamente anche se i caratteri originali non sono disponibili nel sistema in cui viene visualizzato o stampato il PDF. Aiuta a prevenire problemi come testo mancante o confuso, garantendo un'esperienza di visualizzazione coerente e affidabile.

#### D: Posso scegliere qualsiasi tipo di carattere come carattere predefinito utilizzando Aspose.PDF per .NET?

 R: Sì, puoi scegliere qualsiasi carattere disponibile nel sistema come carattere predefinito utilizzando Aspose.PDF per .NET. Basta specificare il nome del carattere nel file`DefaultFontName` proprietà del`PdfSaveOptions` classe.

#### D: Cosa succede se il carattere predefinito specificato non è disponibile nel sistema?

R: Se il carattere predefinito specificato non è disponibile nel sistema, il visualizzatore PDF utilizzerà un carattere di riserva per visualizzare il testo. Si consiglia di scegliere un carattere comunemente disponibile come Arial o Times New Roman per garantire la compatibilità tra sistemi diversi.