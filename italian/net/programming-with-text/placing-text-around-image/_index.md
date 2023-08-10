---
title: Posizionare il testo attorno all'immagine
linktitle: Posizionare il testo attorno all'immagine
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come posizionare il testo attorno a un'immagine in un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 260
url: /it/net/programming-with-text/placing-text-around-image/
---

In questo tutorial, spiegheremo come posizionare il testo attorno a un'immagine in un documento PDF utilizzando la libreria Aspose.PDF per .NET. Verrà eseguito il processo dettagliato di creazione di una tabella, aggiunta di un'immagine e posizionamento del testo attorno all'immagine utilizzando il codice sorgente C# fornito.

## Requisiti

Prima di iniziare, assicurati di disporre di quanto segue:

- La libreria Aspose.PDF per .NET installata.
- Una conoscenza di base della programmazione C#.

## Passaggio 1: impostare la directory dei documenti

 Innanzitutto, devi impostare il percorso della directory in cui desideri salvare il file PDF generato. Sostituire`"YOUR DOCUMENT DIRECTORY"` nel`dataDir` variabile con il percorso della directory desiderata.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: creare un documento e una pagina

 Successivamente, creiamo un file`Document` oggetto e aggiungere una pagina ad esso utilizzando il`Pages.Add()` metodo.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Passaggio 3: creare una tabella

 Creiamo una tabella usando il`Table` class e aggiungerlo alla raccolta dei paragrafi della pagina.

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
page.Paragraphs.Add(table1);
```

## Passaggio 4: impostare la larghezza e i margini delle colonne della tabella

 Impostiamo le larghezze delle colonne della tabella e creiamo a`MarginInfo` oggetto per impostare i margini.

```csharp
table1. ColumnWidths = "120,270";
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;
table1. DefaultCellPadding = margin;
```

## Passaggio 5: aggiungi un'immagine alla tabella

 Creiamo un`Image` oggetto, specificare il percorso del file immagine e impostare l'altezza e la larghezza fisse dell'immagine. Quindi, aggiungiamo l'immagine alla raccolta dei paragrafi della cella della tabella.

```csharp
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
logo.File = dataDir + "aspose-logo.jpg";
logo.FixHeight = 120;
logo.FixWidth = 110;
row1.Cells.Add();
row1.Cells[0].Paragraphs.Add(logo);
```

## Passaggio 6: aggiungi testo attorno all'immagine

Creiamo variabili stringa contenenti testo in formato HTML e creiamo un file`HtmlFragment` oggetto. Quindi, aggiungiamo il testo HTML alla cella della tabella contenente l'immagine.

```csharp
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b>Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>" ;

Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
row1.Cells[1].Paragraphs.Add(TitleText);
```

## Passaggio 7: aggiungi testo aggiuntivo

 Ne creiamo un altro`HtmlFragment` oggetto contenente testo in formato HTML aggiuntivo e aggiungerlo a una cella di tabella separata.

```csharp
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
```

## Passaggio 8: salvare il documento PDF

Infine, salviamo il documento PDF nel file di output specificato.

```csharp
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

### Esempio di codice sorgente per posizionare il testo attorno all'immagine utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crea un'istanza dell'oggetto documento
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Crea una pagina nel Pdf
Aspose.Pdf.Page page = doc.Pages.Add();
// Crea un'istanza di un oggetto tabella
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
// Aggiungi la tabella nella raccolta di paragrafi della sezione desiderata
page.Paragraphs.Add(table1);
// Impostare con le larghezze delle colonne della tabella
table1.ColumnWidths = "120 270";
// Crea un oggetto MarginInfo e imposta i suoi margini sinistro, inferiore, destro e superiore
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Imposta la spaziatura predefinita della cella sull'oggetto MarginInfo
table1.DefaultCellPadding = margin;
// Crea righe nella tabella e quindi celle nelle righe
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
// Aggiungi l'immagine alla raccolta di paragrafi della cella della tabella
row1.Cells[0].Paragraphs.Add(logo);
//Crea variabili stringa con testo contenente tag html
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b> Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>";
// Crea un oggetto di testo da aggiungere a destra dell'immagine
Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
// Aggiungi i paragrafi di testo contenenti testo HTML alla cella della tabella
row1.Cells[1].Paragraphs.Add(TitleText);
// Impostare l'allineamento verticale del contenuto della riga come Alto
row1.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
// Crea righe nella tabella e quindi celle nelle righe
Aspose.Pdf.Row SecondRow = table1.Rows.Add();
SecondRow.Cells.Add();
// Impostare il valore dell'intervallo di riga per Seconda riga su 2
SecondRow.Cells[0].ColSpan = 2;
// Impostare l'allineamento verticale della seconda riga come Top
SecondRow.Cells[0].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
// Aggiungi i paragrafi di testo contenenti testo HTML alla cella della tabella
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
// Salva il file Pdf
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

## Conclusione

In questo tutorial, hai imparato come posizionare il testo attorno a un'immagine in un documento PDF utilizzando la libreria Aspose.PDF per .NET. Seguendo la guida dettagliata ed eseguendo il codice C# fornito, puoi creare una tabella, aggiungere un'immagine e posizionare il testo attorno all'immagine in un documento PDF.