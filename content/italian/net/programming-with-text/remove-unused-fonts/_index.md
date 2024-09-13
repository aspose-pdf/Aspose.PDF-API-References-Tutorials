---
title: Rimuovi i font inutilizzati nel file PDF
linktitle: Rimuovi i font inutilizzati nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come rimuovere i font inutilizzati nei file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 300
url: /it/net/programming-with-text/remove-unused-fonts/
---
In questo tutorial, spiegheremo come rimuovere i font inutilizzati in un file PDF usando la libreria Aspose.PDF per .NET. Esamineremo passo dopo passo il processo di caricamento di un PDF, identificazione e rimozione dei font inutilizzati e salvataggio del PDF aggiornato usando il codice sorgente C# fornito.

## Requisiti

Prima di iniziare, assicurati di avere quanto segue:

- È stata installata la libreria Aspose.PDF per .NET.
- Conoscenza di base della programmazione C#.

## Passaggio 1: impostare la directory dei documenti

 Per prima cosa, devi impostare il percorso della directory in cui si trovano i tuoi file PDF. Sostituisci`"YOUR DOCUMENT DIRECTORY"` nel`dataDir` variabile con il percorso dei file PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: caricare il PDF di origine

 Successivamente, carichiamo il documento PDF di origine utilizzando`Document` classe dalla libreria Aspose.PDF.

```csharp
Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
```

## Passaggio 3: identificare e rimuovere i font inutilizzati

 Creiamo un`TextFragmentAbsorber` oggetto con il`TextEditOptions` parametro impostato su`TextEditOptions.FontReplace.RemoveUnusedFonts` Questa opzione ci consente di identificare e rimuovere i font inutilizzati nel documento PDF. Quindi eseguiamo l'iterazione attraverso tutti i`TextFragments` e imposta il font sul font desiderato.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
doc.Pages.Accept(absorb);

foreach(TextFragment textFragment in absorber.TextFragments)
{
     textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
}
```

## Passaggio 4: Salva il PDF aggiornato

Infine, salviamo il documento PDF aggiornato nel file di output specificato.

```csharp
dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nUnused fonts removed successfully from the PDF document.\nFile saved at " + dataDir);
```

### Esempio di codice sorgente per rimuovere i font inutilizzati utilizzando Aspose.PDF per .NET 
```csharp
try
{
	// Percorso verso la directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Carica il file PDF di origine
	Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	doc.Pages.Accept(absorber);
	// Scorrere tutti i TextFragments
	foreach (TextFragment textFragment in absorber.TextFragments)
	{
		textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
	}
	dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
	// Salva il documento aggiornato
	doc.Save(dataDir);
	Console.WriteLine("\nUnused fonts removed successfully from pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.");
}
```

## Conclusione

In questo tutorial, hai imparato come rimuovere i font inutilizzati da un documento PDF utilizzando la libreria Aspose.PDF per .NET. Seguendo la guida passo passo ed eseguendo il codice C# fornito, puoi caricare un PDF, identificare e rimuovere i font inutilizzati e salvare il PDF aggiornato.

### Domande frequenti

#### D: Qual è lo scopo del tutorial "Rimuovere i font inutilizzati nei file PDF"?

R: Il tutorial "Rimuovi font inutilizzati nel file PDF" spiega come usare la libreria Aspose.PDF per .NET per rimuovere i font inutilizzati da un documento PDF. Il tutorial ti guida attraverso il processo di caricamento di un PDF, identificazione e rimozione dei font inutilizzati e salvataggio del PDF aggiornato.

#### D: Perché dovrei voler rimuovere i font inutilizzati da un documento PDF?

R: La rimozione di font inutilizzati da un documento PDF può aiutare a ridurre le dimensioni del file e ottimizzare il documento per prestazioni migliori. Ciò è particolarmente utile quando si ha a che fare con PDF che contengono font incorporati che non sono effettivamente utilizzati nel contenuto del documento.

#### D: Come faccio a impostare la directory dei documenti?

A: Per impostare la directory dei documenti:

1.  Sostituire`"YOUR DOCUMENT DIRECTORY"` nel`dataDir` variabile con il percorso della directory in cui si trovano i file PDF.

#### D: Come posso rimuovere i font inutilizzati da un documento PDF utilizzando la libreria Aspose.PDF?

A: Il tutorial ti guida passo dopo passo attraverso il processo:

1.  Aprire il documento PDF utilizzando`Document` classe.
2.  Crea un`TextFragmentAbsorber` oggetto con`TextEditOptions` impostare su`FontReplace.RemoveUnusedFonts`.
3. Accetta l'assorbitore per identificare e rimuovere i font inutilizzati dal PDF.
4.  Ripeti tutto`TextFragments` e imposta il font sul font desiderato.
5. Salvare il documento PDF aggiornato.

####  D: Qual è lo scopo del`TextEditOptions.FontReplace.RemoveUnusedFonts` parameter?

 A: Il`TextEditOptions.FontReplace.RemoveUnusedFonts` il parametro istruisce il`TextFragmentAbsorber`per identificare e rimuovere i font inutilizzati dal documento PDF.

#### D: Posso sostituire i font inutilizzati con un font di mia scelta?

R: Sì, puoi modificare il codice per sostituire i font inutilizzati con un font di tua scelta. Nel codice di esempio fornito, il font "Arial, Bold" è utilizzato come sostituzione.

#### D: Come funziona il`TextFragmentAbsorber` work to remove unused fonts?

 A: Il`TextFragmentAbsorber` è configurato con il`TextEditOptions.FontReplace.RemoveUnusedFonts` parametro, che identifica i font inutilizzati all'interno dei frammenti di testo del PDF. Dopo l'assorbimento, puoi scorrere il`TextFragments` e impostare i font sui font sostitutivi desiderati.

#### D: Qual è il risultato previsto dall'esecuzione del codice fornito?

R: Seguendo il tutorial ed eseguendo il codice C# fornito, rimuoverai i font inutilizzati dal documento PDF di input e salverai la versione aggiornata come file PDF di output.

#### D: Posso modificare il codice per rimuovere i font solo da pagine o aree specifiche?

R: Il codice fornito si concentra sulla rimozione dei font inutilizzati dall'intero documento PDF. Se si desidera indirizzare la rimozione dei font a pagine o regioni specifiche, è necessario modificare l'approccio e utilizzare una logica più complessa per identificare i font inutilizzati in quelle aree.