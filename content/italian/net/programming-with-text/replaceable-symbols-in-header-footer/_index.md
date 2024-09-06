---
title: Simboli sostituibili nell'intestazione e nel piè di pagina
linktitle: Simboli sostituibili nell'intestazione e nel piè di pagina
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come utilizzare simboli sostituibili nell'intestazione e nel piè di pagina di un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 320
url: /it/net/programming-with-text/replaceable-symbols-in-header-footer/
---
In questo tutorial, spiegheremo come usare simboli sostituibili nell'intestazione e nel piè di pagina di un documento PDF usando la libreria Aspose.PDF per .NET. Esamineremo passo dopo passo il processo di creazione di un PDF, impostazione dei margini, aggiunta di intestazione e piè di pagina con simboli sostituibili e salvataggio del PDF usando il codice sorgente C# fornito.

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
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Passaggio 3: imposta i margini

Impostiamo i margini per la pagina utilizzando`MarginInfo` classe. Regola i valori del margine in base alle tue esigenze.

```csharp
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
page.PageInfo.Margin = marginInfo;
```

## Passaggio 4: aggiungere l'intestazione con simboli sostituibili

 Creiamo un`HeaderFooter` oggetto per la pagina e aggiungi un`TextFragment` con simboli sostituibili.

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

// Aggiungi altri TextFragments o personalizza in base alle tue esigenze
```

## Passaggio 5: aggiungere un piè di pagina con simboli sostituibili

 Allo stesso modo, creiamo un`HeaderFooter` oggetto per il piè di pagina e aggiungi`TextFragment` oggetti con simboli sostituibili.

```csharp
HeaderFooter hfFoot = new HeaderFooter();
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;

TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");

// Aggiungi altri TextFragments o personalizza in base alle tue esigenze

hfFoot.Paragraphs.Add(tab2);
```

## Passaggio 6: Salvare il documento PDF

Infine, salviamo il documento PDF nel file di output specificato.

```csharp
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols replaced successfully in the header and footer.\nFile saved at " + dataDir);
```

### Esempio di codice sorgente per simboli sostituibili nell'intestazione e nel piè di pagina utilizzando Aspose.PDF per .NET 
```csharp
// Percorso verso la directory dei documenti.
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
// Crea un paragrafo di testo che memorizzerà il contenuto da mostrare come intestazione
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
// Imposta l'oggetto HeaderFooter su piè di pagina dispari e pari
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;
// Aggiungere un paragrafo di testo contenente il numero di pagina corrente del numero totale di pagine
TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");
// Creare un'istanza di un oggetto tabella
Table tab2 = new Table();
// Aggiungere la tabella nella raccolta di paragrafi della sezione desiderata
hfFoot.Paragraphs.Add(tab2);
// Impostato con le larghezze delle colonne della tabella
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
//Sec1.Paragraphs.Add(New Text("Aspose.Total per Java è una compilazione di tutti i componenti Java offerti da Aspose. Viene compilato su base giornaliera per garantire che contenga le versioni più aggiornate di ciascuno dei nostri componenti Java. #$NL " + "Utilizzando Aspose.Total per Java gli sviluppatori possono creare un'ampia gamma di applicazioni. #$NL #$NL #$NP" + "Aspose.Total per Java è una compilazione di tutti i componenti Java offerti da Aspose. Viene compilato su base giornaliera per garantire che contenga le versioni più aggiornate di ciascuno dei nostri componenti Java. #$NL " + "Utilizzando Aspose.Total per Java gli sviluppatori possono creare un'ampia gamma di applicazioni. #$NL #$NL #$NP" + "Aspose.Total per Java è una compilazione di tutti i componenti Java offerti da Aspose. Viene compilato su base giornaliera per garantire che contenga le versioni più aggiornate di ciascuno dei nostri Componenti Java. #$NL " + "Utilizzando Aspose.Total per gli sviluppatori Java è possibile creare un'ampia gamma di applicazioni. #$NL #$NL"))
Table table = new Table();
table.ColumnWidths = "33% 33% 34%";
table.DefaultCellPadding = new MarginInfo();
table.DefaultCellPadding.Top = 10;
table.DefaultCellPadding.Bottom = 10;
// Aggiungere la tabella nella raccolta di paragrafi della sezione desiderata
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

In questo tutorial, hai imparato come usare simboli sostituibili nell'intestazione e nel piè di pagina di un documento PDF usando la libreria Aspose.PDF per .NET. Seguendo la guida passo passo ed eseguendo il codice C# fornito, puoi creare un PDF, impostare i margini, aggiungere intestazione e piè di pagina con simboli sostituibili e salvare il PDF.

### Domande frequenti

#### D: Qual è lo scopo del tutorial "Simboli sostituibili nell'intestazione e nel piè di pagina"?

R: Il tutorial "Simboli sostituibili nell'intestazione e nel piè di pagina" mira a guidarti attraverso il processo di utilizzo della libreria Aspose.PDF per .NET per aggiungere simboli sostituibili all'intestazione e al piè di pagina di un documento PDF. I simboli sostituibili consentono di sostituire dinamicamente segnaposto specifici con valori effettivi durante la generazione del PDF.

#### D: Cosa sono i simboli sostituibili nel contesto di un'intestazione e di un piè di pagina PDF?

R: I simboli sostituibili sono segnaposto che puoi inserire nell'intestazione e nel piè di pagina di un documento PDF. Questi simboli fungono da segnaposto dinamici per valori che possono essere inseriti in fase di esecuzione, come numeri di pagina, date e informazioni personalizzate.

#### D: Perché dovrei voler utilizzare simboli sostituibili nell'intestazione e nel piè di pagina di un PDF?

R: I simboli sostituibili nell'intestazione e nel piè di pagina sono utili quando si desidera includere informazioni dinamiche nei documenti PDF, come numeri di pagina, date o altri dati variabili che potrebbero cambiare durante la generazione del documento.

#### D: Come posso impostare i margini per la pagina PDF?

 A: È possibile impostare i margini per la pagina PDF utilizzando`MarginInfo` classe e assegnandola al`Margin` proprietà del`PageInfo` della pagina. Regola i valori dei margini come necessario.

#### D: Come posso aggiungere simboli sostituibili all'intestazione e al piè di pagina?

 A: È possibile aggiungere simboli sostituibili creando un`HeaderFooter` oggetto per l'intestazione e il piè di pagina della pagina. Quindi, puoi aggiungere`TextFragment`oggetti con il testo desiderato, inclusi simboli sostituibili, al`Paragraphs` raccolta di`HeaderFooter` oggetto.

#### D: Posso personalizzare l'aspetto dei simboli sostituibili?

 A: Sì, puoi personalizzare l'aspetto dei simboli sostituibili modificando le proprietà del`TextFragment` oggetti che contengono i simboli. Puoi impostare proprietà come font, dimensione del font, colore, allineamento e spaziatura delle linee.

#### D: Che tipo di simboli sostituibili posso usare?

A: È possibile utilizzare una varietà di simboli sostituibili, come:

- `$p`: Numero di pagina corrente.
- `$P`: Numero totale di pagine.
- `$d`: Data corrente.
- `$t`: Ora corrente.
- Segnaposto personalizzati da te definiti.

#### D: Posso includere altro testo e formattazione attorno ai simboli sostituibili?

 A: Sì, puoi includere altro testo e formattazione attorno ai simboli sostituibili all'interno del`TextFragment` oggetti. Ciò consente di creare intestazioni e piè di pagina più complessi che incorporano contenuti dinamici e statici.

#### D: Come posso salvare il documento PDF generato?

 A: Per salvare il documento PDF generato, puoi utilizzare`Save` metodo del`Document`classe. Fornisci il percorso e il nome del file di output desiderato come argomento.

#### D: Per questo tutorial è richiesta una licenza Aspose valida?

R: Sì, è richiesta una licenza Aspose valida per eseguire correttamente il codice in questo tutorial. Puoi ottenere una licenza completa o una licenza temporanea di 30 giorni dal sito Web di Aspose.