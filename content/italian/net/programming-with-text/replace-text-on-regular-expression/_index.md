---
title: Sostituisci il testo nell'espressione regolare nel file PDF
linktitle: Sostituisci l'espressione regolare Texton nel file PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come sostituire il testo in base a un'espressione regolare nel file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 360
url: /it/net/programming-with-text/replace-text-on-regular-expression/
---
In questo tutorial spiegheremo come sostituire il testo in base a un'espressione regolare nel file PDF utilizzando la libreria Aspose.PDF per .NET. Forniremo una guida passo passo insieme al codice sorgente C# necessario.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

- Aspose.PDF per la libreria .NET installata.
- Conoscenza di base della programmazione C#.

## Passaggio 1: impostare la directory dei documenti

 Imposta il percorso della directory in cui hai il file PDF di input. Sostituire`"YOUR DOCUMENT DIRECTORY"` nel`dataDir` variabile con il percorso del file PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: carica il documento PDF

 Caricare il documento PDF utilizzando il file`Document` classe dalla libreria Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionPage.pdf");
```

## Passaggio 3: cerca e sostituisci testo utilizzando l'espressione regolare

 Creare un`TextFragmentAbsorber` oggetto e specificare il modello dell'espressione regolare per trovare tutte le frasi che corrispondono al modello. Imposta l'opzione di ricerca testo per abilitare l'utilizzo delle espressioni regolari.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Come il 1999-2000
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

### Codice sorgente di esempio per sostituire l'espressione regolare Texton utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionPage.pdf");
// Crea un oggetto TextAbsorber per trovare tutte le frasi che corrispondono all'espressione regolare
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Come il 1999-2000
// Imposta l'opzione di ricerca testo per specificare l'utilizzo delle espressioni regolari
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
// Accettare l'assorbitore per una singola pagina
pdfDocument.Pages[1].Accept(textFragmentAbsorber);
// Ottieni i frammenti di testo estratti
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Passa in rassegna i frammenti
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

In questo tutorial hai imparato come sostituire il testo in base a un'espressione regolare in un documento PDF utilizzando la libreria Aspose.PDF per .NET. Seguendo la guida passo passo ed eseguendo il codice C# fornito, puoi caricare un documento PDF, cercare testo utilizzando un'espressione regolare, sostituirlo e salvare il PDF modificato.

### Domande frequenti

#### D: Qual è lo scopo del tutorial "Sostituisci testo nell'espressione regolare nel file PDF"?

R: Il tutorial "Sostituisci testo su espressione regolare nel file PDF" mira a guidarti attraverso il processo di utilizzo della libreria Aspose.PDF per .NET per cercare e sostituire il testo in un documento PDF basato su un'espressione regolare. Fornisce una guida dettagliata insieme al codice C# di esempio.

#### D: Perché dovrei utilizzare un'espressione regolare per sostituire il testo in un documento PDF?

R: L'uso delle espressioni regolari ti consente di cercare e sostituire modelli di testo che seguono un formato specifico, rendendolo un modo potente per manipolare il contenuto. Questo approccio è particolarmente utile quando è necessario sostituire il testo che corrisponde a un determinato modello o struttura nel documento PDF.

#### D: Come posso impostare la directory dei documenti?

R: Per impostare la directory dei documenti:

1.  Sostituire`"YOUR DOCUMENT DIRECTORY"` nel`dataDir` variabile con il percorso della directory in cui si trova il file PDF di input.

#### D: Come posso sostituire il testo in base a un'espressione regolare in un documento PDF?

R: Il tutorial ti guida attraverso i seguenti passaggi:

1.  Caricare il documento PDF utilizzando il file`Document` classe.
2.  Creare un`TextFragmentAbsorber` oggetto e specificare il modello dell'espressione regolare per trovare le frasi corrispondenti al modello. Imposta l'opzione di ricerca testo per abilitare l'utilizzo delle espressioni regolari.
3. Passa in rassegna i frammenti di testo estratti e sostituisci il testo. Aggiorna altre proprietà come carattere, dimensione del carattere, colore di primo piano e colore di sfondo come richiesto.
4. Salva il documento PDF modificato.

#### D: Posso sostituire il testo utilizzando espressioni regolari complesse?

R: Sì, puoi utilizzare espressioni regolari complesse per abbinare e sostituire il testo nel documento PDF. Le espressioni regolari forniscono un modo flessibile per identificare modelli o strutture specifici nel testo.

####  D: Qual è lo scopo di`TextSearchOptions` class in the tutorial?

 R: Il`TextSearchOptions`La classe consente di specificare le opzioni di ricerca del testo, ad esempio l'abilitazione dell'utilizzo delle espressioni regolari durante la ricerca di frammenti di testo. Nel tutorial viene utilizzato per abilitare la modalità espressione regolare per il file`TextFragmentAbsorber`.

#### D: La sostituzione dei caratteri è facoltativa quando si utilizzano le espressioni regolari per sostituire il testo?

R: Sì, la sostituzione dei caratteri è facoltativa quando si utilizzano espressioni regolari per sostituire il testo. Se non specifichi un nuovo carattere, il testo manterrà il carattere del frammento di testo originale.

#### D: Come posso sostituire il testo in più pagine utilizzando un'espressione regolare?

R: Puoi modificare il ciclo attraverso i frammenti di testo per includere tutte le pagine del documento PDF, in modo simile all'esempio del tutorial. In questo modo, puoi sostituire il testo su più pagine in base al modello di espressione regolare.

#### D: Qual è il risultato previsto dell'esecuzione del codice fornito?

R: Seguendo il tutorial ed eseguendo il codice C# fornito, sostituirai il testo nel documento PDF che corrisponde al modello di espressione regolare specificato. Il testo sostituito avrà le proprietà specificate, ad esempio carattere, dimensione del carattere, colore di primo piano e colore di sfondo.

#### D: Posso utilizzare questo approccio per sostituire il testo con una formattazione complessa?

R: Sì, puoi personalizzare la formattazione del testo sostituito aggiornando proprietà come carattere, dimensione del carattere, colore di primo piano e colore di sfondo. Ciò consente di mantenere o modificare la formattazione secondo necessità.