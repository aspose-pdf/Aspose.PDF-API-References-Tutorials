---
title: Sostituisci testo tutto
linktitle: Sostituisci testo tutto
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come sostituire tutto il testo in un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 350
url: /it/net/programming-with-text/replace-text-all/
---

In questo tutorial, spiegheremo come sostituire tutto il testo in un documento PDF utilizzando la libreria Aspose.PDF per .NET. Forniremo una guida dettagliata insieme al codice sorgente C# necessario.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

- Aspose.PDF per la libreria .NET installata.
- Comprensione di base della programmazione C#.

## Passaggio 1: impostare la directory dei documenti

 Imposta il percorso della directory in cui hai il file PDF di input. Sostituire`"YOUR DOCUMENT DIRECTORY"` nel`dataDir` variabile con il percorso del file PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: caricare il documento PDF

 Carica il documento PDF utilizzando il file`Document` class dalla libreria Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "ReplaceTextAll.pdf");
```

## Passaggio 3: ricerca e sostituzione del testo

 Creare un`TextFragmentAbsorber`oggetto per trovare tutte le istanze della frase di ricerca di input. Accetta l'assorbitore per tutte le pagine del documento PDF per estrarre i frammenti di testo.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Passaggio 4: sostituisci il testo

Passa in rassegna i frammenti di testo estratti e sostituisci il testo come richiesto. Aggiorna il testo e altre proprietà come carattere, dimensione del carattere, colore di primo piano e colore di sfondo.

```csharp
foreach (TextFragment textFragment in textFragmentAbsorber.TextFragments)
{
    textFragment.Text = "TEXT";
    textFragment.TextState.Font = FontRepository.FindFont("Verdana");
    textFragment.TextState.FontSize = 22;
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
    textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
```

## Passaggio 5: salva il PDF modificato

Salva il documento PDF modificato nel file di output specificato.

```csharp
dataDir = dataDir + "ReplaceTextAll_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully.\nFile saved at " + dataDir);
```

### Esempio di codice sorgente per Sostituisci tutto il testo utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "ReplaceTextAll.pdf");
// Crea un oggetto TextAbsorber per trovare tutte le istanze della frase di ricerca di input
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Accetta l'assorbitore per tutte le pagine
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Ottieni i frammenti di testo estratti
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Passa attraverso i frammenti
foreach (TextFragment textFragment in textFragmentCollection)
{
	// Aggiorna testo e altre proprietà
	textFragment.Text = "TEXT";
	textFragment.TextState.Font = FontRepository.FindFont("Verdana");
	textFragment.TextState.FontSize = 22;
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
	textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
dataDir = dataDir + "ReplaceTextAll_out.pdf";
// Salva il documento PDF risultante.
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced  successfully.\nFile saved at " + dataDir);
```

## Conclusione

In questo tutorial, hai imparato come sostituire tutto il testo in un documento PDF utilizzando la libreria Aspose.PDF per .NET. Seguendo la guida passo-passo ed eseguendo il codice C# fornito, puoi caricare un documento PDF, cercare il testo desiderato, sostituirlo e salvare il PDF modificato.