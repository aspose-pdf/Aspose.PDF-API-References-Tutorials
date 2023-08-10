---
title: Cerca Espressione regolare
linktitle: Cerca Espressione regolare
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come cercare e recuperare il testo utilizzando le espressioni regolari in un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 440
url: /it/net/programming-with-text/search-regular-expression/
---

Questo tutorial spiega come utilizzare Aspose.PDF per .NET per cercare e recuperare il testo che corrisponde a un'espressione regolare in un documento PDF. Il codice sorgente C# fornito illustra il processo passo dopo passo.

## Prerequisiti

Prima di procedere con il tutorial, assicurati di disporre di quanto segue:

- Conoscenza base del linguaggio di programmazione C#.
- Aspose.PDF per la libreria .NET installata. Puoi ottenerlo dal sito Web di Aspose o utilizzare NuGet per installarlo nel tuo progetto.

## Passaggio 1: impostare il progetto

Inizia creando un nuovo progetto C# nel tuo ambiente di sviluppo integrato (IDE) preferito e aggiungi un riferimento alla libreria Aspose.PDF per .NET.

## Passaggio 2: importa gli spazi dei nomi necessari

Aggiungi le seguenti direttive using all'inizio del tuo file C# per importare gli spazi dei nomi richiesti:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Passaggio 3: caricare il documento PDF

 Imposta il percorso della directory del documento PDF e carica il documento utilizzando il file`Document` classe:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
```

 Assicurati di sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

## Passaggio 4: ricerca con espressione regolare

 Creare un`TextFragmentAbsorber` oggetto e imposta il modello di espressione regolare per trovare tutte le frasi che corrispondono al modello:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Come 1999-2000
```

 Sostituire`"\\d{4}-\\d{4}"` con il modello di espressione regolare desiderato.

## Passaggio 5: imposta le opzioni di ricerca del testo

 Creare un`TextSearchOptions` oggetto e impostarlo su`TextSearchOptions` proprietà del`TextFragmentAbsorber` oggetto per abilitare l'uso delle espressioni regolari:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
```

## Passaggio 6: ricerca su tutte le pagine

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

È possibile modificare il codice all'interno del ciclo per eseguire ulteriori azioni su ciascun frammento di testo.

### Esempio di codice sorgente per la ricerca di espressioni regolari utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
// Crea un oggetto TextAbsorber per trovare tutte le frasi che corrispondono all'espressione regolare
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Come 1999-2000
// Imposta l'opzione di ricerca del testo per specificare l'utilizzo delle espressioni regolari
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
// Accetta l'assorbitore per tutte le pagine
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Ottieni i frammenti di testo estratti
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Passa attraverso i frammenti
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

Congratulazioni! Hai imparato con successo come cercare e recuperare il testo che corrisponde a un'espressione regolare in un documento PDF utilizzando Aspose.PDF per .NET. Questo tutorial ha fornito una guida passo passo, dal caricamento del documento all'accesso ai frammenti di testo estratti. Ora puoi incorporare questo codice nei tuoi progetti C# per eseguire ricerche di testo avanzate nei file PDF.