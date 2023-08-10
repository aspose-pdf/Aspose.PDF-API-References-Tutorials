---
title: Simboli sostituibili nel piè di pagina dell'intestazione
linktitle: Simboli sostituibili nel piè di pagina dell'intestazione
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come utilizzare i simboli sostituibili nell'intestazione e nel piè di pagina di un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 320
url: /it/net/programming-with-text/replaceable-symbols-in-header-footer/
---

In questo tutorial, spiegheremo come utilizzare i simboli sostituibili nell'intestazione e nel piè di pagina di un documento PDF utilizzando la libreria Aspose.PDF per .NET. Passeremo attraverso il processo passo-passo di creazione di un PDF, impostazione dei margini, aggiunta di intestazione e piè di pagina con simboli sostituibili e salvataggio del PDF utilizzando il codice sorgente C# fornito.

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
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Passaggio 3: imposta i margini

 Impostiamo i margini della pagina utilizzando il file`MarginInfo` classe. Regola i valori del margine in base alle tue esigenze.

```csharp
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
page.PageInfo.Margin = marginInfo;
```

## Passaggio 4: aggiungi un'intestazione con simboli sostituibili

 Creiamo un`HeaderFooter` oggetto per la pagina e aggiungere a`TextFragment` con simboli sostituibili ad esso.

```csharp
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;

TextFragment t1 = new TextFragment("report title");
// Impostare le proprietà del testo se lo si desidera
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t1.TextState.LineSpacing = 5f;

hfFirst.Paragraphs.Add(t1);

// Aggiungi più TextFragments o personalizza secondo necessità
```

## Passaggio 5: aggiungi piè di pagina con simboli sostituibili

 Allo stesso modo, creiamo a`HeaderFooter` oggetto per il piè di pagina e add`TextFragment` oggetti con simboli sostituibili.

```csharp
HeaderFooter hfFoot = new HeaderFooter();
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;

TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");

// Aggiungi più TextFragments o personalizza secondo necessità

hfFoot.Paragraphs.Add(tab2);
```

## Passaggio 6: salva il documento PDF

Infine, salviamo il documento PDF nel file di output specificato.

```csharp
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols replaced successfully in the header and footer.\nFile saved at " + dataDir);
```

### Esempio di codice sorgente per i simboli sostituibili nel piè di pagina dell'intestazione utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
// Assegnare l'istanza marginInfo alla proprietà Margin di sec1.PageInfo
page.PageInfo.Margin = marginInfo;
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;
// Crea un'istanza di un paragrafo di testo che memorizzerà il contenuto da mostrare come intestazione
TextFragment t1 = new TextFragment("report title");
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t1.TextState.LineSpacing = 5f;
hfFirst.Paragraphs.Add(t1);
TextFragment t2 = new TextFragment("Report_Name");
t2.TextState.Font = FontRepository.FindFont("Arial");
t2.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t2.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t2.TextState.LineSpacing = 5f;
t2.TextState.FontSize = 12;
hfFirst.Paragraphs.Add(t2);
// Crea un oggetto HeaderFooter per la sezione
HeaderFooter hfFoot = new HeaderFooter();
// Imposta l'oggetto HeaderFooter su piè di pagina pari e dispari
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;
// Aggiungi un paragrafo di testo contenente il numero di pagina corrente del numero totale di pagine
TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");
// Crea un'istanza di un oggetto tabella
Table tab2 = new Table();
// Aggiungi la tabella nella raccolta di paragrafi della sezione desiderata
hfFoot.Paragraphs.Add(tab2);
// Impostare con le larghezze delle colonne della tabella
tab2.ColumnWidths = "165 172 165";
// Crea righe nella tabella e quindi celle nelle righe
Row row3 = tab2.Rows.Add();
row3.Cells.Add();
row3.Cells.Add();
row3.Cells.Add();
// Imposta l'allineamento verticale del testo come allineato al centro
row3.Cells[0].Alignment = Aspose.Pdf.HorizontalAlignment.Left;
row3.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
row3.Cells[2].Alignment = Aspose.Pdf.HorizontalAlignment.Right;
row3.Cells[0].Paragraphs.Add(t3);
row3.Cells[1].Paragraphs.Add(t4);
row3.Cells[2].Paragraphs.Add(t5);
//Sec1.Paragraphs.Add(New Text("Aspose.Total per Java è una raccolta di tutti i componenti Java offerti da Aspose. Viene compilata su base giornaliera#$NL" + "per garantire che contenga le versioni più aggiornate di ogni dei nostri componenti Java. #$NL " + "Usando Aspose.Total per Java gli sviluppatori possono creare una vasta gamma di applicazioni. #$NL #$NL #$NP" + "Aspose.Total per Java è una raccolta di tutti i componenti Java offerto da Aspose. Viene compilato#$NL" + "giornalmente per garantire che contenga le versioni più aggiornate di ciascuno dei nostri componenti Java. #$NL " + "Usando Aspose.Total per gli sviluppatori Java è possibile creare un'ampia gamma di applicazioni. #$NL #$NL #$NP" + "Aspose.Total for Java è una raccolta di tutti i componenti Java offerti da Aspose. versioni aggiornate di ciascuno dei nostri componenti Java. #$NL " + "Utilizzando Aspose.Total per gli sviluppatori Java è possibile creare un'ampia gamma di applicazioni. #$NL #$NL"))
Table table = new Table();
table.ColumnWidths = "33% 33% 34%";
table.DefaultCellPadding = new MarginInfo();
table.DefaultCellPadding.Top = 10;
table.DefaultCellPadding.Bottom = 10;
// Aggiungi la tabella nella raccolta di paragrafi della sezione desiderata
page.Paragraphs.Add(table);
// Imposta il bordo della cella predefinito utilizzando l'oggetto BorderInfo
table.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1f);
// Imposta il bordo della tabella utilizzando un altro oggetto BorderInfo personalizzato
table.Border = new BorderInfo(BorderSide.All, 1f);
table.RepeatingRowsCount = 1;
// Crea righe nella tabella e quindi celle nelle righe
Row row1 = table.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");
const string CRLF = "\r\n";
for (int i = 0; i <= 10; i++)
{
	Row row = table.Rows.Add();
	row.IsRowBroken = true;
	for (int c = 0; c <= 2; c++)
	{
		Cell c1;
		if (c == 2)
			c1 = row.Cells.Add("Aspose.Total for Java is a compilation of every Java component offered by Aspose. It is compiled on a" + CRLF + "daily basis to ensure it contains the most up to date versions of each of our Java components. " + CRLF + "daily basis to ensure it contains the most up to date versions of each of our Java components. " + CRLF + "Using Aspose.Total for Java developers can create a wide range of applications.");
		else
			c1 = row.Cells.Add("item1" + c);
		c1.Margin = new MarginInfo();
		c1.Margin.Left = 30;
		c1.Margin.Top = 10;
		c1.Margin.Bottom = 10;
	}
}
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nSymbols replaced successfully in header and footer.\nFile saved at " + dataDir);
```

## Conclusione

In questo tutorial, hai imparato come utilizzare i simboli sostituibili nell'intestazione e nel piè di pagina di un documento PDF utilizzando la libreria Aspose.PDF per .NET. Seguendo la guida passo-passo ed eseguendo il codice C# fornito, puoi creare un PDF, impostare i margini, aggiungere intestazione e piè di pagina con simboli sostituibili e salvare il PDF.