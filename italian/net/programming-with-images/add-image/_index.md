---
title: Aggiungi immagine
linktitle: Aggiungi immagine
second_title: Aspose.PDF per riferimento API .NET
description: Aggiungi facilmente un'immagine a un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 10
url: /it/net/programming-with-images/add-image/
---

Questa guida ti guiderà passo dopo passo su come aggiungere un'immagine a un documento PDF utilizzando Aspose.PDF per .NET. Assicurati di aver già configurato il tuo ambiente e procedi nel seguente modo:

## Passaggio 1: definire la directory dei documenti

 Prima di iniziare, assicurati di impostare la directory corretta per i documenti. Sostituire`"YOUR DOCUMENT DIRECTORY"` nel codice con il percorso della directory in cui si trova il documento PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: apri il documento

 In questo passaggio, apriremo il documento PDF utilizzando il file`Document` classe di Aspose.PDF. Usa il`Document` costruttore e passare il percorso al documento PDF.

```csharp
Document pdfDocument = new Document(dataDir + "AddImage.pdf");
```

## Passaggio 3: imposta le coordinate dell'immagine

 Imposta le coordinate dell'immagine che desideri aggiungere. Le variabili`lowerLeftX`, `lowerLeftY`, `upperRightX` E`upperRightY` rappresentano rispettivamente le coordinate dell'angolo inferiore sinistro e dell'angolo superiore destro dell'immagine.

```csharp
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;
```

## Passaggio 4: ottieni la pagina in cui deve essere aggiunta l'immagine

Per aggiungere l'immagine a una pagina specifica del documento PDF, dobbiamo prima recuperare quella pagina. In questo esempio, aggiungiamo l'immagine alla seconda pagina (indice 1) del documento.

```csharp
Page page = pdfDocument.Pages[1];
```

## Passaggio 5: carica l'immagine da un flusso

Ora caricheremo l'immagine che vogliamo aggiungere al documento PDF. Questo esempio presuppone che tu abbia un file immagine denominato`aspose-logo.jpg` nella stessa directory del documento. Sostituire il nome del file se necessario.

```csharp
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
```

## Passaggio 6: aggiungi l'immagine alle risorse della pagina

Per utilizzare l'immagine nel documento PDF, dobbiamo aggiungerla alla raccolta di immagini delle risorse della pagina.

```csharp
page.Resources.Images.Add(imageStream);
```

## Passaggio 7: salva lo stato grafico corrente

 Prima di disegnare l'immagine, dobbiamo salvare lo stato grafico corrente utilizzando il file`GSave` operatore. Ciò garantisce che le modifiche allo stato della grafica possano essere ripristinate in un secondo momento.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.GSave());
```

## Passaggio 8: creare oggetti Rectangle e Matrix

 Ora creeremo un file`Rectangle` oggetto e a`Matrix` oggetto. Il rettangolo rappresenta la posizione e la dimensione dell'immagine, mentre la matrice definisce come deve essere posizionata l'immagine.

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lower

LeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
```

## Passaggio 9: matrice concatenata per il posizionamento dell'immagine

 Per specificare come l'immagine deve essere posizionata nel rettangolo, usiamo il`ConcatenateMatrix`operatore. Questo operatore definisce la matrice di trasformazione che associa lo spazio delle coordinate dell'immagine allo spazio delle coordinate della pagina.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
```

## Passaggio 10: Disegna l'immagine

 In questo passaggio disegneremo l'immagine sulla pagina utilizzando il file`Do` operatore. IL`Do` L'operatore prende il nome dell'immagine dalle risorse e lo disegna sulla pagina.

```csharp
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
```

## Passaggio 11: ripristinare lo stato della grafica

 Dopo aver disegnato l'immagine, dobbiamo ripristinare lo stato grafico precedente utilizzando il file`GRestore` operatore.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
```

## Passaggio 12: salvare il documento aggiornato

 Infine, salveremo il documento aggiornato in un nuovo file. Aggiorna il`dataDir` variabile con la directory di output e il nome file desiderati.

```csharp
dataDir = dataDir + "AddImage_out.pdf";
pdfDocument.Save(dataDir);
```

### Esempio di codice sorgente per Aggiungi immagine utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir+ "AddImage.pdf");
// Imposta le coordinate
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;
// Ottieni la pagina in cui è necessario aggiungere l'immagine
Page page = pdfDocument.Pages[1];
// Carica l'immagine nello stream
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
// Aggiungi l'immagine alla raccolta di immagini delle risorse della pagina
page.Resources.Images.Add(imageStream);
// Utilizzo dell'operatore GSave: questo operatore salva lo stato grafico corrente
page.Contents.Add(new Aspose.Pdf.Operators.GSave());
// Crea oggetti Rectangle e Matrix
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
//Utilizzo dell'operatore ConcatenateMatrix (matrice concatenata): definisce come deve essere posizionata l'immagine
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
// Utilizzo dell'operatore Do: questo operatore disegna un'immagine
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
// Utilizzo dell'operatore GRestore: questo operatore ripristina lo stato della grafica
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
dataDir = dataDir + "AddImage_out.pdf";
// Salva documento aggiornato
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage added successfully.\nFile saved at " + dataDir); 
```

## Conclusione

In questo tutorial, abbiamo imparato come aggiungere un'immagine a un documento PDF utilizzando Aspose.PDF per .NET. Abbiamo coperto ogni passaggio in dettaglio, dall'apertura del documento al salvataggio della versione aggiornata. Seguendo questa guida, ora dovresti essere in grado di incorporare le immagini nei tuoi file PDF in modo programmatico utilizzando C# e Aspose.PDF.