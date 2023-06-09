---
title: Converti la regione della pagina in DOM
linktitle: Converti la regione della pagina in DOM
second_title: Aspose.PDF per riferimento API .NET
description: Converti facilmente una regione specifica di una pagina PDF in un Document Object Model (DOM) con Aspose.PDF per .NET.
type: docs
weight: 80
url: /it/net/programming-with-images/convert-page-region-to-dom/
---

Questa guida ti guiderà passo dopo passo su come convertire una regione specifica di una pagina in un Document Object Model (DOM) utilizzando Aspose.PDF per .NET. Assicurati di aver già configurato il tuo ambiente e procedi nel seguente modo:

## Passaggio 1: definire la directory dei documenti

 Prima di iniziare, assicurati di impostare la directory corretta per i documenti. Sostituire`"YOUR DOCUMENT DIRECTORY"` nel codice con il percorso della directory in cui si trova il documento PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: apri il documento

 In questo passaggio, apriremo il documento PDF utilizzando il file`Document` classe di Aspose.PDF. Usa il`Document` costruttore e passare il percorso al documento PDF.

```csharp
Document document = new Document(dataDir + "AddImage.pdf");
```

## Passaggio 3: ottieni il rettangolo dell'area della pagina

 In questo passaggio, definiremo un rettangolo che rappresenta la regione specifica della pagina che vogliamo convertire in DOM. Usa il`Aspose.Pdf.Rectangle` class per definire le coordinate del rettangolo.

```csharp
Aspose.Pdf.Rectangle pageRect = new Aspose.Pdf.Rectangle(20, 671, 693, 1125);
```

## Passaggio 4: definire l'area di ritaglio della pagina

 Usa il`CropBox` proprietà del`Page` oggetto per impostare la casella di ritaglio della pagina sul rettangolo dell'area desiderata.

```csharp
document.Pages[1].CropBox = pageRect;
```

## Passaggio 5: salva il documento PDF ritagliato in un flusso

 In questo passaggio, salveremo il documento PDF ritagliato in un flusso utilizzando il file`MemoryStream` classe.

```csharp
MemoryStream ms = new MemoryStream();
document.Save(ms);
```

## Passaggio 6: apri il documento PDF ritagliato e convertilo in un'immagine

 Apri il documento PDF ritagliato utilizzando il file`Document` class e convertirlo in un'immagine. Useremo una risoluzione di 300 dpi.

```csharp
document = newDocument(ms);
Resolution resolution = new Resolution(300);
PngDevice pngDevice = new PngDevice(resolution);
```

## Passaggio 7: converti la pagina specifica in un'immagine

 Converti la pagina specifica in un'immagine utilizzando il file`Process` metodo del`pngDevice` oggetto. Specificare il percorso di output dell'immagine.

```csharp
dataDir = dataDir + "ConvertPageRegionToDOM_out.png";
pngDevice.Process(document.Pages[1], dataDir);
```

### Codice sorgente di esempio per convertire la regione della pagina in DOM utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document document = new Document( dataDir + "AddImage.pdf");
// Ottieni il rettangolo di una particolare regione della pagina
Aspose.Pdf.Rectangle pageRect = new Aspose.Pdf.Rectangle(20, 671, 693, 1125);
//Imposta il valore di CropBox in base al rettangolo dell'area della pagina desiderata
document.Pages[1].CropBox = pageRect;
// Salva il documento ritagliato nello stream
MemoryStream ms = new MemoryStream();
document.Save(ms);
// Apri il documento PDF ritagliato e converti in immagine
document = new Document(ms);
// Crea oggetto Risoluzione
Resolution resolution = new Resolution(300);
// Crea un dispositivo PNG con gli attributi specificati
PngDevice pngDevice = new PngDevice(resolution);
dataDir = dataDir + "ConvertPageRegionToDOM_out.png";
// Converti una pagina specifica e salva l'immagine per lo streaming
pngDevice.Process(document.Pages[1], dataDir);
ms.Close();
Console.WriteLine("\nPage region converted to DOM successfully.\nFile saved at " + dataDir); 
```

## Conclusione

Congratulazioni! Hai convertito con successo una regione specifica di una pagina in un Document Object Model (DOM) utilizzando Aspose.PDF per .NET. L'immagine risultante viene salvata nella directory specificata. Ora puoi utilizzare questa immagine nei tuoi progetti o applicazioni.