---
title: Simboli sostituibili nel piè di pagina dell'intestazione
linktitle: Simboli sostituibili nel piè di pagina dell'intestazione
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come utilizzare simboli sostituibili nell'intestazione e nel piè di pagina di un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 320
url: /it/net/programming-with-text/replaceable-symbols-in-header-footer/
---
In questo tutorial spiegheremo come utilizzare simboli sostituibili nell'intestazione e nel piè di pagina di un documento PDF utilizzando la libreria Aspose.PDF per .NET. Seguiremo il processo passo passo di creazione di un PDF, impostazione dei margini, aggiunta di intestazione e piè di pagina con simboli sostituibili e salvataggio del PDF utilizzando il codice sorgente C# fornito.

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
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Passaggio 3: imposta i margini

 Impostiamo i margini della pagina utilizzando il file`MarginInfo`classe. Modifica i valori dei margini in base alle tue esigenze.

```csharp
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
page.PageInfo.Margin = marginInfo;
```

## Passaggio 4: aggiungi intestazione con simboli sostituibili

 Creiamo un`HeaderFooter` oggetto per la pagina e aggiungi un file`TextFragment` con simboli sostituibili.

```csharp
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;

TextFragment t1 = new TextFragment("report title");
// Imposta le proprietà del testo se lo desideri
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

 Allo stesso modo, creiamo a`HeaderFooter` oggetto per il piè di pagina e aggiungi`TextFragment` oggetti con simboli sostituibili.

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

### Codice sorgente di esempio per i simboli sostituibili nel piè di pagina dell'intestazione utilizzando Aspose.PDF per .NET 
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
// Imposta l'oggetto HeaderFooter sul piè di pagina pari e dispari
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;
// Aggiungi un paragrafo di testo contenente il numero di pagina corrente del numero totale di pagine
TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");
// Istanziare un oggetto tabella
Table tab2 = new Table();
// Aggiungi la tabella nella raccolta paragrafi della sezione desiderata
hfFoot.Paragraphs.Add(tab2);
// Impostato con la larghezza delle colonne della tabella
tab2.ColumnWidths = "165 172 165";
// Crea righe nella tabella e poi celle nelle righe
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
//Sec1.Paragraphs.Add(New Text("Aspose.Total per Java è una raccolta di tutti i componenti Java offerti da Aspose. È compilato su base giornaliera#$NL" + "per garantire che contenga le versioni più aggiornate di ciascuno dei nostri componenti Java. #$NL " + "Utilizzando Aspose.Total per Java gli sviluppatori possono creare un'ampia gamma di applicazioni. #$NL #$NL #$NP" + "Aspose.Total per Java è una raccolta di tutti i componenti Java offerto da Aspose. Viene compilato #$NL" + "giornalmente per garantire che contenga le versioni più aggiornate di ciascuno dei nostri componenti Java. #$NL " + "Utilizzando Aspose.Total per gli sviluppatori Java è possibile creare un'ampia gamma di applicazioni. #$NL #$NL #$NP" + "Aspose.Total for Java è una raccolta di tutti i componenti Java offerti da Aspose. Viene compilato #$NL" + "su base giornaliera per garantire che contenga la maggior parte versioni aggiornate di ciascuno dei nostri componenti Java. #$NL " + "Utilizzando Aspose.Total per gli sviluppatori Java è possibile creare un'ampia gamma di applicazioni. #$NL #$NL"))
Table table = new Table();
table.ColumnWidths = "33% 33% 34%";
table.DefaultCellPadding = new MarginInfo();
table.DefaultCellPadding.Top = 10;
table.DefaultCellPadding.Bottom = 10;
// Aggiungi la tabella nella raccolta paragrafi della sezione desiderata
page.Paragraphs.Add(table);
// Imposta il bordo predefinito della cella utilizzando l'oggetto BorderInfo
table.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1f);
// Imposta il bordo della tabella utilizzando un altro oggetto BorderInfo personalizzato
table.Border = new BorderInfo(BorderSide.All, 1f);
table.RepeatingRowsCount = 1;
// Crea righe nella tabella e poi celle nelle righe
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

In questo tutorial hai imparato come utilizzare simboli sostituibili nell'intestazione e nel piè di pagina di un documento PDF utilizzando la libreria Aspose.PDF per .NET. Seguendo la guida passo passo ed eseguendo il codice C# fornito, puoi creare un PDF, impostare i margini, aggiungere intestazione e piè di pagina con simboli sostituibili e salvare il PDF.

### Domande frequenti

#### D: Qual è lo scopo del tutorial "Simboli sostituibili nel piè di pagina dell'intestazione"?

R: Il tutorial "Simboli sostituibili nel piè di pagina dell'intestazione" mira a guidarti attraverso il processo di utilizzo della libreria Aspose.PDF per .NET per aggiungere simboli sostituibili all'intestazione e al piè di pagina di un documento PDF. I simboli sostituibili consentono di sostituire dinamicamente segnaposto specifici con valori effettivi durante la generazione del PDF.

#### D: Quali sono i simboli sostituibili nel contesto di un'intestazione e di un piè di pagina PDF?

R: I simboli sostituibili sono segnaposto che puoi inserire nell'intestazione e nel piè di pagina di un documento PDF. Questi simboli fungono da segnaposto dinamici per valori che possono essere compilati in fase di esecuzione, come numeri di pagina, date e informazioni personalizzate.

#### D: Perché dovrei utilizzare simboli sostituibili nell'intestazione e nel piè di pagina di un PDF?

R: I simboli sostituibili nell'intestazione e nel piè di pagina sono utili quando desideri includere informazioni dinamiche nei tuoi documenti PDF, come numeri di pagina, date o altri dati variabili che potrebbero cambiare quando il documento viene generato.

#### D: Come posso impostare i margini per la pagina PDF?

 R: Puoi impostare i margini per la pagina PDF utilizzando il file`MarginInfo` classe e assegnandolo a`Margin` proprietà del`PageInfo` della pagina. Regolare i valori dei margini secondo necessità.

#### D: Come posso aggiungere simboli sostituibili all'intestazione e al piè di pagina?

 R: Puoi aggiungere simboli sostituibili creando un`HeaderFooter` oggetto per l'intestazione e il piè di pagina della pagina. Quindi puoi aggiungere`TextFragment`oggetti con il testo desiderato, inclusi i simboli sostituibili, al`Paragraphs` raccolta del`HeaderFooter` oggetto.

#### D: Posso personalizzare l'aspetto dei simboli sostituibili?

 R: Sì, puoi personalizzare l'aspetto dei simboli sostituibili modificando le proprietà del file`TextFragment` oggetti che contengono i simboli. È possibile impostare proprietà quali carattere, dimensione del carattere, colore, allineamento e interlinea.

#### D: Che tipo di simboli sostituibili posso utilizzare?

R: Puoi utilizzare una varietà di simboli sostituibili, come ad esempio:

- `$p`: Numero della pagina corrente.
- `$P`: Numero totale di pagine.
- `$d`: Data odierna.
- `$t`: Ora attuale.
- Segnaposto personalizzati definiti dall'utente.

#### D: Posso includere altro testo e formattazione attorno ai simboli sostituibili?

 R: Sì, puoi includere altro testo e formattazione attorno ai simboli sostituibili all'interno del file`TextFragment` oggetti. Ciò consente di creare intestazioni e piè di pagina più complessi che incorporano contenuto dinamico e statico.

#### D: Come posso salvare il documento PDF generato?

 R: Per salvare il documento PDF generato, puoi utilizzare il file`Save` metodo del`Document`classe. Fornire il percorso e il nome del file di output desiderati come argomento.

#### D: Per questo tutorial è necessaria una licenza Aspose valida?

R: Sì, è necessaria una licenza Aspose valida per eseguire correttamente il codice in questo tutorial. È possibile ottenere una licenza completa o una licenza temporanea di 30 giorni dal sito Web Aspose.