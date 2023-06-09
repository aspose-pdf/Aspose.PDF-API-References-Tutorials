---
title: Cerca testo e disegna rettangolo
linktitle: Cerca testo e disegna rettangolo
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come cercare testo in un PDF, disegnare rettangoli attorno al testo trovato e salvare il documento modificato utilizzando Aspose.PDF per .NET.
type: docs
weight: 460
url: /it/net/programming-with-text/search-text-and-draw-rectangle/
---

Questo tutorial spiega come utilizzare Aspose.PDF per .NET per cercare un testo specifico in un documento PDF, disegnare un rettangolo attorno al testo trovato e salvare il documento modificato. Il codice sorgente C# fornito illustra il processo passo dopo passo.

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
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
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
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 Sostituire`"SearchAndGetTextFromAll.pdf"` con il nome effettivo del file PDF.

## Passaggio 5: creare un TextFragmentAbsorber

 Creare un`TextFragmentAbsorber` oggetto per trovare tutte le istanze della frase di ricerca di input:

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

 Sostituire`@"[\S]+"` con il modello di espressione regolare desiderato.

## Passaggio 6: abilita la ricerca delle espressioni regolari

Abilita la ricerca di espressioni regolari impostando il`TextSearchOptions` proprietà dell'assorbitore:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

## Passaggio 7: ricerca su tutte le pagine

Accetta l'assorbitore per tutte le pagine del documento:

```csharp
document.Pages.Accept(textAbsorber);
```

## Passaggio 8: Disegna un rettangolo attorno al testo trovato

 Creare un`PdfContentEditor` oggetto e scorrere i frammenti di testo recuperati, disegnando un rettangolo attorno a ciascun segmento di testo:

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

## Passaggio 9: salvare il documento modificato

Salva il documento modificato:

```csharp
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
```

 Assicurati di sostituire`"SearchTextAndDrawRectangle_out.pdf"` con il nome del file di output desiderato.

### Esempio di codice sorgente per Cerca testo e disegna rettangolo utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
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

Congratulazioni! Hai imparato con successo come cercare un testo specifico in un documento PDF, disegnare un rettangolo attorno al testo trovato e salvare il documento modificato utilizzando Aspose.PDF per .NET. Questo tutorial ha fornito una guida dettagliata, dall'impostazione del progetto all'esecuzione delle azioni richieste. Ora puoi incorporare questo codice nei tuoi progetti C# per manipolare il testo e disegnare rettangoli nei file PDF.