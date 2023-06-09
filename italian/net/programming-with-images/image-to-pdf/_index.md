---
title: Immagine in PDF
linktitle: Immagine in PDF
second_title: Aspose.PDF per riferimento API .NET
description: Converti facilmente l'immagine in PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 180
url: /it/net/programming-with-images/image-to-pdf/
---

Aspose.PDF per .NET è una potente libreria che consente agli sviluppatori di creare, manipolare e convertire documenti PDF utilizzando C# o qualsiasi linguaggio .NET. In questo tutorial, ti guideremo attraverso il processo di conversione di un'immagine in PDF utilizzando Aspose.PDF per .NET.

## Passaggio 1: configurazione dell'ambiente

Prima di iniziare, assicurati di avere Aspose.PDF per .NET installato sul tuo sistema. Puoi scaricarlo e installarlo dal sito Web ufficiale di Aspose. Una volta installato, crea un nuovo progetto C# nel tuo ambiente di sviluppo preferito.

## Passaggio 2: importazione delle librerie richieste

Per utilizzare Aspose.PDF per .NET nel tuo progetto, devi importare le librerie necessarie. Aggiungi le seguenti istruzioni using all'inizio del tuo file C#:

```csharp
using Aspose.Pdf;
using System.IO;
using System.Drawing;
```

## Passaggio 3: inizializzazione dell'oggetto documento

 Nel codice C#, il primo passaggio consiste nell'inizializzare il file`Document` oggetto. Questo oggetto rappresenta il documento PDF che creeremo. Aggiungi il seguente codice al tuo progetto:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

 Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo in cui si desidera salvare il file PDF.

## Passaggio 4: aggiunta di una pagina al documento

 Successivamente, dobbiamo aggiungere una pagina al documento. Una pagina è rappresentata da`Page` classe. Utilizzare il seguente codice per aggiungere una pagina al documento:

```csharp
Page page = doc.Pages.Add();
```

 Questo codice crea una nuova pagina e la aggiunge al file`Pages` raccolta del documento.

## Passaggio 5: caricamento del file immagine

 Per convertire un'immagine in PDF, dobbiamo prima caricare il file immagine di origine. In questo esempio, assumiamo che il file immagine sia denominato`aspose-logo.jpg` e si trova nella stessa directory del file C#. Utilizzare il seguente codice per caricare il file immagine:

```csharp
FileStream fs = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open, FileAccess.Read);
byte[] tmpBytes = new byte[fs.Length];
fs.Read(tmpBytes, 0, int.Parse(fs.Length.ToString()));
MemoryStream mystream = new MemoryStream(tmpBytes);
```

 Assicurati di sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo del file immagine.

## Passaggio 6: impostazione dei margini e della casella di ritaglio

Prima di aggiungere l'immagine alla pagina PDF, possiamo personalizzare il layout della pagina. Ad esempio, possiamo impostare i margini e la casella di ritaglio per adattarli alle dimensioni dell'immagine. Utilizzare il seguente codice per regolare le impostazioni della pagina:

```csharp
Bitmap b = new Bitmap(mystream);
page.PageInfo.Margin.Bottom = 0;
page.PageInfo.Margin.Top = 0;
page.PageInfo.Margin.Left = 0;
page

.PageInfo.Margin.Right = 0;
page.CropBox = new Aspose.Pdf.Rectangle(0, 0, b.Width, b.Height);
```

Queste impostazioni assicurano che l'immagine si adatti alla pagina senza margini aggiuntivi.

## Passaggio 7: creazione di un oggetto immagine

 Ora, creiamo un file`Aspose.Pdf.Image` oggetto per contenere i dati dell'immagine. Aggiungi il seguente codice al tuo progetto:

```csharp
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
```

Questo oggetto rappresenterà l'immagine che vogliamo aggiungere alla pagina PDF.

## Passaggio 8: aggiunta dell'immagine alla pagina

 Per aggiungere l'immagine alla pagina PDF, dobbiamo assegnare i dati dell'immagine al file`ImageStream` proprietà del`Aspose.Pdf.Image`oggetto. Utilizzare il seguente codice per aggiungere l'immagine:

```csharp
image1.ImageStream = mystream;
page.Paragraphs.Add(image1);
```

 Qui, assegniamo il flusso di immagini al file`ImageStream` proprietà e quindi aggiungere l'oggetto immagine al file`Paragraphs` raccolta della pagina.

## Passaggio 9: salvare il file PDF

Dopo aver aggiunto l'immagine alla pagina PDF, possiamo salvare il file PDF risultante. Utilizzare il seguente codice per salvare il file:

```csharp
dataDir = dataDir + "ImageToPDF_out.pdf";
doc.Save(dataDir);
```

 Sostituire`"YOUR DOCUMENT DIRECTORY"` con la directory di output e il nome del file desiderati.

## Passaggio 10: chiusura del flusso di memoria

Dopo aver salvato il file PDF, è importante chiudere il flusso di memoria per liberare risorse di sistema. Aggiungere il seguente codice per chiudere il flusso di memoria:

```csharp
mystream. Close();
```

## Esecuzione del codice e verifica dell'output

Ora hai completato l'implementazione del codice. Esegui il codice e verifica che l'immagine sia stata convertita correttamente in PDF. Il file di output deve essere salvato nella directory specificata.


### Esempio di codice sorgente per Image to PDF utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crea un'istanza dell'oggetto documento
Document doc = new Document();
// Aggiungi una pagina alla raccolta di pagine del documento
Page page = doc.Pages.Add();
//Carica il file immagine di origine nell'oggetto Stream
FileStream fs = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open, FileAccess.Read);
byte[] tmpBytes = new byte[fs.Length];
fs.Read(tmpBytes, 0, int.Parse(fs.Length.ToString()));
MemoryStream mystream = new MemoryStream(tmpBytes);
// Crea un'istanza dell'oggetto BitMap con il flusso di immagini caricato
Bitmap b = new Bitmap(mystream);
// Imposta i margini in modo che l'immagine si adatti, ecc.
page.PageInfo.Margin.Bottom = 0;
page.PageInfo.Margin.Top = 0;
page.PageInfo.Margin.Left = 0;
page.PageInfo.Margin.Right = 0;
page.CropBox = new Aspose.Pdf.Rectangle(0, 0, b.Width, b.Height);
// Crea un oggetto immagine
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
// Aggiungi l'immagine nella raccolta di paragrafi della sezione
page.Paragraphs.Add(image1);
// Imposta il flusso del file immagine
image1.ImageStream = mystream;
dataDir = dataDir + "ImageToPDF_out.pdf";
// Salva il file PDF risultante
doc.Save(dataDir);
// Chiudi l'oggetto memoryStream
mystream.Close();
Console.WriteLine("\nImage converted to pdf successfully.\nFile saved at " + dataDir); 
```

## Conclusione

In questo tutorial, abbiamo imparato come convertire un'immagine in PDF usando Aspose.PDF per .NET. Abbiamo coperto il processo passo dopo passo, inclusa la configurazione dell'ambiente, l'importazione delle librerie, l'inizializzazione dell'oggetto documento, il caricamento del file immagine, l'impostazione dei margini e della casella di ritaglio, l'aggiunta dell'immagine alla pagina, il salvataggio del file PDF e la chiusura del flusso di memoria. Seguendo questi passaggi, puoi convertire facilmente le immagini in PDF nelle tue applicazioni .NET.