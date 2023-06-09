---
title: Ruota il testo usando il frammento di testo
linktitle: Ruota il testo usando il frammento di testo
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come ruotare il testo utilizzando frammenti di testo in un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 390
url: /it/net/programming-with-text/rotate-text-using-text-fragment/
---

Questo tutorial spiega come utilizzare Aspose.PDF per .NET per ruotare il testo utilizzando frammenti di testo. Il codice sorgente C# fornito illustra il processo passo dopo passo.

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
using Aspose.Pdf.Text.TextBuilder;
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

 Crea multipli`TextFragment` oggetti, impostarne il testo e le proprietà e specificarne le posizioni sulla pagina:

```csharp
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.Position = new Position(100, 600);
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.Position = new Position(200, 600);
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;

TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.Position = new Position(300, 600);
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
```

Regola il testo, le posizioni e altre proprietà come desideri.

## Passaggio 6: crea un TextBuilder e aggiungi frammenti di testo

 Creare un`TextBuilder` oggetto utilizzando il`pdfPage` e aggiungi i frammenti di testo alla pagina PDF:

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
```

## Passaggio 7: salvare il documento PDF

 Salva il documento PDF modificato in un file utilizzando il formato`Save` metodo:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

 Assicurati di sostituire`"TextFragmentTests_Rotated1_out.pdf"` con il nome del file di output desiderato.

### Esempio di codice sorgente per Ruota il testo utilizzando il frammento di testo utilizzando Aspose.PDF per .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Inizializza oggetto documento
Document pdfDocument = new Document();
// Ottieni una pagina particolare
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Crea un frammento di testo
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.Position = new Position(100, 600);
// Imposta le proprietà del testo
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Crea un frammento di testo ruotato
TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.Position = new Position(200, 600);
// Imposta le proprietà del testo
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;
// Crea un frammento di testo ruotato
TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.Position = new Position(300, 600);
// Imposta le proprietà del testo
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
// creare un oggetto TextBuilder
TextBuilder textBuilder = new TextBuilder(pdfPage);
// Aggiungi il frammento di testo alla pagina PDF
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
// Salva documento
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

## Conclusione

Congratulazioni! Hai imparato con successo come ruotare il testo utilizzando frammenti di testo in un documento PDF utilizzando Aspose.PDF per .NET. Questo tutorial ha fornito una guida passo passo, dalla creazione del documento al salvataggio della versione modificata. Ora puoi incorporare questo codice nei tuoi progetti C# per manipolare la rotazione del testo nei file PDF.