---
title: Cerca e ottieni testo tutto
linktitle: Cerca e ottieni testo tutto
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come cercare e ottenere testo da tutte le pagine di un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 420
url: /it/net/programming-with-text/search-and-get-text-all/
---
Questo tutorial spiega come utilizzare Aspose.PDF per .NET per cercare e ottenere testo da tutte le pagine di un documento PDF. Il codice sorgente C# fornito illustra il processo passo dopo passo.

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
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 Assicurati di sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

## Passaggio 4: cerca ed estrai il testo

 Creare un`TextFragmentAbsorber` oggetto per trovare tutte le istanze della frase di ricerca di input:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 Sostituire`"text"` con il testo effettivo che desideri cercare.

## Passaggio 5: cerca su tutte le pagine

Accetta l'assorbitore per tutte le pagine del documento:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Passaggio 6: ottieni i frammenti di testo estratti

Ottieni i frammenti di testo estratti utilizzando il file`TextFragments` proprietà del`TextFragmentAbsorber` oggetto:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Passaggio 7: scorrere i frammenti di testo

Passa in rassegna i frammenti di testo ottenuti e accedi alle loro proprietà:

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

### Codice sorgente di esempio per Cerca e ottieni testo tutto utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
// Crea un oggetto TextAbsorber per trovare tutte le istanze della frase di ricerca di input
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
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

Congratulazioni! Hai imparato con successo come cercare e ottenere testo da tutte le pagine di un documento PDF utilizzando Aspose.PDF per .NET. Questo tutorial ha fornito una guida passo passo, dal caricamento del documento all'accesso ai frammenti di testo estratti. Ora puoi incorporare questo codice nei tuoi progetti C# per analizzare ed elaborare il contenuto di testo nei file PDF.

### Domande frequenti

#### D: Qual è lo scopo del tutorial "Cerca e ottieni tutto il testo"?

R: Il tutorial "Cerca e ottieni tutto il testo" dimostra come utilizzare la libreria Aspose.PDF per .NET per cercare ed estrarre testo da tutte le pagine di un documento PDF. L'esercitazione fornisce istruzioni dettagliate insieme al codice C# di esempio per eseguire la ricerca e il recupero del testo.

#### D: In che modo questo tutorial aiuta a estrarre testo da documenti PDF?

R: Questo tutorial ti guida attraverso il processo di estrazione del testo da tutte le pagine di un documento PDF. Utilizza la libreria Aspose.PDF per individuare frasi di testo specifiche e recuperare informazioni associate, come posizione, proprietà dei caratteri e colori.

#### D: Quali sono i prerequisiti per seguire questo tutorial?

R: Prima di iniziare questo tutorial, dovresti avere una conoscenza di base del linguaggio di programmazione C#. Inoltre, è necessario che sia installata la libreria Aspose.PDF per .NET. Puoi ottenerlo dal sito Web Aspose o utilizzare NuGet per integrarlo nel tuo progetto.

#### D: Come posso impostare il mio progetto per seguire questo tutorial?

R: Per iniziare, crea un nuovo progetto C# nel tuo ambiente di sviluppo integrato (IDE) preferito e aggiungi un riferimento alla libreria Aspose.PDF per .NET. Ciò ti consentirà di accedere alle funzionalità della libreria nel tuo progetto.

#### D: Come posso cercare un testo specifico all'interno di un documento PDF?

R: Puoi usare il`TextFragmentAbsorber`classe per trovare istanze di una frase di ricerca specifica all'interno del documento PDF. Creando un'istanza di questa classe e specificando il testo di destinazione, puoi acquisire tutte le occorrenze di quel testo.

#### D: Posso cercare testo in tutte le pagine del documento PDF?

 R: Sì, il tutorial mostra come cercare testo in tutte le pagine del documento PDF. IL`pdfDocument.Pages.Accept(textFragmentAbsorber)` Il metodo viene utilizzato per accettare l'assorbitore per tutte le pagine, consentendo di cercare il testo desiderato su ogni pagina.

#### D: Come posso accedere ai frammenti di testo estratti?

 R: Dopo aver cercato il testo, puoi accedere ai frammenti di testo estratti utilizzando il file`TextFragments` proprietà del`TextFragmentAbsorber` oggetto. Questa proprietà fornisce l'accesso a una raccolta di`TextFragment` oggetti che contengono il testo estratto e le relative informazioni.

#### D: Quali informazioni posso recuperare dai frammenti di testo estratti?

R: Puoi recuperare vari dettagli dai frammenti di testo estratti, come il contenuto effettivo del testo, la posizione (coordinate X e Y), le informazioni sui caratteri (nome, dimensione, colore, ecc.) e altro. Il codice di esempio dell'esercitazione illustra come accedere e stampare questi dettagli.

#### D: Posso eseguire ulteriori azioni sui frammenti di testo estratti?

R: Assolutamente. Una volta estratti i frammenti di testo, puoi modificare il codice all'interno del ciclo per eseguire azioni personalizzate su ciascun frammento. Ciò potrebbe includere il salvataggio del testo estratto, l'analisi dei modelli di testo o l'applicazione di modifiche alla formattazione.