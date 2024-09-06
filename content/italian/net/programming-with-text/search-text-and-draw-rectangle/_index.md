---
title: Cerca testo e disegna rettangolo
linktitle: Cerca testo e disegna rettangolo
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come cercare testo in un PDF, disegnare rettangoli attorno al testo trovato e salvare il documento modificato utilizzando Aspose.PDF per .NET.
type: docs
weight: 460
url: /it/net/programming-with-text/search-text-and-draw-rectangle/
---
Questo tutorial spiega come usare Aspose.PDF per .NET per cercare testo specifico in un documento PDF, disegnare un rettangolo attorno al testo trovato e salvare il documento modificato. Il codice sorgente C# fornito illustra il processo passo dopo passo.

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
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
```

## Passaggio 3: impostare il percorso della directory del documento

 Imposta il percorso della directory del documento utilizzando`dataDir` variabile:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory del documento.

## Passaggio 4: caricare il documento PDF

 Caricare il documento PDF utilizzando`Document` classe:

```csharp
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 Sostituire`"SearchAndGetTextFromAll.pdf"` con il nome effettivo del file PDF.

## Passaggio 5: creare un TextFragmentAbsorber

 Crea un`TextFragmentAbsorber` oggetto per trovare tutte le istanze della frase di ricerca di input:

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

 Sostituire`@"[\S]+"` con il modello di espressione regolare desiderato.

## Passaggio 6: abilitare la ricerca tramite espressioni regolari

 Abilita la ricerca di espressioni regolari impostando`TextSearchOptions` proprietà dell'assorbitore:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

## Passaggio 7: Cerca in tutte le pagine

Accetta l'assorbitore per tutte le pagine del documento:

```csharp
document.Pages.Accept(textAbsorber);
```

## Passaggio 8: Disegna un rettangolo attorno al testo trovato

 Crea un`PdfContentEditor` oggetto e scorrere i frammenti di testo recuperati, disegnando un rettangolo attorno a ciascun segmento di testo:

```csharp
var editor = new PdfContentEditor(document);
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
    foreach (TextSegment textSegment in textFragment.Segments)
    {
        DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
    }
}
```

## Passaggio 9: Salvare il documento modificato

Salvare il documento modificato:

```csharp
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
```

 Assicurati di sostituire`"SearchTextAndDrawRectangle_out.pdf"` con il nome del file di output desiderato.

### Esempio di codice sorgente per Cerca testo e disegna rettangolo usando Aspose.PDF per .NET 
```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
// Crea un oggetto TextAbsorber per trovare tutte le frasi che corrispondono all'espressione regolare
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
document.Pages.Accept(textAbsorber); 
var editor = new PdfContentEditor(document); 
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
			DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
	}
}
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
Console.WriteLine("\nRectangle drawn successfully on searched text.\nFile saved at " + dataDir);
```

## Conclusione

Congratulazioni! Hai imparato con successo come cercare testo specifico in un documento PDF, disegnare un rettangolo attorno al testo trovato e salvare il documento modificato utilizzando Aspose.PDF per .NET. Questo tutorial ha fornito una guida passo passo, dall'impostazione del progetto all'esecuzione delle azioni richieste. Ora puoi incorporare questo codice nei tuoi progetti C# per manipolare il testo e disegnare rettangoli nei file PDF.

### Domande frequenti

#### D: Qual è lo scopo del tutorial "Cerca testo e disegna rettangolo"?

R: Il tutorial "Cerca testo e disegna rettangolo" mira a guidare gli utenti attraverso il processo di utilizzo della libreria Aspose.PDF per .NET per cercare testo specifico all'interno di un documento PDF, disegnare rettangoli attorno ai segmenti di testo trovati e salvare il documento modificato. Il tutorial fornisce istruzioni dettagliate ed esempi di codice C# per illustrare ogni passaggio del processo.

#### D: In che modo questo tutorial aiuta a disegnare rettangoli attorno a un testo specifico in un documento PDF?

R: Questo tutorial fornisce una guida completa su come individuare e disegnare rettangoli attorno a specifici segmenti di testo all'interno di un documento PDF. Illustra il processo di impostazione di un progetto, caricamento di un documento PDF, abilitazione della ricerca di espressioni regolari, disegno di rettangoli attorno a segmenti di testo trovati e salvataggio del PDF modificato.

#### D: Quali prerequisiti sono richiesti per seguire questo tutorial?

R: Prima di iniziare il tutorial, dovresti avere una conoscenza di base del linguaggio di programmazione C#. Inoltre, devi avere installata la libreria Aspose.PDF per .NET. Puoi ottenerla dal sito web di Aspose o installarla nel tuo progetto usando NuGet.

#### D: Come posso impostare il mio progetto in modo che segua questo tutorial?

R: Inizia creando un nuovo progetto C# nel tuo ambiente di sviluppo integrato (IDE) preferito. Quindi, aggiungi un riferimento alla libreria Aspose.PDF per .NET al tuo progetto. Ciò ti consentirà di usare la funzionalità della libreria per manipolare documenti PDF.

#### D: Posso disegnare rettangoli attorno a un testo specifico usando questo tutorial?

R: Sì, il tutorial si concentra sul disegno di rettangoli attorno a specifici segmenti di testo all'interno di un documento PDF. Dimostra come individuare il testo desiderato utilizzando espressioni regolari, creare rettangoli attorno ai segmenti di testo identificati e salvare il PDF modificato.

#### D: Come posso specificare il testo che voglio cercare e disegnare dei rettangoli attorno a esso?

 A: Per specificare il testo che vuoi cercare e disegnare rettangoli attorno, crea un`TextFragmentAbsorber` oggetto e imposta il suo modello utilizzando il`Text` parametro. Sostituisci il modello predefinito`@"[\S]+"` nel codice del tutorial con il modello di espressione regolare desiderato.

#### D: Come posso abilitare la ricerca tramite espressioni regolari nel testo?

 A: La ricerca di espressioni regolari è abilitata creando un`TextSearchOptions` oggetto e impostandone il valore su`true` Assegna questo oggetto al`TextSearchOptions` proprietà del`TextFragmentAbsorber` istanza. Ciò garantisce che il modello di espressione regolare venga utilizzato durante la ricerca di testo.

#### D: Come faccio a disegnare dei rettangoli attorno al testo trovato?

 A: Dopo aver identificato i segmenti di testo utilizzando il`TextFragmentAbsorber` , il tutorial fornisce un ciclo per scorrere questi segmenti. Per ogni segmento di testo, il tutorial dimostra come creare un rettangolo attorno ad esso utilizzando il`DrawBox` e specificare l'aspetto del rettangolo.

#### D: Quali sono i passaggi per salvare il PDF modificato con i rettangoli disegnati?

A: Dopo aver disegnato i rettangoli attorno ai segmenti di testo desiderati, utilizzare il`Document` di classe`Save` metodo per salvare il documento modificato. Il codice di esempio del tutorial mostra come salvare il PDF modificato e visualizzare un messaggio di successo.

#### D: Posso personalizzare l'aspetto dei rettangoli disegnati?

 A: Sì, puoi personalizzare l'aspetto dei rettangoli disegnati. Nel codice di esempio del tutorial, il`DrawBox` Il metodo viene utilizzato per creare rettangoli. È possibile modificare proprietà quali colore, stile e spessore per personalizzare l'aspetto dei rettangoli disegnati.