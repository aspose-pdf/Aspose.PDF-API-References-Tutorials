---
title: Tabella nella sezione del piè di pagina dell'intestazione
linktitle: Tabella nella sezione del piè di pagina dell'intestazione
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come aggiungere una tabella nella sezione intestazione/piè di pagina di un documento PDF con Aspose.PDF per .NET.
type: docs
weight: 170
url: /it/net/programming-with-stamps-and-watermarks/table-in-header-footer-section/
---
In questo tutorial, ti guideremo passo dopo passo su come aggiungere una tabella nella sezione dell'intestazione o del piè di pagina di un documento PDF utilizzando Aspose.PDF per .NET. Il codice sorgente C# fornito mostra come creare un documento PDF vuoto, aggiungere una pagina, configurare la sezione dell'intestazione, creare una tabella, aggiungere righe e celle alla tabella e infine salvare il documento PDF.

## Passaggio 1: configurazione dell'ambiente

Prima di iniziare, assicurati di avere quanto segue:

- Un ambiente di sviluppo .NET installato.
- La libreria Aspose.PDF per .NET scaricata e referenziata nel tuo progetto.

## Passaggio 2: creazione del documento e della pagina PDF

 Il primo passaggio consiste nel creare un'istanza di`Document` class e aggiungi una pagina al documento. Ecco come:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Crea un'istanza di un oggetto Document
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// Crea una pagina nel documento PDF
Aspose.Pdf.Page page = pdfDocument.Pages.Add();
```

Assicurati di sostituire "YOUR DOCUMENTI DIRECTORY" con il percorso effettivo della directory in cui desideri salvare il documento PDF.

## Passaggio 3: configurazione della sezione dell'intestazione

 Ora configureremo la sezione dell'intestazione del documento PDF creando un'istanza del file`HeaderFooter` classe. Ecco come:

```csharp
// Crea una sezione di intestazione per il file PDF
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Definire la sezione dell'intestazione per la pagina
page. Header = header;

//Imposta il margine superiore della sezione dell'intestazione
header. Margin. Top = 20;
```

## Passaggio 4: creazione della tabella

 Ora creeremo una tabella usando il`Table` class e aggiungerlo alla raccolta di paragrafi della sezione di intestazione. Ecco come:

```csharp
// Crea un'istanza di un oggetto Table
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Aggiungi la tabella alla raccolta di paragrafi della sezione di intestazione
header.Paragraphs.Add(tab1);

// Definire le larghezze delle colonne della tabella
tab1.ColumnWidths = "60,300";
```

Il codice sopra crea una tabella con due colonne di larghezze specificate.

## Passaggio 5: aggiungi righe e celle alla tabella

 Ora aggiungeremo righe e celle alla tabella utilizzando il`Row` classe e il`Cell` classe. Ecco come:

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

## Passaggio 6: salvare il documento PDF

Una volta che la tabella è stata aggiunta alla sezione dell'intestazione, possiamo salvare il documento PDF. Ecco come:

```csharp
//Salva il file PDF
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");
```

Assicurati di sostituire "YOUR DOCUMENTI DIRECTORY" con il percorso effettivo della directory in cui desideri salvare il documento PDF.

### Esempio di codice sorgente per la sezione Table In Header Footer utilizzando Aspose.PDF per .NET 
```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crea un'istanza di Document chiamando il costruttore vuoto
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

//Crea una pagina nel documento pdf
Aspose.Pdf.Page page = pdfDocument.Pages.Add();

// Crea una sezione di intestazione del file PDF
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Imposta l'intestazione dispari per il file PDF
page.Header = header;

// Imposta il margine superiore per la sezione dell'intestazione
header.Margin.Top = 20;

// Crea un'istanza di un oggetto tabella
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Aggiungi la tabella nella raccolta di paragrafi della sezione desiderata
header.Paragraphs.Add(tab1);

// Imposta il bordo della cella predefinito utilizzando l'oggetto BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Impostare con le larghezze delle colonne della tabella
tab1.ColumnWidths = "60 300";
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg";

// Crea righe nella tabella e quindi celle nelle righe
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in Header Section");
row1.BackgroundColor = Color.Gray;

// Impostare il valore dell'intervallo di riga per la prima riga su 2
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// Crea righe nella tabella e quindi celle nelle righe
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

// Salva il file Pdf
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");

```

## Conclusione

Congratulazioni! Hai imparato come aggiungere una tabella nella sezione dell'intestazione o del piè di pagina di un documento PDF utilizzando Aspose.PDF per .NET. Ora puoi personalizzare intestazioni e piè di pagina aggiungendo tabelle per visualizzare informazioni aggiuntive nei tuoi documenti PDF.

### Domande frequenti per la tabella nella sezione del piè di pagina dell'intestazione

#### D: Qual è lo scopo dell'aggiunta di una tabella nella sezione dell'intestazione o del piè di pagina di un documento PDF?

R: L'aggiunta di una tabella nella sezione dell'intestazione o del piè di pagina di un documento PDF consente di visualizzare informazioni strutturate e organizzate come titoli, sottotitoli, loghi o qualsiasi altro contenuto che desideri venga visualizzato in modo coerente su ogni pagina del documento.

#### D: In che modo il codice sorgente C# fornito ottiene l'aggiunta di una tabella nella sezione dell'intestazione o del piè di pagina di un documento PDF?

R: Il codice mostra il processo di creazione di un documento PDF vuoto, l'aggiunta di una pagina, la configurazione della sezione dell'intestazione, la creazione di una tabella con righe e celle e infine il salvataggio del documento PDF. Il risultato è una tabella visualizzata nella sezione dell'intestazione del documento PDF.

#### D: Posso personalizzare l'aspetto delle celle della tabella, come i bordi, il colore di sfondo e lo stile del testo?

R: Sì, puoi personalizzare l'aspetto delle celle della tabella impostando proprietà come i bordi delle celle, il colore di sfondo, lo stile del testo, il carattere, la dimensione del carattere e altro.

#### D: Come viene aggiunta la tabella alla sezione dell'intestazione del documento PDF?

R: Il codice aggiunge la tabella alla raccolta dei paragrafi della sezione dell'intestazione, il che garantisce che la tabella venga visualizzata nell'intestazione di ogni pagina.

#### D: Posso aggiungere più righe e celle alla tabella secondo necessità?

 A: Assolutamente, puoi aggiungere più righe e celle alla tabella usando il`Rows.Add()` E`Cells.Add()` metodi. Ciò consente di strutturare il contenuto della tabella come desiderato.

#### D: È possibile regolare la larghezza delle colonne della tabella?
 R: Sì, puoi regolare la larghezza delle colonne della tabella utilizzando il`ColumnWidths` proprietà. Ciò consente di controllare il layout della tabella.

#### D: Come posso estendere le celle su più colonne o righe all'interno della tabella?
 A: Per estendere le celle su più colonne, puoi utilizzare il`ColSpan`proprietà della cella corrispondente. Allo stesso modo, puoi usare il`RowSpan` proprietà per estendere le celle su più righe.

#### D: Cosa succede se desidero aggiungere una tabella a entrambe le sezioni dell'intestazione e del piè di pagina del documento PDF?

 R: Puoi seguire un approccio simile per entrambe le sezioni dell'intestazione e del piè di pagina. Crea semplicemente un file`HeaderFooter` esempio per il piè di pagina, configuralo e aggiungi la tabella alla sua raccolta di paragrafi.

#### D: Posso utilizzare le immagini all'interno delle celle della tabella e come si ottiene ciò?

 R: Sì, puoi aggiungere immagini all'interno delle celle della tabella. L'esempio di codice illustra l'aggiunta di un'immagine a una cella creando un file`Image` oggetto, impostandone il percorso e le dimensioni del file, quindi aggiungendolo ai paragrafi di una cella.

#### D: Come posso assicurarmi che la tabella appaia uniformemente su tutte le pagine del documento PDF?

 R: Quando aggiungi la tabella alla sezione dell'intestazione o del piè di pagina utilizzando il file`HeaderFooter` esempio, Aspose.PDF assicura che la tabella appaia in modo coerente su ogni pagina, fornendo un layout uniforme.