---
title: Cerca e ottieni una pagina di testo
linktitle: Cerca e ottieni una pagina di testo
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come cercare e ottenere testo da una pagina specifica di un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 430
url: /it/net/programming-with-text/search-and-get-text-page/
---

Questo tutorial spiega come utilizzare Aspose.PDF per .NET per cercare e ottenere testo da una pagina specifica di un documento PDF. Il codice sorgente C# fornito illustra il processo passo dopo passo.

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
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
```

 Assicurati di sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

## Passaggio 4: cerca ed estrai il testo da una pagina

 Creare un`TextFragmentAbsorber` oggetto per trovare tutte le istanze della frase di ricerca di input su una pagina specifica:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
```

 Sostituire`"Figure"` con il testo effettivo che desideri cercare.

## Passaggio 5: ricerca su una pagina specifica

Accetta l'assorbitore per una pagina specifica del documento:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Passaggio 6: ottieni frammenti di testo estratti

Ottieni i frammenti di testo estratti utilizzando il file`TextFragments` proprietà del`TextFragmentAbsorber` oggetto:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Passaggio 7: scorrere i frammenti e i segmenti di testo

Passa in rassegna i frammenti di testo ottenuti e i relativi segmenti e accedi alle loro proprietà:

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

È possibile modificare il codice all'interno del ciclo per eseguire ulteriori azioni su ciascun segmento di testo.

### Esempio di codice sorgente per Cerca e ottieni pagine di testo utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
//Crea un oggetto TextAbsorber per trovare tutte le istanze della frase di ricerca di input
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
// Accetta l'assorbitore per tutte le pagine
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Ottieni i frammenti di testo estratti
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Passa attraverso i frammenti
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text : {0} ", textSegment.Text);
		Console.WriteLine("Position : {0} ", textSegment.Position);
		Console.WriteLine("XIndent : {0} ", textSegment.Position.XIndent);
		Console.WriteLine("YIndent : {0} ", textSegment.Position.YIndent);
		Console.WriteLine("Font - Name : {0}", textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible : {0} ", textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded : {0} ", textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset : {0} ", textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size : {0} ", textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color : {0} ", textSegment.TextState.ForegroundColor);
	}
}
```

## Conclusione

Congratulazioni! Hai imparato con successo come cercare e ottenere testo da una pagina specifica di un documento PDF utilizzando Aspose.PDF per .NET. Questo tutorial ha fornito una guida passo passo, dal caricamento del documento all'accesso ai segmenti di testo estratti. Ora puoi incorporare