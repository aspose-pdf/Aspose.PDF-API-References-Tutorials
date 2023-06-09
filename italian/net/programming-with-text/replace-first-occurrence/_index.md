---
title: Sostituisci la prima occorrenza
linktitle: Sostituisci la prima occorrenza
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come sostituire la prima occorrenza di testo in un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 330
url: /it/net/programming-with-text/replace-first-occurrence/
---

In questo tutorial, spiegheremo come sostituire la prima occorrenza di un testo specifico in un documento PDF utilizzando la libreria Aspose.PDF per .NET. Seguiremo il processo passo-passo di apertura di un documento PDF, ricerca della prima occorrenza della frase di ricerca, sostituzione del testo, aggiornamento delle proprietà e salvataggio del PDF modificato utilizzando il codice sorgente C# fornito.

## Prerequisiti

Prima di iniziare, assicurati di disporre di quanto segue:

- La libreria Aspose.PDF per .NET installata.
- Una conoscenza di base della programmazione C#.

## Passaggio 1: impostare la directory dei documenti

 Innanzitutto, devi impostare il percorso della directory in cui hai il file PDF di input. Sostituire`"YOUR DOCUMENT DIRECTORY"` nel`dataDir` variabile con il percorso del file PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: apri il documento PDF

 Successivamente, apriamo il documento PDF utilizzando il file`Document` class dalla libreria Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
```

## Passaggio 3: trova la prima occorrenza della frase di ricerca

 Creiamo un`TextFragmentAbsorber`oggetto e accettarlo per tutte le pagine del documento PDF per trovare tutte le occorrenze della frase di ricerca.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Passaggio 4: sostituire il testo

Se la frase di ricerca viene trovata nel documento PDF, recuperiamo la prima occorrenza del frammento di testo e ne aggiorniamo le proprietà con il nuovo testo e la formattazione.

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
if (textFragmentCollection.Count > 0)
{
    TextFragment textFragment = textFragmentCollection[1];
    textFragment.Text = "New Phrase";
    textFragment.TextState.Font = FontRepository.FindFont("Verdana");
    textFragment.TextState.FontSize = 22;
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
}
```

## Passaggio 5: salva il PDF modificato

Infine, salviamo il documento PDF modificato nel file di output specificato.

```csharp
dataDir = dataDir + "ReplaceFirstOccurrence_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully.\nFile saved at " + dataDir);
```

### Esempio di codice sorgente per Sostituisci la prima occorrenza utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
// Crea un oggetto TextAbsorber per trovare tutte le istanze della frase di ricerca di input
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Accetta l'assorbitore per tutte le pagine
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Ottieni i frammenti di testo estratti
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
if (textFragmentCollection.Count > 0)
{
	// Ottieni la prima occorrenza del testo e sostituisci
	TextFragment textFragment = textFragmentCollection[1];
	// Aggiorna testo e altre proprietà
	textFragment.Text = "New Phrase";
	textFragment.TextState.Font = FontRepository.FindFont("Verdana");
	textFragment.TextState.FontSize = 22;
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
	dataDir = dataDir + "ReplaceFirstOccurrence_out.pdf";
	pdfDocument.Save(dataDir);                 
	Console.WriteLine("\nText replaced successfully.\nFile saved at " + dataDir);
}
```

## Conclusione

In questo tutorial, hai imparato come sostituire la prima occorrenza di un testo specifico in un documento PDF utilizzando la libreria Aspose.PDF per .NET. Seguendo la guida passo-passo ed eseguendo il codice C# fornito, puoi aprire un documento PDF, trovare la prima occorrenza di una frase di ricerca, sostituire il testo, aggiornare le proprietà e salvare il PDF modificato.