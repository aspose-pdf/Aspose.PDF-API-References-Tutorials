---
title: Sostituisci il testo sull'espressione regolare
linktitle: Sostituisci l'espressione regolare di Texton
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come sostituire il testo basato su un'espressione regolare in un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 360
url: /it/net/programming-with-text/replace-text-on-regular-expression/
---

In questo tutorial, spiegheremo come sostituire il testo basato su un'espressione regolare in un documento PDF utilizzando la libreria Aspose.PDF per .NET. Forniremo una guida dettagliata insieme al codice sorgente C# necessario.

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
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionPage.pdf");
```

## Passaggio 3: ricerca e sostituzione del testo utilizzando l'espressione regolare

 Creare un`TextFragmentAbsorber` oggetto e specificare il modello di espressione regolare per trovare tutte le frasi corrispondenti al modello. Imposta l'opzione di ricerca testo per abilitare l'utilizzo delle espressioni regolari.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Come 1999-2000
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
pdfDocument.Pages[1].Accept(textFragmentAbsorber);
```

## Passaggio 4: sostituisci il testo

Passa in rassegna i frammenti di testo estratti e sostituisci il testo come richiesto. Aggiorna il testo e altre proprietà come carattere, dimensione del carattere, colore di primo piano e colore di sfondo.

```csharp
foreach (TextFragment textFragment in textFragmentAbsorber.TextFragments)
{
    textFragment.Text = "New Phrase";
    textFragment.TextState.Font = FontRepository.FindFont("Verdana");
    textFragment.TextState.FontSize = 22;
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
    textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
```

## Passaggio 5: salva il PDF modificato

Salva il documento PDF modificato nel file di output specificato.

```csharp
dataDir = dataDir + "ReplaceTextonRegularExpression_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully based on a regular expression.\nFile saved at " + dataDir);
```

### Esempio di codice sorgente per Sostituire l'espressione regolare di Texton utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionPage.pdf");
// Crea un oggetto TextAbsorber per trovare tutte le frasi che corrispondono all'espressione regolare
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Come 1999-2000
// Imposta l'opzione di ricerca del testo per specificare l'utilizzo delle espressioni regolari
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
// Accetta l'assorbitore per una singola pagina
pdfDocument.Pages[1].Accept(textFragmentAbsorber);
// Ottieni i frammenti di testo estratti
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Passa attraverso i frammenti
foreach (TextFragment textFragment in textFragmentCollection)
{
	// Aggiorna testo e altre proprietà
	textFragment.Text = "New Phrase";
	// Impostato su un'istanza di un oggetto.
	textFragment.TextState.Font = FontRepository.FindFont("Verdana");
	textFragment.TextState.FontSize = 22;
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
	textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
dataDir = dataDir + "ReplaceTextonRegularExpression_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully based on a regular expression.\nFile saved at " + dataDir);
```

## Conclusione

In questo tutorial, hai imparato a sostituire il testo basato su un'espressione regolare in un documento PDF utilizzando la libreria Aspose.PDF per .NET. Seguendo la guida dettagliata ed eseguendo il codice C# fornito, puoi caricare un documento PDF, cercare testo utilizzando un'espressione regolare, sostituirlo e salvare il PDF modificato.