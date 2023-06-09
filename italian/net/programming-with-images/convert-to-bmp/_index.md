---
title: Converti in BMP
linktitle: Converti in BMP
second_title: Aspose.PDF per riferimento API .NET
description: Converti facilmente PDF in singole immagini BMP con Aspose.PDF per .NET.
type: docs
weight: 90
url: /it/net/programming-with-images/convert-to-bmp/
---

Questa guida ti guiderà passo dopo passo su come convertire un file PDF in singole immagini BMP utilizzando Aspose.PDF per .NET. Assicurati di aver già configurato il tuo ambiente e procedi nel seguente modo:

## Passaggio 1: definire la directory dei documenti

 Prima di iniziare, assicurati di impostare la directory corretta per i documenti. Sostituire`"YOUR DOCUMENT DIRECTORY"` nel codice con il percorso della directory in cui si trova il documento PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: apri il documento

 In questo passaggio, apriremo il documento PDF utilizzando il file`Document` classe di Aspose.PDF. Usa il`Document` costruttore e passare il percorso al documento PDF.

```csharp
Document pdfDocument = new Document(dataDir + "AddImage.pdf");
```

## Passo 3: Converti ogni pagina in BMP

 In questo passaggio, esamineremo ogni pagina del documento PDF e le convertiremo in singole immagini BMP. Useremo un`for`loop per scorrere tutte le pagine.

```csharp
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
     // Crea uno stream per salvare l'immagine BMP
     using (FileStream imageStream = new FileStream("image" + pageCount + "_out" + ".bmp", FileMode.Create))
     {
         // Crea un oggetto Risoluzione
         Resolution resolution = new Resolution(300);
        
         // Crea un dispositivo BMP con gli attributi specificati
         //Larghezza, Altezza, Risoluzione, Dimensione pagina
         BmpDevice bmpDevice = new BmpDevice(resolution);
        
         // Converti una pagina specifica e salva l'immagine nello stream
         bmpDevice.Process(pdfDocument.Pages[pageCount], imageStream);
        
         // Chiudi il flusso
         imageStream.Close();
     }
}
```

### Esempio di codice sorgente per Convert To BMP utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "AddImage.pdf");
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
	using (FileStream imageStream = new FileStream("image" + pageCount + "_out" + ".bmp", FileMode.Create))
	{
		// Crea oggetto Risoluzione
		Resolution resolution = new Resolution(300);
		// Crea un dispositivo BMP con gli attributi specificati
		// Larghezza, Altezza, Risoluzione, PageSize
		BmpDevice bmpDevice = new BmpDevice(resolution);
		// Converti una pagina specifica e salva l'immagine per lo streaming
		bmpDevice.Process(pdfDocument.Pages[pageCount], imageStream);
		// Chiudi flusso
		imageStream.Close();
	}
} 
Console.WriteLine("\nPDF file converted to bmp successfully!"); 
```

## Conclusione

Congratulazioni! Hai convertito con successo un file PDF in singole immagini BMP utilizzando Aspose.PDF per .NET. Le immagini BMP vengono salvate nella directory specificata. Ora puoi utilizzare queste immagini nei tuoi progetti o applicazioni.