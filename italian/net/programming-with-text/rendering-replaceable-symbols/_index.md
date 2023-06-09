---
title: Rendering di simboli sostituibili
linktitle: Rendering di simboli sostituibili
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come eseguire il rendering di simboli sostituibili in un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 310
url: /it/net/programming-with-text/rendering-replaceable-symbols/
---

In questo tutorial, spiegheremo come rendere i simboli sostituibili in un documento PDF utilizzando la libreria Aspose.PDF per .NET. Passeremo attraverso il processo passo-passo di creazione di un PDF, aggiungendo un frammento di testo con marcatori di nuova riga, impostando le proprietà del testo, posizionando il testo e salvando il PDF utilizzando il codice sorgente C# fornito.

## Prerequisiti

Prima di iniziare, assicurati di disporre di quanto segue:

- La libreria Aspose.PDF per .NET installata.
- Una conoscenza di base della programmazione C#.

## Passaggio 1: impostare la directory dei documenti

 Innanzitutto, devi impostare il percorso della directory in cui desideri salvare il file PDF generato. Sostituire`"YOUR DOCUMENT DIRECTORY"` nel`dataDir` variabile con il percorso della directory desiderata.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: creare un documento e una pagina PDF

Successivamente, creiamo un nuovo documento PDF e vi aggiungiamo una pagina utilizzando il file`Document` classe e`Page` class dalla libreria Aspose.PDF.

```csharp
Aspose.Pdf.Document pdfApplicationDoc = new Aspose.Pdf.Document();
Aspose.Pdf.Page applicationFirstPage = (Aspose.Pdf.Page)pdfApplicationDoc.Pages.Add();
```

## Passaggio 3: aggiungi un frammento di testo con i marcatori di nuova riga

 Creiamo un`TextFragment` oggetto e impostare il suo testo per includere i marcatori di nuova riga (`Environment.NewLine`) per rappresentare più righe di testo.

```csharp
Aspose.Pdf.Text.TextFragment textFragment = new Aspose.Pdf.Text.TextFragment("Applicant Name: " + Environment.NewLine + " Joe Smoe");
```

## Passaggio 4: impostare le proprietà del frammento di testo

Se lo desideri, possiamo impostare varie proprietà per il frammento di testo, come la dimensione del carattere, il carattere, il colore di sfondo e il colore di primo piano.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
```

## Passaggio 5: creare un paragrafo e una posizione di testo

 Creiamo un`TextParagraph` oggetto, aggiungere il frammento di testo al paragrafo e impostare la posizione del paragrafo sulla pagina.

```csharp
TextParagraph par = new TextParagraph();
par.AppendLine(textFragment);
par.Position = new Aspose.Pdf.Text.Position(100, 600);
```

## Passaggio 6: aggiungi un paragrafo di testo alla pagina

 Creiamo un`TextBuilder` oggetto con la pagina e aggiungi il paragrafo di testo al generatore di testo.

```csharp
TextBuilder textBuilder = new TextBuilder(applicationFirstPage);
textBuilder.AppendParagraph(par);
```

## Passaggio 7: salva il documento PDF

Infine, salviamo il documento PDF nel file di output specificato.

```csharp
dataDir = dataDir + "RenderingReplaceableSymbols_out.pdf";
pdfApplicationDoc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols rendered successfully during PDF creation.\nFile saved at " + dataDir);
```

### Esempio di codice sorgente per il rendering di simboli sostituibili utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document pdfApplicationDoc = new Aspose.Pdf.Document();
Aspose.Pdf.Page applicationFirstPage = (Aspose.Pdf.Page)pdfApplicationDoc.Pages.Add();
// Inizializza il nuovo TextFragment con testo contenente i marcatori di nuova riga richiesti
Aspose.Pdf.Text.TextFragment textFragment = new Aspose.Pdf.Text.TextFragment("Applicant Name: " + Environment.NewLine + " Joe Smoe");
// Impostare le proprietà del frammento di testo, se necessario
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// Crea un oggetto TextParagraph
TextParagraph par = new TextParagraph();
// Aggiungi un nuovo TextFragment al paragrafo
par.AppendLine(textFragment);
// Imposta la posizione del paragrafo
par.Position = new Aspose.Pdf.Text.Position(100, 600);
// Crea un oggetto TextBuilder
TextBuilder textBuilder = new TextBuilder(applicationFirstPage);
// Aggiungi il TextParagraph usando TextBuilder
textBuilder.AppendParagraph(par);
dataDir = dataDir + "RenderingReplaceableSymbols_out.pdf";
pdfApplicationDoc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols render successfully duing pdf creation.\nFile saved at " + dataDir);
```

## Conclusione

In questo tutorial, hai imparato come eseguire il rendering di simboli sostituibili in un documento PDF utilizzando la libreria Aspose.PDF per .NET. Seguendo la guida passo-passo ed eseguendo il codice C# fornito, puoi creare un PDF, aggiungere testo con marcatori di nuova riga, impostare le proprietà del testo, posizionare il testo sulla pagina e salvare il PDF.