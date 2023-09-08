---
title: Cerca espressione regolare nel file PDF
linktitle: Cerca espressione regolare nel file PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come cercare e recuperare testo utilizzando le espressioni regolari nel file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 440
url: /it/net/programming-with-text/search-regular-expression/
---
Questo tutorial spiega come utilizzare Aspose.PDF per .NET per cercare e recuperare testo che corrisponde a un'espressione regolare nel file PDF. Il codice sorgente C# fornito illustra il processo passo dopo passo.

## Prerequisiti

Prima di procedere con il tutorial, assicurati di avere quanto segue:

- Conoscenza base del linguaggio di programmazione C#.
- Aspose.PDF per la libreria .NET installata. Puoi ottenerlo dal sito Web Aspose o utilizzare NuGet per installarlo nel tuo progetto.

## Passaggio 1: impostare il progetto

Inizia creando un nuovo progetto C# nel tuo ambiente di sviluppo integrato (IDE) preferito e aggiungi un riferimento alla libreria Aspose.PDF per .NET.

## Passaggio 2: importa gli spazi dei nomi necessari

Aggiungi le seguenti direttive using all'inizio del file C# per importare gli spazi dei nomi richiesti:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Passaggio 3: carica il documento PDF

 Imposta il percorso della directory dei documenti PDF e carica il documento utilizzando il file`Document` classe:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
```

 Assicurati di sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

## Passaggio 4: cerca con l'espressione regolare

 Creare un`TextFragmentAbsorber` oggetto e imposta il pattern dell'espressione regolare per trovare tutte le frasi che corrispondono al pattern:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Come il 1999-2000
```

 Sostituire`"\\d{4}-\\d{4}"` con il modello di espressione regolare desiderato.

## Passaggio 5: imposta le opzioni di ricerca del testo

 Creare un`TextSearchOptions` oggetto e impostarlo su`TextSearchOptions` proprietà del`TextFragmentAbsorber` oggetto per abilitare l'utilizzo delle espressioni regolari:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
```

## Passaggio 6: cerca su tutte le pagine

Accetta l'assorbitore per tutte le pagine del documento:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Passaggio 7: recupera i frammenti di testo estratti

Ottieni i frammenti di testo estratti utilizzando il file`TextFragments` proprietà del`TextFragmentAbsorber` oggetto:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Passaggio 8: scorrere i frammenti di testo

Passa in rassegna i frammenti di testo recuperati e accedi alle loro proprietà:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine("Text: {0} ", textFragment.Text);
	Console.WriteLine("Position: {0} ", textFragment.Position);
	Console.WriteLine("XIndent: {0} ", textFragment.Position.XIndent);
	Console.WriteLine("YIndent: {0} ", textFragment.Position.YIndent);
	Console.WriteLine("Font - Name: {0}", textFragment.TextState.Font.FontName);
	Console.WriteLine("Font - IsAccessible: {0} ", textFragment.TextState.Font.IsAccessible);
	Console.WriteLine("Font - IsEmbedded: {0} ", textFragment.TextState.Font.IsEmbedded);
	Console.WriteLine("Font - IsSubset: {0} ", textFragment.TextState.Font.IsSubset);
	Console.WriteLine("Font Size: {0} ", textFragment.TextState.FontSize);
	Console.WriteLine("Foreground Color: {0} ", textFragment.TextState.ForegroundColor);
}
```

Puoi modificare il codice all'interno del ciclo per eseguire ulteriori azioni su ciascun frammento di testo.

### Codice sorgente di esempio per la ricerca di espressioni regolari utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
// Crea un oggetto TextAbsorber per trovare tutte le frasi che corrispondono all'espressione regolare
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Come il 1999-2000
// Imposta l'opzione di ricerca testo per specificare l'utilizzo delle espressioni regolari
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
// Accettare l'assorbitore per tutte le pagine
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Ottieni i frammenti di testo estratti
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Passa in rassegna i frammenti
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine("Text : {0} ", textFragment.Text);
	Console.WriteLine("Position : {0} ", textFragment.Position);
	Console.WriteLine("XIndent : {0} ", textFragment.Position.XIndent);
	Console.WriteLine("YIndent : {0} ", textFragment.Position.YIndent);
	Console.WriteLine("Font - Name : {0}", textFragment.TextState.Font.FontName);
	Console.WriteLine("Font - IsAccessible : {0} ", textFragment.TextState.Font.IsAccessible);
	Console.WriteLine("Font - IsEmbedded : {0} ", textFragment.TextState.Font.IsEmbedded);
	Console.WriteLine("Font - IsSubset : {0} ", textFragment.TextState.Font.IsSubset);
	Console.WriteLine("Font Size : {0} ", textFragment.TextState.FontSize);
	Console.WriteLine("Foreground Color : {0} ", textFragment.TextState.ForegroundColor);
}
```

## Conclusione

Congratulazioni! Hai imparato con successo come cercare e recuperare testo che corrisponde a un'espressione regolare in un documento PDF utilizzando Aspose.PDF per .NET. Questo tutorial ha fornito una guida passo passo, dal caricamento del documento all'accesso ai frammenti di testo estratti. Ora puoi incorporare questo codice nei tuoi progetti C# per eseguire ricerche di testo avanzate nei file PDF.

### Domande frequenti

#### D: Qual è lo scopo del tutorial "Cerca espressione regolare nel file PDF"?

R: Il tutorial "Cerca espressione regolare nel file PDF" mira a mostrare come utilizzare la libreria Aspose.PDF per .NET per cercare ed estrarre testo che corrisponde a un modello di espressione regolare specificato all'interno di un file PDF. L'esercitazione fornisce indicazioni complete e codice C# di esempio per dimostrare il processo.

#### D: In che modo questo tutorial aiuta nella ricerca di testo utilizzando le espressioni regolari in un documento PDF?

R: Questo tutorial fornisce un approccio passo passo all'utilizzo della libreria Aspose.PDF per condurre ricerche di testo in un documento PDF in base a un modello di espressione regolare. Descrive in dettaglio come impostare il progetto, caricare il documento PDF, definire un modello di espressione regolare e recuperare i frammenti di testo corrispondenti.

#### D: Quali sono i prerequisiti per seguire questo tutorial?

R: Prima di iniziare questo tutorial, dovresti avere una conoscenza di base del linguaggio di programmazione C#. Inoltre, è necessario che sia installata la libreria Aspose.PDF per .NET. Puoi ottenerlo dal sito Web Aspose o utilizzare NuGet per integrarlo nel tuo progetto.

#### D: Come posso impostare il mio progetto per seguire questo tutorial?

R: Per iniziare, crea un nuovo progetto C# nel tuo ambiente di sviluppo integrato (IDE) preferito e aggiungi un riferimento alla libreria Aspose.PDF per .NET. Ciò ti consentirà di sfruttare le capacità della libreria all'interno del tuo progetto.

#### D: Posso utilizzare le espressioni regolari per cercare testo in un documento PDF?

 R: Sì, questo tutorial dimostra come utilizzare le espressioni regolari per cercare ed estrarre testo da un documento PDF. Implica l'utilizzo di`TextFragmentAbsorber` class e specificando un modello di espressione regolare per trovare frasi che corrispondono al modello fornito.

#### D: Come posso definire il modello di espressione regolare per la ricerca di testo?

 R: Per definire un modello di espressione regolare per la ricerca di testo, crea a`TextFragmentAbsorber` oggetto e impostarne il modello utilizzando il comando`Text` parametro. Sostituisci il modello predefinito`"\\d{4}-\\d{4}"` nel codice del tutorial con il modello di espressione regolare desiderato.

#### D: Come posso abilitare l'utilizzo delle espressioni regolari per la ricerca di testo?

 R: L'utilizzo delle espressioni regolari è abilitato creando un file`TextSearchOptions` oggetto e impostandone il valore su`true` . Assegna questo oggetto a`TextSearchOptions` proprietà del`TextFragmentAbsorber` esempio. Ciò garantisce che il modello di espressione regolare venga applicato durante la ricerca di testo.

#### D: Posso recuperare frammenti di testo che corrispondono al modello di espressione regolare?

 R: Assolutamente. Dopo aver applicato la ricerca con espressioni regolari al documento PDF, puoi recuperare i frammenti di testo estratti utilizzando il file`TextFragments` proprietà del`TextFragmentAbsorber` oggetto. Questi frammenti di testo contengono i segmenti di testo che corrispondono al modello di espressione regolare specificato.

#### D: A cosa posso accedere dai frammenti di testo recuperati?

R: Dai frammenti di testo recuperati, puoi accedere a varie proprietà come il contenuto del testo corrispondente, la posizione (coordinate X e Y), le informazioni sul carattere (nome, dimensione, colore) e altro. Il codice di esempio all'interno del ciclo dell'esercitazione illustra come accedere e visualizzare queste proprietà.

#### D: Come posso personalizzare le azioni sui frammenti di testo estratti?

R: Una volta estratti i frammenti di testo, puoi personalizzare il codice all'interno del ciclo per eseguire azioni aggiuntive su ciascun frammento di testo. Ciò può includere il salvataggio del testo estratto, l'analisi dei modelli o l'implementazione di modifiche alla formattazione in base alle tue esigenze.