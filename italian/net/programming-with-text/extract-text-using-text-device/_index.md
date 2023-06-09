---
title: Estrai il testo usando il dispositivo di testo
linktitle: Estrai il testo usando il dispositivo di testo
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come estrarre il testo da un documento PDF utilizzando il dispositivo di testo in Aspose.PDF per .NET.
type: docs
weight: 210
url: /it/net/programming-with-text/extract-text-using-text-device/
---

Questo tutorial ti guiderà attraverso il processo di estrazione del testo da un documento PDF utilizzando il dispositivo di testo in Aspose.PDF per .NET. Il codice sorgente C# fornito illustra i passaggi necessari.

## Requisiti
Prima di iniziare, assicurati di disporre di quanto segue:

- Visual Studio o qualsiasi altro compilatore C# installato nel tuo computer.
- Aspose.PDF per la libreria .NET. Puoi scaricarlo dal sito Web ufficiale di Aspose o utilizzare un gestore di pacchetti come NuGet per installarlo.

## Passaggio 1: impostare il progetto
1. Crea un nuovo progetto C# nel tuo ambiente di sviluppo preferito.
2. Aggiungere un riferimento alla libreria Aspose.PDF per .NET.

## Passaggio 2: importa gli spazi dei nomi richiesti
Nel file di codice in cui desideri estrarre il testo, aggiungi le seguenti direttive using nella parte superiore del file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

## Passaggio 3: impostare la directory dei documenti
 Nel codice, individuare la riga che dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso della directory in cui sono archiviati i documenti.

## Passaggio 4: apri il documento PDF
 Apri un documento PDF esistente utilizzando il file`Document` costruttore e passando il percorso al file PDF di input.

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## Passaggio 5: estrarre il testo utilizzando il dispositivo di testo
 Creare un`StringBuilder` oggetto per contenere il testo estratto. Scorri ogni pagina del documento e usa a`TextDevice` per estrarre il testo da ogni pagina.

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

## Passaggio 6: salva il testo estratto
 Specificare il percorso del file di output e salvare il testo estratto in un file di testo utilizzando l'estensione`File.WriteAllText` metodo.

```csharp
dataDir = dataDir + "input_Text_Extracted_out.txt";
File.WriteAllText(dataDir, builder.ToString());
```

### Esempio di codice sorgente per estrarre il testo utilizzando il dispositivo di testo utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document( dataDir + "input.pdf");
System.Text.StringBuilder builder = new System.Text.StringBuilder();
// Stringa per contenere il testo estratto
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
		// Converti una determinata pagina e salva il testo nello stream
		textDevice.Process(pdfPage, textStream);
		// Converti una determinata pagina e salva il testo nello stream
		textDevice.Process(pdfDocument.Pages[1], textStream);
		// Chiudi flusso di memoria
		textStream.Close();
		// Ottieni testo dal flusso di memoria
		extractedText = Encoding.Unicode.GetString(textStream.ToArray());
	}
	builder.Append(extractedText);
}
dataDir = dataDir + "input_Text_Extracted_out.txt";
// Salva il testo estratto in un file di testo
File.WriteAllText(dataDir, builder.ToString());
Console.WriteLine("\nText extracted successfully using text device from page of PDF Document.\nFile saved at " + dataDir);
```

## Conclusione
Hai estratto correttamente il testo da un documento PDF utilizzando il dispositivo di testo in Aspose.PDF per .NET. Il testo estratto è stato salvato nel file di output specificato.