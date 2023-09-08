---
title: Cerca la pagina dei segmenti di testo nel file PDF
linktitle: Cerca la pagina dei segmenti di testo nel file PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come cercare segmenti di testo su una pagina nel file PDF e recuperare le loro proprietà utilizzando Aspose.PDF per .NET.
type: docs
weight: 470
url: /it/net/programming-with-text/search-text-segments-page/
---
Questo tutorial spiega come utilizzare Aspose.PDF per .NET per cercare segmenti di testo specifici su una pagina di file PDF e recuperare le loro proprietà. Il codice sorgente C# fornito illustra il processo passo dopo passo.

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

## Passaggio 3: impostare il percorso della directory dei documenti

 Imposta il percorso della directory dei documenti utilizzando il file`dataDir` variabile:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

## Passaggio 4: carica il documento PDF

 Caricare il documento PDF utilizzando il file`Document` classe:

```csharp
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
```

 Sostituire`"SearchTextSegmentsPage.pdf"` con il nome effettivo del file PDF.

## Passaggio 5: crea un TextFragmentAbsorber

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

Se necessario, modifica il codice all'interno del ciclo per eseguire ulteriori azioni su ciascun segmento di testo.

### Codice sorgente di esempio per la pagina di segmenti di testo di ricerca utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
// Crea un oggetto TextAbsorber per trovare tutte le istanze della frase di ricerca di input
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Accettare l'assorbitore per tutte le pagine
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
// Ottieni i frammenti di testo estratti
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Passa in rassegna i frammenti
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

### Domande frequenti

#### D: Qual è lo scopo del tutorial "Cerca segmenti di testo nella pagina nel file PDF"?

R: Il tutorial "Cerca pagine di segmenti di testo nel file PDF" fornisce una guida completa su come utilizzare la libreria Aspose.PDF per .NET per cercare segmenti di testo specifici su una particolare pagina di un documento PDF. Copre il processo di impostazione di un progetto, caricamento di un documento PDF, ricerca di segmenti di testo e recupero delle relative proprietà utilizzando il codice C#.

#### D: In che modo questo tutorial aiuta nella ricerca di segmenti di testo specifici in un documento PDF?

R: Questo tutorial dimostra il processo di individuazione ed estrazione di segmenti di testo specifici su una particolare pagina di un documento PDF. Seguendo i passaggi e gli esempi di codice forniti, gli utenti possono cercare in modo efficace i segmenti di testo desiderati e recuperare informazioni sulle loro proprietà.

#### D: Quali prerequisiti sono richiesti per seguire questo tutorial?

R: Prima di iniziare il tutorial, dovresti avere una conoscenza di base del linguaggio di programmazione C#. Inoltre, è necessario che sia installata la libreria Aspose.PDF per .NET. È possibile ottenerlo dal sito Web Aspose o installarlo nel progetto utilizzando NuGet.

#### D: Come posso impostare il mio progetto per seguire questo tutorial?

R: Per iniziare, crea un nuovo progetto C# nel tuo ambiente di sviluppo integrato (IDE) preferito e aggiungi un riferimento alla libreria Aspose.PDF per .NET. Ciò ti consentirà di utilizzare le funzionalità della libreria per cercare e lavorare con documenti PDF.

#### D: Posso utilizzare questo tutorial per cercare segmenti di testo specifici su qualsiasi pagina di un PDF?

R: Sì, questo tutorial fornisce istruzioni su come cercare segmenti di testo specifici su una pagina selezionata di un documento PDF. Guida gli utenti nella configurazione di un progetto, nel caricamento di un PDF e nell'utilizzo della libreria Aspose.PDF per individuare e recuperare le proprietà dei segmenti di testo desiderati.

#### D: Come posso specificare il testo che voglio cercare in questo tutorial?

 R: Per specificare il testo che vuoi cercare, crea un file`TextFragmentAbsorber` oggetto e impostarne il parametro di ricerca utilizzando il comando`Text` proprietà. Sostituisci l'impostazione predefinita`"text"` nel codice del tutorial con la frase di ricerca desiderata.

#### D: Come posso recuperare le proprietà dei segmenti di testo estratti?

Dopo aver accettato il`TextFragmentAbsorber` per una pagina specifica del PDF, puoi recuperare i segmenti di testo estratti utilizzando il file`TextFragments` proprietà dell'oggetto assorbente. Ciò fornisce l'accesso a una raccolta di frammenti di testo, ciascuno contenente più segmenti di testo.

#### D: Posso personalizzare il codice per eseguire azioni aggiuntive su ciascun segmento di testo?

R: Assolutamente. Il codice di esempio dell'esercitazione fornisce un ciclo per scorrere i segmenti di testo recuperati. Puoi personalizzare il codice all'interno di questo ciclo per eseguire azioni aggiuntive su ciascun segmento di testo, in base ai requisiti del tuo progetto.

#### D: Come posso salvare il documento PDF modificato dopo aver estratto i segmenti di testo?

R: Questo tutorial si concentra principalmente sulla ricerca di segmenti di testo e sul recupero delle loro proprietà. Se intendi apportare modifiche al PDF, puoi fare riferimento ad altra documentazione Aspose.PDF per imparare come manipolare e salvare il documento in base alle tue esigenze specifiche.