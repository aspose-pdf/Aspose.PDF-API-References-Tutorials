---
title: Posizionamento delle immagini
linktitle: Posizionamento delle immagini
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come estrarre e manipolare i posizionamenti delle immagini nei documenti PDF utilizzando Aspose.PDF per .NET. Guida passo passo con esempi e frammenti di codice.
type: docs
weight: 170
url: /it/net/programming-with-images/image-placements/
---
## Introduzione

Lavorare con le immagini nei file PDF può essere complicato, ma con Aspose.PDF per .NET, puoi facilmente manipolare ed estrarre le proprietà delle immagini senza sforzo. Che tu voglia ottenere le dimensioni delle immagini, estrarle o recuperare altre proprietà come la risoluzione, Aspose.PDF ha gli strumenti di cui hai bisogno. Questo tutorial ti guiderà passo dopo passo su come estrarre i posizionamenti delle immagini in un documento PDF utilizzando Aspose.PDF per .NET. Tratteremo tutto, dall'importazione di pacchetti al recupero delle proprietà delle immagini come larghezza, altezza e risoluzione.

## Prerequisiti

Prima di passare al tutorial, ci sono alcune cose che dovrai avere a disposizione. Ecco una rapida checklist:

1.  Aspose.PDF per .NET: assicurati di aver installato la libreria Aspose.PDF per .NET. Puoi scaricarla[Qui](https://releases.aspose.com/pdf/net/).
2. Ambiente di sviluppo: sarà necessario che sul computer sia installato Visual Studio o qualsiasi altro IDE supportato da .NET.
3. Un documento PDF: tieni pronto un documento PDF di esempio che contenga immagini. Per questo esempio, useremo un file denominato`ImagePlacement.pdf`.
4. Conoscenze di base di C#: sebbene questa guida sia adatta ai principianti, una conoscenza di base di C# ti aiuterà a comprendere meglio i frammenti di codice.

## Importa pacchetti

Prima di entrare nel vivo del codice, la prima cosa che devi fare è importare i namespace necessari. Questi pacchetti sono essenziali per lavorare con documenti PDF e manipolazione di immagini in Aspose.PDF per .NET.

```csharp
using System.IO;
using Aspose.Pdf;
using System;
using System.Drawing;
```

Questi pacchetti consentono di lavorare con i PDF (`Aspose.Pdf`), manipolare i posizionamenti delle immagini (`Aspose.Pdf.ImagePlacement`) e gestire flussi di immagini e grafica (`System.Drawing` E`System.IO`).

Ora che abbiamo predisposto i prerequisiti e i pacchetti, scomponiamo ogni parte del tutorial in una guida semplice e facile da seguire.

## Passaggio 1: caricare il documento PDF

Il primo passo è caricare il documento PDF nel tuo progetto. Questa sarà la base per lavorare con le immagini all'interno del file PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "ImagePlacement.pdf");
```

 In questo passaggio, definiamo il percorso del file del documento PDF utilizzando`dataDir` quindi creando una nuova istanza di`Aspose.Pdf.Document` classe. Questo ci consente di caricare il file PDF nel nostro programma. Semplice, vero? Proprio come quando apriamo un libro per iniziare a leggere, ora siamo pronti a esplorare il contenuto al suo interno.

## Passaggio 2: inizializzare l'assorbitore di posizionamento dell'immagine

Per estrarre le immagini, abbiamo bisogno di qualcosa chiamato "Image Placement Absorber". Immaginalo come uno strumento che assorbe tutte le informazioni delle immagini su una determinata pagina.

```csharp
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
```

 Qui stiamo creando un'istanza di`ImagePlacementAbsorber`. Questo oggetto raccoglierà e memorizzerà informazioni su tutti i posizionamenti delle immagini su una pagina PDF specifica. Immagina di scansionare una pagina con una lente di ingrandimento e identificare tutte le immagini su di essa!

## Passaggio 3: accettare l'assorbitore nella prima pagina

Poi, dobbiamo dire all'assorbitore quale pagina del PDF scansionare. Per questo esempio, ci concentreremo sulla prima pagina.

```csharp
doc.Pages[1].Accept(abs);
```

 IL`Accept` il metodo esegue la scansione della prima pagina del documento PDF per eventuali immagini e memorizza i risultati all'interno del`ImagePlacementAbsorber`È come dire alla lente di ingrandimento dove cercare le immagini.

## Passaggio 4: scorrere ogni posizionamento dell'immagine

Ora che abbiamo scansionato la pagina, dobbiamo scorrere ogni immagine trovata sulla pagina e recuperarne le proprietà.

```csharp
foreach (ImagePlacement imagePlacement in abs.ImagePlacements)
{
    Console.Out.WriteLine("image width:" + imagePlacement.Rectangle.Width);
    Console.Out.WriteLine("image height:" + imagePlacement.Rectangle.Height);
    Console.Out.WriteLine("image LLX:" + imagePlacement.Rectangle.LLX);
    Console.Out.WriteLine("image LLY:" + imagePlacement.Rectangle.LLY);
    Console.Out.WriteLine("image horizontal resolution:" + imagePlacement.Resolution.X);
    Console.Out.WriteLine("image vertical resolution:" + imagePlacement.Resolution.Y);
}
```

Questo ciclo passa attraverso ogni immagine trovata sulla pagina. Stiamo stampando la larghezza, l'altezza, la x in basso a sinistra (LLX), la y in basso a sinistra (LLY) e la risoluzione dell'immagine (sia orizzontale che verticale). Questi dettagli ti aiutano a capire le dimensioni e il posizionamento di ogni immagine all'interno del PDF.

## Passaggio 5: Estrarre l'immagine con dimensioni visibili

Dopo aver raccolto informazioni sulle immagini, potresti voler estrarre l'immagine effettiva con le sue dimensioni. Ecco come puoi farlo.

```csharp
Bitmap scaledImage;
using (MemoryStream imageStream = new MemoryStream())
{
    imagePlacement.Image.Save(imageStream, System.Drawing.Imaging.ImageFormat.Png);
    Bitmap resourceImage = (Bitmap)Bitmap.FromStream(imageStream);
    scaledImage = new Bitmap(resourceImage, (int)imagePlacement.Rectangle.Width, (int)imagePlacement.Rectangle.Height);
}
```

 Questo frammento di codice recupera l'immagine dal PDF e la ridimensiona alle sue dimensioni effettive come definito nel`ImagePlacement` oggetto. Salvando l'immagine in un flusso di memoria e ridimensionandola, ti assicuri che l'immagine estratta mantenga le dimensioni esatte in cui è stata visualizzata nel PDF.

## Conclusione

L'estrazione di posizionamenti di immagini da un documento PDF tramite Aspose.PDF per .NET è piuttosto semplice una volta che lo si analizza passo dopo passo. Abbiamo trattato tutto, dal caricamento di un PDF al recupero delle proprietà delle immagini e all'estrazione delle immagini con le loro dimensioni effettive. Aspose.PDF semplifica incredibilmente il lavoro con i PDF e la manipolazione dei contenuti, consentendo di lavorare in modo efficiente con immagini, testo e molto altro.

## Domande frequenti

### Posso estrarre immagini da una pagina specifica del PDF?  
 Sì, specificando il numero di pagina quando si utilizza il`Accept` metodo, puoi concentrarti su una pagina specifica.

### Quali formati di immagine sono supportati per l'estrazione?  
Aspose.PDF supporta vari formati, tra cui PNG, JPEG, BMP e altri.

### È possibile manipolare l'immagine estratta?  
 Assolutamente! Una volta estratto, puoi utilizzare il`System.Drawing` namespace per manipolare l'immagine.

### Posso estrarre immagini da PDF protetti da password?  
Sì, è possibile, ma prima di estrarre le immagini sarà necessario sbloccare il PDF utilizzando le credenziali appropriate.

### Aspose.PDF per .NET funziona su tutti i framework .NET?  
Sì, supporta .NET Framework, .NET Core e .NET 5 e versioni successive.