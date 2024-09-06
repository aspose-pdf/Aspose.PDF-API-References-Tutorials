---
title: Memorizza l'immagine nella raccolta XImage
linktitle: Memorizza l'immagine nella raccolta XImage
second_title: Riferimento API Aspose.PDF per .NET
description: Guida passo passo per memorizzare un'immagine nella raccolta XImage utilizzando Aspose.PDF per .NET.
type: docs
weight: 290
url: /it/net/programming-with-images/store-image-in-ximage-collection/
---
In questo tutorial, ti guideremo attraverso come archiviare un'immagine nella raccolta XImage usando Aspose.PDF per .NET. Segui questi passaggi per eseguire questa operazione facilmente.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

- Visual Studio o qualsiasi altro ambiente di sviluppo installato e configurato.
- Conoscenza di base del linguaggio di programmazione C#.
- Libreria Aspose.PDF per .NET installata. Puoi scaricarla dal sito ufficiale di Aspose.

## Fase 1: Inizializzazione del documento PDF

Per iniziare, utilizza il seguente codice per inizializzare un nuovo documento PDF:

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

Assicuratevi di fornire il percorso corretto al file sorgente dell'immagine.

## Fase 3: Posizionamento dell'immagine sulla pagina

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

Questo posizionerà l'immagine nelle coordinate specificate sulla pagina.

## Passaggio 4: salvataggio del documento PDF

Infine, salveremo il documento PDF aggiornato. Utilizza il seguente codice:

```csharp
document.Save(dataDir + "FlateDecodeCompression.pdf");
```

Assicuratevi di fornire il percorso e il nome file desiderati per il documento PDF finale.

### Esempio di codice sorgente per Store Image In XImage Collection utilizzando Aspose.PDF per .NET 
```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Inizializza il documento
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
// Utilizzo dell'operatore ConcatenateMatrix (matrice di concatenazione): definisce come deve essere posizionata l'immagine
page.Contents.Add(new ConcatenateMatrix(matrix));
page.Contents.Add(new Do(ximage.Name));
page.Contents.Add(new GRestore());
document.Save(dataDir + "FlateDecodeCompression.pdf");
```

## Conclusione

Congratulazioni! Hai archiviato con successo un'immagine nella raccolta XImage usando Aspose.PDF per .NET. Ora puoi applicare questo metodo ai tuoi progetti per manipolare e personalizzare le immagini nei file PDF.

### Domande frequenti

#### D: Qual è lo scopo di memorizzare un'immagine nella raccolta XImage utilizzando Aspose.PDF per .NET?

R: Memorizzare un'immagine nella raccolta XImage consente di gestire e utilizzare in modo efficiente le immagini all'interno di un documento PDF. Questo approccio consente di manipolare, personalizzare e personalizzare le immagini prima di posizionarle su pagine specifiche.

#### D: In che cosa differisce l'archiviazione di un'immagine nella raccolta XImage dall'inserimento diretto di un'immagine in una pagina PDF?

R: Memorizzare un'immagine nella raccolta XImage fornisce un modo più organizzato e riutilizzabile per gestire le immagini. Invece di posizionare direttamente un'immagine su una pagina, la memorizzi nella raccolta e puoi quindi farvi riferimento per nome quando necessario, consentendo una gestione e una modifica più semplici.

#### D: Posso aggiungere più immagini alla raccolta XImage all'interno di un singolo documento PDF?

R: Sì, puoi aggiungere più immagini alla raccolta XImage all'interno dello stesso documento PDF. A ogni immagine viene assegnato un nome univoco nella raccolta, che può essere utilizzato per fare riferimento e posizionare le immagini su pagine diverse.

#### D: Come faccio a specificare la posizione e le dimensioni dell'immagine quando la inserisco in una pagina PDF dalla raccolta XImage?

R: Per specificare la posizione e la dimensione dell'immagine, è necessario definire un rettangolo e una trasformazione di matrice. Il rettangolo definisce i confini dell'immagine e la trasformazione di matrice specifica come l'immagine deve essere posizionata all'interno di quel rettangolo.

####  D: Qual è lo scopo del`GSave()` and `GRestore()` operators in the code for placing the image?

 A: Il`GSave()` E`GRestore()` Gli operatori vengono utilizzati per salvare e ripristinare lo stato grafico della pagina PDF. Ciò garantisce che le operazioni eseguite sulla pagina, come il posizionamento dell'immagine, non influenzino lo stato della pagina dopo il posizionamento dell'immagine.

#### D: Posso applicare ulteriori modifiche o trasformazioni alle immagini memorizzate nella raccolta XImage?

R: Sì, puoi applicare varie modifiche e trasformazioni alle immagini archiviate nella raccolta XImage. Puoi ruotare, ridimensionare, ritagliare ed eseguire altre trasformazioni utilizzando le operazioni e le tecniche appropriate fornite da Aspose.PDF per .NET.

#### D: Come posso integrare questo metodo nei miei progetti per archiviare e posizionare le immagini nella raccolta XImage di un documento PDF?

R: Per integrare questo metodo, segui i passaggi descritti e modifica il codice per soddisfare i requisiti del tuo progetto. Puoi usare la raccolta XImage per archiviare e gestire le immagini, quindi posizionarle su pagine specifiche usando le coordinate e le trasformazioni specificate.

#### D: Ci sono considerazioni o limitazioni da tenere presente quando si lavora con la raccolta XImage in Aspose.PDF per .NET?

R: Sebbene la raccolta XImage fornisca un modo potente per gestire e manipolare le immagini, è importante considerare fattori come l'utilizzo della memoria e la complessità delle operazioni eseguite sulle immagini. Si raccomanda una gestione attenta della raccolta e un uso efficiente delle risorse.

#### D: Posso riutilizzare le immagini archiviate nella raccolta XImage in più documenti PDF?

R: La raccolta XImage è specifica per ogni documento PDF e non è progettata per il riutilizzo tra documenti. Se hai bisogno di riutilizzare le immagini in più documenti, dovrai archiviarle e gestirle separatamente per ogni documento.