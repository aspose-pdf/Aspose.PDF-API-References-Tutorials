---
title: Immagine nell'intestazione
linktitle: Immagine nell'intestazione
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come aggiungere un'immagine nella sezione dell'intestazione di un documento PDF con Aspose.PDF per .NET.
type: docs
weight: 140
url: /it/net/programming-with-stamps-and-watermarks/image-in-header/
---
In questo tutorial, ti guideremo passo dopo passo su come aggiungere un'immagine nella sezione dell'intestazione di un documento PDF utilizzando Aspose.PDF per .NET. Utilizzeremo il codice sorgente C# fornito per aprire un documento PDF esistente, creare un buffer immagine, impostarne le proprietà e aggiungerlo a tutte le pagine del documento PDF.

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
Document pdfDocument = new Document(dataDir + "ImageinHeader.pdf");
```

Assicurati di sostituire "YOUR DOCUMENTI DIRECTORY" con il percorso effettivo della directory in cui si trova il tuo documento PDF.

## Passaggio 3: creazione e aggiunta dell'immagine nella sezione dell'intestazione

Ora che il documento PDF è caricato, possiamo creare un buffer immagine e aggiungerlo a tutte le pagine del documento come sezione di intestazione. Ecco come:

```csharp
// Crea il frame buffer
ImageStamp imageStamp = new ImageStamp(dataDir + "aspose-logo.jpg");

// Imposta le proprietà del buffer dell'immagine
imageStamp.TopMargin = 10;
imageStamp.HorizontalAlignment = HorizontalAlignment.Center;
imageStamp.VerticalAlignment = VerticalAlignment.Top;

//Aggiungi il buffer dell'immagine a tutte le pagine
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(imageStamp);
}
```

Il codice precedente crea un buffer immagine dal file "aspose-logo.jpg" e ne imposta le proprietà, come il margine superiore, l'allineamento orizzontale e verticale. Quindi il timbro dell'immagine viene aggiunto a tutte le pagine del documento PDF come sezione di intestazione.

## Passaggio 4: salvare il documento PDF modificato

Una volta aggiunta l'immagine nella sezione dell'intestazione, possiamo salvare il documento PDF modificato. Ecco come:

```csharp
// Salva il documento PDF modificato
pdfDocument.Save(dataDir + "ImageinHeader_out.pdf");
```

Il codice precedente salva il documento PDF modificato nella directory specificata.

### Esempio di codice sorgente per Imagein Header utilizzando Aspose.PDF per .NET 

```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Apri documento
Document pdfDocument = new Document(dataDir+ "ImageinHeader.pdf");

// Crea intestazione
ImageStamp imageStamp = new ImageStamp(dataDir+ "aspose-logo.jpg");

// Imposta le proprietà del timbro
imageStamp.TopMargin = 10;
imageStamp.HorizontalAlignment = HorizontalAlignment.Center;
imageStamp.VerticalAlignment = VerticalAlignment.Top;

// Aggiungi intestazione su tutte le pagine
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(imageStamp);
}
dataDir = dataDir + "ImageinHeader_out.pdf";

// Salva documento aggiornato
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage in header added successfully.\nFile saved at " + dataDir);                        

```

## Conclusione

Congratulazioni! Hai imparato come aggiungere un'immagine nella sezione dell'intestazione di un documento PDF utilizzando Aspose.PDF per .NET. Ora puoi personalizzare le intestazioni dei tuoi documenti PDF aggiungendo immagini.
