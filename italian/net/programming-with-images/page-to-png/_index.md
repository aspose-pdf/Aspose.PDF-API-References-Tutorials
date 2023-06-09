---
title: Pagina in PNG
linktitle: Pagina in PNG
second_title: Aspose.PDF per riferimento API .NET
description: Guida passo passo per convertire una pagina in formato PNG utilizzando Aspose.PDF per .NET.
type: docs
weight: 220
url: /it/net/programming-with-images/page-to-png/
---

In questo tutorial, ti illustreremo come convertire una pagina in formato PNG utilizzando Aspose.PDF per .NET. Segui questi passaggi per eseguire facilmente questa operazione.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

- Visual Studio o qualsiasi altro ambiente di sviluppo installato e configurato.
- Conoscenza di base del linguaggio di programmazione C#.
- Libreria Aspose.PDF per .NET installata. Puoi scaricarlo dal sito ufficiale di Aspose.

## Passaggio 1: caricamento del documento PDF

Per iniziare, utilizza il seguente codice per caricare il documento PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Apri il documento
Document pdfDocument = new Document(dataDir + "PageToPNG.pdf");
```

Assicurati di fornire il percorso corretto al tuo documento PDF.

## Passaggio 2: converti la pagina in PNG

Successivamente, convertiremo una pagina specifica del documento PDF in formato PNG. Usa il seguente codice:

```csharp
using (FileStream imageStream = new FileStream(dataDir + "aspose-logo.png", FileMode.Create))
{
// Crea un oggetto Risoluzione
Resolution resolution = new Resolution(300);
// Crea un dispositivo PNG con gli attributi specificati (larghezza, altezza, risoluzione)
PngDevice pngDevice = new PngDevice(resolution);
// Converti una pagina specifica e salva l'immagine nello stream
pngDevice.Process(pdfDocument.Pages[1], imageStream);
// Chiudi il flusso
imageStream.Close();
}
```

Assicurati di fornire il percorso e il nome file desiderati per l'immagine PNG di output.

### Esempio di codice sorgente per Page To PNG utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "PageToPNG.pdf");
using (FileStream imageStream = new FileStream(dataDir + "aspose-logo.png", FileMode.Create))
{
	// Crea oggetto Risoluzione
	Resolution resolution = new Resolution(300);
	// Crea dispositivo PNG con attributi specificati (larghezza, altezza, risoluzione)
	PngDevice pngDevice = new PngDevice(resolution);
	// Converti una pagina specifica e salva l'immagine per lo streaming
	pngDevice.Process(pdfDocument.Pages[1], imageStream);
	// Chiudi flusso
	imageStream.Close();
}
```

## Conclusione

Congratulazioni! Hai convertito con successo una pagina in formato PNG utilizzando Aspose.PDF per .NET. Ora puoi applicare questo metodo ai tuoi progetti per estrarre pagine specifiche da file PDF e salvarle come immagini PNG.