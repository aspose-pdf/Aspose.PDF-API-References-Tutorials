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

			//Converti una pagina specifica e salva l'immagine per lo streaming
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

### FAQ

#### D: Che cos'è il suggerimento sui caratteri e perché è importante quando si converte un PDF in PNG?

R: Il suggerimento sui caratteri è una tecnica utilizzata per migliorare la leggibilità dei caratteri piccoli regolandone la forma e il posizionamento. Durante la conversione da PDF a immagini PNG, l'abilitazione dei suggerimenti sui caratteri garantisce che il testo nelle immagini PNG risultanti rimanga leggibile e chiaro, soprattutto per i caratteri di piccole dimensioni. Questo è importante per mantenere la qualità e la leggibilità del testo durante la conversione di documenti PDF in immagini.

#### D: In che modo i suggerimenti sui caratteri influiscono sul processo di conversione PNG?

R: I suggerimenti sui caratteri influiscono sul modo in cui il testo viene visualizzato nelle immagini PNG risultanti durante il processo di conversione da PDF a PNG. Abilitando i suggerimenti sui caratteri, la libreria Aspose.PDF regola il rendering dei caratteri per garantire che i caratteri piccoli mantengano la loro chiarezza e leggibilità, rendendo le immagini PNG visivamente più accattivanti e leggibili.

#### D: Posso modificare le impostazioni dei suggerimenti sui caratteri per personalizzare la conversione PNG?

 R: Sì, la libreria Aspose.PDF per .NET fornisce opzioni per personalizzare il processo di conversione PNG, comprese le impostazioni di suggerimento sui caratteri. Nell'esempio di codice fornito, il`UseFontHinting` proprietà del`RenderingOptions` l'oggetto è impostato`true` per abilitare i suggerimenti sui caratteri. È possibile perfezionare ulteriormente il processo di conversione regolando altre proprietà nel file`RenderingOptions` classe in base alle vostre esigenze.

#### D: Come vengono salvate le immagini PNG nel processo di conversione PNG?

R: Nell'esempio di codice fornito, ogni pagina del documento PDF viene convertita in un'immagine PNG separata. Le immagini PNG vengono salvate come singoli file con nomi di file che seguono il modello "image{pageCount}_ fuori.png", dove`{pageCount}` è il numero della pagina da convertire. Ogni immagine PNG rappresenta una pagina del documento PDF originale.