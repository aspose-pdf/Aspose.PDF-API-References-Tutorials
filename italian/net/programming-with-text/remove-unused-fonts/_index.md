---
title: Rimuovi i caratteri inutilizzati
linktitle: Rimuovi i caratteri inutilizzati
second_title: Aspose.PDF per riferimento API .NET
description: Ulteriori informazioni su come rimuovere i caratteri inutilizzati da un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 300
url: /it/net/programming-with-text/remove-unused-fonts/
---

In questo tutorial, spiegheremo come rimuovere i caratteri inutilizzati da un documento PDF utilizzando la libreria Aspose.PDF per .NET. Seguiremo il processo passo-passo di caricamento di un PDF, identificazione e rimozione dei font inutilizzati e salvataggio del PDF aggiornato utilizzando il codice sorgente C# fornito.

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
Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
```

## Passaggio 3: identificare e rimuovere i caratteri inutilizzati

 Creiamo un`TextFragmentAbsorber` oggetto con il`TextEditOptions` parametro impostato su`TextEditOptions.FontReplace.RemoveUnusedFonts` Questa opzione ci consente di identificare e rimuovere i caratteri inutilizzati nel documento PDF. Quindi iteriamo attraverso tutti i file`TextFragments` e impostare il carattere su un carattere desiderato.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
doc.Pages.Accept(absorb);

foreach(TextFragment textFragment in absorber.TextFragments)
{
     textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
}
```

## Passaggio 4: salva il PDF aggiornato

Infine, salviamo il documento PDF aggiornato nel file di output specificato.

```csharp
dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nUnused fonts removed successfully from the PDF document.\nFile saved at " + dataDir);
```

### Esempio di codice sorgente per Rimuovi caratteri inutilizzati utilizzando Aspose.PDF per .NET 
```csharp
try
{
	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Carica il file PDF di origine
	Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	doc.Pages.Accept(absorber);
	// Scorri tutti i TextFragments
	foreach (TextFragment textFragment in absorber.TextFragments)
	{
		textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
	}
	dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
	// Salva documento aggiornato
	doc.Save(dataDir);
	Console.WriteLine("\nUnused fonts removed successfully from pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.");
}
```

## Conclusione

In questo tutorial, hai imparato come rimuovere i caratteri inutilizzati da un documento PDF utilizzando la libreria Aspose.PDF per .NET. Seguendo la guida dettagliata ed eseguendo il codice C# fornito, puoi caricare un PDF, identificare e rimuovere i font inutilizzati e salvare il PDF aggiornato.