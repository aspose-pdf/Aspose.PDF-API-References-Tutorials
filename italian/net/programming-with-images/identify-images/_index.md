---
title: Identificare le immagini
linktitle: Identificare le immagini
second_title: Aspose.PDF per riferimento API .NET
description: Identifica facilmente le immagini in un file PDF e determina il loro tipo di colore con Aspose.PDF per .NET.
type: docs
weight: 150
url: /it/net/programming-with-images/identify-images/
---

Questa guida ti guiderà passo dopo passo su come identificare le immagini in un file PDF utilizzando Aspose.PDF per .NET. Assicurati di aver già configurato il tuo ambiente e procedi nel seguente modo:

## Passaggio 1: definire la directory dei documenti

 Assicurati di impostare la directory dei documenti corretta. Sostituire`"YOUR DOCUMENT DIRECTORY"` nel codice con il percorso della directory in cui si trova il documento PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: inizializzare i contatori

In questo passaggio, inizializzeremo i contatori per le immagini in scala di grigi e le immagini RGB.

```csharp
int grayscaled = 0; // Contatore per immagini in scala di grigi
int rdg = 0; // Contatore per immagini RGB
```

## Passaggio 3: apri il documento PDF

 In questo passaggio, apriremo il documento PDF utilizzando il file`Document` classe di Aspose.PDF. Usa il`Document` costruttore e passare il percorso al documento PDF.

```csharp
using (Document document = new Document(dataDir + "ExtractImages.pdf"))
{
```

## Passaggio 4: sfoglia le pagine del documento

In questo passaggio, esamineremo tutte le pagine del documento PDF e identificheremo le immagini su ogni pagina.

```csharp
foreach(Page page in document.Pages)
{
```

## Passaggio 5: recupera i posizionamenti delle immagini

 In questo passaggio, useremo`ImagePlacementAbsorber` per recuperare i posizionamenti delle immagini su ogni pagina.

```csharp
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
page. Accept(abs);
```

## Passaggio 6: conta le immagini e identifica il tipo di colore

In questo passaggio, conteremo il numero di immagini su ogni pagina e identificheremo il loro tipo di colore (scala di grigi o RGB).

```csharp
Console.WriteLine("Total Images = {0} on page number {1}", abs.ImagePlacements.Count, page.Number);
int image_counter = 1;
foreach(ImagePlacement ia in abs.ImagePlacements)
{
     ColorType colorType = ia.Image.GetColorType();
     switch (colorType)
     {
         ColorType.Grayscale box:
             ++grayscaled;
             Console.WriteLine("Image {0} is grayscale...", image_counter);
             break;
         box ColorType.Rgb:
             ++rgd;
             Console.WriteLine("Image {0} is RGB...", image_counter);
             break;
     }
     image_counter += 1;
}
```

### Codice sorgente di esempio per identificare le immagini utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Contatore per immagini in scala di grigi
int grayscaled = 0;
// Contatore per immagini RGB
int rgd = 0;
using (Document document = new Document(dataDir + "ExtractImages.pdf"))
{
	foreach (Page page in document.Pages)
	{
		Console.WriteLine("--------------------------------");
		ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
		page.Accept(abs);
		// Ottieni il conteggio delle immagini su una pagina specifica
		Console.WriteLine("Total Images = {0} over page number {1}", abs.ImagePlacements.Count, page.Number);
		// Documento.Pagine[29].Accetta(abs);
		int image_counter = 1;
		foreach (ImagePlacement ia in abs.ImagePlacements)
		{
			ColorType colorType = ia.Image.GetColorType();
			switch (colorType)
			{
				case ColorType.Grayscale:
					++grayscaled;
					Console.WriteLine("Image {0} is GrayScale...", image_counter);
					break;
				case ColorType.Rgb:
					++rgd;
					Console.WriteLine("Image {0} is RGB...", image_counter);
					break;
			}
			image_counter += 1;
		}
	}
}
```

## Conclusione

Congratulazioni! Hai identificato con successo le immagini in un PDF utilizzando Aspose.PDF per .NET. Le immagini sono state contate ed è stato identificato il loro tipo di colore (scala di grigi o RGB). Ora puoi utilizzare queste informazioni per le tue esigenze specifiche.