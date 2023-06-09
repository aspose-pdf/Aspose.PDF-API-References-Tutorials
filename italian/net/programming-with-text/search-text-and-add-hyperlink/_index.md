---
title: Cerca testo e aggiungi collegamento ipertestuale
linktitle: Cerca testo e aggiungi collegamento ipertestuale
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come cercare testo in un PDF, aggiungere collegamenti ipertestuali al testo trovato e salvare il documento modificato utilizzando Aspose.PDF per .NET.
type: docs
weight: 450
url: /it/net/programming-with-text/search-text-and-add-hyperlink/
---

Questo tutorial spiega come utilizzare Aspose.PDF per .NET per cercare testo specifico in un documento PDF, aggiungere un collegamento ipertestuale al testo trovato e salvare il documento modificato. Il codice sorgente C# fornito illustra il processo passo dopo passo.

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
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Text;
```

## Passaggio 3: impostare il percorso della directory dei documenti

 Imposta il percorso della directory dei documenti utilizzando il file`dataDir` variabile:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

## Passaggio 4: creare un TextFragmentAbsorber

 Creare un`TextFragmentAbsorber` oggetto per trovare tutte le istanze della frase di ricerca di input:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
```

 Sostituire`"\\d{4}-\\d{4}"` con il modello di espressione regolare desiderato.

## Passaggio 5: abilita la ricerca delle espressioni regolari

Abilita la ricerca di espressioni regolari impostando il`TextSearchOptions` proprietà dell'assorbitore:

```csharp
absorber.TextSearchOptions = new TextSearchOptions(true);
```

## Passaggio 6: aprire e rilegare il documento PDF

 Creare un`PdfContentEditor` oggetto e associarlo al file PDF di origine:

```csharp
PdfContentEditor editor = new PdfContentEditor();
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
```

 Sostituire`"SearchRegularExpressionPage.pdf"` con il nome effettivo del file PDF.

## Passaggio 7: accettare l'assorbitore per la pagina

Accettare l'assorbitore per la pagina desiderata del documento:

```csharp
editor.Document.Pages[1].Accept(absorber);
```

 Sostituire`1` con il numero di pagina desiderato.

## Passaggio 8: aggiungi collegamenti ipertestuali al testo trovato

Passa in rassegna i frammenti di testo recuperati e aggiungi loro collegamenti ipertestuali:

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
    // Crea un rettangolo basato sulla posizione del frammento di testo
    System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
        (int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
        (int)Math.Round(textFragment.Rectangle.Height + 1));
    // Aggiungere un collegamento Web al rettangolo
    editor.CreateWebLink(rect, "http://www.aspose.com", 1, System.Drawing.Color.Blue);
}
```

 Sostituire`"http://www.aspose.com"` con l'URL del collegamento ipertestuale desiderato.

## Passaggio 9: salva e chiudi il documento modificato

Salva il documento modificato e chiudi l'editor:

```csharp
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

 Assicurati di sostituire`"SearchTextAndAddHyperlink_out.pdf"` con il nome del file di output desiderato.

### Esempio di codice sorgente per Cerca testo e aggiungi collegamento ipertestuale utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crea un oggetto assorbitore per trovare tutte le istanze della frase di ricerca di input
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
// Abilita la ricerca di espressioni regolari
absorber.TextSearchOptions = new TextSearchOptions(true);
// Apri documento
PdfContentEditor editor = new PdfContentEditor();
//Associa il file PDF di origine
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
// Accetta l'assorbitore per la pagina
editor.Document.Pages[1].Accept(absorber);
int[] dashArray = { };
String[] LEArray = { };
System.Drawing.Color blue = System.Drawing.Color.Blue;
// Passa attraverso i frammenti
foreach (TextFragment textFragment in absorber.TextFragments)
{
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
		(int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
		(int)Math.Round(textFragment.Rectangle.Height + 1));
	Enum[] actionName = new Enum[2] { Aspose.Pdf.Annotations.PredefinedAction.Document_AttachFile, Aspose.Pdf.Annotations.PredefinedAction.Document_ExtractPages };
	editor.CreateWebLink(rect, "http:// Www.aspose.com", 1, blu, actionName);
	editor.CreateLine(rect, "", (float)textFragment.Rectangle.LLX + 1, (float)textFragment.Rectangle.LLY - 1,
		(float)textFragment.Rectangle.URX, (float)textFragment.Rectangle.LLY - 1, 1, 1, blue, "S", dashArray, LEArray);
}
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

## Conclusione

Congratulazioni! Hai imparato con successo come cercare un testo specifico in un documento PDF, aggiungere collegamenti ipertestuali al testo trovato e salvare il documento modificato utilizzando Aspose.PDF per .NET. Questo tutorial ha fornito una guida dettagliata, dall'impostazione del progetto all'esecuzione delle azioni richieste. Ora puoi incorporare questo codice nei tuoi progetti C# per manipolare il testo e aggiungere collegamenti ipertestuali nei file PDF.