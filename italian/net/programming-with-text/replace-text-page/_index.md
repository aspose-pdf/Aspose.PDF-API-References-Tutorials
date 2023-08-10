---
title: Sostituisci pagina di testo
linktitle: Sostituisci pagina di testo
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come sostituire il testo su una pagina specifica di un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 370
url: /it/net/programming-with-text/replace-text-page/
---

Questo tutorial spiega come utilizzare Aspose.PDF per .NET per sostituire il testo su una pagina specifica di un documento PDF. Il codice sorgente C# fornito illustra il processo passo dopo passo.

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
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
```

 Assicurati di sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

## Passaggio 4: trova e sostituisci il testo

 Creare un`TextFragmentAbsorber` oggetto per trovare tutte le istanze della frase di ricerca di input:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 Sostituire`"text"` con il testo effettivo che desideri cercare e sostituire.

## Passaggio 5: specificare la pagina di destinazione

 Accetta l'assorbitore per una determinata pagina accedendo al file`Pages` raccolta del`pdfDocument` oggetto e chiamando il`Accept` metodo:

```csharp
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
```

 Sostituire`2` con il numero di pagina in cui si desidera sostituire il testo. Nota che i numeri di pagina sono in base zero, quindi`0` rappresenta la prima pagina.

## Passaggio 6: recupera i frammenti di testo estratti

Ottieni i frammenti di testo estratti utilizzando il file`TextFragments` proprietà del`TextFragmentAbsorber` oggetto:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Passaggio 7: scorrere i frammenti di testo

Passa in rassegna i frammenti di testo recuperati e aggiorna il testo e altre proprietà come desiderato:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
    textFragment.Text = "New Phrase";
    textFragment.TextState.Font = FontRepository.FindFont("Verdana");
    textFragment.TextState.FontSize = 22;
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
    textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
```

 Nel frammento di codice sopra, sostituisci`"New Phrase"` con il testo sostitutivo che desideri utilizzare. Puoi anche personalizzare altre proprietà come carattere, dimensione del carattere, colore di primo piano e colore di sfondo.

## Passaggio 8: salva il PDF modificato

 Salva il documento PDF modificato in un nuovo file utilizzando il formato`Save` metodo:

```csharp
pdfDocument.Save(dataDir + "ReplaceTextPage_out.pdf");
```

 Assicurati di sostituire`"ReplaceTextPage_out.pdf"` con il nome del file di output desiderato.

### Esempio di codice sorgente per Sostituisci pagina di testo utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
//Crea un oggetto TextAbsorber per trovare tutte le istanze della frase di ricerca di input
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
//Accetta l'assorbitore per una pagina particolare
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
// Ottieni i frammenti di testo estratti
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Passa attraverso i frammenti
foreach (TextFragment textFragment in textFragmentCollection)
{
	// Aggiorna testo e altre proprietà
	textFragment.Text = "New Phrase";
	textFragment.TextState.Font = FontRepository.FindFont("Verdana");
	textFragment.TextState.FontSize = 22;
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
	textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
pdfDocument.Save(dataDir + "ReplaceTextPage_out.pdf");
```

## Conclusione

Congratulazioni! Hai imparato con successo come sostituire il testo su una pagina specifica di un documento PDF utilizzando Aspose.PDF per .NET. Questo tutorial ha fornito una guida passo passo, dal caricamento del documento al salvataggio della versione modificata. Ora puoi incorporare questo codice nei tuoi progetti C# per automatizzare la sostituzione del testo nei file PDF.