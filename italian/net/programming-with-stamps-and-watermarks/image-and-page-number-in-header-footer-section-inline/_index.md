---
title: Immagine e numero di pagina nella sezione del piè di pagina dell'intestazione in linea
linktitle: Immagine e numero di pagina nella sezione del piè di pagina dell'intestazione in linea
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come aggiungere l'immagine e il numero di pagina nell'intestazione e nel piè di pagina utilizzando i paragrafi in linea con Aspose.PDF per .NET.
type: docs
weight: 120
url: /it/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section-inline/
---
In questo tutorial, ti guideremo passo dopo passo su come aggiungere l'immagine e il numero di pagina nella sezione dell'intestazione e del piè di pagina del documento PDF utilizzando Aspose.PDF per .NET. Utilizzeremo il codice sorgente C# fornito per creare una pagina, impostare intestazione e piè di pagina, aggiungere immagini e testo utilizzando paragrafi incorporati nell'intestazione del documento PDF.

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
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// Crea una pagina nel documento
Aspose.Pdf.Page page = pdf1.Pages.Add();
```

Il codice precedente crea un nuovo oggetto Document e una pagina vuota nel documento PDF.

## Passaggio 3: aggiunta dell'intestazione con un'immagine e testo incorporato

Ora che la pagina è stata creata, possiamo aggiungere una sezione di intestazione con un'immagine e un testo utilizzando i paragrafi incorporati. Ecco come:

```csharp
// Crea una sezione di intestazione
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Imposta l'intestazione della pagina
page. Header = header;

// Crea un oggetto TextFragment per il primo testo in linea
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a robust component developed by");

// Specifica il colore del testo
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

// Creare un oggetto Immagine per l'immagine
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Imposta il percorso dell'immagine
image1.File = dataDir + "aspose-logo.jpg";

// Definire le dimensioni dell'immagine
image1.FixWidth = 50;
image1.FixHeight = 20;

// Indica che il primo testo in linea è un'immagine
image1.IsInLineParagraph = true;

// Crea un secondo testo in linea
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;

// Aggiungi elementi all'intestazione
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);
```

Il codice sopra crea una sezione di intestazione, imposta l'intestazione della pagina con questa sezione, aggiunge un TextFragment con testo in linea e un oggetto Image in linea.

## Passaggio 4: salvare il documento PDF modificato

Una volta aggiunta l'intestazione con l'immagine e il testo in linea, possiamo salvare il documento PDF modificato. Ecco come:

```csharp
// Salva il documento PDF modificato
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");
```

Il codice precedente salva il documento PDF modificato nella directory specificata.

### Esempio di codice sorgente per immagine e numero di pagina nella sezione Intestazione piè di pagina Inline utilizzando Aspose.PDF per .NET 
```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crea un'istanza di un oggetto Document chiamando il suo costruttore vuoto
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// Crea una pagina nell'oggetto Pdf
Aspose.Pdf.Page page = pdf1.Pages.Add();

// Crea Sezione Intestazione del documento
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Imposta l'intestazione per il file PDF
page.Header = header;

// Crea un oggetto Testo
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a Robust component by");

// Specifica il colore
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

// Creare un oggetto immagine nella sezione
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

//Imposta il percorso del file immagine
image1.File = dataDir + "aspose-logo.jpg";

// Impostare la larghezza dell'immagine Informazioni
image1.FixWidth = 50;
image1.FixHeight = 20;

// Indica che InlineParagraph di seg1 è un'immagine.
image1.IsInLineParagraph = true;
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);

// Salva il Pdf
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");

```

## Conclusione

Congratulazioni! Hai imparato come aggiungere un'immagine e un numero di pagina nella sezione dell'intestazione e del piè di pagina di un documento PDF utilizzando i paragrafi in linea con Aspose.PDF per .NET. Ora puoi personalizzare in modo flessibile l'intestazione e il piè di pagina dei tuoi documenti PDF.

### FAQ

#### D: Qual è il vantaggio di utilizzare paragrafi in linea per aggiungere un'immagine e un testo all'intestazione di un documento PDF?

R: L'utilizzo di paragrafi in linea consente di integrare perfettamente immagini e testo all'interno dello stesso paragrafo, fornendo un controllo preciso sulla loro posizione e formattazione. Questo metodo è particolarmente utile per creare intestazioni personalizzate con elementi visivi.

#### D: In che modo il codice sorgente C# fornito ottiene i paragrafi incorporati per l'intestazione in un documento PDF?

R: Il codice fornito mostra come creare un documento PDF, aggiungere una pagina e personalizzare l'intestazione utilizzando paragrafi incorporati. Aggiunge un TextFragment con testo in linea, un'immagine in linea e un altro TextFragment in linea.

#### D: Come faccio a specificare il colore del testo in linea nell'intestazione?

 R: Il colore del testo in linea viene specificato utilizzando il`ForegroundColor` proprietà del`TextState` del`TextFragment` oggetto.

#### D: Posso regolare le dimensioni dell'immagine in linea nell'intestazione?

 R: Sì, puoi regolare le dimensioni dell'immagine in linea utilizzando il`FixWidth` E`FixHeight` proprietà del`Image` oggetto. Ciò consente di controllare la larghezza e l'altezza dell'immagine all'interno dell'intestazione.

#### D: Posso includere ulteriori elementi incorporati, come collegamenti ipertestuali o stili di carattere diversi, nell'intestazione?

 R: Sì, puoi includere ulteriori elementi incorporati nell'intestazione creandone altri`TextFragment` O`Image` oggetti con le proprietà desiderate. Ciò consente di personalizzare ulteriormente l'intestazione, inclusi collegamenti ipertestuali, diversi stili di carattere o altri elementi visivi.

#### D: Come posso assicurarmi che l'immagine e il testo in linea rimangano correttamente allineati e formattati su diversi dispositivi e visualizzatori?

R: Aspose.PDF per .NET garantisce che le immagini e il testo in linea siano correttamente allineati e formattati, risultando in un aspetto coerente su diversi dispositivi e visualizzatori di PDF.

#### D: Posso applicare paragrafi incorporati anche alla sezione del piè di pagina?

 A: Sì, puoi applicare la stessa tecnica di utilizzo dei paragrafi in linea alla sezione del piè di pagina creando un file`Footer` oggetto e l'aggiunta di elementi in linea come testo e immagini ad esso.

#### D: È possibile combinare paragrafi incorporati con altri metodi di personalizzazione dell'intestazione o del piè di pagina?

R: Sì, puoi combinare paragrafi in linea con altri metodi di personalizzazione di intestazioni o piè di pagina forniti da Aspose.PDF per .NET per creare progetti di intestazioni o piè di pagina più complessi e personalizzati.

#### D: Posso rimuovere o cancellare gli elementi incorporati dall'intestazione, se necessario?

 R: Sì, puoi rimuovere o cancellare gli elementi inline modificando il contenuto del file`HeaderFooter` oggetto e rimuovendo i rispettivi paragrafi incorporati.

#### D: Come posso applicare paragrafi incorporati a pagine specifiche del documento PDF?

 R: Per applicare paragrafi in linea a pagine specifiche, puoi creare paragrafi separati`HeaderFooter` oggetti per ogni pagina e assegnarli utilizzando il`Header` proprietà del rispettivo`Aspose.Pdf.Page` oggetti.