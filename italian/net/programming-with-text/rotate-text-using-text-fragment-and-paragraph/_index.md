---
title: Ruota il testo usando il frammento di testo e il paragrafo
linktitle: Ruota il testo usando il frammento di testo e il paragrafo
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come ruotare il testo utilizzando il frammento di testo e il paragrafo in un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 400
url: /it/net/programming-with-text/rotate-text-using-text-fragment-and-paragraph/
---

Questo tutorial spiega come utilizzare Aspose.PDF per .NET per ruotare il testo utilizzando il frammento di testo e il paragrafo. Il codice sorgente C# fornito illustra il processo passo dopo passo.

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

## Passaggio 3: creare il documento PDF

 Inizializza il`Document` oggetto per creare un nuovo documento PDF:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document();
```

 Assicurati di sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

## Passaggio 4: aggiungi una pagina

 Ottenere una pagina particolare dal documento utilizzando il file`Pages.Add()` metodo:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Passaggio 5: crea frammenti di testo

 Crea multipli`TextFragment` oggetti, impostarne il testo e le proprietà e specificare l'angolo di rotazione:

```csharp
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 315;

TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 270;
```

Regola il testo, l'angolo di rotazione e altre proprietà come desideri.

## Passaggio 6: aggiungi frammenti di testo alla pagina

 Aggiungi i frammenti di testo creati alla pagina aggiungendoli al file`Paragraphs` collezione:

```csharp
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
```

## Passaggio 7: salvare il documento PDF

 Salva il documento PDF modificato in un file utilizzando il formato`Save` metodo:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

 Assicurati di sostituire`"TextFragmentTests_Rotated3_out.pdf"` con il nome del file di output desiderato.

### Codice sorgente di esempio per Ruotare il testo utilizzando il frammento di testo e il paragrafo utilizzando Aspose.PDF per .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Inizializza oggetto documento
Document pdfDocument = new Document();
// Ottieni una pagina particolare
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Crea un frammento di testo
TextFragment textFragment1 = new TextFragment("main text");
// Imposta le proprietà del testo
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Crea un frammento di testo
TextFragment textFragment2 = new TextFragment("rotated text");
// Imposta le proprietà del testo
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Imposta la rotazione
textFragment2.TextState.Rotation = 315;
// Crea un frammento di testo
TextFragment textFragment3 = new TextFragment("rotated text");
// Imposta le proprietà del testo
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Imposta la rotazione
textFragment3.TextState.Rotation = 270;
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
// Salva documento
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

## Conclusione

Congratulazioni! Hai imparato con successo come ruotare il testo utilizzando frammenti di testo e paragrafi in un documento PDF utilizzando Aspose.PDF per .NET. Questo tutorial ha fornito una guida passo passo, dalla creazione del documento al salvataggio della versione modificata. Ora puoi incorporare questo codice nei tuoi progetti C# per manipolare la rotazione del testo nei file PDF.