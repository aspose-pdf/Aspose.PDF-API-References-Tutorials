---
title: Converti la regione della pagina in DOM
linktitle: Converti la regione della pagina in DOM
second_title: Aspose.PDF per riferimento all'API .NET
description: Converti facilmente un'area specifica di una pagina PDF in un Document Object Model (DOM) con Aspose.PDF per .NET.
type: docs
weight: 80
url: /it/net/programming-with-images/convert-page-region-to-dom/
---
Questa guida ti guiderà passo dopo passo su come convertire un'area specifica di una pagina in un Document Object Model (DOM) utilizzando Aspose.PDF per .NET. Assicurati di aver già configurato il tuo ambiente e segui i passaggi seguenti:

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

 In questo passaggio definiremo un rettangolo che rappresenta la regione specifica della pagina che vogliamo convertire in DOM. Usa il`Aspose.Pdf.Rectangle` classe per definire le coordinate del rettangolo.

```csharp
Aspose.Pdf.Rectangle pageRect = new Aspose.Pdf.Rectangle(20, 671, 693, 1125);
```

## Passaggio 4: Definisci l'area di ritaglio della pagina

 Usa il`CropBox` proprietà del`Page` oggetto per impostare la casella di ritaglio della pagina sul rettangolo della regione desiderata.

```csharp
document.Pages[1].CropBox = pageRect;
```

## Passaggio 5: salva il documento PDF ritagliato in uno stream

 In questo passaggio, salveremo il documento PDF ritagliato in uno stream utilizzando il file`MemoryStream` classe.

```csharp
MemoryStream ms = new MemoryStream();
document.Save(ms);
```

## Passaggio 6: apri il documento PDF ritagliato e convertilo in un'immagine

 Apri il documento PDF ritagliato utilizzando il file`Document` classe e convertirlo in un'immagine. Utilizzeremo una risoluzione di 300 dpi.

```csharp
document = newDocument(ms);
Resolution resolution = new Resolution(300);
PngDevice pngDevice = new PngDevice(resolution);
```

## Passaggio 7: converti la pagina specifica in un'immagine

 Converti la pagina specifica in un'immagine utilizzando il file`Process` metodo del`pngDevice`oggetto. Specificare il percorso di output dell'immagine.

```csharp
dataDir = dataDir + "ConvertPageRegionToDOM_out.png";
pngDevice.Process(document.Pages[1], dataDir);
```

### Codice sorgente di esempio per Converti regione della pagina in DOM utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document document = new Document( dataDir + "AddImage.pdf");
// Ottieni il rettangolo di una particolare area della pagina
Aspose.Pdf.Rectangle pageRect = new Aspose.Pdf.Rectangle(20, 671, 693, 1125);
// Imposta il valore CropBox in base al rettangolo dell'area della pagina desiderata
document.Pages[1].CropBox = pageRect;
// Salva il documento ritagliato nello stream
MemoryStream ms = new MemoryStream();
document.Save(ms);
// Apri il documento PDF ritagliato e convertilo in immagine
document = new Document(ms);
// Crea oggetto Risoluzione
Resolution resolution = new Resolution(300);
// Crea un dispositivo PNG con gli attributi specificati
PngDevice pngDevice = new PngDevice(resolution);
dataDir = dataDir + "ConvertPageRegionToDOM_out.png";
//Converti una pagina particolare e salva l'immagine in streaming
pngDevice.Process(document.Pages[1], dataDir);
ms.Close();
Console.WriteLine("\nPage region converted to DOM successfully.\nFile saved at " + dataDir); 
```

## Conclusione

Congratulazioni! Hai convertito con successo un'area specifica di una pagina in un Document Object Model (DOM) utilizzando Aspose.PDF per .NET. L'immagine risultante viene salvata nella directory specificata. Ora puoi utilizzare questa immagine nei tuoi progetti o applicazioni.

## Domande frequenti

#### D: Qual è lo scopo di convertire un'area specifica di una pagina in un Document Object Model (DOM) utilizzando Aspose.PDF per .NET?

R: La conversione di un'area specifica di una pagina PDF in un Document Object Model (DOM) può essere utile per estrarre e manipolare una particolare sezione di contenuto all'interno di un documento PDF.

#### D: In che modo Aspose.PDF per .NET facilita la conversione di un'area di pagina specifica in un DOM?

R: Aspose.PDF per .NET fornisce un processo passo passo per definire l'area della pagina desiderata, impostare l'area di ritaglio, salvare il documento PDF ritagliato in un flusso e convertire l'area della pagina specificata in un'immagine.

#### D: Perché è importante definire la directory dei documenti prima di iniziare il processo di conversione?

R: Specificare la directory del documento garantisce che il documento PDF e l'immagine risultante siano posizionati correttamente nel percorso di output desiderato.

####  D: Come funziona il`Document` class in Aspose.PDF for .NET help in the conversion process?

 R: Il`Document` class ti consente di aprire, manipolare e salvare documenti PDF. In questo caso, viene utilizzato per caricare il documento PDF e crearne una versione ritagliata.

####  D: Qual è lo scopo di`Rectangle` class in the page region conversion process?

 R: Il`Rectangle` class definisce le coordinate della regione specifica sulla pagina PDF che desideri convertire in DOM. Aiuta a specificare con precisione l'area coltivata.

#### D: Come viene impostata l'area di ritaglio della pagina sulla regione desiderata nel processo di conversione?

 R: Il`CropBox` proprietà del`Page` L'oggetto viene utilizzato per impostare l'area di ritaglio della pagina sul rettangolo definito che rappresenta la regione specifica.

#### D: Come viene salvato in uno stream il documento PDF ritagliato durante il processo di conversione?

 R: Il documento PDF ritagliato viene salvato in un file`MemoryStream` oggetto, che consente una manipolazione efficiente del contenuto PDF.

####  D: Che ruolo ha il`PngDevice` class play in the page region to DOM conversion process?

 R: Il`PngDevice` La classe aiuta a convertire il documento PDF ritagliato in un formato immagine, come PNG, consentendo di visualizzare l'area specifica della pagina.

#### D: Posso regolare la risoluzione o altri attributi dell'immagine risultante durante il processo di conversione?

 R: Sì, puoi modificare la risoluzione e altri attributi dell'immagine risultante configurando il file`PngDevice` oggetto prima di convertire la pagina.