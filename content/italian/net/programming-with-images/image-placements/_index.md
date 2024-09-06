---
title: Posizionamento delle immagini
linktitle: Posizionamento delle immagini
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come utilizzare Aspose.PDF per .NET per inserire immagini in un documento PDF.
type: docs
weight: 170
url: /it/net/programming-with-images/image-placements/
---
In questo tutorial, useremo la libreria Aspose.PDF per .NET per lavorare con documenti PDF ed eseguire operazioni sulle immagini. Caricheremo un documento PDF, estrarremo le informazioni di posizionamento delle immagini e recupereremo le immagini con le loro dimensioni visibili.

## Fase 1: Impostazione dell'ambiente
Prima di iniziare, assicurati di aver configurato il tuo ambiente di sviluppo con quanto segue:
- Aspose.PDF per .NET installato sul computer.
- Progetto AC# pronto per essere utilizzato.

## Passaggio 2: caricamento del documento PDF
Per iniziare, dobbiamo caricare il documento PDF che vogliamo elaborare. Assicurati di avere il percorso corretto per la directory contenente il documento PDF.

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Carica il documento PDF di origine
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "PlacementImage.pdf");
```

 Assicurati di sostituire`"YOUR DOCUMENTS DIRECTORY"` con il percorso effettivo alla directory dei documenti contenente il file PDF.

## Passaggio 3: estrarre le informazioni di posizionamento dalle immagini
 Ora che abbiamo caricato il documento PDF, possiamo estrarre le informazioni di posizionamento dalle immagini. Useremo`ImagePlacementAbsorber`per assorbire le posizioni delle immagini dalla prima pagina del documento.

```csharp
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
// Carica il contenuto della prima pagina
doc.Pages[1].Accept(abs);
```

Abbiamo ora estratto le informazioni sul posizionamento delle immagini dalla prima pagina del documento.

## Fase 4: Recupero delle immagini con dimensioni visibili
Ora recupereremo le immagini con le loro dimensioni visibili dalle informazioni di posizionamento estratte in precedenza.

```csharp
foreach(ImagePlacement imagePlacement in abs.ImagePlacements)
{
     // Ottieni le proprietà dell'immagine
     Console.Out.WriteLine("Image Width: " + imagePlacement.Rectangle.Width);
     Console.Out.WriteLine("Image Height: " + imagePlacement.Rectangle.Height);
     Console.Out.WriteLine("LLX of image: " + imagePlacement.Rectangle.LLX);
     Console.Out.WriteLine("LLY of image: " + imagePlacement.Rectangle.LLY);
     Console.Out.WriteLine("Horizontal resolution of the image

  : " + imagePlacement.Resolution.X);
     Console.Out.WriteLine("Vertical image resolution: " + imagePlacement.Resolution.Y);

     // Recupera l'immagine con dimensioni visibili
     Bitmap scaledImage;
     using (MemoryStream imageStream = new MemoryStream())
     {
         // Ottieni l'immagine dalle risorse
         imagePlacement.Image.Save(imageStream, System.Drawing.Imaging.ImageFormat.Png);
         Bitmap resourceImage = (Bitmap)Bitmap.FromStream(imageStream);

         // Crea un'immagine con dimensioni reali
         scaledImage = new Bitmap(resourceImage, (int)imagePlacement.Rectangle.Width, (int)imagePlacement.Rectangle.Height);
     }
}
```

In questo ciclo, recuperiamo le proprietà di ogni immagine, come larghezza, altezza, coordinate X e Y dell'angolo inferiore sinistro e risoluzione orizzontale e verticale. Quindi recuperiamo ogni immagine con le sue dimensioni visibili usando le informazioni di posizionamento.

### Esempio di codice sorgente per il posizionamento delle immagini tramite Aspose.PDF per .NET 
```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Carica il documento PDF di origine
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "ImagePlacement.pdf");
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
// Carica il contenuto della prima pagina
doc.Pages[1].Accept(abs);
foreach (ImagePlacement imagePlacement in abs.ImagePlacements)
{
	// Ottieni le proprietà dell'immagine
	Console.Out.WriteLine("image width:" + imagePlacement.Rectangle.Width);
	Console.Out.WriteLine("image height:" + imagePlacement.Rectangle.Height);
	Console.Out.WriteLine("image LLX:" + imagePlacement.Rectangle.LLX);
	Console.Out.WriteLine("image LLY:" + imagePlacement.Rectangle.LLY);
	Console.Out.WriteLine("image horizontal resolution:" + imagePlacement.Resolution.X);
	Console.Out.WriteLine("image vertical resolution:" + imagePlacement.Resolution.Y);
	// Recupera l'immagine con dimensioni visibili
	Bitmap scaledImage;
	using (MemoryStream imageStream = new MemoryStream())
	{
		// Recupera l'immagine dalle risorse
		imagePlacement.Image.Save(imageStream, System.Drawing.Imaging.ImageFormat.Png);
		Bitmap resourceImage = (Bitmap)Bitmap.FromStream(imageStream);
		//Crea bitmap con dimensioni reali
		scaledImage = new Bitmap(resourceImage, (int)imagePlacement.Rectangle.Width, (int)imagePlacement.Rectangle.Height);
	}
}
```

## Conclusione
Congratulazioni! Ora hai imparato come usare Aspose.PDF per .NET per eseguire posizionamenti di immagini in un documento PDF. Abbiamo spiegato il codice sorgente C# fornito, che ti consente di caricare un documento PDF, estrarre le informazioni di posizionamento dalle immagini e recuperare le immagini con le loro dimensioni visibili. Sentiti libero di sperimentare di più con Aspose.PDF per esplorare le sue numerose altre funzionalità.

### Domande frequenti

#### D: Qual è lo scopo dell'estrazione delle informazioni sul posizionamento delle immagini da un documento PDF utilizzando Aspose.PDF per .NET?

A: L'estrazione delle informazioni sul posizionamento delle immagini consente di recuperare il posizionamento, le dimensioni e la risoluzione delle immagini all'interno di un documento PDF. Queste informazioni sono essenziali per una manipolazione e un'analisi precise delle immagini.

#### D: In che modo Aspose.PDF per .NET facilita l'estrazione delle informazioni sul posizionamento delle immagini da un documento PDF?

 A: Aspose.PDF per .NET fornisce`ImagePlacementAbsorber`classe, che può essere utilizzata per assorbire i dettagli di posizionamento delle immagini da un documento PDF. Il codice fornito dimostra come utilizzare questa classe per recuperare le informazioni di posizionamento delle immagini.

#### D: A cosa possono servire le informazioni sul posizionamento delle immagini in scenari reali?

R: Le informazioni sul posizionamento delle immagini sono utili per attività quali garantire un allineamento accurato delle immagini, calcolare le dimensioni delle immagini, verificarne la qualità e generare report sull'utilizzo delle immagini in un documento PDF.

#### D: In che modo il codice di esempio garantisce l'estrazione accurata delle informazioni sul posizionamento delle immagini?

 A: Il codice di esempio utilizza il`ImagePlacementAbsorber` classe per esplorare il contenuto di una pagina specificata, identificare il posizionamento delle immagini e recuperarne gli attributi, quali larghezza, altezza, coordinate e risoluzione.

#### D: Il codice può essere esteso per elaborare immagini su più pagine o documenti?

R: Sì, il codice può essere esteso iterando su più pagine o documenti per estrarre informazioni sul posizionamento delle immagini ed eseguire attività correlate alle immagini.

#### D: In che modo il codice recupera le immagini con le loro dimensioni visibili in base alle informazioni sul posizionamento?

R: L'esempio di codice estrae i dati dell'immagine dalle risorse, crea un'immagine bitmap con le dimensioni effettive e fornisce proprietà quali larghezza, altezza, coordinate e risoluzione.

#### D: Questo approccio è efficiente per documenti PDF di grandi dimensioni contenenti numerose immagini?

R: Sì, Aspose.PDF per .NET è ottimizzato per prestazioni e utilizzo delle risorse. Estrae in modo efficiente le informazioni sul posizionamento delle immagini anche da documenti PDF di grandi dimensioni.

#### D: In che modo gli sviluppatori possono trarre vantaggio dalla comprensione e dall'utilizzo delle informazioni sul posizionamento delle immagini?

R: Gli sviluppatori possono garantire una manipolazione, un allineamento e un'analisi precisi delle immagini all'interno dei documenti PDF. Queste informazioni consentono loro di creare applicazioni per l'elaborazione delle immagini, la creazione di report e la garanzia della qualità.

#### D: È possibile personalizzare il codice per estrarre ulteriori attributi o metadati relativi all'immagine?

R: Certamente, il codice può essere migliorato per estrarre attributi aggiuntivi, come tipo di immagine, spazio colore, compressione e altro, utilizzando classi e metodi appropriati forniti da Aspose.PDF per .NET.

#### D: Qual è il significato della conclusione fornita in questo tutorial?

R: La conclusione riassume il contenuto del tutorial e incoraggia un'ulteriore esplorazione di Aspose.PDF per .NET per sfruttarne le capacità oltre al posizionamento delle immagini, aprendo le porte a varie attività correlate ai PDF.