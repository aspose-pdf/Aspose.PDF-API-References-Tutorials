---
title: Cerca e ottieni immagini
linktitle: Cerca e ottieni immagini
second_title: Aspose.PDF per riferimento API .NET
description: Guida passo passo per cercare e ottenere immagini in un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 260
url: /it/net/programming-with-images/search-and-get-images/
---

In questo tutorial, ti illustreremo come cercare e ottenere immagini in un documento PDF utilizzando Aspose.PDF per .NET. Segui questi passaggi per eseguire facilmente questa operazione.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

- Visual Studio o qualsiasi altro ambiente di sviluppo installato e configurato.
- Conoscenza di base del linguaggio di programmazione C#.
- Libreria Aspose.PDF per .NET installata. Puoi scaricarlo dal sito ufficiale di Aspose.

## Passaggio 1: caricamento del documento PDF

Per iniziare, utilizza il seguente codice per caricare il documento PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Apri il documento
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SearchAndGetImages.pdf");
```

Assicurati di fornire il percorso corretto al tuo documento PDF.

## Passaggio 2: ricerca delle posizioni delle immagini

Per cercare le posizioni delle immagini nel documento PDF, utilizzare il seguente codice:

```csharp
// Crea un oggetto ImagePlacementAbsorber per cercare le posizioni delle immagini
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();

// Accetta l'assorbitore per tutte le pagine del documento
doc.Pages.Accept(abs);
```

Questo raccoglierà le posizioni delle immagini nell'assorbitore.

## Passaggio 3: sfoglia le posizioni delle immagini e ottieni le immagini e le loro proprietà

Successivamente, esploreremo le posizioni delle immagini raccolte e otterremo le immagini e le loro proprietà. Usa il seguente codice:

```csharp
foreach(ImagePlacement imagePlacement in abs.ImagePlacements)
{
     //Ottenere l'immagine utilizzando l'oggetto ImagePlacement
     XImage image = imagePlacement.Image;

     // Visualizza le proprietà della posizione dell'immagine
     Console.Out.WriteLine("Image Width: " + imagePlacement.Rectangle.Width);
     Console.Out.WriteLine("Image Height: " + imagePlacement.Rectangle.Height);
     Console.Out.WriteLine("LLX of image: " + imagePlacement.Rectangle.LLX);
     Console.Out.WriteLine("LLY of image: " + imagePlacement.Rectangle.LLY);
     Console.Out.WriteLine("Horizontal image resolution: " + imagePlacement.Resolution.X);
     Console.Out.WriteLine("Vertical image resolution: " + imagePlacement.Resolution.Y);
}
```

Questo esplorerà tutte le posizioni delle immagini, otterrà le immagini corrispondenti e visualizzerà le loro proprietà.

### Esempio di codice sorgente per Cerca e ottieni immagini utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "SearchAndGetImages.pdf");
// Crea un oggetto ImagePlacementAbsorber per eseguire la ricerca del posizionamento delle immagini
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
// Accetta l'assorbitore per tutte le pagine
doc.Pages.Accept(abs);
// Passa in rassegna tutti gli ImagePlacement, ottieni l'immagine e le proprietà ImagePlacement
foreach (ImagePlacement imagePlacement in abs.ImagePlacements)
{
	// Ottenere l'immagine utilizzando l'oggetto ImagePlacement
	XImage image = imagePlacement.Image;
	// Visualizza le proprietà del posizionamento dell'immagine per tutti i posizionamenti
	Console.Out.WriteLine("image width:" + imagePlacement.Rectangle.Width);
	Console.Out.WriteLine("image height:" + imagePlacement.Rectangle.Height);
	Console.Out.WriteLine("image LLX:" + imagePlacement.Rectangle.LLX);
	Console.Out.WriteLine("image LLY:" + imagePlacement.Rectangle.LLY);
	Console.Out.WriteLine("image horizontal resolution:" + imagePlacement.Resolution.X);
	Console.Out.WriteLine("image vertical resolution:" + imagePlacement.Resolution.Y);
}
```

## Conclusione

Congratulazioni! Hai cercato e ottenuto con successo le immagini in un documento PDF utilizzando Aspose.PDF per .NET. Ora puoi applicare questo metodo ai tuoi progetti per estrarre immagini e ottenere le loro proprietà dai file PDF.