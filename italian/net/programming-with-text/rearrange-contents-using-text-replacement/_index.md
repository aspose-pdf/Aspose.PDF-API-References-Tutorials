---
title: Riorganizzare i contenuti utilizzando la sostituzione del testo
linktitle: Riorganizzare i contenuti utilizzando la sostituzione del testo
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come riorganizzare i contenuti in un documento PDF utilizzando la sostituzione del testo con Aspose.PDF per .NET.
type: docs
weight: 270
url: /it/net/programming-with-text/rearrange-contents-using-text-replacement/
---

In questo tutorial, spiegheremo come riorganizzare i contenuti in un documento PDF utilizzando la sostituzione del testo con la libreria Aspose.PDF per .NET. Seguiremo il processo passo-passo di caricamento di un PDF, ricerca di frammenti di testo specifici, sostituzione del testo e salvataggio del PDF modificato utilizzando il codice sorgente C# fornito.

## Requisiti

Prima di iniziare, assicurati di disporre di quanto segue:

- La libreria Aspose.PDF per .NET installata.
- Una conoscenza di base della programmazione C#.

## Passaggio 1: impostare la directory dei documenti

 Innanzitutto, devi impostare il percorso della directory in cui si trovano i tuoi file PDF. Sostituire`"YOUR DOCUMENT DIRECTORY"` nel`dataDir` variabile con il percorso dei file PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: carica il PDF di origine

 Successivamente, carichiamo il documento PDF di origine utilizzando il file`Document` class dalla libreria Aspose.PDF.

```csharp
Document doc = new Document(dataDir + "ExtractTextPage.pdf");
```

## Passaggio 3: ricerca e sostituzione di frammenti di testo

 Creiamo un`TextFragmentAbsorber` oggetto con un'espressione regolare per cercare frammenti di testo specifici. Quindi, iteriamo attraverso i frammenti di testo, personalizziamo il carattere, la dimensione, il colore e sostituiamo il testo.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("[TextFragmentAbsorber,companyname,Textbox,50]");
doc.Pages.Accept(textFragmentAbsorber);

foreach(TextFragment textFragment in textFragmentAbsorber.TextFragments)
{
     textFragment.TextState.Font = FontRepository.FindFont("Arial");
     textFragment.TextState.FontSize = 12;
     textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Navy;
     textFragment.Text = "This is a Larger String for the Testing of this issue";
}
```

## Passaggio 4: salvare il PDF modificato

Infine, salviamo il documento PDF modificato nel file di output specificato.

```csharp
dataDir = dataDir + "RearrangeContentsUsingTextReplacement_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nContents rearranged successfully using text replacement.\nFile saved at " + dataDir);
```

### Esempio di codice sorgente per riorganizzare i contenuti utilizzando la sostituzione del testo utilizzando Aspose.PDF per .NET 
```csharp
try
{
	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Carica il file PDF di origine
	Document doc = new Document(dataDir + "ExtractTextPage.pdf");
	//Crea un oggetto TextFragment Absorber con un'espressione regolare
	TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("[TextFragmentAbsorber,companyname,Textbox,50]");
	doc.Pages.Accept(textFragmentAbsorber);
	// Sostituisci ogni TextFragment
	foreach (TextFragment textFragment in textFragmentAbsorber.TextFragments)
	{
		// Imposta il carattere del frammento di testo da sostituire
		textFragment.TextState.Font = FontRepository.FindFont("Arial");
		// Imposta la dimensione del carattere
		textFragment.TextState.FontSize = 12;
		textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Navy;
		// Sostituisci il testo con una stringa più grande del segnaposto
		textFragment.Text = "This is a Larger String for the Testing of this issue";
	}
	dataDir = dataDir + "RearrangeContentsUsingTextReplacement_out.pdf";
	// Salva il PDF risultante
	doc.Save(dataDir);
	Console.WriteLine("\nContents rearranged successfully using text replacement.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.");
}
```

## Conclusione

In questo tutorial, hai imparato come riorganizzare i contenuti in un documento PDF utilizzando la sostituzione del testo con la libreria Aspose.PDF per .NET. Seguendo la guida dettagliata ed eseguendo il codice C# fornito, puoi cercare frammenti di testo specifici, personalizzarne l'aspetto e sostituire il testo in un documento PDF.