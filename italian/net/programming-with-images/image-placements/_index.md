---
title: Posizionamenti delle immagini
linktitle: Posizionamenti delle immagini
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come utilizzare Aspose.PDF per .NET per posizionare le immagini in un documento PDF.
type: docs
weight: 170
url: /it/net/programming-with-images/image-placements/
---

In questo tutorial, utilizzeremo la libreria Aspose.PDF per .NET per lavorare con documenti PDF ed eseguire operazioni sulle immagini. Carichiamo un documento PDF, estraiamo le informazioni sul posizionamento dell'immagine e recuperiamo le immagini con le loro dimensioni visibili.

## Passaggio 1: configurazione dell'ambiente
Prima di iniziare, assicurati di aver configurato il tuo ambiente di sviluppo con quanto segue:
- Aspose.PDF per .NET installato sul tuo computer.
- Progetto AC# pronto per essere utilizzato.

## Passaggio 2: caricamento del documento PDF
Per iniziare, dobbiamo caricare il documento PDF che vogliamo elaborare. Assicurati di avere il percorso corretto della directory contenente il documento PDF.

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Carica il documento PDF di origine
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "PlacementImage.pdf");
```

 Assicurati di sostituire`"YOUR DOCUMENTS DIRECTORY"` con il percorso effettivo della directory dei documenti contenente il file PDF.

## Passaggio 3: estrarre le informazioni sul posizionamento dalle immagini
 Ora che abbiamo caricato il documento PDF, possiamo estrarre le informazioni sul posizionamento dalle immagini. Noi useremo`ImagePlacementAbsorber`per assorbire le posizioni delle immagini dalla prima pagina del documento.

```csharp
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
// Carica il contenuto della prima pagina
doc.Pages[1].Accept(abs);
```

Ora abbiamo estratto le informazioni sul posizionamento dell'immagine dalla prima pagina del documento.

## Passaggio 4: recupero di immagini con dimensioni visibili
Ora recupereremo le immagini con le loro dimensioni visibili dalle informazioni sul posizionamento che abbiamo estratto in precedenza.

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

     // Recupera l'immagine con le dimensioni visibili
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

In questo ciclo, recuperiamo le proprietà di ciascuna immagine, come larghezza, altezza, coordinate X e Y dell'angolo inferiore sinistro e risoluzione orizzontale e verticale. Quindi recuperiamo ogni immagine con le sue dimensioni visibili utilizzando le informazioni sul posizionamento.

### Esempio di codice sorgente per posizionamenti di immagini utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
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
	// Recupera immagine con dimensioni visibili
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
Congratulazioni! Ora hai imparato come utilizzare Aspose.PDF per .NET per eseguire posizionamenti di immagini in un documento PDF. Abbiamo spiegato il codice sorgente C# fornito, che consente di caricare un documento PDF, estrarre le informazioni di posizionamento dalle immagini e recuperare le immagini con le loro dimensioni visibili. Sentiti libero di sperimentare di più con Aspose.PDF per esplorare le sue numerose altre funzionalità.