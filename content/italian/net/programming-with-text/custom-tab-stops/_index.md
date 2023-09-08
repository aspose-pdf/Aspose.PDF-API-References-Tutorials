---
title: Tabulazioni personalizzate nel file PDF
linktitle: Tabulazioni personalizzate nel file PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come creare tabulazioni personalizzate nel file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 120
url: /it/net/programming-with-text/custom-tab-stops/
---

Questo tutorial ti guiderà attraverso il processo di creazione di tabulazioni personalizzate nel file PDF utilizzando Aspose.PDF per .NET. Il codice sorgente C# fornito illustra i passaggi necessari.

## Requisiti
Prima di iniziare, assicurati di avere quanto segue:

- Visual Studio o qualsiasi altro compilatore C# installato sul tuo computer.
- Aspose.PDF per la libreria .NET. Puoi scaricarlo dal sito Web ufficiale di Aspose o utilizzare un gestore di pacchetti come NuGet per installarlo.

## Passaggio 1: impostare il progetto
1. Crea un nuovo progetto C# nel tuo ambiente di sviluppo preferito.
2. Aggiungere un riferimento alla libreria Aspose.PDF per .NET.

## Passaggio 2: importa gli spazi dei nomi richiesti
Nel file di codice in cui desideri creare tabulazioni personalizzate, aggiungi le seguenti direttive using nella parte superiore del file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Passaggio 3: imposta la directory dei documenti
 Nel codice, individua la riga che dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso della directory in cui sono archiviati i tuoi documenti.

## Passaggio 4: crea una nuova istanza del documento
 Istanziarne uno nuovo`Document` oggetto aggiungendo la seguente riga di codice:

```csharp
Document _pdfdocument = new Document();
```

## Passaggio 5: aggiungi una pagina al documento
 Aggiungi una nuova pagina al documento utilizzando il file`Add` metodo del`Pages`collezione. Nel codice fornito, la nuova pagina viene assegnata alla variabile`page`.

```csharp
Page page = _pdfdocument.Pages.Add();
```

## Passaggio 6: crea tabulazioni personalizzate
 Creare un`TabStops` oggetto e aggiungervi tabulazioni personalizzate. Imposta il tipo di allineamento e il tipo di direttrice per ciascuna tabulazione.

```csharp
TabStops ts = new TabStops();
TabStop ts1 = ts.Add(100);
ts1.AlignmentType = TabAlignmentType.Right;
ts1.LeaderType = TabLeaderType.Solid;

TabStop ts2 = ts.Add(200);
ts2.AlignmentType = TabAlignmentType.Center;
ts2.LeaderType = TabLeaderType.Dash;

TabStop ts3 = ts.Add(300);
ts3.AlignmentType = TabAlignmentType.Left;
ts3.LeaderType = TabLeaderType.Dot;
```

## Passaggio 7: crea frammenti di testo con tabulazioni
 Creare`TextFragment` oggetti e passare loro le tabulazioni personalizzate. Utilizza i caratteri speciali`#$TAB` per indicare le tabulazioni all'interno del testo.

```csharp
TextFragment header = new TextFragment("This is an example of forming a table with TAB stops", ts);
TextFragment text0 = new TextFragment("#$TABHead1 #$TABHead2 #$TABHead3", ts);
TextFragment text1 = new TextFragment("#$TABdata11 #$TABdata12 #$TABdata13", ts);
TextFragment text2 = new TextFragment("#$TABdata21 ", ts);
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data22 "));
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data23"));

page.Paragraphs.Add(header);
page.Paragraphs.Add(text0);
page.Paragraphs.Add(text1);
page.Paragraphs.Add(text2);
```

## Passaggio 8: salva il documento PDF
 Salvare il documento PDF utilizzando il file`Save` metodo del`Document` oggetto.

```csharp
_pdfdocument.Save(dataDir);
Console.WriteLine("\nCustom tab stops setup successfully.\nFile saved at " + dataDir);
```

### Codice sorgente di esempio per tabulazioni personalizzate utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document _pdfdocument = new Document();
Page page = _pdfdocument.Pages.Add();
Aspose.Pdf.Text.TabStops ts = new Aspose.Pdf.Text.TabStops();
Aspose.Pdf.Text.TabStop ts1 = ts.Add(100);
ts1.AlignmentType = TabAlignmentType.Right;
ts1.LeaderType = TabLeaderType.Solid;
Aspose.Pdf.Text.TabStop ts2 = ts.Add(200);
ts2.AlignmentType = TabAlignmentType.Center;
ts2.LeaderType = TabLeaderType.Dash;
Aspose.Pdf.Text.TabStop ts3 = ts.Add(300);
ts3.AlignmentType = TabAlignmentType.Left;
ts3.LeaderType = TabLeaderType.Dot;
TextFragment header = new TextFragment("This is a example of forming table with TAB stops", ts);
TextFragment text0 = new TextFragment("#$TABHead1 #$TABHead2 #$TABHead3", ts);
TextFragment text1 = new TextFragment("#$TABdata11 #$TABdata12 #$TABdata13", ts);
TextFragment text2 = new TextFragment("#$TABdata21 ", ts);
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data22 "));
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data23"));
page.Paragraphs.Add(header);
page.Paragraphs.Add(text0);
page.Paragraphs.Add(text1);
page.Paragraphs.Add(text2);
dataDir = dataDir + "CustomTabStops_out.pdf";
_pdfdocument.Save(dataDir);
Console.WriteLine("\nCustom tab stops setup successfully.\nFile saved at " + dataDir);
```

## Conclusione
Hai creato con successo un documento PDF con tabulazioni personalizzate utilizzando Aspose.PDF per .NET. Il file PDF risultante può ora essere trovato nel percorso del file di output specificato.

### Domande frequenti

#### D: Qual è il focus di questo tutorial?

R: Questo tutorial è incentrato sulla guida dell'utente attraverso il processo di creazione di tabulazioni personalizzate in un file PDF utilizzando la libreria Aspose.PDF per .NET. Il codice sorgente C# fornito illustra i passaggi necessari per raggiungere questo obiettivo.

#### D: Quali spazi dei nomi devo importare per questo tutorial?

R: Nel file di codice in cui desideri creare tabulazioni personalizzate, importa i seguenti spazi dei nomi all'inizio del file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### D: Come posso specificare la directory dei documenti?

 A: Nel codice, trova la riga`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

#### D: Come posso creare una nuova istanza del documento?

 R: Nel passaggio 4 creerai un'istanza di new`Document` oggetto utilizzando il codice fornito.

#### D: Come faccio ad aggiungere una pagina al documento?

 R: Nel passaggio 5, aggiungerai una nuova pagina al documento utilizzando il file`Add` metodo del`Pages` collezione.

#### D: Come posso creare tabulazioni personalizzate?

 R: Nel passaggio 6 creerai un file`TabStops` oggetto e aggiungervi tabulazioni personalizzate. Imposterai inoltre l'allineamento e i tipi di direttrice per ciascuna tabulazione.

#### D: Come posso creare frammenti di testo con tabulazioni?

 A: Nel passaggio 7 creerai`TextFragment` oggetti e passare loro le tabulazioni personalizzate. Utilizzerai i caratteri speciali`#$TAB` per indicare le tabulazioni all'interno del testo.

#### D: Come posso salvare il documento PDF?

 R: Nel passaggio 8, salverai il documento PDF utilizzando il file`Save` metodo del`Document` oggetto.

#### D: Qual è il punto principale di questo tutorial?

R: Seguendo questo tutorial, hai imparato come creare un documento PDF con tabulazioni personalizzate utilizzando Aspose.PDF per .NET. Ciò può essere utile per organizzare e allineare il testo in modo strutturato.