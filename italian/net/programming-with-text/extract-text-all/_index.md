---
title: Estrai tutto il testo
linktitle: Estrai tutto il testo
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come estrarre tutto il testo da un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 180
url: /it/net/programming-with-text/extract-text-all/
---

Questo tutorial ti guiderà attraverso il processo di estrazione di tutto il testo da un documento PDF utilizzando Aspose.PDF per .NET. Il codice sorgente C# fornito illustra i passaggi necessari.

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
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
```

## Passaggio 5: estrai tutto il testo
 Creare un`TextAbsorber` oggetto per estrarre il testo dal documento. Quindi, accetta l'assorbitore per tutte le pagine.

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
```

## Passaggio 6: ottieni il testo estratto
 Accedi al testo estratto dal file`TextAbsorber` oggetto.

```csharp
string extractedText = textAbsorber.Text;
```

## Passaggio 7: salva il testo estratto
 Creare un`TextWriter` e apri il file in cui vuoi salvare il testo estratto. Scrivi il testo estratto nel file e chiudi lo stream.

```csharp
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
tw.WriteLine(extractedText);
tw. Close();
```

### Esempio di codice sorgente per Estrai tutto il testo utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
// Crea un oggetto TextAbsorber per estrarre il testo
TextAbsorber textAbsorber = new TextAbsorber();
// Accetta l'assorbitore per tutte le pagine
pdfDocument.Pages.Accept(textAbsorber);
// Ottieni il testo estratto
string extractedText = textAbsorber.Text;
// Crea uno scrittore e apri il file
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
// Scrivi una riga di testo nel file
tw.WriteLine(extractedText);
// Chiudi il flusso
tw.Close();
```

## Conclusione
Hai estratto con successo tutto il testo da un documento PDF utilizzando Aspose.PDF per .NET. Il testo estratto è stato salvato nel file di output specificato.