---
title: Memorizza l'immagine nella raccolta XImage
linktitle: Memorizza l'immagine nella raccolta XImage
second_title: Aspose.PDF per riferimento all'API .NET
description: Guida passo passo per archiviare un'immagine nella raccolta XImage utilizzando Aspose.PDF per .NET.
type: docs
weight: 290
url: /it/net/programming-with-images/store-image-in-ximage-collection/
---
In questo tutorial ti spiegheremo come archiviare un'immagine nella raccolta XImage utilizzando Aspose.PDF per .NET. Seguire questi passaggi per eseguire facilmente questa operazione.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

- Visual Studio o qualsiasi altro ambiente di sviluppo installato e configurato.
- Conoscenza base del linguaggio di programmazione C#.
- Libreria Aspose.PDF per .NET installata. Puoi scaricarlo dal sito ufficiale di Aspose.

## Passaggio 1: inizializzazione del documento PDF

Per iniziare, utilizza il codice seguente per inizializzare un nuovo documento PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
//Inizializzare il documento
Aspose.Pdf.Document document = new Document();
document.Pages.Add();
Page page = document.Pages[1];
```

## Passaggio 2: aggiunta dell'immagine alla raccolta XImage

Successivamente, aggiungeremo l'immagine alla raccolta XImage del documento PDF. Utilizza il seguente codice:

```csharp
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
page.Resources.Images.Add(imageStream, ImageFilterType.Flate);
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
```

Assicurati di fornire il percorso corretto del file di origine dell'immagine.

## Passaggio 3: posizionamento dell'immagine sulla pagina

Ora posizioniamo l'immagine sulla pagina del documento PDF. Utilizza il seguente codice:

```csharp
page. Contents. Add(new GSave());

// Imposta le coordinate
int lowerLeftX = 0;
int lowerLeftY = 0;
int upperRightX = 600;
int upperRightY = 600;
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] {rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY});

// Utilizzando l'operatore ConcatenateMatrix: definire come deve essere posizionata l'immagine
page.Contents.Add(new ConcatenateMatrix(matrix));
page.Contents.Add(new Do(ximage.Name));
page. Contents. Add(new GRestore());
```

Ciò posizionerà l'immagine alle coordinate specificate sulla pagina.

## Passaggio 4: salvataggio del documento PDF

Infine, salveremo il documento PDF aggiornato. Utilizza il seguente codice:

```csharp
document.Save(dataDir + "FlateDecodeCompression.pdf");
```

Assicurati di fornire il percorso e il nome file desiderati per il documento PDF finale.

### Codice sorgente di esempio per Store Image In XImage Collection utilizzando Aspose.PDF per .NET 
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
// Utilizzo dell'operatore ConcatenateMatrix (matrice concatenata): definisce come deve essere posizionata l'immagine
page.Contents.Add(new ConcatenateMatrix(matrix));
page.Contents.Add(new Do(ximage.Name));
page.Contents.Add(new GRestore());
document.Save(dataDir + "FlateDecodeCompression.pdf");
```

## Conclusione

Congratulazioni! Hai archiviato con successo un'immagine nella raccolta XImage utilizzando Aspose.PDF per .NET. Ora puoi applicare questo metodo ai tuoi progetti per manipolare e personalizzare le immagini nei file PDF.

### Domande frequenti

#### D: Qual è lo scopo di archiviare un'immagine nella raccolta XImage utilizzando Aspose.PDF per .NET?

R: La memorizzazione di un'immagine nella raccolta XImage consente di gestire e utilizzare in modo efficiente le immagini all'interno di un documento PDF. Questo approccio ti consente di manipolare, personalizzare e personalizzare le immagini prima di posizionarle su pagine specifiche.

#### D: In che modo l'archiviazione di un'immagine nella raccolta XImage differisce dall'inserimento diretto di un'immagine in una pagina PDF?

R: Archiviare un'immagine nella raccolta XImage fornisce un modo più organizzato e riutilizzabile per gestire le immagini. Invece di posizionare direttamente un'immagine su una pagina, la memorizzi nella raccolta e puoi quindi fare riferimento ad essa per nome quando necessario, consentendo una gestione e una modifica più semplici.

#### D: Posso aggiungere più immagini alla raccolta XImage all'interno di un singolo documento PDF?

R: Sì, puoi aggiungere più immagini alla raccolta XImage all'interno dello stesso documento PDF. A ogni immagine viene assegnato un nome univoco nella raccolta, che può essere utilizzato per fare riferimento e posizionare le immagini su pagine diverse.

#### D: Come posso specificare la posizione e la dimensione dell'immagine quando la inserisco in una pagina PDF della raccolta XImage?

R: Per specificare la posizione e la dimensione dell'immagine, è necessario definire un rettangolo e una trasformazione di matrice. Il rettangolo definisce i confini dell'immagine e la trasformazione della matrice specifica come posizionare l'immagine all'interno di quel rettangolo.

####  D: Qual è lo scopo di`GSave()` and `GRestore()` operators in the code for placing the image?

 R: Il`GSave()` E`GRestore()` gli operatori vengono utilizzati per salvare e ripristinare lo stato grafico della pagina PDF. Ciò garantisce che le operazioni eseguite sulla pagina, come il posizionamento dell'immagine, non influenzino lo stato della pagina dopo il posizionamento dell'immagine.

#### D: Posso applicare ulteriori modifiche o trasformazioni alle immagini archiviate nella raccolta XImage?

R: Sì, puoi applicare varie modifiche e trasformazioni alle immagini archiviate nella raccolta XImage. È possibile ruotare, ridimensionare, ritagliare ed eseguire altre trasformazioni utilizzando le operazioni e le tecniche appropriate fornite da Aspose.PDF per .NET.

#### D: Come posso integrare questo metodo nei miei progetti per archiviare e inserire immagini nella raccolta XImage di un documento PDF?

R: Per integrare questo metodo, segui i passaggi descritti e modifica il codice per soddisfare i requisiti del tuo progetto. Puoi utilizzare la raccolta XImage per archiviare e gestire le immagini, quindi posizionarle su pagine specifiche utilizzando le coordinate e le trasformazioni specificate.

#### D: Ci sono considerazioni o limitazioni quando si lavora con la raccolta XImage in Aspose.PDF per .NET?

R: Anche se la raccolta XImage fornisce un modo potente per gestire e manipolare le immagini, è importante considerare fattori come l'utilizzo della memoria e la complessità delle operazioni eseguite sulle immagini. Si raccomanda un'attenta gestione della raccolta e un uso efficiente delle risorse.

#### D: Posso riutilizzare le immagini archiviate nella raccolta XImage su più documenti PDF?

R: La raccolta XImage è specifica per ogni documento PDF e non è progettata per il riutilizzo tra documenti. Se devi riutilizzare le immagini su più documenti, dovrai archiviarle e gestirle separatamente per ciascun documento.