---
title: Memorizza l'immagine nella raccolta XImage
linktitle: Memorizza l'immagine nella raccolta XImage
second_title: Aspose.PDF per riferimento API .NET
description: Guida passo passo per archiviare un'immagine nella raccolta XImage utilizzando Aspose.PDF per .NET.
type: docs
weight: 290
url: /it/net/programming-with-images/store-image-in-ximage-collection/
---

In questo tutorial, ti illustreremo come archiviare un'immagine nella raccolta XImage utilizzando Aspose.PDF per .NET. Segui questi passaggi per eseguire facilmente questa operazione.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

- Visual Studio o qualsiasi altro ambiente di sviluppo installato e configurato.
- Conoscenza di base del linguaggio di programmazione C#.
- Libreria Aspose.PDF per .NET installata. Puoi scaricarlo dal sito ufficiale di Aspose.

## Passaggio 1: inizializzazione del documento PDF

Per iniziare, utilizza il seguente codice per inizializzare un nuovo documento PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Inizializza il documento
Aspose.Pdf.Document document = new Document();
document.Pages.Add();
Page page = document.Pages[1];
```

## Passaggio 2: aggiunta dell'immagine alla raccolta XImage

Successivamente, aggiungeremo l'immagine alla raccolta XImage del documento PDF. Usa il seguente codice:

```csharp
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
page.Resources.Images.Add(imageStream, ImageFilterType.Flate);
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
```

Assicurati di fornire il percorso corretto al file di origine dell'immagine.

## Passaggio 3: Posizionamento dell'immagine sulla pagina

Ora posizioniamo l'immagine sulla pagina del documento PDF. Usa il seguente codice:

```csharp
page. Contents. Add(new GSave());

// Imposta le coordinate
int lowerLeftX = 0;
int lowerLeftY = 0;
int upperRightX = 600;
int upperRightY = 600;
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] {rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY});

//Utilizzando l'operatore ConcatenateMatrix: definisci come deve essere posizionata l'immagine
page.Contents.Add(new ConcatenateMatrix(matrix));
page.Contents.Add(new Do(ximage.Name));
page. Contents. Add(new GRestore());
```

Questo posizionerà l'immagine alle coordinate specificate sulla pagina.

## Passaggio 4: salvare il documento PDF

Infine, salveremo il documento PDF aggiornato. Usa il seguente codice:

```csharp
document.Save(dataDir + "FlateDecodeCompression.pdf");
```

Assicurati di fornire il percorso e il nome file desiderati per il documento PDF finale.

### Esempio di codice sorgente per Store Image In XImage Collection utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Inizializza documento
Aspose.Pdf.Document document = new Document();
document.Pages.Add();
Page page = document.Pages[1];
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
page.Resources.Images.Add(imageStream, ImageFilterType.Flate);
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
page.Contents.Add(new GSave());
// Imposta le coordinate
int lowerLeftX = 0;
int lowerLeftY = 0;
int upperRightX = 600;
int upperRightY = 600;
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] {rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY});
//Utilizzo dell'operatore ConcatenateMatrix (matrice concatenata): definisce come deve essere posizionata l'immagine
page.Contents.Add(new ConcatenateMatrix(matrix));
page.Contents.Add(new Do(ximage.Name));
page.Contents.Add(new GRestore());
document.Save(dataDir + "FlateDecodeCompression.pdf");
```

## Conclusione

Congratulazioni! Hai archiviato correttamente un'immagine nella raccolta XImage utilizzando Aspose.PDF per .NET. Ora puoi applicare questo metodo ai tuoi progetti per manipolare e personalizzare le immagini nei file PDF.