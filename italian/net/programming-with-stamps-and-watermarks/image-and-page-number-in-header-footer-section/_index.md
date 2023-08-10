---
title: Immagine e numero di pagina nella sezione del piè di pagina dell'intestazione
linktitle: Immagine e numero di pagina nella sezione del piè di pagina dell'intestazione
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come aggiungere un'immagine e un numero di pagina nell'intestazione e nel piè di pagina di un documento PDF con Aspose.
type: docs
weight: 110
url: /it/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section/
---
In questo tutorial, ti guideremo passo dopo passo su come aggiungere un'immagine e un numero di pagina nella sezione dell'intestazione e del piè di pagina di un documento PDF utilizzando Aspose.PDF per .NET. Ti mostreremo come utilizzare il codice sorgente C# fornito per creare una pagina, impostare intestazione e piè di pagina, aggiungere un'immagine all'intestazione e testo con numero di pagina al documento PDF a piè di pagina.

## Passaggio 1: configurazione dell'ambiente

Prima di iniziare, assicurati di avere quanto segue:

- Un ambiente di sviluppo .NET installato.
- La libreria Aspose.PDF per .NET scaricata e referenziata nel tuo progetto.

## Passaggio 2: creazione del documento e della pagina PDF

Il primo passaggio consiste nel creare un nuovo oggetto Documento e una pagina nel documento PDF. Ecco come:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Crea un nuovo oggetto Documento
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Crea una pagina nel documento
Aspose.Pdf.Page page = doc.Pages.Add();
```

Il codice precedente crea un nuovo oggetto Document e una pagina vuota nel documento PDF.

## Passaggio 3: aggiunta dell'intestazione con un'immagine

Ora che la pagina è stata creata, possiamo aggiungere una sezione di intestazione con un'immagine. Ecco come:

```csharp
// Crea una sezione di intestazione
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Imposta l'intestazione della pagina
page. Header = header;

// Crea un oggetto Immagine
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Imposta il percorso dell'immagine
image1.File = dataDir + "aspose-logo.jpg";

// Aggiungi l'immagine all'intestazione della pagina del documento PDF
header.Paragraphs.Add(image1);
```

Il codice sopra crea una sezione di intestazione, imposta l'intestazione della pagina con questa sezione e aggiunge un'immagine all'intestazione.

## Passaggio 4: aggiungere il piè di pagina con il numero di pagina

Ora che l'intestazione è stata aggiunta, possiamo aggiungere una sezione a piè di pagina con un numero di pagina. Ecco come:

```csharp
// Crea una sezione a piè di pagina
Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();

// Definire il piè di pagina del documento PDF
page. Footer = footer;

// Crea un oggetto TextFragment
Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P)");

// Aggiungi il testo con il numero di pagina al piè di pagina del documento PDF
footer.Paragraphs.Add(txt);
```

Il codice precedente crea una sezione footer, imposta il footer della pagina con questa sezione e aggiunge un TextFragment contenente il testo "Page: ($p of $P )"

  che visualizza il numero di pagina.

## Passaggio 5: salvare il documento PDF modificato

Una volta aggiunti l'intestazione e il piè di pagina, possiamo salvare il documento PDF modificato. Ecco come:

```csharp
// Salva il documento PDF modificato
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");
```

Il codice precedente salva il documento PDF modificato nella directory specificata.

### Esempio di codice sorgente per immagine e numero di pagina nella sezione piè di pagina dell'intestazione utilizzando Aspose.PDF per .NET 
```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Creare una pagina nell'oggetto documento
Aspose.Pdf.Page page = doc.Pages.Add();

// Crea Sezione Intestazione del documento
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Imposta l'intestazione per il file PDF
page.Header = header;

// Crea un oggetto immagine nella pagina
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

//Imposta il percorso del file immagine
image1.File = dataDir + "aspose-logo.jpg";

// Aggiungi l'immagine alla pagina di intestazione del file Pdf
header.Paragraphs.Add(image1);

// Crea una sezione piè di pagina del documento
Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();

// Imposta il piè di pagina del file PDF
page.Footer = footer;

// Crea un oggetto Testo
Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P ) ");

// Aggiungi testo alla sezione Intestazione del file Pdf
footer.Paragraphs.Add(txt);

// Salva il file Pdf
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");

```

## Conclusione

Congratulazioni! Hai imparato come aggiungere un'immagine e un numero di pagina nella sezione dell'intestazione e del piè di pagina di un documento PDF utilizzando Aspose.PDF per .NET. Ora puoi utilizzare questo metodo per personalizzare intestazione e piè di pagina nei tuoi documenti PDF.

### FAQ

#### D: Qual è lo scopo dell'aggiunta di un'immagine e di un numero di pagina nella sezione dell'intestazione e del piè di pagina di un documento PDF?

R: L'aggiunta di un'immagine e di un numero di pagina nella sezione dell'intestazione e del piè di pagina di un documento PDF può migliorarne l'attrattiva visiva, il marchio e gli elementi di navigazione. Un'immagine può rappresentare un logo, una filigrana o qualsiasi elemento grafico, mentre un numero di pagina aiuta gli utenti a tenere traccia dei propri progressi e a individuare pagine specifiche.

#### D: In che modo il codice sorgente C# fornito aiuta ad aggiungere un'immagine e un numero di pagina all'intestazione e al piè di pagina di un documento PDF?

R: Il codice fornito mostra come creare un documento PDF, aggiungere una pagina e quindi personalizzare le sezioni di intestazione e piè di pagina. Mostra come aggiungere un'immagine all'intestazione e un frammento di testo con la numerazione delle pagine al piè di pagina.

#### D: Posso utilizzare qualsiasi formato di immagine per l'intestazione e come faccio a specificarne il percorso?

 R: Sì, puoi utilizzare vari formati di immagine (come JPEG, PNG, GIF, ecc.) per l'immagine di intestazione. Il percorso dell'immagine viene specificato utilizzando il file`File` proprietà del`Aspose.Pdf.Image` oggetto.

#### D: Come si personalizza l'aspetto e il posizionamento dell'immagine nella sezione dell'intestazione?

 R: È possibile personalizzare l'aspetto e il posizionamento dell'immagine regolando le proprietà del file`Aspose.Pdf.Image` oggetto prima di aggiungerlo alla sezione dell'intestazione. Ad esempio, puoi impostare le dimensioni dell'immagine, l'allineamento, la rotazione, l'opacità, ecc.

####  D: Qual è lo scopo del`TextFragment` object used for the footer?

 R: Il`TextFragment`L'oggetto viene utilizzato per creare e formattare il testo che verrà visualizzato nella sezione del piè di pagina. Nel codice fornito, viene utilizzato per visualizzare il numero di pagina e il conteggio totale delle pagine.

#### D: Posso modificare il testo del piè di pagina per includere informazioni o formattazione aggiuntive?

 R: Sì, puoi modificare il testo del piè di pagina modificando il contenuto del file`TextFragment` oggetto. Puoi aggiungere testo aggiuntivo, modificare caratteri, colori e formattazione in base alle tue esigenze.

#### D: Posso applicare contenuti di intestazione e piè di pagina diversi a pagine diverse del documento PDF?

 R: Sì, puoi applicare diversi contenuti di intestazione e piè di pagina a pagine diverse creando file separati`HeaderFooter` oggetti e assegnandoli a pagine specifiche utilizzando il file`Header` E`Footer` proprietà del`Aspose.Pdf.Page` oggetto.

#### D: Come posso personalizzare ulteriormente l'intestazione e il piè di pagina, ad esempio modificando gli stili dei caratteri o aggiungendo elementi aggiuntivi?

R: Puoi personalizzare l'intestazione e il piè di pagina utilizzando varie classi e proprietà fornite da Aspose.PDF per .NET. Ad esempio, puoi utilizzare diverse opzioni di formattazione del testo, aggiungere più paragrafi, immagini o persino tabelle alle sezioni di intestazione e piè di pagina.

#### D: Posso rimuovere o cancellare le sezioni di intestazione e piè di pagina, se necessario?

 R: Sì, puoi rimuovere o cancellare le sezioni di intestazione e piè di pagina impostando il file`Header` E`Footer` proprietà del`Aspose.Pdf.Page` opporsi a`null`.

#### D: Come posso garantire che l'immagine aggiunta e il numero di pagina rimangano coerenti su diversi dispositivi e visualizzatori?

R: Aspose.PDF per .NET fornisce funzionalità per creare documenti PDF standardizzati e coerenti, assicurando che l'immagine aggiunta e il numero di pagina vengano visualizzati in modo coerente su diversi dispositivi e visualizzatori PDF.