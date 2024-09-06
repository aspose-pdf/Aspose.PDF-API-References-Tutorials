---
title: Cerca e ottieni la pagina di testo nel file PDF
linktitle: Cerca e ottieni la pagina di testo nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come cercare e ottenere testo da una pagina specifica in un file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 430
url: /it/net/programming-with-text/search-and-get-text-page/
---
Questo tutorial spiega come usare Aspose.PDF per .NET per cercare e ottenere testo da una pagina specifica in un file PDF. Il codice sorgente C# fornito illustra il processo passo dopo passo.

## Prerequisiti

Prima di procedere con il tutorial, assicurati di avere quanto segue:

- Conoscenza di base del linguaggio di programmazione C#.
- Aspose.PDF per la libreria .NET installata. Puoi ottenerla dal sito web di Aspose o usare NuGet per installarla nel tuo progetto.

## Passaggio 1: impostare il progetto

Inizia creando un nuovo progetto C# nel tuo ambiente di sviluppo integrato (IDE) preferito e aggiungi un riferimento alla libreria Aspose.PDF per .NET.

## Passaggio 2: importare gli spazi dei nomi necessari

Aggiungere le seguenti direttive using all'inizio del file C# per importare gli spazi dei nomi richiesti:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Passaggio 3: caricare il documento PDF

 Imposta il percorso della directory del documento PDF e carica il documento utilizzando`Document` classe:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
```

 Assicurati di sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory del documento.

## Passaggio 4: cercare ed estrarre il testo da una pagina

 Crea un`TextFragmentAbsorber`oggetto per trovare tutte le istanze della frase di ricerca di input su una pagina specifica:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
```

 Sostituire`"Figure"` con il testo effettivo che vuoi cercare.

## Passaggio 5: Cerca in una pagina specifica

Accetta l'assorbitore per una pagina specifica del documento:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Passaggio 6: ottenere frammenti di testo estratti

Ottieni i frammenti di testo estratti utilizzando`TextFragments` proprietà del`TextFragmentAbsorber` oggetto:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Passaggio 7: scorrere i frammenti e i segmenti di testo

Esegui un ciclo attraverso i frammenti di testo getd e i loro segmenti e accedi alle loro proprietà:

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

### Esempio di codice sorgente per la pagina Cerca e ottieni testo utilizzando Aspose.PDF per .NET 
```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
// Crea un oggetto TextAbsorber per trovare tutte le istanze della frase di ricerca di input
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
// Accetta l'assorbitore per tutte le pagine
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Ottieni i frammenti di testo estratti
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Fai un giro tra i frammenti
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

Congratulazioni! Hai imparato con successo come cercare e ottenere testo da una pagina specifica di un documento PDF usando Aspose.PDF per .NET. Questo tutorial ha fornito una guida passo passo, dal caricamento del documento all'accesso ai segmenti di testo estratti. Ora puoi incorporare

### Domande frequenti

#### D: Qual è lo scopo del tutorial "Cerca e ottieni testo nella pagina"?

R: Il tutorial "Search And Get Text Page" è progettato per illustrare come usare la libreria Aspose.PDF per .NET per cercare e recuperare testo da una pagina specifica all'interno di un file PDF. Il tutorial fornisce istruzioni dettagliate e codice C# di esempio per dimostrare il processo.

#### D: In che modo questo tutorial aiuta a estrarre il testo da una pagina specifica di un documento PDF?

A: Questo tutorial ti guida attraverso il processo di estrazione del testo da una pagina specifica di un documento PDF utilizzando la libreria Aspose.PDF. Descrive i passaggi necessari e fornisce codice C# per cercare una frase di testo specificata nella pagina selezionata e recuperare i segmenti di testo associati.

#### D: Quali sono i prerequisiti per seguire questo tutorial?

R: Prima di iniziare questo tutorial, dovresti avere una conoscenza di base del linguaggio di programmazione C#. Inoltre, devi avere installata la libreria Aspose.PDF per .NET. Puoi ottenerla dal sito web di Aspose o usare NuGet per integrarla nel tuo progetto.

#### D: Come posso impostare il mio progetto in modo che segua questo tutorial?

R: Per iniziare, crea un nuovo progetto C# nel tuo ambiente di sviluppo integrato (IDE) preferito e aggiungi un riferimento alla libreria Aspose.PDF per .NET. Ciò ti consentirà di utilizzare le capacità della libreria nel tuo progetto.

#### D: Posso cercare del testo in una pagina specifica del documento PDF?

R: Sì, questo tutorial mostra come cercare testo in una pagina specifica di un documento PDF. Comporta l'utilizzo di`TextFragmentAbsorber` classe per individuare le istanze di una particolare frase di testo nella pagina scelta.

#### D: Come posso accedere ai segmenti di testo estratti dalla pagina specifica?

 A: Dopo aver cercato il testo nella pagina designata, puoi accedere ai segmenti di testo estratti utilizzando`TextSegments` proprietà del`TextFragment` oggetto. Questa proprietà fornisce l'accesso a una raccolta di`TextSegment` oggetti che contengono il testo estratto e le informazioni correlate.

#### D: Quali informazioni posso recuperare dai segmenti di testo estratti?

R: Puoi recuperare vari dettagli dai segmenti di testo estratti, tra cui il contenuto del testo, la posizione (coordinate X e Y), le informazioni sul font (nome, dimensione, colore, ecc.) e altro. Il codice di esempio del tutorial mostra come accedere e stampare questi dettagli per ogni segmento di testo.

#### D: Posso eseguire azioni personalizzate sui segmenti di testo estratti?

R: Certamente. Una volta estratti i segmenti di testo, puoi personalizzare il codice all'interno del ciclo per eseguire azioni aggiuntive su ogni segmento. Ciò potrebbe includere il salvataggio del testo estratto, l'analisi di pattern di testo o l'applicazione di modifiche di formattazione.