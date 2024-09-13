---
title: Estrarre il testo utilizzando il dispositivo di testo
linktitle: Estrarre il testo utilizzando il dispositivo di testo
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come estrarre il testo da un documento PDF utilizzando il dispositivo di testo in Aspose.PDF per .NET.
type: docs
weight: 210
url: /it/net/programming-with-text/extract-text-using-text-device/
---
Questo tutorial ti guiderà attraverso il processo di estrazione del testo da un documento PDF utilizzando il Text Device in Aspose.PDF per .NET. Il codice sorgente C# fornito illustra i passaggi necessari.

## Requisiti
Prima di iniziare, assicurati di avere quanto segue:

- Visual Studio o qualsiasi altro compilatore C# installato sul computer.
- Aspose.PDF per la libreria .NET. Puoi scaricarlo dal sito web ufficiale di Aspose o usare un gestore di pacchetti come NuGet per installarlo.

## Passaggio 1: impostare il progetto
1. Crea un nuovo progetto C# nel tuo ambiente di sviluppo preferito.
2. Aggiungere un riferimento alla libreria Aspose.PDF per .NET.

## Passaggio 2: importare gli spazi dei nomi richiesti
Nel file di codice in cui vuoi estrarre il testo, aggiungi le seguenti direttive using all'inizio del file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

## Passaggio 3: impostare la directory del documento
 Nel codice, individua la riga che dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso della directory in cui sono archiviati i tuoi documenti.

## Passaggio 4: aprire il documento PDF
 Aprire un documento PDF esistente utilizzando`Document`costruttore e passando il percorso al file PDF di input.

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## Passaggio 5: estrarre il testo utilizzando il dispositivo di testo
 Crea un`StringBuilder` oggetto per contenere il testo estratto. Scorrere ogni pagina del documento e utilizzare un`TextDevice` per estrarre il testo da ogni pagina.

```csharp
StringBuilder builder = new StringBuilder();
string extractedText = "";
foreach(Page pdfPage in pdfDocument.Pages)
{
using (MemoryStream textStream = new MemoryStream())
{
TextDevice textDevice = new TextDevice();
TextExtractionOptions textExtOptions = new TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
textDevice.ExtractionOptions = textExtOptions;
textDevice.Process(pdfPage, textStream);
textStream. Close();
extractedText = Encoding.Unicode.GetString(textStream.ToArray());
}
builder. Append(extractedText);
}
```

## Passaggio 6: salvare il testo estratto
 Specificare il percorso del file di output e salvare il testo estratto in un file di testo utilizzando`File.WriteAllText` metodo.

```csharp
dataDir = dataDir + "input_Text_Extracted_out.txt";
File.WriteAllText(dataDir, builder.ToString());
```

### Esempio di codice sorgente per Estrarre testo utilizzando il dispositivo di testo utilizzando Aspose.PDF per .NET 
```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document( dataDir + "input.pdf");
System.Text.StringBuilder builder = new System.Text.StringBuilder();
//Stringa per contenere il testo estratto
string extractedText = "";
foreach (Page pdfPage in pdfDocument.Pages)
{
	using (MemoryStream textStream = new MemoryStream())
	{
		// Crea dispositivo di testo
		TextDevice textDevice = new TextDevice();
		// Imposta le opzioni di estrazione del testo - imposta la modalità di estrazione del testo (Raw o Pure)
		TextExtractionOptions textExtOptions = new
		TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
		textDevice.ExtractionOptions = textExtOptions;
		// Converti una pagina specifica e salva il testo nel flusso
		textDevice.Process(pdfPage, textStream);
		// Converti una pagina specifica e salva il testo nel flusso
		textDevice.Process(pdfDocument.Pages[1], textStream);
		// Chiudi flusso di memoria
		textStream.Close();
		// Ottieni testo dal flusso di memoria
		extractedText = Encoding.Unicode.GetString(textStream.ToArray());
	}
	builder.Append(extractedText);
}
dataDir = dataDir + "input_Text_Extracted_out.txt";
// Salva il testo estratto nel file di testo
File.WriteAllText(dataDir, builder.ToString());
Console.WriteLine("\nText extracted successfully using text device from page of PDF Document.\nFile saved at " + dataDir);
```

## Conclusione
Hai estratto con successo il testo da un documento PDF utilizzando il Text Device in Aspose.PDF per .NET. Il testo estratto è stato salvato nel file di output specificato.

### Domande frequenti

#### D: Qual è lo scopo di questo tutorial?

A: Questo tutorial fornisce indicazioni su come estrarre testo da un documento PDF utilizzando la funzionalità Text Device in Aspose.PDF per .NET. Il codice sorgente C# allegato illustra i passaggi necessari per raggiungere questo obiettivo.

#### D: Quali namespace dovrei importare?

A: Nel file di codice in cui intendi estrarre il testo, includi le seguenti direttive using all'inizio del file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

#### D: Come faccio a specificare la directory dei documenti?

 A: Nel codice, trova la riga che dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory del documento.

#### D: Come faccio ad aprire un documento PDF esistente?

 A: Nel passaggio 4, aprirai un documento PDF esistente utilizzando`Document` costruttore e fornendo il percorso al file PDF di input.

#### D: Come faccio ad estrarre il testo utilizzando il dispositivo di testo?

 A: Il passaggio 5 prevede la creazione di un`StringBuilder` oggetto per contenere il testo estratto. Quindi scorrerai ogni pagina del documento e utilizzerai un`TextDevice` insieme a`TextExtractionOptions` per estrarre il testo da ogni pagina.

#### D: Come posso salvare il testo estratto in un file?

 A: Nel passaggio 6, specificherai il percorso del file di output e utilizzerai`File.WriteAllText`metodo per salvare il testo estratto in un file di testo.

#### D: Qual è il messaggio più importante da trarre da questo tutorial?

R: Seguendo questo tutorial, hai imparato come sfruttare la funzionalità Text Device in Aspose.PDF per .NET per estrarre testo da un documento PDF. Il testo estratto è stato salvato in un file di output specificato, consentendoti di manipolare e utilizzare il contenuto estratto secondo necessità.