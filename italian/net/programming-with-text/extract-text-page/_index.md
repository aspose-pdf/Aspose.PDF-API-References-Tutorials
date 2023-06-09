---
title: Estrai pagina di testo
linktitle: Estrai pagina di testo
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come estrarre il testo da una pagina specifica di un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 200
url: /it/net/programming-with-text/extract-text-page/
---

Questo tutorial ti guiderà attraverso il processo di estrazione del testo da una pagina specifica di un documento PDF utilizzando Aspose.PDF per .NET. Il codice sorgente C# fornito illustra i passaggi necessari.

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
using System.IO;
```

## Passaggio 3: impostare la directory dei documenti
 Nel codice, individuare la riga che dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso della directory in cui sono archiviati i documenti.

## Passaggio 4: apri il documento PDF
 Apri un documento PDF esistente utilizzando il file`Document` costruttore e passando il percorso al file PDF di input.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## Passaggio 5: estrarre il testo da una pagina specifica
 Creare un`TextAbsorber` oggetto per estrarre il testo dal documento. Accettare l'assorbitore per la pagina desiderata accedendovi tramite il`Pages` raccolta del`pdfDocument`.

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages[1].Accept(textAbsorber);
```

## Passaggio 6: ottieni il testo estratto
 Accedi al testo estratto dal file`TextAbsorber` oggetto.

```csharp
string extractedText = textAbsorber.Text;
```

## Passaggio 7: salva il testo estratto
 Creare un`TextWriter` e apri il file in cui vuoi salvare il testo estratto. Scrivi il testo estratto nel file e chiudi lo stream.

```csharp
dataDir = dataDir + "extracted-text_out.txt";
TextWriter tw = new StreamWriter(dataDir);
tw.WriteLine(extractedText);
tw. Close();
```

### Esempio di codice sorgente per estrarre la pagina di testo utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
// Crea un oggetto TextAbsorber per estrarre il testo
TextAbsorber textAbsorber = new TextAbsorber();
// Accetta l'assorbitore per una pagina particolare
pdfDocument.Pages[1].Accept(textAbsorber);
// Ottieni il testo estratto
string extractedText = textAbsorber.Text;
dataDir = dataDir + "extracted-text_out.txt";
// Crea uno scrittore e apri il file
TextWriter tw = new StreamWriter(dataDir);
// Scrivi una riga di testo nel file
tw.WriteLine(extractedText);
// Chiudi il flusso
tw.Close();
Console.WriteLine("\nText extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

## Conclusione
Hai estratto correttamente il testo da una pagina specifica di un documento PDF utilizzando Aspose.PDF per .NET. Il testo estratto è stato salvato nel file di output specificato.