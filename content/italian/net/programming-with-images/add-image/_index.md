---
title: Aggiungi immagine nel file PDF
linktitle: Aggiungi immagine nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Aggiungi facilmente un'immagine in un file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 10
url: /it/net/programming-with-images/add-image/
---
Questa guida ti guiderà passo dopo passo su come aggiungere un'immagine in un file PDF usando Aspose.PDF per .NET. Assicurati di aver già impostato il tuo ambiente e segui i passaggi sottostanti:

## Passaggio 1: definire la directory dei documenti

Prima di iniziare, assicurati di impostare la directory corretta per i documenti. Sostituisci`"YOUR DOCUMENT DIRECTORY"` nel codice con il percorso alla directory in cui si trova il documento PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: aprire il documento

 In questo passaggio, apriremo il documento PDF utilizzando`Document` classe di Aspose.PDF. Utilizzare il`Document` costruttore e passare il percorso al documento PDF.

```csharp
Document pdfDocument = new Document(dataDir + "AddImage.pdf");
```

## Passaggio 3: imposta le coordinate dell'immagine

 Imposta le coordinate dell'immagine che vuoi aggiungere. Le variabili`lowerLeftX`, `lowerLeftY`, `upperRightX` E`upperRightY` rappresentano rispettivamente le coordinate dell'angolo inferiore sinistro e dell'angolo superiore destro dell'immagine.

```csharp
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;
```

## Passaggio 4: Ottieni la pagina in cui aggiungere l'immagine

Per aggiungere l'immagine a una pagina specifica del documento PDF, dobbiamo prima recuperare quella pagina. In questo esempio, aggiungiamo l'immagine alla seconda pagina (indice 1) del documento.

```csharp
Page page = pdfDocument.Pages[1];
```

## Passaggio 5: caricare l'immagine da un flusso

 Ora caricheremo l'immagine che vogliamo aggiungere al documento PDF. Questo esempio presuppone che tu abbia un file immagine denominato`aspose-logo.jpg` nella stessa directory del tuo documento. Sostituisci il nome del file se necessario.

```csharp
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
```

## Passaggio 6: aggiungere l'immagine alle risorse della pagina

Per utilizzare l'immagine nel documento PDF, dobbiamo aggiungerla alla raccolta di immagini delle risorse della pagina.

```csharp
page.Resources.Images.Add(imageStream);
```

## Passaggio 7: Salvare lo stato grafico corrente

 Prima di disegnare l'immagine, dobbiamo salvare lo stato grafico corrente utilizzando`GSave` operatore. Ciò garantisce che le modifiche allo stato grafico possano essere ripristinate in seguito.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.GSave());
```

## Passaggio 8: creare oggetti Rettangolo e Matrice

 Ora creeremo un`Rectangle` oggetto e un`Matrix` oggetto. Il rettangolo rappresenta la posizione e la dimensione dell'immagine, mentre la matrice definisce come l'immagine dovrebbe essere posizionata.

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lower

LeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
```

## Passaggio 9: concatenare la matrice per il posizionamento dell'immagine

 Per specificare come l'immagine deve essere posizionata nel rettangolo, utilizziamo il`ConcatenateMatrix` operatore. Questo operatore definisce la matrice di trasformazione che mappa lo spazio delle coordinate dell'immagine nello spazio delle coordinate della pagina.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
```

## Passaggio 10: disegna l'immagine

 In questo passaggio disegneremo l'immagine sulla pagina utilizzando il`Do` operatore. L'`Do`L'operatore prende il nome dell'immagine dalle risorse e lo disegna sulla pagina.

```csharp
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
```

## Passaggio 11: Ripristinare lo stato della grafica

 Dopo aver disegnato l'immagine, dobbiamo ripristinare lo stato grafico precedente utilizzando`GRestore` operatore.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
```

## Passaggio 12: Salvare il documento aggiornato

 Infine, salveremo il documento aggiornato in un nuovo file. Aggiornare il`dataDir` variabile con la directory di output e il nome file desiderati.

```csharp
dataDir = dataDir + "AddImage_out.pdf";
pdfDocument.Save(dataDir);
```

### Esempio di codice sorgente per Aggiungi immagine utilizzando Aspose.PDF per .NET 
```csharp
// Percorso verso la directory dei documenti.
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
// Carica l'immagine nel flusso
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
// Aggiungi immagine alla raccolta Immagini di Risorse di pagina
page.Resources.Images.Add(imageStream);
// Utilizzo dell'operatore GSave: questo operatore salva lo stato grafico corrente
page.Contents.Add(new Aspose.Pdf.Operators.GSave());
// Crea oggetti Rettangolo e Matrice
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
// Utilizzo dell'operatore ConcatenateMatrix (matrice di concatenazione): definisce come deve essere posizionata l'immagine
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
// Utilizzo dell'operatore Do: questo operatore disegna l'immagine
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
// Utilizzo dell'operatore GRestore: questo operatore ripristina lo stato della grafica
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
dataDir = dataDir + "AddImage_out.pdf";
// Salva il documento aggiornato
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage added successfully.\nFile saved at " + dataDir); 
```

## Conclusione

In questo tutorial, abbiamo imparato come aggiungere un'immagine a un documento PDF usando Aspose.PDF per .NET. Abbiamo trattato ogni passaggio in dettaglio, dall'apertura del documento al salvataggio della versione aggiornata. Seguendo questa guida, dovresti ora essere in grado di incorporare le immagini nei tuoi file PDF a livello di programmazione usando C# e Aspose.PDF.

### FAQ per aggiungere un'immagine in un file PDF

#### D: Perché dovrei voler aggiungere un'immagine a un documento PDF?

R: L'aggiunta di immagini a un documento PDF può migliorare il contenuto visivo, fornire ulteriore contesto o includere loghi e grafici nei file PDF.

#### D: Posso aggiungere immagini a pagine specifiche all'interno di un documento PDF?

A: Sì, puoi specificare la pagina in cui vuoi aggiungere l'immagine. Nel codice fornito, l'immagine viene aggiunta alla seconda pagina del documento PDF.

#### D: Come faccio a regolare la posizione e le dimensioni dell'immagine aggiunta?

 A: Puoi modificare il`lowerLeftX`, `lowerLeftY`, `upperRightX` , E`upperRightY` variabili nel codice per impostare le coordinate dell'immagine e controllarne le dimensioni e la posizione sulla pagina.

#### D: Quali tipi di formati di immagine posso aggiungere utilizzando questo metodo?

A: L'esempio di codice fornito presuppone che tu stia caricando un'immagine JPG (`aspose-logo.jpg`). Aspose.PDF per .NET supporta vari formati di immagine, tra cui PNG, BMP, GIF e altri.

#### D: Come posso assicurarmi che l'immagine aggiunta rientri nelle coordinate specificate?

 A: Assicurati di regolare le coordinate e le dimensioni del`Rectangle` oggetto (`rectangle`) per adattare le dimensioni dell'immagine e il posizionamento desiderato sulla pagina.

#### D: Posso aggiungere più immagini a una singola pagina PDF?

R: Sì, puoi aggiungere più immagini a una singola pagina PDF ripetendo il procedimento per ogni immagine e regolando di conseguenza le coordinate e altri parametri.

####  D: Come funziona il`GSave` and `GRestore` operator work in the code?

 A: Il`GSave` L'operatore salva lo stato grafico corrente, consentendo di apportare modifiche senza influire sul contesto grafico generale.`GRestore` l'operatore ripristina lo stato grafico precedente dopo aver apportato modifiche.

#### D: Cosa succede se il file immagine non viene trovato nel percorso specificato?

A: Se il file immagine non viene trovato nel percorso specificato, il codice genererà un'eccezione quando si tenta di caricare il flusso di immagini. Assicurarsi che il file immagine si trovi nella directory corretta.

#### D: Posso personalizzare ulteriormente il posizionamento e l'aspetto delle immagini?

 A: Sì, puoi personalizzare l'aspetto dell'immagine modificando il`Matrix` oggetto e regolando altri operatori all'interno del codice. Fare riferimento alla documentazione Aspose.PDF per una personalizzazione avanzata.

#### D: Come posso verificare se l'immagine è stata aggiunta correttamente al PDF?

R: Dopo aver applicato il codice fornito per aggiungere l'immagine, aprire il file PDF modificato e verificare che l'immagine venga visualizzata nella pagina specificata con la posizione corretta.

#### D: L'aggiunta di immagini influisce sul contenuto originale del documento PDF?

A: L'aggiunta di immagini non influisce sul contenuto originale del documento PDF. Migliora il documento includendo elementi visivi.