---
title: Cerca testo e aggiungi collegamento ipertestuale
linktitle: Cerca testo e aggiungi collegamento ipertestuale
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come cercare testo in un PDF, aggiungere collegamenti ipertestuali al testo trovato e salvare il documento modificato utilizzando Aspose.PDF per .NET.
type: docs
weight: 450
url: /it/net/programming-with-text/search-text-and-add-hyperlink/
---
Questo tutorial spiega come utilizzare Aspose.PDF per .NET per cercare testo specifico in un documento PDF, aggiungere un collegamento ipertestuale al testo trovato e salvare il documento modificato. Il codice sorgente C# fornito illustra il processo passo dopo passo.

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

## Passaggio 4: crea un TextFragmentAbsorber

 Creare un`TextFragmentAbsorber` oggetto per trovare tutte le istanze della frase di ricerca di input:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
```

 Sostituire`"\\d{4}-\\d{4}"` con il modello di espressione regolare desiderato.

## Passaggio 5: attiva la ricerca con espressioni regolari

 Abilita la ricerca di espressioni regolari impostando il file`TextSearchOptions` proprietà dell'assorbitore:

```csharp
absorber.TextSearchOptions = new TextSearchOptions(true);
```

## Passaggio 6: apri e rilega il documento PDF

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
    // Crea un rettangolo in base alla posizione del frammento di testo
    System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
        (int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
        (int)Math.Round(textFragment.Rectangle.Height + 1));
    //Aggiungi un collegamento Web al rettangolo
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

### Codice sorgente di esempio per cercare testo e aggiungere collegamento ipertestuale utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crea un oggetto assorbitore per trovare tutte le istanze della frase di ricerca di input
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
// Abilita la ricerca con espressioni regolari
absorber.TextSearchOptions = new TextSearchOptions(true);
// Apri documento
PdfContentEditor editor = new PdfContentEditor();
// Associa il file PDF di origine
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
// Accetta l'assorbitore per la pagina
editor.Document.Pages[1].Accept(absorber);
int[] dashArray = { };
String[] LEArray = { };
System.Drawing.Color blue = System.Drawing.Color.Blue;
// Passa in rassegna i frammenti
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

Congratulazioni! Hai imparato con successo come cercare testo specifico in un documento PDF, aggiungere collegamenti ipertestuali al testo trovato e salvare il documento modificato utilizzando Aspose.PDF per .NET. Questo tutorial fornisce una guida passo passo, dall'impostazione del progetto all'esecuzione delle azioni richieste. Ora puoi incorporare questo codice nei tuoi progetti C# per manipolare il testo e aggiungere collegamenti ipertestuali nei file PDF.

### Domande frequenti

#### D: Qual è lo scopo del tutorial "Cerca testo e aggiungi collegamento ipertestuale"?

R: Il tutorial "Cerca testo e aggiungi collegamento ipertestuale" mira a dimostrare come utilizzare la libreria Aspose.PDF per .NET per cercare testo specifico all'interno di un documento PDF, aggiungere collegamenti ipertestuali al testo trovato e quindi salvare il documento modificato. L'esercitazione fornisce una guida completa ed esempi di codice C# per illustrare il processo passo passo.

#### D: In che modo questo tutorial aiuta ad aggiungere collegamenti ipertestuali a testo specifico in un documento PDF?

R: Questo tutorial ti guida attraverso il processo di utilizzo della libreria Aspose.PDF per individuare testo specifico in un documento PDF, applicare un collegamento ipertestuale al testo identificato e salvare il PDF modificato. Copre passaggi essenziali come l'impostazione del progetto, il caricamento del documento, l'abilitazione della ricerca di espressioni regolari e l'aggiunta di collegamenti ipertestuali al testo trovato.

#### D: Quali prerequisiti sono necessari per seguire questo tutorial?

R: Prima di iniziare, dovresti avere una conoscenza di base del linguaggio di programmazione C#. Inoltre, è necessario che sia installata la libreria Aspose.PDF per .NET, che può essere ottenuta dal sito Web Aspose o installata utilizzando NuGet nel progetto.

#### D: Come posso impostare il mio progetto per seguire questo tutorial?

R: Inizia creando un nuovo progetto C# nel tuo ambiente di sviluppo integrato (IDE) preferito. Quindi, aggiungi un riferimento alla libreria Aspose.PDF per .NET, che ti consentirà di utilizzare le funzionalità della libreria nel tuo progetto.

#### D: Posso aggiungere collegamenti ipertestuali a testo specifico utilizzando questo tutorial?

R: Sì, questo tutorial si concentra specificamente sull'aggiunta di collegamenti ipertestuali a testo specifico in un documento PDF. Dimostra come trovare ed estrarre il testo desiderato utilizzando espressioni regolari, creare collegamenti ipertestuali associati ai frammenti di testo e salvare il PDF modificato.

#### D: Come posso definire il testo che voglio cercare e a cui aggiungere un collegamento ipertestuale?

 R: Per specificare il testo che desideri cercare e a cui aggiungere un collegamento ipertestuale, crea un file`TextFragmentAbsorber` oggetto e impostarne il modello utilizzando il comando`Text` parametro. Sostituisci il modello predefinito`"\\d{4}-\\d{4}"` nel codice del tutorial con il modello di espressione regolare desiderato.

#### D: Come posso abilitare la ricerca di testo tramite espressioni regolari?

 R: La ricerca delle espressioni regolari viene abilitata creando un file`TextSearchOptions` oggetto e impostandone il valore su`true` . Assegna questo oggetto a`TextSearchOptions` proprietà del`TextFragmentAbsorber` esempio. Ciò garantisce che il modello di espressione regolare venga applicato durante la ricerca di testo.

#### D: Come posso aggiungere collegamenti ipertestuali al testo trovato?

 R: Dopo aver identificato i frammenti di testo utilizzando il file`TextFragmentAbsorber` , l'esercitazione fornisce un ciclo per scorrere questi frammenti. Per ogni frammento di testo, il tutorial mostra come impostare il colore del testo su blu e creare un collegamento ipertestuale utilizzando il file`CreateWebLink` metodo.

#### D: Quali sono i passaggi per salvare il PDF modificato con collegamenti ipertestuali?

 R: Dopo aver aggiunto i collegamenti ipertestuali ai frammenti di testo desiderati, utilizzare il file`PdfContentEditor` classe per salvare il documento modificato. Il codice di esempio del tutorial mostra come salvare il PDF modificato, chiudere l'editor e visualizzare un messaggio di successo.