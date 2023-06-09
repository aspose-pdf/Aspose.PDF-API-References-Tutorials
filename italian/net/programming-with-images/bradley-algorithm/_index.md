---
title: Algoritmo di Bradley
linktitle: Algoritmo di Bradley
second_title: Aspose.PDF per riferimento API .NET
description: Converti un documento PDF utilizzando l'algoritmo Bradley con Aspose.PDF per .NET.
type: docs
weight: 30
url: /it/net/programming-with-images/bradley-algorithm/
---

Questa guida dettagliata spiega come utilizzare l'algoritmo Bradley con Aspose.PDF per .NET. Assicurati di aver già configurato il tuo ambiente e procedi nel seguente modo:

## Passaggio 1: definire la directory dei documenti

 Prima di iniziare, assicurati di impostare la directory corretta per i documenti. Sostituire`"YOUR DOCUMENT DIRECTORY"` nel codice con il percorso della directory in cui si trova il documento PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: apri il documento

 In questo passaggio, apriremo il documento PDF utilizzando il file`Document` classe di Aspose.PDF. Usa il`Document` costruttore e passare il percorso al documento PDF.

```csharp
Document pdfDocument = new Document(dataDir + "PageToTIFF.pdf");
```

## Passaggio 3: definire i file di output

 Definire i nomi dei file di output per l'immagine risultante e l'immagine binaria. Sostituire`"resultant_out.tif"` E`"37116-bin_out.tif"` con i nomi desiderati per i file di output.

```csharp
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
```

## Passaggio 4: creare l'oggetto Risoluzione

 Creare un`Resolution` oggetto per impostare la risoluzione dell'immagine TIFF. In questo esempio, stiamo usando una risoluzione di 300 dpi.

```csharp
Resolution resolution = new Resolution(300);
```

## Passaggio 5: creare l'oggetto TiffSettings

 Creare un`TiffSettings` oggetto per specificare le impostazioni per il file TIFF di output. In questo esempio, stiamo usando la compressione LZW e una profondità di colore di 1 bit per pixel (formato 1 bpp).

```csharp
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.LZW;
tiffSettings.Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp;
```

## Passaggio 6: creare il dispositivo TIFF

 Creare un dispositivo TIFF utilizzando il file`TiffDevice` oggetto, specificando la risoluzione e le impostazioni TIFF.

```csharp
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
```

## Passaggio 7: convertire la pagina specifica e salvare l'immagine

 Usa il`Process` metodo del dispositivo TIFF per convertire una pagina specifica del documento PDF e salvare l'immagine in un file TIFF. Specificare il percorso di output del file.

```csharp
tiffDevice.Process(pdfDocument, outputImageFile);
```

## Passaggio 8: Binarizzare l'immagine utilizzando l'algoritmo Bradley

 Usa il`BinarizeBradley`metodo del dispositivo TIFF per binarizzare l'immagine utilizzando l'algoritmo Bradley. Questo metodo accetta un flusso di input dell'immagine originale e un flusso di output per l'immagine binaria. Specificare la soglia di binarizzazione (0,1 in questo esempio).

```csharp
using (FileStream

  inStream = new FileStream(outputImageFile, FileMode.Open))
{
using (FileStream outStream = new FileStream(outputBinImageFile, FileMode.Create))
{
tiffDevice. Binarize Bradley(inStream, outStream, 0.1);
}
}
```

### Esempio di codice sorgente per Bradley Algorithm utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir+ "PageToTIFF.pdf");
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
// Crea oggetto Risoluzione
Resolution resolution = new Resolution(300);
// Crea un oggetto TiffSettings
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.LZW;
tiffSettings.Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp;
// Crea dispositivo TIFF
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
// Converti una pagina specifica e salva l'immagine per lo streaming
tiffDevice.Process(pdfDocument, outputImageFile);
using (FileStream inStream = new FileStream(outputImageFile, FileMode.Open))
{
	using (FileStream outStream = new FileStream(outputBinImageFile, FileMode.Create))
	{
		tiffDevice.BinarizeBradley(inStream, outStream, 0.1);
	}
}
System.Console.WriteLine("Conversion using bradley algorithm performed successfully!");
```

## Conclusione

Congratulazioni! Hai completato con successo la conversione utilizzando l'algoritmo Bradley con Aspose.PDF per .NET. Ora puoi utilizzare le immagini risultanti nei tuoi progetti o applicazioni.