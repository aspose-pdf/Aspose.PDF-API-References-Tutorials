---
title: Converti tutte le pagine in PNG
linktitle: Converti tutte le pagine in PNG
second_title: Aspose.PDF per riferimento API .NET
description: Converti facilmente tutte le pagine di un documento PDF in file PNG con Aspose.PDF per .NET.
type: docs
weight: 60
url: /it/net/programming-with-images/convert-all-pages-to-png/
---

Questa guida ti guiderà passo dopo passo su come convertire tutte le pagine di un documento PDF in file PNG utilizzando Aspose.PDF per .NET. Assicurati di aver già configurato il tuo ambiente e procedi nel seguente modo:

## Passaggio 1: definire la directory dei documenti

 Prima di iniziare, assicurati di impostare la directory corretta per i documenti. Sostituire`"YOUR DOCUMENT DIRECTORY"` nel codice con il percorso della directory in cui si trova il documento PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: apri il documento

 In questo passaggio, apriremo il documento PDF utilizzando il file`Document` classe di Aspose.PDF. Usa il`Document` costruttore e passare il percorso al documento PDF.

```csharp
Document pdfDocument = new Document(dataDir + "ConvertAllPagesToPNG.pdf");
```

## Passaggio 3: converti ogni pagina in PNG

 In questo passaggio, esamineremo ogni pagina del documento PDF e le convertiremo in singoli file PNG. Useremo un`for`loop per scorrere tutte le pagine.

```csharp
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
     //Crea uno stream per salvare l'immagine PNG
     using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".png", FileMode.Create))
     {
         // Crea un dispositivo PNG con gli attributi specificati
         // Larghezza, Altezza, Risoluzione, Qualità
         // Qualità [0-100], 100 è il massimo
         Resolution resolution = new Resolution(300);
         PngDevice pngDevice = new PngDevice(resolution);
        
         // Converti una pagina specifica e salva l'immagine nello stream
         pngDevice.Process(pdfDocument.Pages[pageCount], imageStream);
        
         // Chiudi il flusso
         imageStream.Close();
     }
}
```

### Esempio di codice sorgente per Converti tutte le pagine in PNG utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "ConvertAllPagesToPNG.pdf");
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
	using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".png", FileMode.Create))
	{
		// Crea un dispositivo PNG con gli attributi specificati
		// Larghezza, Altezza, Risoluzione, Qualità
		// Qualità [0-100], 100 è il massimo
		// Crea oggetto Risoluzione
		Resolution resolution = new Resolution(300);
		PngDevice pngDevice = new PngDevice(resolution);
		// Converti una pagina specifica e salva l'immagine per lo streaming
		pngDevice.Process(pdfDocument.Pages[pageCount], imageStream);
		// Chiudi flusso
		imageStream.Close();
	}
}
System.Console.WriteLine("PDF pages are converted to PNG successfully!");
```

## Conclusione

Congratulazioni! Hai convertito con successo tutte le pagine di un documento PDF in file PNG utilizzando Aspose.PDF per .NET. I singoli file PNG vengono salvati nella directory specificata. Ora puoi utilizzare questi file PNG nei tuoi progetti o applicazioni.