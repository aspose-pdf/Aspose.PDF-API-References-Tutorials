---
title: Rendering di simboli sostituibili in file PDF
linktitle: Rendering di simboli sostituibili in file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come rendere simboli sostituibili in un file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 310
url: /it/net/programming-with-text/rendering-replaceable-symbols/
---
In questo tutorial, spiegheremo come rendere simboli sostituibili in un file PDF usando la libreria Aspose.PDF per .NET. Esamineremo passo dopo passo il processo di creazione di un PDF, aggiungendo un frammento di testo con marcatori di nuova riga, impostando le proprietà del testo, posizionando il testo e salvando il PDF usando il codice sorgente C# fornito.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

- È stata installata la libreria Aspose.PDF per .NET.
- Conoscenza di base della programmazione C#.

## Passaggio 1: impostare la directory dei documenti

 Per prima cosa, devi impostare il percorso della directory in cui vuoi salvare il file PDF generato. Sostituisci`"YOUR DOCUMENT DIRECTORY"` nel`dataDir` variabile con il percorso della directory desiderata.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: creare un documento PDF e una pagina

 Successivamente, creiamo un nuovo documento PDF e aggiungiamo una pagina ad esso utilizzando`Document` classe e`Page` classe dalla libreria Aspose.PDF.

```csharp
Aspose.Pdf.Document pdfApplicationDoc = new Aspose.Pdf.Document();
Aspose.Pdf.Page applicationFirstPage = (Aspose.Pdf.Page)pdfApplicationDoc.Pages.Add();
```

## Passaggio 3: aggiungere un frammento di testo con i marcatori di nuova riga

 Creiamo un`TextFragment` oggetto e imposta il suo testo per includere i marcatori di nuova riga (`Environment.NewLine`) per rappresentare più righe di testo.

```csharp
Aspose.Pdf.Text.TextFragment textFragment = new Aspose.Pdf.Text.TextFragment("Applicant Name: " + Environment.NewLine + " Joe Smoe");
```

## Passaggio 4: impostare le proprietà del frammento di testo

Se lo desideriamo, possiamo impostare diverse proprietà per il frammento di testo, come la dimensione del carattere, il tipo di carattere, il colore di sfondo e il colore di primo piano.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
```

## Passaggio 5: creare il paragrafo di testo e la posizione

 Creiamo un`TextParagraph` oggetto, aggiungere il frammento di testo al paragrafo e impostare la posizione del paragrafo sulla pagina.

```csharp
TextParagraph par = new TextParagraph();
par.AppendLine(textFragment);
par.Position = new Aspose.Pdf.Text.Position(100, 600);
```

## Passaggio 6: aggiungere un paragrafo di testo alla pagina

 Creiamo un`TextBuilder` oggetto con la pagina e aggiungere il paragrafo di testo al generatore di testo.

```csharp
TextBuilder textBuilder = new TextBuilder(applicationFirstPage);
textBuilder.AppendParagraph(par);
```

## Passaggio 7: Salvare il documento PDF

Infine, salviamo il documento PDF nel file di output specificato.

```csharp
dataDir = dataDir + "RenderingReplaceableSymbols_out.pdf";
pdfApplicationDoc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols rendered successfully during PDF creation.\nFile saved at " + dataDir);
```

### Esempio di codice sorgente per il rendering di simboli sostituibili utilizzando Aspose.PDF per .NET 
```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document pdfApplicationDoc = new Aspose.Pdf.Document();
Aspose.Pdf.Page applicationFirstPage = (Aspose.Pdf.Page)pdfApplicationDoc.Pages.Add();
// Inizializza il nuovo TextFragment con il testo contenente i marcatori di nuova riga richiesti
Aspose.Pdf.Text.TextFragment textFragment = new Aspose.Pdf.Text.TextFragment("Applicant Name: " + Environment.NewLine + " Joe Smoe");
// Imposta le proprietà del frammento di testo se necessario
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// Crea oggetto TextParagraph
TextParagraph par = new TextParagraph();
// Aggiungi un nuovo TextFragment al paragrafo
par.AppendLine(textFragment);
// Imposta la posizione del paragrafo
par.Position = new Aspose.Pdf.Text.Position(100, 600);
// Crea oggetto TextBuilder
TextBuilder textBuilder = new TextBuilder(applicationFirstPage);
// Aggiungere il TextParagraph utilizzando TextBuilder
textBuilder.AppendParagraph(par);
dataDir = dataDir + "RenderingReplaceableSymbols_out.pdf";
pdfApplicationDoc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols render successfully duing pdf creation.\nFile saved at " + dataDir);
```

## Conclusione

In questo tutorial, hai imparato come rendere simboli sostituibili in un documento PDF usando la libreria Aspose.PDF per .NET. Seguendo la guida passo passo ed eseguendo il codice C# fornito, puoi creare un PDF, aggiungere testo con marcatori di nuova riga, impostare proprietà di testo, posizionare il testo sulla pagina e salvare il PDF.

### Domande frequenti

#### D: Qual è lo scopo del tutorial "Rendering di simboli sostituibili in file PDF"?

R: Il tutorial "Rendering Replaceable Symbols In PDF File" illustra come usare la libreria Aspose.PDF per .NET per creare un documento PDF che include simboli sostituibili. Questi simboli sono rappresentati come frammenti di testo con marcatori di nuova riga per creare contenuti multi-riga.

#### D: Perché dovrei voler rendere simboli sostituibili in un documento PDF?

R: Il rendering di simboli sostituibili è utile quando è necessario generare dinamicamente contenuti PDF che includono informazioni variabili o specifiche dell'utente. Questi simboli fungono da segnaposto che possono essere sostituiti con dati effettivi durante l'esecuzione, come valori di campi di moduli o dettagli personalizzati.

#### D: Come faccio a impostare la directory dei documenti?

A: Per impostare la directory dei documenti:

1.  Sostituire`"YOUR DOCUMENT DIRECTORY"` nel`dataDir` variabile con il percorso della directory in cui si desidera salvare il file PDF generato.

#### D: Come posso rendere i simboli sostituibili in un documento PDF utilizzando la libreria Aspose.PDF?

A: Il tutorial ti guida passo dopo passo attraverso il processo:

1.  Crea un nuovo documento PDF utilizzando`Document` classe.
2.  Aggiungere una pagina al documento utilizzando`Page` classe.
3.  Crea un`TextFragment` oggetto con marcatori di nuova riga (`Environment.NewLine`) per rappresentare contenuti multi-linea.
4. Personalizza le proprietà del frammento di testo, come dimensione del carattere, tipo di carattere, colore di sfondo e colore di primo piano.
5.  Crea un`TextParagraph` oggetto, aggiungervi il frammento di testo e impostare la posizione del paragrafo sulla pagina.
6.  Crea un`TextBuilder` oggetto con la pagina e aggiungervi il paragrafo di testo.
7. Salvare il documento PDF.

#### D: Qual è lo scopo dell'utilizzo dei marcatori di nuova riga (`Environment.NewLine`) in the text fragment?

 A: I marcatori di nuova riga vengono utilizzati per creare contenuti multi-riga all'interno di un singolo frammento di testo. Utilizzando`Environment.NewLine`è possibile indicare dove devono avvenire le interruzioni di riga nel testo.

#### D: Posso personalizzare l'aspetto dei simboli sostituibili?

R: Sì, puoi personalizzare varie proprietà del frammento di testo, come dimensione del carattere, font, colore di sfondo e colore di primo piano. Queste proprietà determinano l'aspetto visivo dei simboli sostituibili nel documento PDF.

#### D: Come faccio a specificare la posizione del testo sulla pagina?

 A: Puoi impostare la posizione del testo creando un`TextParagraph` oggetto e utilizzando il`Position` proprietà per specificare le coordinate X e Y sulla pagina in cui deve essere posizionato il paragrafo.

#### D: Qual è il risultato previsto dall'esecuzione del codice fornito?

R: Seguendo il tutorial ed eseguendo il codice C# fornito, creerai un documento PDF che include simboli sostituibili. I simboli sostituibili saranno rappresentati come frammenti di testo con marcatori di nuova riga e proprietà personalizzate.

#### D: Posso usare questo approccio per generare dinamicamente documenti PDF personalizzati?

R: Sì, questo approccio è adatto per generare dinamicamente documenti PDF con informazioni personalizzate. Sostituendo i simboli sostituibili con dati effettivi, puoi creare contenuti PDF personalizzati per ogni utente o scenario.