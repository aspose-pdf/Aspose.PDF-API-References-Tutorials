---
title: Sostituisci i caratteri nel file PDF
linktitle: Sostituisci i caratteri nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come sostituire i font nei file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 340
url: /it/net/programming-with-text/replace-fonts/
---
In questo tutorial, spiegheremo come sostituire specifici font in un file PDF usando la libreria Aspose.PDF per .NET. Esamineremo passo dopo passo il processo di caricamento di un documento PDF, la ricerca di frammenti di testo, l'identificazione dei font da sostituire, la sostituzione dei font e il salvataggio del PDF modificato usando il codice sorgente C# fornito.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

- È stata installata la libreria Aspose.PDF per .NET.
- Conoscenza di base della programmazione C#.

## Passaggio 1: impostare la directory dei documenti

 Per prima cosa, devi impostare il percorso della directory in cui hai il file PDF di input. Sostituisci`"YOUR DOCUMENT DIRECTORY"` nel`dataDir` variabile con il percorso del file PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: caricare il documento PDF

 Successivamente, carichiamo il documento PDF utilizzando`Document` classe dalla libreria Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
```

## Passaggio 3: Cerca e sostituisci i caratteri

 Creiamo un`TextFragmentAbsorber`oggetto e impostiamo l'opzione di modifica per rimuovere i font inutilizzati. Quindi, accettiamo l'assorbitore per tutte le pagine del documento PDF per cercare frammenti di testo.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
pdfDocument.Pages.Accept(absorber);
```

## Passaggio 4: Sostituisci i caratteri

Attraversiamo tutti i frammenti di testo identificati dall'assorbitore. Se il nome del font di un frammento di testo corrisponde al font desiderato da sostituire, lo sostituiamo con il nuovo font.

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    if (textFragment.TextState.Font.FontName == "Arial,Bold")
    {
        textFragment.TextState.Font = FontRepository.FindFont("Arial");
    }
}
```

## Passaggio 5: Salvare il PDF modificato

Infine, salviamo il documento PDF modificato nel file di output specificato.

```csharp
dataDir = dataDir + "ReplaceFonts_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nFonts replaced successfully in the PDF document.\nFile saved at " + dataDir);
```

### Esempio di codice sorgente per sostituire i caratteri utilizzando Aspose.PDF per .NET 
```csharp
try
{
	// Percorso verso la directory dei documenti.
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
		// Se il nome del font è ArialMT, sostituisci il nome del font con Arial
		if (textFragment.TextState.Font.FontName == "Arial,Bold")
		{
			textFragment.TextState.Font = FontRepository.FindFont("Arial");
		}
	}
	dataDir = dataDir + "ReplaceFonts_out.pdf";
	// Salva il documento aggiornato
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nFonts replaced successfully in pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.");
}
```

## Conclusione

In questo tutorial, hai imparato come sostituire font specifici in un documento PDF usando la libreria Aspose.PDF per .NET. Seguendo la guida passo passo ed eseguendo il codice C# fornito, puoi caricare un documento PDF, cercare frammenti di testo, identificare e sostituire font specifici e salvare il PDF modificato.

### Domande frequenti

#### D: Qual è lo scopo del tutorial "Sostituisci i caratteri nel file PDF"?

R: Il tutorial "Sostituisci font nel file PDF" illustra come usare la libreria Aspose.PDF per .NET per sostituire font specifici in un documento PDF. Fornisce una guida passo passo su come caricare un documento PDF, cercare frammenti di testo, identificare i font da sostituire, sostituire i font e salvare il PDF modificato.

#### D: Perché dovrei voler sostituire i font in un documento PDF?

R: La sostituzione dei font in un documento PDF può essere necessaria quando si desidera standardizzare l'aspetto del testo o migliorare la compatibilità del documento su diversi dispositivi e piattaforme. Consente di garantire una tipografia e una formattazione coerenti.

#### D: Come faccio a impostare la directory dei documenti?

A: Per impostare la directory dei documenti:

1.  Sostituire`"YOUR DOCUMENT DIRECTORY"` nel`dataDir` variabile con il percorso della directory in cui si trova il file PDF di input.

#### D: Come faccio a sostituire specifici font in un documento PDF?

A: Il tutorial ti guida passo dopo passo attraverso il processo:

1.  Caricare il documento PDF utilizzando`Document` classe.
2.  Crea un`TextFragmentAbsorber` oggetto e imposta l'opzione di modifica per rimuovere i font inutilizzati. Accetta l'assorbitore per tutte le pagine per cercare frammenti di testo.
3. Attraversa i frammenti di testo identificati. Se il nome del font di un frammento di testo corrisponde al font che vuoi sostituire, sostituiscilo con il nuovo font.

####  D: Qual è lo scopo dell'utilizzo`TextFragmentAbsorber` with font replacement options?

 A: Il`TextFragmentAbsorber` con opzioni di sostituzione font consente di individuare frammenti di testo e rimuovere simultaneamente font inutilizzati. Ciò è importante per garantire che i font sostituiti non vengano aggiunti come risorse aggiuntive nel PDF.

#### D: Come faccio a identificare i font specifici da sostituire?

R: Attraversando i frammenti di testo identificati dall'assorbitore, puoi accedere alle informazioni sul font per ogni frammento di testo. Se il nome del font corrisponde al font che vuoi sostituire, puoi eseguire la sostituzione.

#### D: Cosa succede se il font da sostituire non viene trovato in un frammento di testo?

A: Se il font da sostituire non si trova in un frammento di testo, il font del frammento di testo rimane invariato. La sostituzione avverrà solo se il nome del font corrisponde.

#### D: C'è una limitazione alla sostituzione dei font in questo tutorial?

R: Questo tutorial si concentra sulla sostituzione di font specifici in frammenti di testo. Se hai bisogno di sostituire font in altri contesti, come annotazioni o campi di form, dovrai estendere l'approccio di conseguenza.

#### D: Qual è il risultato previsto dall'esecuzione del codice fornito?

A: Seguendo il tutorial ed eseguendo il codice C# fornito, sostituirai specifici font nel documento PDF. I font identificati dai criteri che hai impostato saranno sostituiti con il nuovo font che hai specificato.

#### D: Posso usare questo approccio per sostituire i font nell'intero documento PDF?

R: Sì, puoi adattare il codice per sostituire i font nell'intero documento PDF, esaminando tutti i frammenti di testo e applicando la logica di sostituzione dei font.