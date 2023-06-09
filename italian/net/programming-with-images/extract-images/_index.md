---
title: Estrai immagini
linktitle: Estrai immagini
second_title: Aspose.PDF per riferimento API .NET
description: Estrai facilmente le immagini da un file PDF con Aspose.PDF per .NET.
type: docs
weight: 120
url: /it/net/programming-with-images/extract-images/
---

Questa guida ti guiderà passo dopo passo su come estrarre immagini da un file PDF utilizzando Aspose.PDF per .NET. Assicurati di aver già configurato il tuo ambiente e procedi nel seguente modo:

## Passaggio 1: definire la directory dei documenti

 Prima di iniziare, assicurati di impostare la directory corretta per i documenti. Sostituire`"YOUR DOCUMENT DIRECTORY"` nel codice con il percorso della directory in cui si trova il documento PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: apri il documento PDF

 In questo passaggio, apriremo il documento PDF utilizzando il file`Document` classe di Aspose.PDF. Usa il`Document` costruttore e passare il percorso al documento PDF.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractImages.pdf");
```

## Passaggio 3: estrarre un'immagine specifica

 In questo passaggio, estrarremo un'immagine specifica da una determinata pagina. Usa il`Images` raccolta della pagina`s `Oggetto Resources per accedere all'immagine desiderata. Nell'esempio seguente, estraiamo l'immagine con indice 1 dalla prima pagina.

```csharp
XImage xImage = pdfDocument.Pages[1].Resources.Images[1];
```

## Passaggio 4: salva l'immagine estratta

 Salva l'immagine estratta in un file utilizzando il formato`Save` metodo del`xImage`oggetto. Specificare il percorso di output e il formato dell'immagine (in questo esempio stiamo usando il formato JPEG).

```csharp
FileStream outputImage = new FileStream(dataDir + "output.jpg", FileMode.Create);
xImage.Save(outputImage, ImageFormat.Jpeg);
outputImage.Close();
```

## Passaggio 5: salvare il file PDF aggiornato

 Salvare il file PDF aggiornato utilizzando il file`Save` metodo del`pdfDocument` oggetto. Specificare il percorso di output per il file PDF.

```csharp
dataDir = dataDir + "ExtractImages_out.pdf";
pdfDocument.Save(dataDir);
```

### Esempio di codice sorgente per Estrai immagini utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir+ "ExtractImages.pdf");
// Estrai un'immagine particolare
XImage xImage = pdfDocument.Pages[1].Resources.Images[1];
FileStream outputImage = new FileStream(dataDir + "output.jpg", FileMode.Create);
// Salva l'immagine di output
xImage.Save(outputImage, ImageFormat.Jpeg);
outputImage.Close();
dataDir = dataDir + "ExtractImages_out.pdf";
// Salva il file PDF aggiornato
pdfDocument.Save(dataDir);
Console.WriteLine("\nImages extracted successfully.\nFile saved at " + dataDir); 
```

## Conclusione

Congratulazioni! Hai estratto con successo le immagini da un PDF utilizzando Aspose.PDF per .NET. L'immagine estratta viene salvata nella directory specificata e viene salvato anche il file PDF aggiornato. Ora puoi utilizzare questi file per le tue esigenze specifiche.