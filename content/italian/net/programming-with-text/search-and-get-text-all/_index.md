---
title: Cerca e ottieni tutto il testo
linktitle: Cerca e ottieni tutto il testo
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come cercare e ottenere testo da tutte le pagine di un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 420
url: /it/net/programming-with-text/search-and-get-text-all/
---
Questo tutorial spiega come usare Aspose.PDF per .NET per cercare e ottenere testo da tutte le pagine di un documento PDF. Il codice sorgente C# fornito illustra il processo passo dopo passo.

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
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 Assicurati di sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory del documento.

## Passaggio 4: Cerca ed estrai il testo

 Crea un`TextFragmentAbsorber` oggetto per trovare tutte le istanze della frase di ricerca di input:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 Sostituire`"text"` con il testo effettivo che vuoi cercare.

## Passaggio 5: Cerca in tutte le pagine

Accetta l'assorbitore per tutte le pagine del documento:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Passaggio 6: ottenere frammenti di testo estratti

 Ottieni i frammenti di testo estratti utilizzando`TextFragments` proprietà del`TextFragmentAbsorber` oggetto:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Passaggio 7: scorrere i frammenti di testo

Esegui un ciclo attraverso i frammenti di testo getd e accedi alle loro proprietà:

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

### Esempio di codice sorgente per Search And Get Text All utilizzando Aspose.PDF per .NET 
```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
// Crea un oggetto TextAbsorber per trovare tutte le istanze della frase di ricerca di input
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Accetta l'assorbitore per tutte le pagine
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Ottieni i frammenti di testo estratti
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Fai un giro tra i frammenti
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

Congratulazioni! Hai imparato con successo come cercare e ottenere testo da tutte le pagine di un documento PDF usando Aspose.PDF per .NET. Questo tutorial ha fornito una guida passo passo, dal caricamento del documento all'accesso ai frammenti di testo estratti. Ora puoi incorporare questo codice nei tuoi progetti C# per analizzare ed elaborare il contenuto di testo nei file PDF.

### Domande frequenti

#### D: Qual è lo scopo del tutorial "Cerca e ottieni tutto il testo"?

R: Il tutorial "Search And Get Text All" illustra come utilizzare la libreria Aspose.PDF per .NET per cercare ed estrarre testo da tutte le pagine di un documento PDF. Il tutorial fornisce istruzioni dettagliate insieme a codice C# di esempio per eseguire la ricerca e il recupero di testo.

#### D: In che modo questo tutorial aiuta a estrarre testo dai documenti PDF?

R: Questo tutorial ti guida attraverso il processo di estrazione del testo da tutte le pagine di un documento PDF. Utilizza la libreria Aspose.PDF per individuare frasi di testo specifiche e recuperare informazioni associate, come posizione, proprietà del font e colori.

#### D: Quali sono i prerequisiti per seguire questo tutorial?

R: Prima di iniziare questo tutorial, dovresti avere una conoscenza di base del linguaggio di programmazione C#. Inoltre, devi avere installata la libreria Aspose.PDF per .NET. Puoi ottenerla dal sito web di Aspose o usare NuGet per integrarla nel tuo progetto.

#### D: Come posso impostare il mio progetto in modo che segua questo tutorial?

R: Per iniziare, crea un nuovo progetto C# nel tuo ambiente di sviluppo integrato (IDE) preferito e aggiungi un riferimento alla libreria Aspose.PDF per .NET. Ciò ti consentirà di accedere alle funzionalità della libreria nel tuo progetto.

#### D: Come faccio a cercare un testo specifico all'interno di un documento PDF?

 A: Puoi usare il`TextFragmentAbsorber`classe per trovare istanze di una frase di ricerca specifica all'interno del documento PDF. Creando un'istanza di questa classe e specificando il testo di destinazione, puoi catturare tutte le occorrenze di quel testo.

#### D: Posso cercare testo in tutte le pagine del documento PDF?

 A: Sì, il tutorial mostra come cercare testo in tutte le pagine del documento PDF.`pdfDocument.Pages.Accept(textFragmentAbsorber)` Il metodo viene utilizzato per accettare l'assorbitore per tutte le pagine, consentendo di cercare il testo desiderato in ogni pagina.

#### D: Come posso accedere ai frammenti di testo estratti?

 A: Dopo aver cercato il testo, puoi accedere ai frammenti di testo estratti utilizzando`TextFragments` proprietà del`TextFragmentAbsorber` oggetto. Questa proprietà fornisce l'accesso a una raccolta di`TextFragment` oggetti che contengono il testo estratto e le informazioni correlate.

#### D: Quali informazioni posso recuperare dai frammenti di testo estratti?

R: Puoi recuperare vari dettagli dai frammenti di testo estratti, come il contenuto effettivo del testo, la posizione (coordinate X e Y), le informazioni sul font (nome, dimensione, colore, ecc.) e altro. Il codice di esempio del tutorial mostra come accedere e stampare questi dettagli.

#### D: Posso eseguire ulteriori azioni sui frammenti di testo estratti?

R: Assolutamente. Una volta estratti i frammenti di testo, puoi modificare il codice all'interno del ciclo per eseguire azioni personalizzate su ogni frammento. Ciò potrebbe includere il salvataggio del testo estratto, l'analisi di pattern di testo o l'applicazione di modifiche di formattazione.