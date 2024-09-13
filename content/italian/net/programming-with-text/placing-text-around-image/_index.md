---
title: Posizionamento del testo attorno all'immagine nel file PDF
linktitle: Posizionamento del testo attorno all'immagine nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come posizionare del testo attorno a un'immagine in un file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 260
url: /it/net/programming-with-text/placing-text-around-image/
---
In questo tutorial, spiegheremo come posizionare il testo attorno a un'immagine in un file PDF utilizzando la libreria Aspose.PDF per .NET. Esamineremo passo dopo passo il processo di creazione di una tabella, aggiunta di un'immagine e posizionamento del testo attorno all'immagine utilizzando il codice sorgente C# fornito.

## Requisiti

Prima di iniziare, assicurati di avere quanto segue:

- È stata installata la libreria Aspose.PDF per .NET.
- Conoscenza di base della programmazione C#.

## Passaggio 1: impostare la directory dei documenti

 Per prima cosa, devi impostare il percorso della directory in cui vuoi salvare il file PDF generato. Sostituisci`"YOUR DOCUMENT DIRECTORY"` nel`dataDir` variabile con il percorso della directory desiderata.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: creare un documento e una pagina

 Successivamente, creiamo un`Document` oggetto e aggiungi una pagina ad esso utilizzando il`Pages.Add()` metodo.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Passaggio 3: creare una tabella

 Creiamo una tabella utilizzando il`Table` classe e aggiungerla alla raccolta dei paragrafi della pagina.

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
page.Paragraphs.Add(table1);
```

## Passaggio 4: impostare la larghezza e i margini delle colonne della tabella

 Impostiamo la larghezza delle colonne della tabella e creiamo un`MarginInfo` oggetto per impostare i margini.

```csharp
table1. ColumnWidths = "120,270";
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;
table1. DefaultCellPadding = margin;
```

## Passaggio 5: aggiungere un'immagine alla tabella

 Creiamo un`Image` object, specificare il percorso del file immagine e impostare l'altezza e la larghezza fisse dell'immagine. Quindi, aggiungiamo l'immagine alla raccolta di paragrafi della cella della tabella.

```csharp
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
logo.File = dataDir + "aspose-logo.jpg";
logo.FixHeight = 120;
logo.FixWidth = 110;
row1.Cells.Add();
row1.Cells[0].Paragraphs.Add(logo);
```

## Passaggio 6: aggiungere testo attorno all'immagine

 Creiamo variabili stringa contenenti testo formattato in HTML e creiamo un`HtmlFragment`oggetto. Quindi, aggiungiamo il testo HTML alla cella della tabella contenente l'immagine.

```csharp
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b>Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>" ;

Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
row1.Cells[1].Paragraphs.Add(TitleText);
```

## Passaggio 7: aggiungere testo aggiuntivo

 Ne creiamo un altro`HtmlFragment` oggetto contenente testo aggiuntivo formattato in HTML e aggiungerlo a una cella di tabella separata.

```csharp
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
```

## Passaggio 8: Salvare il documento PDF

Infine, salviamo il documento PDF nel file di output specificato.

```csharp
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

### Esempio di codice sorgente per posizionare il testo attorno all'immagine utilizzando Aspose.PDF per .NET 
```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crea un'istanza dell'oggetto documento
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Crea una pagina nel Pdf
Aspose.Pdf.Page page = doc.Pages.Add();
// Creare un'istanza di un oggetto tabella
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
// Aggiungere la tabella nella raccolta di paragrafi della sezione desiderata
page.Paragraphs.Add(table1);
// Impostato con le larghezze delle colonne della tabella
table1.ColumnWidths = "120 270";
// Crea l'oggetto MarginInfo e imposta i suoi margini sinistro, inferiore, destro e superiore
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Imposta la spaziatura predefinita delle celle sull'oggetto MarginInfo
table1.DefaultCellPadding = margin;
// Crea righe nella tabella e poi celle nelle righe
Aspose.Pdf.Row row1 = table1.Rows.Add();
// Crea un oggetto immagine
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
// Specificare il percorso del file immagine
logo.File = dataDir + "aspose-logo.jpg";
// Specificare l'altezza fissa dell'immagine
logo.FixHeight = 120;
// Specificare la larghezza fissa dell'immagine
logo.FixWidth = 110;
row1.Cells.Add();
// Aggiungere l'immagine alla raccolta di paragrafi della cella della tabella
row1.Cells[0].Paragraphs.Add(logo);
// Crea variabili stringa con testo contenente tag html
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b> Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>";
//Crea un oggetto di testo da aggiungere a destra dell'immagine
Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
// Aggiungere i paragrafi di testo contenenti testo HTML alla cella della tabella
row1.Cells[1].Paragraphs.Add(TitleText);
// Imposta l'allineamento verticale del contenuto della riga come In alto
row1.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
//Crea righe nella tabella e poi celle nelle righe
Aspose.Pdf.Row SecondRow = table1.Rows.Add();
SecondRow.Cells.Add();
// Imposta il valore dell'intervallo di riga per la seconda riga su 2
SecondRow.Cells[0].ColSpan = 2;
// Imposta l'allineamento verticale della seconda riga come In alto
SecondRow.Cells[0].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
// Aggiungere i paragrafi di testo contenenti testo HTML alla cella della tabella
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
// Salva il file PDF
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

## Conclusione

In questo tutorial, hai imparato come posizionare il testo attorno a un'immagine in un documento PDF utilizzando la libreria Aspose.PDF per .NET. Seguendo la guida passo passo ed eseguendo il codice C# fornito, puoi creare una tabella, aggiungere un'immagine e posizionare il testo attorno all'immagine in un documento PDF.

### Domande frequenti

#### D: Qual è lo scopo del tutorial "Posizionamento del testo attorno all'immagine in un file PDF"?

R: Il tutorial "Posizionare il testo attorno all'immagine nel file PDF" illustra come utilizzare la libreria Aspose.PDF per .NET per posizionare il testo attorno a un'immagine in un documento PDF. Il tutorial fornisce una guida passo passo e un codice sorgente C# per aiutarti a creare una tabella, aggiungere un'immagine e posizionare il testo attorno all'immagine.

#### D: Perché dovrei voler inserire del testo attorno a un'immagine in un documento PDF?

R: Posizionare del testo attorno a un'immagine migliora la presentazione visiva dei tuoi documenti PDF, rendendoli più coinvolgenti e informativi. Questa tecnica è spesso utilizzata in documenti, brochure, report e altri materiali in cui vuoi combinare immagini e testo in modo esteticamente gradevole.

#### D: Come faccio a impostare la directory dei documenti?

A: Per impostare la directory dei documenti:

1.  Sostituire`"YOUR DOCUMENT DIRECTORY"` nel`dataDir` variabile con il percorso della directory in cui si desidera salvare il file PDF generato.

#### D: Come faccio a creare una tabella e ad aggiungervi un'immagine?

 A: Il tutorial ti guida attraverso il processo di creazione di una tabella utilizzando`Table` classe e aggiungendo un'immagine alla tabella utilizzando`Image` classe. Specificherai il percorso del file immagine, l'altezza e la larghezza prima di aggiungerlo a una cella della tabella.

#### D: Come posso posizionare il testo attorno all'immagine?

 A: Per posizionare il testo attorno all'immagine, creerai un testo formattato in HTML utilizzando`HtmlFragment` classe. Questo testo conterrà sia un titolo che un corpo di testo. Aggiungerai quindi questo testo HTML a una cella della tabella adiacente alla cella dell'immagine.

#### D: Posso personalizzare l'aspetto del testo e dell'immagine?

R: Sì, puoi personalizzare l'aspetto del testo e dell'immagine usando tag e proprietà HTML. Ad esempio, puoi impostare dimensioni del carattere, colori, stili e allineamento per il testo. Inoltre, puoi regolare le dimensioni e le dimensioni dell'immagine.

#### D: Come posso salvare il documento PDF?

 A: Dopo aver aggiunto l'immagine e il testo alla tabella, puoi salvare il documento PDF utilizzando`Save` metodo del`Document` classe. Fornire il percorso del file di output desiderato come argomento per`Save` metodo.

#### D: Qual è il risultato atteso da questo tutorial?

A: Seguendo il tutorial ed eseguendo il codice C# fornito, genererai un documento PDF che mostra come posizionare il testo attorno a un'immagine. Il documento di output conterrà una tabella con un'immagine e del testo posizionati attorno ad essa.

#### D: Posso usare formati di immagine diversi dal JPG?

 R: Sì, puoi usare diversi formati di immagine supportati dalla libreria Aspose.PDF, come PNG, BMP, GIF e altri. Quando crei il`Image` oggetto, specificare il percorso del file nel formato immagine desiderato.

#### D: Per questo tutorial è richiesta una licenza Aspose valida?

R: Sì, è richiesta una licenza Aspose valida affinché questo tutorial funzioni correttamente. Puoi acquistare una licenza completa o ottenere una licenza temporanea di 30 giorni dal sito Web di Aspose.