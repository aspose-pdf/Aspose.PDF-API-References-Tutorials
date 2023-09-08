---
title: Tabella nella sezione piè di pagina dell'intestazione
linktitle: Tabella nella sezione piè di pagina dell'intestazione
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come aggiungere una tabella nella sezione intestazione/piè di pagina di un documento PDF con Aspose.PDF per .NET.
type: docs
weight: 170
url: /it/net/programming-with-stamps-and-watermarks/table-in-header-footer-section/
---
In questo tutorial, ti guideremo passo dopo passo su come aggiungere una tabella nella sezione intestazione o piè di pagina di un documento PDF utilizzando Aspose.PDF per .NET. Il codice sorgente C# fornito mostra come creare un documento PDF vuoto, aggiungere una pagina, configurare la sezione dell'intestazione, creare una tabella, aggiungere righe e celle alla tabella e infine salvare il documento PDF.

## Passaggio 1: configurazione dell'ambiente

Prima di iniziare, assicurati di avere quanto segue:

- Un ambiente di sviluppo .NET installato.
- La libreria Aspose.PDF per .NET scaricata e a cui si fa riferimento nel progetto.

## Passaggio 2: creazione del documento PDF e della pagina

 Il primo passo è creare un'istanza del file`Document` class e aggiungi una pagina al documento. Ecco come:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Istanziare un oggetto Document
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// Creare una pagina nel documento PDF
Aspose.Pdf.Page page = pdfDocument.Pages.Add();
```

Assicurati di sostituire "LA TUA DIRECTORY DOCUMENTI" con il percorso effettivo della directory in cui desideri salvare il documento PDF.

## Passaggio 3: configurazione della sezione di intestazione

 Ora configureremo la sezione di intestazione del documento PDF creando un'istanza del file`HeaderFooter` classe. Ecco come:

```csharp
// Crea una sezione di intestazione per il file PDF
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Definire la sezione di intestazione della pagina
page. Header = header;

// Imposta il margine superiore della sezione dell'intestazione
header. Margin. Top = 20;
```

## Passaggio 4: creazione della tabella

 Ora creeremo una tabella utilizzando il file`Table` class e aggiungerlo alla raccolta di paragrafi della sezione dell'intestazione. Ecco come:

```csharp
// Istanziare un oggetto Tabella
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Aggiungi la tabella alla raccolta di paragrafi della sezione di intestazione
header.Paragraphs.Add(tab1);

// Definire la larghezza delle colonne della tabella
tab1.ColumnWidths = "60,300";
```

Il codice precedente crea una tabella con due colonne di larghezza specificata.

## Passaggio 5: aggiungi righe e celle alla tabella

 Ora aggiungeremo righe e celle alla tabella utilizzando il comando`Row` classe e il`Cell` classe. Ecco come:

```csharp
// Crea una riga nella tabella e aggiungi celle
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in header section");
row1.BackgroundColor = Color.Gray;

// Unisci la prima cella della prima riga
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// Crea un'altra riga nella tabella e aggiungi una cella con un'immagine
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.BackgroundColor = Color.White;
Aspose.Pdf.Cell cell2 = row2.Cells.Add();
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg";
img. FixWidth = 60;
cell2.Paragraphs.Add(img);
row2.Cells.Add("The logo is beautiful!");
row2.Cells[1].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");
row2.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
row2.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
```

## Passaggio 6: salvataggio del documento PDF

Una volta aggiunta la tabella alla sezione dell'intestazione, possiamo salvare il documento PDF. Ecco come:

```csharp
// Salvare il file PDF
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");
```

Assicurati di sostituire "LA TUA DIRECTORY DOCUMENTI" con il percorso effettivo della directory in cui desideri salvare il documento PDF.

### Codice sorgente di esempio per la tabella nella sezione piè di pagina dell'intestazione utilizzando Aspose.PDF per .NET 
```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crea un'istanza del documento chiamando il costruttore vuoto
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// Creare una pagina nel documento pdf
Aspose.Pdf.Page page = pdfDocument.Pages.Add();

// Crea una sezione di intestazione del file PDF
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

//Imposta l'intestazione dispari per il file PDF
page.Header = header;

// Imposta il margine superiore per la sezione dell'intestazione
header.Margin.Top = 20;

// Istanziare un oggetto tabella
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Aggiungi la tabella nella raccolta paragrafi della sezione desiderata
header.Paragraphs.Add(tab1);

// Imposta il bordo predefinito della cella utilizzando l'oggetto BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Impostato con la larghezza delle colonne della tabella
tab1.ColumnWidths = "60 300";
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg";

// Crea righe nella tabella e poi celle nelle righe
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in Header Section");
row1.BackgroundColor = Color.Gray;

// Imposta il valore dell'intervallo di righe per la prima riga su 2
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// Crea righe nella tabella e poi celle nelle righe
Aspose.Pdf.Row row2 = tab1.Rows.Add();

// Imposta il colore di sfondo per Row2
row2.BackgroundColor = Color.White;

// Aggiungi la cella che contiene l'immagine
Aspose.Pdf.Cell cell2 = row2.Cells.Add();

// Imposta la larghezza dell'immagine su 60
img.FixWidth = 60;

// Aggiungi l'immagine alla cella della tabella
cell2.Paragraphs.Add(img);
row2.Cells.Add("Logo is looking fine !");
row2.Cells[1].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// Imposta l'allineamento verticale del testo come allineato al centro
row2.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
row2.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;

// Salvare il file PDF
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");

```

## Conclusione

Congratulazioni! Hai imparato come aggiungere una tabella nella sezione intestazione o piè di pagina di un documento PDF utilizzando Aspose.PDF per .NET. Ora puoi personalizzare intestazioni e piè di pagina aggiungendo tabelle per visualizzare informazioni aggiuntive nei tuoi documenti PDF.

### Domande frequenti sulla tabella nella sezione del piè di pagina dell'intestazione

#### D: Qual è lo scopo di aggiungere una tabella nella sezione dell'intestazione o del piè di pagina di un documento PDF?

R: L'aggiunta di una tabella nella sezione intestazione o piè di pagina di un documento PDF ti consente di visualizzare informazioni strutturate e organizzate come titoli, sottotitoli, loghi o qualsiasi altro contenuto che desideri appaia in modo coerente su ogni pagina del documento.

#### D: In che modo il codice sorgente C# fornito consente di aggiungere una tabella nella sezione dell'intestazione o del piè di pagina di un documento PDF?

R: Il codice illustra il processo di creazione di un documento PDF vuoto, aggiunta di una pagina, configurazione della sezione di intestazione, creazione di una tabella con righe e celle e infine salvataggio del documento PDF. Il risultato è una tabella visualizzata nella sezione dell'intestazione del documento PDF.

#### D: Posso personalizzare l'aspetto delle celle della tabella, ad esempio bordi, colore di sfondo e stile del testo?

R: Sì, puoi personalizzare l'aspetto delle celle della tabella impostando proprietà come bordi della cella, colore di sfondo, stile del testo, carattere, dimensione del carattere e altro.

#### D: Come viene aggiunta la tabella alla sezione dell'intestazione del documento PDF?

R: Il codice aggiunge la tabella alla raccolta di paragrafi della sezione di intestazione, garantendo che la tabella venga visualizzata nell'intestazione di ogni pagina.

#### D: Posso aggiungere più righe e celle alla tabella secondo necessità?

 R: Assolutamente, puoi aggiungere più righe e celle alla tabella utilizzando il file`Rows.Add()` E`Cells.Add()` metodi. Ciò consente di strutturare il contenuto della tabella come desiderato.

#### D: È possibile regolare la larghezza delle colonne della tabella?
 R: Sì, puoi regolare la larghezza delle colonne della tabella utilizzando`ColumnWidths` proprietà. Ciò consente di controllare il layout della tabella.

#### D: Come posso estendere le celle su più colonne o righe all'interno della tabella?
 R: Per estendere le celle su più colonne, puoi utilizzare il file`ColSpan` proprietà della cella corrispondente. Allo stesso modo, puoi usare il file`RowSpan` proprietà per estendere le celle su più righe.

#### D: Cosa succede se desidero aggiungere una tabella sia alla sezione dell'intestazione che a quella del piè di pagina del documento PDF?

R: Puoi seguire un approccio simile sia per la sezione dell'intestazione che per quella del piè di pagina. Crea semplicemente un file`HeaderFooter` istanza per il piè di pagina, configuralo e aggiungi la tabella alla raccolta di paragrafi.

#### D: Posso utilizzare immagini all'interno delle celle della tabella e come si ottiene ciò?

 R: Sì, puoi aggiungere immagini all'interno delle celle della tabella. L'esempio di codice dimostra l'aggiunta di un'immagine a una cella creando un file`Image` oggetto, impostandone il percorso e le dimensioni del file, quindi aggiungendolo ai paragrafi di una cella.

#### D: Come posso garantire che la tabella venga visualizzata in modo coerente su tutte le pagine del documento PDF?

 R: Quando aggiungi la tabella alla sezione dell'intestazione o del piè di pagina utilizzando il file`HeaderFooter` Ad esempio, Aspose.PDF garantisce che la tabella venga visualizzata in modo coerente su ogni pagina, fornendo un layout uniforme.