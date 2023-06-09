---
title: Tutte le pagine in TIFF
linktitle: Tutte le pagine in TIFF
second_title: Aspose.PDF per riferimento API .NET
description: Converti tutte le pagine di un documento PDF in file TIFF con Aspose.PDF per .NET.
type: docs
weight: 20
url: /it/net/programming-with-images/all-pages-to-tiff/
---

Questa guida ti guiderà passo dopo passo su come convertire tutte le pagine di un documento PDF in un file TIFF utilizzando Aspose.PDF per .NET. Assicurati di aver già configurato il tuo ambiente e procedi nel seguente modo:

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

## Passaggio 3: creare l'oggetto Risoluzione

 Creare un`Resolution` oggetto per impostare la risoluzione dell'immagine TIFF. In questo esempio, stiamo usando una risoluzione di 300 dpi.

```csharp
Resolution resolution = new Resolution(300);
```

## Passaggio 4: creare l'oggetto TiffSettings

 Creare un`TiffSettings` oggetto per specificare le impostazioni per il file TIFF di output. In questo esempio, disattiviamo la compressione, utilizziamo una profondità di colore predefinita e impostiamo la forma in modalità orizzontale.

```csharp
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.None;
tiffSettings.Depth = ColorDepth.Default;
tiffSettings.Shape = ShapeType.Landscape;
tiffSettings.SkipBlankPages = false;
```

## Passaggio 5: creare il dispositivo TIFF

 Creare un dispositivo TIFF utilizzando il file`TiffDevice` oggetto, specificando la risoluzione e le impostazioni TIFF.

```csharp
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
```

## Passaggio 6: converti tutte le pagine e salva l'immagine

 Usa il`Process` metodo del dispositivo TIFF per convertire tutte le pagine del documento PDF e salvare l'immagine in un file TIFF. Specificare il percorso di output del file.

```csharp
tiffDevice.Process(pdfDocument, dataDir + "AllPagesToTIFF_out.tif");
System.Console.WriteLine("PDF all pages converted to one tiff file successfully!");
```

### Esempio di codice sorgente per All Pages To TIFF utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir+ "PageToTIFF.pdf");
// Crea oggetto Risoluzione
Resolution resolution = new Resolution(300);
// Crea un oggetto TiffSettings
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.None;
tiffSettings.Depth = ColorDepth.Default;
tiffSettings.Shape = ShapeType.Landscape;
tiffSettings.SkipBlankPages = false;
// Crea dispositivo TIFF
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
// Converti una pagina specifica e salva l'immagine per lo streaming
tiffDevice.Process(pdfDocument, dataDir + "AllPagesToTIFF_out.tif");
System.Console.WriteLine("PDF all pages converted to one tiff file successfully!");
```

## Conclusione

Congratulazioni! Hai convertito con successo tutte le pagine di un documento PDF in un file TIFF utilizzando Aspose.PDF per .NET. Ora puoi utilizzare il file TIFF generato nei tuoi progetti o applicazioni.