---
title: Convertire la regione della pagina in DOM
linktitle: Convertire la regione della pagina in DOM
second_title: Riferimento API Aspose.PDF per .NET
description: Converti facilmente una specifica area di una pagina PDF in un Document Object Model (DOM) con Aspose.PDF per .NET.
type: docs
weight: 80
url: /it/net/programming-with-images/convert-page-region-to-dom/
---
Questa guida ti guiderà passo dopo passo nella conversione di una regione specifica di una pagina in un Document Object Model (DOM) utilizzando Aspose.PDF per .NET. Assicurati di aver già impostato il tuo ambiente e segui i passaggi sottostanti:

## Passaggio 1: definire la directory dei documenti

Prima di iniziare, assicurati di impostare la directory corretta per i documenti. Sostituisci`"YOUR DOCUMENT DIRECTORY"` nel codice con il percorso alla directory in cui si trova il documento PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: aprire il documento

 In questo passaggio, apriremo il documento PDF utilizzando`Document` classe di Aspose.PDF. Utilizzare il`Document` costruttore e passare il percorso al documento PDF.

```csharp
Document document = new Document(dataDir + "AddImage.pdf");
```

## Passaggio 3: Ottieni il rettangolo della regione della pagina

 In questo passaggio, definiremo un rettangolo che rappresenta la regione specifica della pagina che vogliamo convertire in DOM. Utilizzare il`Aspose.Pdf.Rectangle` classe per definire le coordinate del rettangolo.

```csharp
Aspose.Pdf.Rectangle pageRect = new Aspose.Pdf.Rectangle(20, 671, 693, 1125);
```

## Passaggio 4: definire l'area di ritaglio della pagina

 Utilizzare il`CropBox` proprietà del`Page` oggetto per impostare la casella di ritaglio della pagina sul rettangolo della regione desiderata.

```csharp
document.Pages[1].CropBox = pageRect;
```

## Passaggio 5: salvare il documento PDF ritagliato in un flusso

 In questo passaggio, salveremo il documento PDF ritagliato in un flusso utilizzando`MemoryStream` classe.

```csharp
MemoryStream ms = new MemoryStream();
document.Save(ms);
```

## Passaggio 6: aprire il documento PDF ritagliato e convertirlo in un'immagine

 Aprire il documento PDF ritagliato utilizzando`Document`classe e convertirla in un'immagine. Utilizzeremo una risoluzione di 300 dpi.

```csharp
document = newDocument(ms);
Resolution resolution = new Resolution(300);
PngDevice pngDevice = new PngDevice(resolution);
```

## Passaggio 7: Convertire la pagina specifica in un'immagine

 Converti la pagina specifica in un'immagine utilizzando`Process` metodo del`pngDevice` oggetto. Specificare il percorso di output dell'immagine.

```csharp
dataDir = dataDir + "ConvertPageRegionToDOM_out.png";
pngDevice.Process(document.Pages[1], dataDir);
```

### Esempio di codice sorgente per convertire la regione della pagina in DOM utilizzando Aspose.PDF per .NET 
```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document document = new Document( dataDir + "AddImage.pdf");
// Ottieni il rettangolo di una particolare regione della pagina
Aspose.Pdf.Rectangle pageRect = new Aspose.Pdf.Rectangle(20, 671, 693, 1125);
// Imposta il valore CropBox in base al rettangolo della regione di pagina desiderata
document.Pages[1].CropBox = pageRect;
// Salva il documento ritagliato nel flusso
MemoryStream ms = new MemoryStream();
document.Save(ms);
// Apri il documento PDF ritagliato e convertilo in immagine
document = new Document(ms);
// Crea oggetto Risoluzione
Resolution resolution = new Resolution(300);
// Crea dispositivo PNG con attributi specificati
PngDevice pngDevice = new PngDevice(resolution);
dataDir = dataDir + "ConvertPageRegionToDOM_out.png";
// Converti una pagina specifica e salva l'immagine in streaming
pngDevice.Process(document.Pages[1], dataDir);
ms.Close();
Console.WriteLine("\nPage region converted to DOM successfully.\nFile saved at " + dataDir); 
```

## Conclusione

Congratulazioni! Hai convertito con successo una regione specifica di una pagina in un Document Object Model (DOM) utilizzando Aspose.PDF per .NET. L'immagine risultante è salvata nella directory specificata. Ora puoi utilizzare questa immagine nei tuoi progetti o applicazioni.

## Domande frequenti

#### D: Qual è lo scopo della conversione di una specifica area di una pagina in un Document Object Model (DOM) utilizzando Aspose.PDF per .NET?

R: Convertire una specifica area di una pagina PDF in un Document Object Model (DOM) può essere utile per estrarre e manipolare una particolare sezione di contenuto all'interno di un documento PDF.

#### D: In che modo Aspose.PDF per .NET facilita la conversione di una specifica area di pagina in un DOM?

R: Aspose.PDF per .NET fornisce una procedura dettagliata per definire l'area di pagina desiderata, impostare l'area di ritaglio, salvare il documento PDF ritagliato in un flusso e convertire l'area di pagina specificata in un'immagine.

#### D: Perché è importante definire la directory dei documenti prima di avviare il processo di conversione?

R: Specificando la directory del documento si garantisce che il documento PDF e l'immagine risultante siano posizionati correttamente nel percorso di output desiderato.

####  D: Come funziona il`Document` class in Aspose.PDF for .NET help in the conversion process?

 A: Il`Document` classe consente di aprire, manipolare e salvare documenti PDF. In questo caso, viene utilizzata per caricare il documento PDF e crearne una versione ritagliata.

####  D: Qual è lo scopo del`Rectangle` class in the page region conversion process?

 A: Il`Rectangle`class definisce le coordinate della regione specifica sulla pagina PDF che vuoi convertire in un DOM. Aiuta a specificare con precisione l'area di ritaglio.

#### D: In che modo l'area di ritaglio della pagina viene impostata sulla regione desiderata durante il processo di conversione?

 A: Il`CropBox` proprietà del`Page` L'oggetto viene utilizzato per impostare l'area di ritaglio della pagina sul rettangolo definito che rappresenta la regione specifica.

#### D: Come viene salvato in un flusso il documento PDF ritagliato durante il processo di conversione?

 A: Il documento PDF ritagliato viene salvato in un`MemoryStream` oggetto, che consente una manipolazione efficiente del contenuto PDF.

####  D: Quale ruolo ha il`PngDevice` class play in the page region to DOM conversion process?

 A: Il`PngDevice` La classe aiuta a convertire il documento PDF ritagliato in un formato immagine, ad esempio PNG, consentendo di visualizzare l'area specifica della pagina.

#### D: Posso modificare la risoluzione o altri attributi dell'immagine risultante durante il processo di conversione?

 A: Sì, puoi modificare la risoluzione e altri attributi dell'immagine risultante configurando il`PngDevice` oggetto prima di convertire la pagina.