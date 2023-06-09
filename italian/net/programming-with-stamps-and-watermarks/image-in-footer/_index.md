---
title: Immagine nel piè di pagina
linktitle: Immagine nel piè di pagina
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come aggiungere un'immagine nella sezione piè di pagina di un documento PDF con Aspose.PDF per .NET.
type: docs
weight: 130
url: /it/net/programming-with-stamps-and-watermarks/image-in-footer/
---
In questo tutorial, ti guideremo passo dopo passo su come aggiungere un'immagine nella sezione del piè di pagina di un documento PDF utilizzando Aspose.PDF per .NET. Utilizzeremo il codice sorgente C# fornito per aprire un documento PDF esistente, creare un buffer immagine, impostarne le proprietà e aggiungerlo a tutte le pagine del documento PDF.

## Passaggio 1: configurazione dell'ambiente

Prima di iniziare, assicurati di avere quanto segue:

- Un ambiente di sviluppo .NET installato.
- La libreria Aspose.PDF per .NET scaricata e referenziata nel tuo progetto.

## Passaggio 2: caricamento del documento PDF esistente

Il primo passaggio consiste nel caricare il documento PDF esistente nel progetto. Ecco come:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Apri il documento PDF esistente
Document pdfDocument = new Document(dataDir + "ImageInFooter.pdf");
```

Assicurati di sostituire "YOUR DOCUMENTI DIRECTORY" con il percorso effettivo della directory in cui si trova il tuo documento PDF.

## Passaggio 3: creazione e aggiunta dell'immagine nella sezione del piè di pagina

Ora che il documento PDF è caricato, possiamo creare un timbro immagine e aggiungerlo a tutte le pagine del documento. Ecco come:

```csharp
// Crea il frame buffer
ImageStamp imageStamp = new ImageStamp(dataDir + "aspose-logo.jpg");

// Imposta le proprietà del buffer dell'immagine
imageStamp.BottomMargin = 10;
imageStamp.HorizontalAlignment = HorizontalAlignment.Center;
imageStamp.VerticalAlignment = VerticalAlignment.Bottom;

//Aggiungi il buffer dell'immagine a tutte le pagine
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(imageStamp);
}
```

Il codice sopra crea un buffer immagine dal file "aspose-logo.jpg" e imposta le sue proprietà, come il margine inferiore, l'allineamento orizzontale e verticale. Quindi il buffer dell'immagine viene aggiunto a tutte le pagine del documento PDF.

## Passaggio 4: salvare il documento PDF modificato

Una volta aggiunta l'immagine alla sezione del piè di pagina, possiamo salvare il documento PDF modificato. Ecco come:

```csharp
// Salva il documento PDF modificato
pdfDocument.Save(dataDir + "ImageInFooter_out.pdf");
```

Il codice precedente salva il documento PDF modificato nella directory specificata.

### Esempio di codice sorgente per Image In Footer utilizzando Aspose.PDF per .NET 
```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Apri documento
Document pdfDocument = new Document(dataDir+ "ImageInFooter.pdf");

// Crea piè di pagina
ImageStamp imageStamp = new ImageStamp(dataDir+ "aspose-logo.jpg");

// Imposta le proprietà del timbro
imageStamp.BottomMargin = 10;
imageStamp.HorizontalAlignment = HorizontalAlignment.Center;
imageStamp.VerticalAlignment = VerticalAlignment.Bottom;

// Aggiungi piè di pagina su tutte le pagine
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(imageStamp);
}
dataDir = dataDir + "ImageInFooter_out.pdf";

// Salva il file PDF aggiornato
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage in footer added successfully.\nFile saved at " + dataDir);
```

## Conclusione

Congratulazioni! Hai imparato come aggiungere un'immagine nella sezione piè di pagina di un documento PDF utilizzando Aspose.PDF per .NET. Ora puoi personalizzare i piè di pagina dei tuoi documenti PDF aggiungendo immagini.
