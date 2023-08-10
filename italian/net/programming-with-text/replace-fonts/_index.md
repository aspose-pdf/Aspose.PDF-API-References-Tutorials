---
title: Sostituisci caratteri
linktitle: Sostituisci caratteri
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come sostituire i caratteri in un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 340
url: /it/net/programming-with-text/replace-fonts/
---

In questo tutorial, spiegheremo come sostituire caratteri specifici in un documento PDF utilizzando la libreria Aspose.PDF per .NET. Seguiremo il processo passo dopo passo di caricamento di un documento PDF, ricerca di frammenti di testo, identificazione dei caratteri da sostituire, sostituzione dei caratteri e salvataggio del PDF modificato utilizzando il codice sorgente C# fornito.

## Prerequisiti

Prima di iniziare, assicurati di disporre di quanto segue:

- La libreria Aspose.PDF per .NET installata.
- Una conoscenza di base della programmazione C#.

## Passaggio 1: impostare la directory dei documenti

 Innanzitutto, devi impostare il percorso della directory in cui hai il file PDF di input. Sostituire`"YOUR DOCUMENT DIRECTORY"` nel`dataDir`variabile con il percorso del file PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: caricare il documento PDF

 Successivamente, carichiamo il documento PDF utilizzando il file`Document` class dalla libreria Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
```

## Passaggio 3: ricerca e sostituzione dei caratteri

 Creiamo un`TextFragmentAbsorber` oggetto e impostare l'opzione di modifica per rimuovere i caratteri inutilizzati. Quindi, accettiamo l'assorbitore per tutte le pagine del documento PDF per cercare frammenti di testo.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
pdfDocument.Pages.Accept(absorber);
```

## Passaggio 4: sostituisci i caratteri

Attraversiamo tutti i frammenti di testo identificati dall'assorbitore. Se il nome del carattere di un frammento di testo corrisponde al carattere desiderato da sostituire, lo sostituiamo con il nuovo carattere.

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    if (textFragment.TextState.Font.FontName == "Arial,Bold")
    {
        textFragment.TextState.Font = FontRepository.FindFont("Arial");
    }
}
```

## Passaggio 5: salva il PDF modificato

Infine, salviamo il documento PDF modificato nel file di output specificato.

```csharp
dataDir = dataDir + "ReplaceFonts_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nFonts replaced successfully in the PDF document.\nFile saved at " + dataDir);
```

### Codice sorgente di esempio per sostituire i caratteri utilizzando Aspose.PDF per .NET 
```csharp
try
{
	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Carica il file PDF di origine
	Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
	// Cerca frammenti di testo e imposta l'opzione di modifica come rimuovi i caratteri inutilizzati
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	// Accetta l'assorbitore per tutte le pagine
	pdfDocument.Pages.Accept(absorber);
	// Attraversa tutti i TextFragments
	foreach (TextFragment textFragment in absorber.TextFragments)
	{
		// Se il nome del carattere è ArialMT, sostituire il nome del carattere con Arial
		if (textFragment.TextState.Font.FontName == "Arial,Bold")
		{
			textFragment.TextState.Font = FontRepository.FindFont("Arial");
		}
	}
	dataDir = dataDir + "ReplaceFonts_out.pdf";
	// Salva documento aggiornato
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nFonts replaced successfully in pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.");
}
```

## Conclusione

In questo tutorial, hai imparato come sostituire caratteri specifici in un documento PDF utilizzando la libreria Aspose.PDF per .NET. Seguendo la guida passo-passo ed eseguendo il codice C# fornito, puoi caricare un documento PDF, cercare frammenti di testo, identificare e sostituire font specifici e salvare il PDF modificato.