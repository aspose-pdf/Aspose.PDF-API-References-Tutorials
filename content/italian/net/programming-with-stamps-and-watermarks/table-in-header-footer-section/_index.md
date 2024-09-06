---
title: Tabella nella sezione Intestazione Piè di pagina
linktitle: Tabella nella sezione Intestazione Piè di pagina
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come aggiungere una tabella nella sezione intestazione/piè di pagina di un documento PDF con Aspose.PDF per .NET.
type: docs
weight: 170
url: /it/net/programming-with-stamps-and-watermarks/table-in-header-footer-section/
---
In questo tutorial, ti guideremo passo dopo passo su come aggiungere una tabella nella sezione intestazione o piè di pagina di un documento PDF utilizzando Aspose.PDF per .NET. Il codice sorgente C# fornito ti mostra come creare un documento PDF vuoto, aggiungere una pagina, configurare la sezione intestazione, creare una tabella, aggiungere righe e celle alla tabella e infine salvare il documento PDF.

## Fase 1: Impostazione dell'ambiente

Prima di iniziare, assicurati di avere quanto segue:

- Un ambiente di sviluppo .NET installato.
- La libreria Aspose.PDF per .NET è stata scaricata e a cui si fa riferimento nel progetto.

## Passaggio 2: creazione del documento PDF e della pagina

 Il primo passo è creare un'istanza di`Document` classe e aggiungi una pagina al documento. Ecco come:

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Istanziare un oggetto Documento
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// Crea una pagina nel documento PDF
Aspose.Pdf.Page page = pdfDocument.Pages.Add();
```

Assicurati di sostituire "LA TUA DIRECTORY DEI DOCUMENTI" con il percorso effettivo della directory in cui desideri salvare il documento PDF.

## Passaggio 3: configurazione della sezione dell'intestazione

 Ora configureremo la sezione dell'intestazione del documento PDF creando un'istanza di`HeaderFooter` classe. Ecco come:

```csharp
// Crea una sezione di intestazione per il file PDF
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Definisci la sezione dell'intestazione per la pagina
page. Header = header;

// Imposta il margine superiore della sezione dell'intestazione
header. Margin. Top = 20;
```

## Fase 4: Creazione della tabella

 Ora creeremo una tabella utilizzando il`Table` classe e aggiungerla alla raccolta di paragrafi della sezione intestazione. Ecco come:

```csharp
// Crea un'istanza di un oggetto Tabella
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Aggiungere la tabella alla raccolta di paragrafi della sezione dell'intestazione
header.Paragraphs.Add(tab1);

// Definire le larghezze delle colonne della tabella
tab1.ColumnWidths = "60,300";
```

Il codice sopra crea una tabella con due colonne di larghezze specificate.

## Passaggio 5: aggiungere righe e celle alla tabella

 Ora aggiungeremo righe e celle alla tabella utilizzando`Row` classe e la`Cell` classe. Ecco come:

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

Una volta aggiunta la tabella alla sezione header, possiamo salvare il documento PDF. Ecco come:

```csharp
// Salva il file PDF
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");
```

Assicurati di sostituire "LA TUA DIRECTORY DEI DOCUMENTI" con il percorso effettivo della directory in cui desideri salvare il documento PDF.

### Esempio di codice sorgente per la tabella nella sezione intestazione/piè di pagina utilizzando Aspose.PDF per .NET 
```csharp

// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crea un'istanza del documento chiamando un costruttore vuoto
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// Crea una pagina nel documento pdf
Aspose.Pdf.Page page = pdfDocument.Pages.Add();

//Crea una sezione di intestazione del file PDF
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Imposta l'intestazione dispari per il file PDF
page.Header = header;

// Imposta il margine superiore per la sezione dell'intestazione
header.Margin.Top = 20;

// Creare un'istanza di un oggetto tabella
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Aggiungere la tabella nella raccolta di paragrafi della sezione desiderata
header.Paragraphs.Add(tab1);

// Imposta il bordo predefinito della cella utilizzando l'oggetto BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Impostato con le larghezze delle colonne della tabella
tab1.ColumnWidths = "60 300";
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg";

// Crea righe nella tabella e poi celle nelle righe
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in Header Section");
row1.BackgroundColor = Color.Gray;

// Imposta il valore dell'intervallo di riga per la prima riga su 2
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// Crea righe nella tabella e poi celle nelle righe
Aspose.Pdf.Row row2 = tab1.Rows.Add();

// Imposta il colore di sfondo per Row2
row2.BackgroundColor = Color.White;

// Aggiungi la cella che contiene l'immagine
Aspose.Pdf.Cell cell2 = row2.Cells.Add();

// Imposta la larghezza dell'immagine a 60
img.FixWidth = 60;

// Aggiungere l'immagine alla cella della tabella
cell2.Paragraphs.Add(img);
row2.Cells.Add("Logo is looking fine !");
row2.Cells[1].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// Imposta l'allineamento verticale del testo come allineato al centro
row2.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
row2.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;

// Salva il file PDF
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");

```

## Conclusione

Congratulazioni! Hai imparato come aggiungere una tabella nella sezione intestazione o piè di pagina di un documento PDF usando Aspose.PDF per .NET. Ora puoi personalizzare le tue intestazioni e piè di pagina aggiungendo tabelle per visualizzare informazioni aggiuntive nei tuoi documenti PDF.

### FAQ per la tabella nella sezione intestazione/piè di pagina

#### D: Qual è lo scopo di aggiungere una tabella nella sezione intestazione o piè di pagina di un documento PDF?

R: Aggiungere una tabella nella sezione intestazione o piè di pagina di un documento PDF consente di visualizzare informazioni strutturate e organizzate, come titoli, sottotitoli, loghi o qualsiasi altro contenuto che si desidera venga visualizzato in modo coerente in ogni pagina del documento.

#### D: In che modo il codice sorgente C# fornito consente di aggiungere una tabella nella sezione intestazione o piè di pagina di un documento PDF?

R: Il codice illustra il processo di creazione di un documento PDF vuoto, aggiunta di una pagina, configurazione della sezione dell'intestazione, creazione di una tabella con righe e celle e infine salvataggio del documento PDF. Il risultato è una tabella visualizzata nella sezione dell'intestazione del documento PDF.

#### D: Posso personalizzare l'aspetto delle celle della tabella, ad esempio i bordi, il colore di sfondo e lo stile del testo?

R: Sì, puoi personalizzare l'aspetto delle celle della tabella impostando proprietà come i bordi delle celle, il colore di sfondo, lo stile del testo, il carattere, la dimensione del carattere e altro ancora.

#### D: Come viene aggiunta la tabella alla sezione dell'intestazione del documento PDF?

R: Il codice aggiunge la tabella alla raccolta di paragrafi della sezione dell'intestazione, il che garantisce che la tabella venga visualizzata nell'intestazione di ogni pagina.

#### D: Posso aggiungere altre righe e celle alla tabella se necessario?

 A: Assolutamente, puoi aggiungere più righe e celle alla tabella utilizzando`Rows.Add()` E`Cells.Add()` metodi. Ciò consente di strutturare il contenuto della tabella come desiderato.

#### D: È possibile regolare la larghezza delle colonne della tabella?
 A: Sì, puoi regolare la larghezza delle colonne della tabella utilizzando`ColumnWidths` proprietà. Ciò consente di controllare il layout della tabella.

#### D: Come posso estendere le celle su più colonne o righe all'interno della tabella?
 A: Per estendere le celle su più colonne, puoi utilizzare`ColSpan`proprietà della cella corrispondente. Allo stesso modo, puoi usare la`RowSpan` proprietà per estendere le celle su più righe.

#### D: Cosa succede se voglio aggiungere una tabella sia all'intestazione che al piè di pagina del documento PDF?

 R: Puoi seguire un approccio simile per entrambe le sezioni header e footer. Crea semplicemente un`HeaderFooter` istanza per il piè di pagina, configurarla e aggiungere la tabella alla sua raccolta di paragrafi.

#### D: Posso utilizzare immagini all'interno delle celle della tabella? Come si fa?

 R: Sì, puoi aggiungere immagini all'interno delle celle della tabella. L'esempio di codice dimostra l'aggiunta di un'immagine a una cella creando un`Image` oggetto, impostandone il percorso e le dimensioni, e quindi aggiungendolo ai paragrafi di una cella.

#### D: Come posso assicurarmi che la tabella venga visualizzata in modo uniforme in tutte le pagine del documento PDF?

 A: Quando aggiungi la tabella alla sezione intestazione o piè di pagina utilizzando`HeaderFooter` Ad esempio, Aspose.PDF garantisce che la tabella venga visualizzata in modo coerente su ogni pagina, fornendo un layout uniforme.