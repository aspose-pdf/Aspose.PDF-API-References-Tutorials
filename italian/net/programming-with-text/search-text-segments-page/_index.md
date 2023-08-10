---
title: Cerca nella pagina Segmenti di testo
linktitle: Cerca nella pagina Segmenti di testo
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come cercare segmenti di testo su una pagina in un documento PDF e recuperare le loro proprietà utilizzando Aspose.PDF per .NET.
type: docs
weight: 470
url: /it/net/programming-with-text/search-text-segments-page/
---

Questo tutorial spiega come utilizzare Aspose.PDF per .NET per cercare segmenti di testo specifici su una pagina di un documento PDF e recuperare le loro proprietà. Il codice sorgente C# fornito illustra il processo passo dopo passo.

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

## Passaggio 3: impostare il percorso della directory dei documenti

 Imposta il percorso della directory dei documenti utilizzando il file`dataDir` variabile:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

## Passaggio 4: caricare il documento PDF

 Carica il documento PDF utilizzando il file`Document` classe:

```csharp
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
```

 Sostituire`"SearchTextSegmentsPage.pdf"` con il nome effettivo del file PDF.

## Passaggio 5: creare un TextFragmentAbsorber

 Creare un`TextFragmentAbsorber` oggetto per trovare tutte le istanze della frase di ricerca di input:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 Sostituire`"text"` con la frase di ricerca desiderata.

## Passaggio 6: accettare l'assorbitore per una pagina specifica

Accettare l'assorbitore per la pagina desiderata del documento:

```csharp
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
```

 Sostituire`2` con il numero di pagina desiderato (indice a base 1).

## Passaggio 7: recupera i segmenti di testo estratti

 Ottieni i segmenti di testo estratti utilizzando il file`TextFragments` proprietà del`TextFragmentAbsorber` oggetto:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Passaggio 8: scorrere i segmenti di testo

Passa in rassegna i segmenti di testo recuperati e accedi alle loro proprietà:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text: {0} ", textSegment.Text);
		Console.WriteLine("Position: {0} ", textSegment.Position);
		Console.WriteLine("XIndent: {0} ", textSegment.Position.XIndent);
		Console.WriteLine("YIndent: {0} ", textSegment.Position.YIndent);
		Console.WriteLine("Font - Name: {0}", textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible: {0} ", textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded: {0} ", textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset: {0} ", textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size: {0} ", textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color: {0} ", textSegment.TextState.ForegroundColor);
	}
}
```

Modifica il codice all'interno del ciclo per eseguire ulteriori azioni su ciascun segmento di testo, se necessario.

### Codice sorgente di esempio per la pagina dei segmenti di testo di ricerca utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
//Crea un oggetto TextAbsorber per trovare tutte le istanze della frase di ricerca di input
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Accetta l'assorbitore per tutte le pagine
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
// Ottieni i frammenti di testo estratti
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Passa attraverso i frammenti
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text : {0} ", textSegment.Text);
		Console.WriteLine("Position : {0} ", textSegment.Position);
		Console.WriteLine("XIndent : {0} ",
		textSegment.Position.XIndent);
		Console.WriteLine("YIndent : {0} ",
		textSegment.Position.YIndent);
		Console.WriteLine("Font - Name : {0}",
		textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible : {0} ",
		textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded : {0} ",
		textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset : {0} ",
		textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size : {0} ",
		textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color : {0} ",
		textSegment.TextState.ForegroundColor);
	}
}
```

## Conclusione

Congratulazioni! Hai imparato con successo come cercare segmenti di testo specifici su una pagina di un documento PDF utilizzando Aspose.PDF per .NET. Questo tutorial ha fornito una guida passo passo, dal caricamento del documento all'accesso ai segmenti di testo estratti. Ora puoi incorporare questo codice nei tuoi progetti C# per eseguire ricerche avanzate di segmenti di testo nei file PDF.