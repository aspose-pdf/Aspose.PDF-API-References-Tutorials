---
title: Rimuovi i caratteri inutilizzati nel file PDF
linktitle: Rimuovi i caratteri inutilizzati nel file PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come rimuovere i caratteri inutilizzati nel file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 300
url: /it/net/programming-with-text/remove-unused-fonts/
---
In questo tutorial, spiegheremo come rimuovere i caratteri inutilizzati nel file PDF utilizzando la libreria Aspose.PDF per .NET. Seguiremo il processo passo passo di caricamento di un PDF, identificazione e rimozione dei caratteri inutilizzati e salvataggio del PDF aggiornato utilizzando il codice sorgente C# fornito.

## Requisiti

Prima di iniziare, assicurati di avere quanto segue:

- La libreria Aspose.PDF per .NET installata.
- Una conoscenza di base della programmazione C#.

## Passaggio 1: impostare la directory dei documenti

 Innanzitutto, devi impostare il percorso della directory in cui si trovano i file PDF. Sostituire`"YOUR DOCUMENT DIRECTORY"` nel`dataDir` variabile con il percorso dei file PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: carica il PDF di origine

 Successivamente, carichiamo il documento PDF di origine utilizzando il file`Document` classe dalla libreria Aspose.PDF.

```csharp
Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
```

## Passaggio 3: identificare e rimuovere i caratteri inutilizzati

 Creiamo un`TextFragmentAbsorber` oggetto con il`TextEditOptions` parametro impostato su`TextEditOptions.FontReplace.RemoveUnusedFonts` . Questa opzione ci consente di identificare e rimuovere i caratteri inutilizzati nel documento PDF. Quindi iteriamo attraverso tutto il file`TextFragments` e impostare il carattere su quello desiderato.

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

### Codice sorgente di esempio per rimuovere i caratteri inutilizzati utilizzando Aspose.PDF per .NET 
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

In questo tutorial, hai imparato come rimuovere i caratteri inutilizzati da un documento PDF utilizzando la libreria Aspose.PDF per .NET. Seguendo la guida passo passo ed eseguendo il codice C# fornito, puoi caricare un PDF, identificare e rimuovere i caratteri inutilizzati e salvare il PDF aggiornato.

### Domande frequenti

#### D: Qual è lo scopo del tutorial "Rimuovi caratteri inutilizzati nel file PDF"?

R: Il tutorial "Rimuovi caratteri inutilizzati nel file PDF" spiega come utilizzare la libreria Aspose.PDF per .NET per rimuovere i caratteri inutilizzati da un documento PDF. Il tutorial ti guida attraverso il processo di caricamento di un PDF, identificando e rimuovendo i caratteri inutilizzati e salvando il PDF aggiornato.

#### D: Perché dovrei rimuovere i caratteri inutilizzati da un documento PDF?

R: La rimozione dei caratteri inutilizzati da un documento PDF può aiutare a ridurre le dimensioni del file e ottimizzare il documento per prestazioni migliori. Ciò è particolarmente utile quando si ha a che fare con PDF che contengono caratteri incorporati che non vengono effettivamente utilizzati nel contenuto del documento.

#### D: Come posso impostare la directory dei documenti?

R: Per impostare la directory dei documenti:

1.  Sostituire`"YOUR DOCUMENT DIRECTORY"` nel`dataDir` variabile con il percorso della directory in cui si trovano i file PDF.

#### D: Come posso rimuovere i caratteri inutilizzati da un documento PDF utilizzando la libreria Aspose.PDF?

R: Il tutorial ti guida attraverso il processo passo dopo passo:

1.  Aprire il documento PDF utilizzando il file`Document` classe.
2.  Creare un`TextFragmentAbsorber` oggetto con`TextEditOptions` impostato`FontReplace.RemoveUnusedFonts`.
3. Accettare l'assorbitore per identificare e rimuovere i caratteri inutilizzati dal PDF.
4.  Ripeti tutto`TextFragments` e impostare il carattere su quello desiderato.
5. Salva il documento PDF aggiornato.

####  D: Qual è lo scopo di`TextEditOptions.FontReplace.RemoveUnusedFonts` parameter?

 R: Il`TextEditOptions.FontReplace.RemoveUnusedFonts` il parametro istruisce il`TextFragmentAbsorber` per identificare e rimuovere i caratteri inutilizzati dal documento PDF.

#### D: Posso sostituire i caratteri inutilizzati con un carattere di mia scelta?

R: Sì, puoi modificare il codice per sostituire i caratteri non utilizzati con un carattere a tua scelta. Nel codice di esempio fornito, il carattere "Arial, Bold" viene utilizzato in sostituzione.

####  D: Come funziona il`TextFragmentAbsorber` work to remove unused fonts?

 R: Il`TextFragmentAbsorber` è configurato con il`TextEditOptions.FontReplace.RemoveUnusedFonts` parametro, che identifica i caratteri inutilizzati all'interno dei frammenti di testo del PDF. Dopo l'assorbimento, è possibile scorrere il file`TextFragments` e impostare i caratteri sui caratteri sostitutivi desiderati.

#### D: Qual è il risultato previsto dell'esecuzione del codice fornito?

R: Seguendo il tutorial ed eseguendo il codice C# fornito, rimuoverai i caratteri inutilizzati dal documento PDF di input e salverai la versione aggiornata come file PDF di output.

#### D: Posso modificare il codice per rimuovere i caratteri solo da pagine o aree specifiche?

R: Il codice fornito si concentra sulla rimozione dei caratteri inutilizzati dall'intero documento PDF. Se desideri scegliere come target pagine o aree specifiche per la rimozione dei caratteri, dovrai modificare l'approccio e utilizzare una logica più complessa per identificare i caratteri inutilizzati in quelle aree.