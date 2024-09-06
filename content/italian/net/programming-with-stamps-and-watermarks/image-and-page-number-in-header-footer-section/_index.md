---
title: Immagine e numero di pagina nella sezione intestazione/piè di pagina
linktitle: Immagine e numero di pagina nella sezione intestazione/piè di pagina
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come aggiungere un'immagine e un numero di pagina nell'intestazione e nel piè di pagina di un documento PDF con Aspose.
type: docs
weight: 110
url: /it/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section/
---
In questo tutorial, ti guideremo passo dopo passo su come aggiungere un'immagine e un numero di pagina nella sezione intestazione e piè di pagina di un documento PDF utilizzando Aspose.PDF per .NET. Ti mostreremo come utilizzare il codice sorgente C# fornito per creare una pagina, impostare intestazione e piè di pagina, aggiungere un'immagine all'intestazione e testo con numero di pagina al piè di pagina del documento PDF.

## Fase 1: Impostazione dell'ambiente

Prima di iniziare, assicurati di avere quanto segue:

- Un ambiente di sviluppo .NET installato.
- La libreria Aspose.PDF per .NET è stata scaricata e a cui si fa riferimento nel progetto.

## Passaggio 2: creazione del documento PDF e della pagina

Il primo passo è creare un nuovo oggetto Documento e una pagina nel documento PDF. Ecco come fare:

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Crea un nuovo oggetto Documento
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Crea una pagina nel documento
Aspose.Pdf.Page page = doc.Pages.Add();
```

Il codice sopra crea un nuovo oggetto Documento e una pagina vuota nel documento PDF.

## Passaggio 3: aggiunta dell'intestazione con un'immagine

Ora che la pagina è creata, possiamo aggiungere una sezione di intestazione con un'immagine. Ecco come:

```csharp
// Crea una sezione di intestazione
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Imposta l'intestazione della pagina
page. Header = header;

// Crea un oggetto Immagine
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Imposta il percorso dell'immagine
image1.File = dataDir + "aspose-logo.jpg";

// Aggiungere l'immagine all'intestazione di pagina del documento PDF
header.Paragraphs.Add(image1);
```

Il codice sopra crea una sezione di intestazione, imposta l'intestazione di pagina con questa sezione e aggiunge un'immagine all'intestazione.

## Fase 4: Aggiungere il piè di pagina con il numero di pagina

Ora che l'intestazione è stata aggiunta, possiamo aggiungere una sezione footer con un numero di pagina. Ecco come:

```csharp
// Crea una sezione piè di pagina
Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();

// Definisci il piè di pagina del documento PDF
page. Footer = footer;

// Crea un oggetto TextFragment
Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P)");

// Aggiungere il testo con il numero di pagina al piè di pagina del documento PDF
footer.Paragraphs.Add(txt);
```

Il codice sopra crea una sezione footer, imposta il footer della pagina con questa sezione e aggiunge un TextFragment contenente il testo "Page: ($p of $P )"

  che visualizza il numero di pagina.

## Passaggio 5: salvataggio del documento PDF modificato

Una volta aggiunti intestazione e piè di pagina, possiamo salvare il documento PDF modificato. Ecco come:

```csharp
// Salvare il documento PDF modificato
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");
```

Il codice soprastante salva il documento PDF modificato nella directory specificata.

### Esempio di codice sorgente per Immagine e numero di pagina nella sezione Intestazione/Piè di pagina utilizzando Aspose.PDF per .NET 
```csharp

// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Crea una pagina nell'oggetto documento
Aspose.Pdf.Page page = doc.Pages.Add();

// Crea la sezione intestazione del documento
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Imposta l'intestazione per il file PDF
page.Header = header;

// Crea un oggetto immagine nella pagina
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Imposta il percorso del file immagine
image1.File = dataDir + "aspose-logo.jpg";

// Aggiungi immagine alla pagina dell'intestazione del file PDF
header.Paragraphs.Add(image1);

//Creare una sezione piè di pagina del documento
Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();

// Imposta il piè di pagina del file PDF
page.Footer = footer;

// Crea un oggetto Testo
Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P ) ");

// Aggiungere testo alla sezione Intestazione del file PDF
footer.Paragraphs.Add(txt);

// Salva il file PDF
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");

```

## Conclusione

Congratulazioni! Hai imparato come aggiungere un'immagine e un numero di pagina nella sezione intestazione e piè di pagina di un documento PDF usando Aspose.PDF per .NET. Ora puoi usare questo metodo per personalizzare intestazione e piè di pagina nei tuoi documenti PDF.

### Domande frequenti

#### D: Qual è lo scopo di aggiungere un'immagine e un numero di pagina nella sezione intestazione e piè di pagina di un documento PDF?

R: Aggiungere un'immagine e un numero di pagina nella sezione intestazione e piè di pagina di un documento PDF può migliorarne l'aspetto visivo, il branding e gli elementi di navigazione. Un'immagine può rappresentare un logo, una filigrana o qualsiasi elemento grafico, mentre un numero di pagina aiuta gli utenti a tenere traccia dei loro progressi e a individuare pagine specifiche.

#### D: In che modo il codice sorgente C# fornito aiuta ad aggiungere un'immagine e un numero di pagina all'intestazione e al piè di pagina di un documento PDF?

R: Il codice fornito dimostra come creare un documento PDF, aggiungere una pagina e quindi personalizzare le sezioni di intestazione e piè di pagina. Mostra come aggiungere un'immagine all'intestazione e un frammento di testo con numerazione delle pagine al piè di pagina.

#### D: Posso utilizzare qualsiasi formato immagine per l'intestazione e come faccio a specificarne il percorso?

 R: Sì, puoi usare vari formati di immagine (come JPEG, PNG, GIF, ecc.) per l'immagine di intestazione. Il percorso dell'immagine è specificato usando`File` proprietà del`Aspose.Pdf.Image` oggetto.

#### D: Come posso personalizzare l'aspetto e il posizionamento dell'immagine nella sezione dell'intestazione?

 A: È possibile personalizzare l'aspetto e il posizionamento dell'immagine regolando le proprietà dell'`Aspose.Pdf.Image` oggetto prima di aggiungerlo alla sezione dell'intestazione. Ad esempio, puoi impostare le dimensioni, l'allineamento, la rotazione, l'opacità, ecc. dell'immagine.

####  D: Qual è lo scopo del`TextFragment` object used for the footer?

 A: Il`TextFragment` object viene utilizzato per creare e formattare il testo che verrà visualizzato nella sezione footer. Nel codice fornito, viene utilizzato per visualizzare il numero di pagina e il conteggio totale delle pagine.

#### D: Posso modificare il testo del piè di pagina per includere informazioni o formattazioni aggiuntive?

 A: Sì, puoi modificare il testo del piè di pagina modificando il contenuto del`TextFragment` oggetto. Puoi aggiungere testo aggiuntivo, cambiare font, colori e formattazione in base alle tue esigenze.

#### D: Posso applicare contenuti diversi nell'intestazione e nel piè di pagina alle diverse pagine del documento PDF?

 A: Sì, puoi applicare contenuti diversi di intestazione e piè di pagina a pagine diverse creando pagine separate`HeaderFooter` oggetti e assegnarli a pagine specifiche utilizzando`Header` E`Footer` proprietà del`Aspose.Pdf.Page` oggetto.

#### D: Come posso personalizzare ulteriormente l'intestazione e il piè di pagina, ad esempio cambiando lo stile del carattere o aggiungendo elementi aggiuntivi?

R: Puoi personalizzare l'intestazione e il piè di pagina utilizzando varie classi e proprietà fornite da Aspose.PDF per .NET. Ad esempio, puoi utilizzare diverse opzioni di formattazione del testo, aggiungere più paragrafi, immagini o persino tabelle alle sezioni dell'intestazione e del piè di pagina.

#### D: Posso rimuovere o cancellare le sezioni intestazione e piè di pagina, se necessario?

A: Sì, puoi rimuovere o cancellare le sezioni intestazione e piè di pagina impostando`Header` E`Footer` proprietà del`Aspose.Pdf.Page` opporsi a`null`.

#### D: Come posso garantire che l'immagine aggiunta e il numero di pagina rimangano coerenti su diversi dispositivi e visualizzatori?

R: Aspose.PDF per .NET fornisce funzionalità per creare documenti PDF standardizzati e coerenti, garantendo che l'immagine aggiunta e il numero di pagina vengano visualizzati in modo coerente su diversi dispositivi e visualizzatori PDF.