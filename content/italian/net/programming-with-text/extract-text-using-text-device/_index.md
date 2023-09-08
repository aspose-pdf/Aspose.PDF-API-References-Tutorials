---
title: Estrai testo utilizzando il dispositivo di testo
linktitle: Estrai testo utilizzando il dispositivo di testo
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come estrarre testo da un documento PDF utilizzando il dispositivo di testo in Aspose.PDF per .NET.
type: docs
weight: 210
url: /it/net/programming-with-text/extract-text-using-text-device/
---
Questo tutorial ti guiderà attraverso il processo di estrazione del testo da un documento PDF utilizzando il dispositivo di testo in Aspose.PDF per .NET. Il codice sorgente C# fornito illustra i passaggi necessari.

## Requisiti
Prima di iniziare, assicurati di avere quanto segue:

- Visual Studio o qualsiasi altro compilatore C# installato sul tuo computer.
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

## Passaggio 3: imposta la directory dei documenti
 Nel codice, individua la riga che dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso della directory in cui sono archiviati i tuoi documenti.

## Passaggio 4: apri il documento PDF
 Apri un documento PDF esistente utilizzando il file`Document`costruttore e passando il percorso al file PDF di input.

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## Passaggio 5: estrai il testo utilizzando il dispositivo di testo
 Creare un`StringBuilder` oggetto per contenere il testo estratto. Scorrere ogni pagina del documento e utilizzare a`TextDevice` per estrarre il testo da ogni pagina.

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
 Specificare il percorso del file di output e salvare il testo estratto in un file di testo utilizzando il file`File.WriteAllText` metodo.

```csharp
dataDir = dataDir + "input_Text_Extracted_out.txt";
File.WriteAllText(dataDir, builder.ToString());
```

### Codice sorgente di esempio per estrarre testo utilizzando il dispositivo di testo utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
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
		// Imposta le opzioni di estrazione del testo: imposta la modalità di estrazione del testo (Raw o Puro)
		TextExtractionOptions textExtOptions = new
		TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
		textDevice.ExtractionOptions = textExtOptions;
		// Converti una pagina particolare e salva il testo nello stream
		textDevice.Process(pdfPage, textStream);
		// Converti una pagina particolare e salva il testo nello stream
		textDevice.Process(pdfDocument.Pages[1], textStream);
		// Chiudi il flusso di memoria
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
Hai estratto con successo il testo da un documento PDF utilizzando il dispositivo di testo in Aspose.PDF per .NET. Il testo estratto è stato salvato nel file di output specificato.

### Domande frequenti

#### D: Qual è lo scopo di questo tutorial?

R: Questo tutorial fornisce indicazioni sull'estrazione del testo da un documento PDF utilizzando la funzionalità Dispositivo di testo in Aspose.PDF per .NET. Il codice sorgente C# allegato illustra i passaggi necessari per eseguire questa attività.

#### D: Quali spazi dei nomi devo importare?

R: Nel file di codice in cui prevedi di estrarre il testo, includi le seguenti direttive using all'inizio del file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

#### D: Come posso specificare la directory dei documenti?

 A: Nel codice, trova la riga che dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

#### D: Come posso aprire un documento PDF esistente?

 R: Nel passaggio 4, aprirai un documento PDF esistente utilizzando il file`Document` costruttore e fornendo il percorso del file PDF di input.

#### D: Come posso estrarre il testo utilizzando il dispositivo di testo?

 R: Il passaggio 5 prevede la creazione di un file`StringBuilder` oggetto per contenere il testo estratto. Potrai quindi scorrere ogni pagina del documento e utilizzare a`TextDevice` insieme a`TextExtractionOptions` per estrarre il testo da ogni pagina.

#### D: Come posso salvare il testo estratto in un file?

 R: Nel passaggio 6, specificherai il percorso del file di output e utilizzerai il file`File.WriteAllText`metodo per salvare il testo estratto in un file di testo.

#### D: Qual è il punto chiave di questo tutorial?

R: Seguendo questo tutorial, hai imparato come sfruttare la funzionalità Dispositivo di testo in Aspose.PDF per .NET per estrarre testo da un documento PDF. Il testo estratto è stato salvato in un file di output specificato, consentendoti di manipolare e utilizzare il contenuto estratto secondo necessità.