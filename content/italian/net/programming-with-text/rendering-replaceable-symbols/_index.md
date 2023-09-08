---
title: Rendering di simboli sostituibili nel file PDF
linktitle: Rendering di simboli sostituibili nel file PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come eseguire il rendering di simboli sostituibili nel file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 310
url: /it/net/programming-with-text/rendering-replaceable-symbols/
---
In questo tutorial, spiegheremo come eseguire il rendering dei simboli sostituibili nel file PDF utilizzando la libreria Aspose.PDF per .NET. Seguiremo il processo passo passo di creazione di un PDF, aggiunta di un frammento di testo con marcatori di nuova riga, impostazione delle proprietà del testo, posizionamento del testo e salvataggio del PDF utilizzando il codice sorgente C# fornito.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

- La libreria Aspose.PDF per .NET installata.
- Una conoscenza di base della programmazione C#.

## Passaggio 1: impostare la directory dei documenti

 Innanzitutto, devi impostare il percorso della directory in cui desideri salvare il file PDF generato. Sostituire`"YOUR DOCUMENT DIRECTORY"` nel`dataDir`variabile con il percorso della directory desiderata.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: crea un documento e una pagina PDF

 Successivamente, creiamo un nuovo documento PDF e vi aggiungiamo una pagina utilizzando il file`Document` classe e`Page` classe dalla libreria Aspose.PDF.

```csharp
Aspose.Pdf.Document pdfApplicationDoc = new Aspose.Pdf.Document();
Aspose.Pdf.Page applicationFirstPage = (Aspose.Pdf.Page)pdfApplicationDoc.Pages.Add();
```

## Passaggio 3: aggiungi un frammento di testo con i marcatori di nuova riga

 Creiamo un`TextFragment`oggetto e impostarne il testo in modo da includere marcatori di nuova riga (`Environment.NewLine`) per rappresentare più righe di testo.

```csharp
Aspose.Pdf.Text.TextFragment textFragment = new Aspose.Pdf.Text.TextFragment("Applicant Name: " + Environment.NewLine + " Joe Smoe");
```

## Passaggio 4: impostare le proprietà del frammento di testo

Se lo desideriamo, possiamo impostare varie proprietà per il frammento di testo, come dimensione del carattere, carattere, colore di sfondo e colore di primo piano.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
```

## Passaggio 5: crea il paragrafo e la posizione del testo

 Creiamo un`TextParagraph` oggetto, aggiungi il frammento di testo al paragrafo e imposta la posizione del paragrafo sulla pagina.

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

### Codice sorgente di esempio per il rendering di simboli sostituibili utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document pdfApplicationDoc = new Aspose.Pdf.Document();
Aspose.Pdf.Page applicationFirstPage = (Aspose.Pdf.Page)pdfApplicationDoc.Pages.Add();
// Inizializza il nuovo TextFragment con il testo contenente i marcatori di nuova riga richiesti
Aspose.Pdf.Text.TextFragment textFragment = new Aspose.Pdf.Text.TextFragment("Applicant Name: " + Environment.NewLine + " Joe Smoe");
// Se necessario, imposta le proprietà del frammento di testo
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
// Aggiungi TextParagraph utilizzando TextBuilder
textBuilder.AppendParagraph(par);
dataDir = dataDir + "RenderingReplaceableSymbols_out.pdf";
pdfApplicationDoc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols render successfully duing pdf creation.\nFile saved at " + dataDir);
```

## Conclusione

In questo tutorial, hai imparato come eseguire il rendering di simboli sostituibili in un documento PDF utilizzando la libreria Aspose.PDF per .NET. Seguendo la guida passo passo ed eseguendo il codice C# fornito, puoi creare un PDF, aggiungere testo con indicatori di nuova riga, impostare le proprietà del testo, posizionare il testo sulla pagina e salvare il PDF.

### Domande frequenti

#### D: Qual è lo scopo del tutorial "Rendering dei simboli sostituibili nel file PDF"?

R: Il tutorial "Rendering di simboli sostituibili nel file PDF" mostra come utilizzare la libreria Aspose.PDF per .NET per creare un documento PDF che includa simboli sostituibili. Questi simboli sono rappresentati come frammenti di testo con indicatori di nuova riga per creare contenuto su più righe.

#### D: Perché dovrei rendere simboli sostituibili in un documento PDF?

R: Il rendering dei simboli sostituibili è utile quando è necessario generare dinamicamente contenuto PDF che includa informazioni variabili o specifiche dell'utente. Questi simboli fungono da segnaposto che possono essere sostituiti con dati effettivi durante il runtime, come valori dei campi del modulo o dettagli personalizzati.

#### D: Come posso impostare la directory dei documenti?

R: Per impostare la directory dei documenti:

1.  Sostituire`"YOUR DOCUMENT DIRECTORY"` nel`dataDir` variabile con il percorso della directory in cui si desidera salvare il file PDF generato.

#### D: Come posso eseguire il rendering dei simboli sostituibili in un documento PDF utilizzando la libreria Aspose.PDF?

R: Il tutorial ti guida attraverso il processo passo dopo passo:

1.  Crea un nuovo documento PDF utilizzando il file`Document` classe.
2.  Aggiungi una pagina al documento utilizzando il file`Page` classe.
3.  Creare un`TextFragment` oggetto con marcatori di nuova riga (`Environment.NewLine`) per rappresentare contenuto su più righe.
4. Personalizza le proprietà del frammento di testo come dimensione del carattere, carattere, colore di sfondo e colore di primo piano.
5.  Creare un`TextParagraph` oggetto, aggiungi il frammento di testo e imposta la posizione del paragrafo sulla pagina.
6.  Creare un`TextBuilder` oggetto con la pagina e aggiungervi il paragrafo di testo.
7. Salva il documento PDF.

#### D: Qual è lo scopo dell'utilizzo dei marcatori di nuova riga (`Environment.NewLine`) in the text fragment?

 R: I marcatori di nuova riga vengono utilizzati per creare contenuto su più righe all'interno di un singolo frammento di testo. Usando`Environment.NewLine`, puoi indicare dove devono apparire le interruzioni di riga nel testo.

#### D: Posso personalizzare l'aspetto dei simboli sostituibili?

R: Sì, puoi personalizzare varie proprietà del frammento di testo, come dimensione del carattere, carattere, colore di sfondo e colore di primo piano. Queste proprietà determinano l'aspetto visivo dei simboli sostituibili nel documento PDF.

#### D: Come posso specificare la posizione del testo sulla pagina?

 R: Puoi impostare la posizione del testo creando un file`TextParagraph` oggetto e utilizzando il file`Position` proprietà per specificare le coordinate X e Y della pagina in cui deve essere posizionato il paragrafo.

#### D: Qual è il risultato previsto dell'esecuzione del codice fornito?

R: Seguendo il tutorial ed eseguendo il codice C# fornito, creerai un documento PDF che include simboli sostituibili. I simboli sostituibili verranno rappresentati come frammenti di testo con indicatori di nuova riga e proprietà personalizzate.

#### D: Posso utilizzare questo approccio per generare dinamicamente documenti PDF personalizzati?

R: Sì, questo approccio è adatto per generare dinamicamente documenti PDF con informazioni personalizzate. Sostituendo i simboli sostituibili con dati reali, puoi creare contenuti PDF personalizzati per ciascun utente o scenario.