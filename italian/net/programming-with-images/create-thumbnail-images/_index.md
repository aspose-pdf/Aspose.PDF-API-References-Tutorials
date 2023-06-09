---
title: Crea immagini in miniatura
linktitle: Crea immagini in miniatura
second_title: Aspose.PDF per riferimento API .NET
description: Crea facilmente miniature di immagini da file PDF con Aspose.PDF per .NET.
type: docs
weight: 100
url: /it/net/programming-with-images/create-thumbnail-images/
---

Questa guida ti guiderà passo dopo passo su come creare miniature di immagini da file PDF utilizzando Aspose.PDF per .NET. Assicurati di aver già configurato il tuo ambiente e procedi nel seguente modo:

## Passaggio 1: definire la directory dei documenti

 Prima di iniziare, assicurati di impostare la directory corretta per i documenti. Sostituire`"YOUR DOCUMENT DIRECTORY"` nel codice con il percorso della directory contenente i file PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: ottieni i nomi di tutti i file PDF in una directory

 In questo passaggio, recupereremo i nomi di tutti i file PDF presenti nella directory specificata utilizzando C#`Directory`classe. I file verranno archiviati in un array di stringhe.

```csharp
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
```

## Passo 3: Sfoglia tutti i file PDF e le loro pagine

 In questo passaggio, esamineremo tutti i file PDF e le loro pagine per creare miniature delle immagini. Useremo un`for` loop per scorrere tutti i file.

```csharp
for (int counter = 0; counter < fileEntries.Length; counter++)
{
     // Apri il documento PDF
     Document pdfDocument = new Document(fileEntries[counter]);
    
     // Scorri tutte le pagine del documento
     for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
     {
         // Crea uno stream per salvare l'immagine in miniatura
         using (FileStream imageStream = new FileStream(dataDir + "\\Thumbnails" + counter.ToString() + "_" + pageCount + ".jpg", FileMode.Create))
         {
             // Crea un oggetto Risoluzione
             Resolution resolution = new Resolution(300);
            
             // Crea un dispositivo JPEG con gli attributi specificati
             JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
            
             // Converti una pagina specifica e salva l'immagine nello stream
             jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
            
             // Chiudi il flusso
             imageStream.Close();
         }
     }
}
```

### Codice sorgente di esempio per creare immagini in miniatura utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Recupera i nomi di tutti i file PDF in una particolare directory
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
// Itera attraverso tutte le voci dei file nell'array
for (int counter = 0; counter < fileEntries.Length; counter++)
{
	//Apri documento
	Document pdfDocument = new Document(fileEntries[counter]);
	for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
	{
		using (FileStream imageStream = new FileStream(dataDir + "\\Thumbanils" + counter.ToString() + "_" + pageCount + ".jpg", FileMode.Create))
		{
			//Crea oggetto Risoluzione
			Resolution resolution = new Resolution(300);
			//JpegDevice jpegDevice = nuovo JpegDevice(500, 700, risoluzione, 100);
			JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
			//Converti una pagina specifica e salva l'immagine per lo streaming
			jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
			//Chiudi flusso
			imageStream.Close();
		}
	}
}
System.Console.WriteLine("PDF pages are converted to thumbnails successfully!");
```

## Conclusione

Congratulazioni! Hai creato con successo miniature di immagini da file PDF utilizzando Aspose.PDF per .NET. Le miniature delle immagini vengono salvate nella directory specificata. Ora puoi utilizzare queste miniature per visualizzare un'anteprima visiva dei tuoi file PDF.