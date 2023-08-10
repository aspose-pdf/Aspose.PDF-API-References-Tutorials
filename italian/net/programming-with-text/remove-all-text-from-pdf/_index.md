---
title: Rimuovi tutto il testo dal PDF
linktitle: Rimuovi tutto il testo dal PDF
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come rimuovere tutto il testo da un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 290
url: /it/net/programming-with-text/remove-all-text-from-pdf/
---

 In questo tutorial, spiegheremo come rimuovere tutto il testo da un documento PDF utilizzando la libreria Aspose.PDF per .NET. Seguiremo passo dopo passo il processo di apertura di un PDF, utilizzando un file`TextFragmentAbsorber` per rimuovere tutto il testo e salvare il PDF modificato utilizzando il codice sorgente C# fornito.

## Requisiti

Prima di iniziare, assicurati di disporre di quanto segue:

- La libreria Aspose.PDF per .NET installata.
- Una conoscenza di base della programmazione C#.

## Passaggio 1: impostare la directory dei documenti

 Innanzitutto, devi impostare il percorso della directory in cui si trovano i tuoi file PDF. Sostituire`"YOUR DOCUMENT DIRECTORY"` nel`dataDir` variabile con il percorso dei file PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: apri il documento PDF

 Successivamente, apriamo il documento PDF utilizzando il file`Document` class dalla libreria Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
```

## Passaggio 3: rimuovi tutto il testo

 Inizializziamo a`TextFragmentAbsorber`oggetto e usarlo per rimuovere tutto il testo assorbito dal documento PDF.

```csharp
TextFragmentAbsorber absorb = new TextFragmentAbsorber();
absorb. RemoveAllText(pdfDocument);
```

## Passaggio 4: salvare il PDF modificato

Infine, salviamo il documento PDF modificato nel file di output specificato.

```csharp
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### Esempio di codice sorgente per Rimuovi tutto il testo da PDF utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
// Avvia TextFragmentAbsorber
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
// Rimuovi tutto il testo assorbito
absorber.RemoveAllText(pdfDocument);
// Salva il documento
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

## Conclusione

 In questo tutorial, hai imparato come rimuovere tutto il testo da un documento PDF utilizzando la libreria Aspose.PDF per .NET. Seguendo la guida passo-passo ed eseguendo il codice C# fornito, puoi aprire un PDF, rimuovere tutto il testo utilizzando un`TextFragmentAbsorber`e salvare il PDF modificato.