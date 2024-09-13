---
title: Tabulazione personalizzata nel file PDF
linktitle: Tabulazione personalizzata nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come creare tabulazioni personalizzate nei file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 120
url: /it/net/programming-with-text/custom-tab-stops/
---

Questo tutorial ti guiderà attraverso il processo di creazione di tabulazioni personalizzate in un file PDF utilizzando Aspose.PDF per .NET. Il codice sorgente C# fornito illustra i passaggi necessari.

## Requisiti
Prima di iniziare, assicurati di avere quanto segue:

- Visual Studio o qualsiasi altro compilatore C# installato sul computer.
- Aspose.PDF per la libreria .NET. Puoi scaricarlo dal sito web ufficiale di Aspose o usare un gestore di pacchetti come NuGet per installarlo.

## Passaggio 1: impostare il progetto
1. Crea un nuovo progetto C# nel tuo ambiente di sviluppo preferito.
2. Aggiungere un riferimento alla libreria Aspose.PDF per .NET.

## Passaggio 2: importare gli spazi dei nomi richiesti
Nel file di codice in cui vuoi creare tabulazioni personalizzate, aggiungi le seguenti direttive using all'inizio del file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Passaggio 3: impostare la directory del documento
 Nel codice, individua la riga che dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso della directory in cui sono archiviati i tuoi documenti.

## Passaggio 4: creare una nuova istanza del documento
 Crea un'istanza di un nuovo`Document` oggetto aggiungendo la seguente riga di codice:

```csharp
Document _pdfdocument = new Document();
```

## Passaggio 5: aggiungere una pagina al documento
 Aggiungere una nuova pagina al documento utilizzando`Add` metodo del`Pages` raccolta. Nel codice fornito, la nuova pagina è assegnata alla variabile`page`.

```csharp
Page page = _pdfdocument.Pages.Add();
```

## Passaggio 6: creare tabulazioni personalizzate
 Crea un`TabStops` oggetto e aggiungi tabulazioni personalizzate. Imposta il tipo di allineamento e il tipo di leader per ogni tabulazione.

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

## Passaggio 7: creare frammenti di testo con tabulazioni
 Creare`TextFragment` oggetti e passa loro le tabulazioni personalizzate. Utilizza i caratteri speciali`#$TAB` per indicare le tabulazioni all'interno del testo.

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

## Passaggio 8: Salvare il documento PDF
 Salvare il documento PDF utilizzando`Save` metodo del`Document` oggetto.

```csharp
_pdfdocument.Save(dataDir);
Console.WriteLine("\nCustom tab stops setup successfully.\nFile saved at " + dataDir);
```

### Esempio di codice sorgente per tabulazioni personalizzate utilizzando Aspose.PDF per .NET 
```csharp
// Percorso verso la directory dei documenti.
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

#### D: Qual è l'obiettivo di questo tutorial?

R: Questo tutorial è incentrato sulla guida attraverso il processo di creazione di tabulazioni personalizzate in un file PDF utilizzando la libreria Aspose.PDF per .NET. Il codice sorgente C# fornito illustra i passaggi necessari per ottenere questo risultato.

#### D: Quali namespace dovrei importare per questo tutorial?

A: Nel file di codice in cui vuoi creare tabulazioni personalizzate, importa i seguenti namespace all'inizio del file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### D: Come faccio a specificare la directory dei documenti?

 A: Nel codice, trova la riga`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory del documento.

#### D: Come posso creare una nuova istanza di Documento?

 A: Nel passaggio 4, creerai un nuovo`Document` oggetto utilizzando il codice fornito.

#### D: Come posso aggiungere una pagina al documento?

 A: Nel passaggio 5, aggiungerai una nuova pagina al documento utilizzando`Add` metodo del`Pages` collezione.

#### D: Come posso creare tabulazioni personalizzate?

 A: Nel passaggio 6, creerai un`TabStops` oggetto e aggiungi tabulazioni personalizzate. Imposterai anche l'allineamento e i tipi di leader per ogni tabulazione.

#### D: Come posso creare frammenti di testo con tabulazioni?

 A: Nel passaggio 7, creerai`TextFragment` oggetti e passa loro le tabulazioni personalizzate. Utilizzerai i caratteri speciali`#$TAB` per indicare le tabulazioni all'interno del testo.

#### D: Come posso salvare il documento PDF?

 A: Nel passaggio 8, salverai il documento PDF utilizzando`Save` metodo del`Document` oggetto.

#### D: Qual è la cosa più importante da imparare da questo tutorial?

R: Seguendo questo tutorial, hai imparato a creare un documento PDF con tabulazioni personalizzate usando Aspose.PDF per .NET. Questo può essere utile per organizzare e allineare il testo in modo strutturato.