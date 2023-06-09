---
title: Suggerimenti sui caratteri da PDF a PNG
linktitle: Suggerimenti sui caratteri da PDF a PNG
second_title: Aspose.PDF per riferimento API .NET
description: Guida passo passo per convertire PDF in PNG con suggerimenti sui caratteri utilizzando Aspose.PDF per .NET.
type: docs
weight: 160
url: /it/net/document-conversion/pdf-to-png-font-hinting/
---

In questo tutorial, ti guideremo attraverso il processo di conversione di un PDF in immagini PNG utilizzando Aspose.PDF per .NET, abilitando al contempo i suggerimenti sui caratteri. Il suggerimento sui caratteri è una tecnica che migliora la leggibilità dei caratteri piccoli. Seguendo i passaggi seguenti, sarai in grado di convertire ogni pagina del PDF in un'immagine PNG con suggerimenti sui caratteri.

## Prerequisiti
Prima di iniziare, assicurati di soddisfare i seguenti prerequisiti:

- Conoscenza base del linguaggio di programmazione C#.
- Libreria Aspose.PDF per .NET installata sul tuo sistema.
- Un ambiente di sviluppo come Visual Studio.

## Passaggio 1: apertura del documento PDF di origine
In questo passaggio, apriremo il file PDF di origine utilizzando Aspose.PDF per .NET. Segui il codice qui sotto:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Apri il documento
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 Assicurati di sostituire`"YOUR DOCUMENTS DIRECTORY"` con la directory effettiva in cui si trova il file PDF.

## Passaggio 2: abilita i suggerimenti sui caratteri
Dopo aver aperto il file PDF, abiliteremo i suggerimenti sui caratteri utilizzando le opzioni di rendering. Usa il seguente codice:

```csharp
// Crea opzioni di rendering per abilitare i suggerimenti sui caratteri
RenderingOptions opts = new RenderingOptions();
opts. UseFontHinting = true;
```

## Passaggio 3: converti in immagini PNG
Ora convertiremo ogni pagina del PDF in un'immagine PNG con suggerimenti sui caratteri. Usa il seguente codice:

```csharp
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
     using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".png", FileMode.Create))
     {
         // Crea un oggetto PNGDevice con gli attributi specificati
         // Larghezza, Altezza, Risoluzione, Qualità
         // Qualità [0-100], 100 è il massimo
         // Crea un oggetto Risoluzione
         Resolution resolution = new Resolution(300);
         PngDevice pngDevice = new PngDevice(resolution);
         // Imposta le opzioni di rendering predefinite
         pngDevice.RenderingOptions = opts;

         // Converti una pagina specifica e salva l'immagine nello stream
         pngDevice.Process(pdfDocument.Pages[pageCount], imageStream);

         // Chiudi il flusso
         imageStream.Close();
     }
}
```

Il codice sopra converte ogni pagina del PDF in un'immagine PNG con suggerimenti sui caratteri e salva ogni immagine come file PNG separato.

### Esempio di codice sorgente per PDF in PNGFont Suggerimenti utilizzando Aspose.PDF per .NET

```csharp
try
{
	
	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Apri documento
	Document pdfDocument = new Document(dataDir + "input.pdf");
	// Crea Aspose.Pdf.RenderingOptions per abilitare i suggerimenti sui caratteri
	RenderingOptions opts = new RenderingOptions();
	opts.UseFontHinting = true;
	
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
			// Imposta le opzioni di rendering predefinite
			pngDevice.RenderingOptions = opts;

			// Converti una pagina specifica e salva l'immagine per lo streaming
			pngDevice.Process(pdfDocument.Pages[pageCount], imageStream);

			// Chiudi flusso
			imageStream.Close();
		}
	}
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusione
In questo tutorial, abbiamo coperto il processo passo-passo di conversione da PDF a immagini PNG con suggerimenti sui caratteri utilizzando Aspose.PDF per .NET. Seguendo le istruzioni sopra descritte, ora dovresti essere in grado di convertire ogni pagina del PDF in un'immagine PNG con suggerimenti sui caratteri. Questa funzione è utile quando si desidera mantenere la leggibilità dei caratteri piccoli durante la conversione in immagini PNG.