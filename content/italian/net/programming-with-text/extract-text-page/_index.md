---
title: Estrai la pagina di testo nel file PDF
linktitle: Estrai la pagina di testo nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come estrarre il testo da una pagina specifica di un file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 200
url: /it/net/programming-with-text/extract-text-page/
---
Questo tutorial ti guiderà attraverso il processo di estrazione del testo da una pagina specifica in un file PDF utilizzando Aspose.PDF per .NET. Il codice sorgente C# fornito illustra i passaggi necessari.

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
using System.IO;
```

## Passaggio 3: impostare la directory del documento
 Nel codice, individua la riga che dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso della directory in cui sono archiviati i tuoi documenti.

## Passaggio 4: aprire il documento PDF
 Aprire un documento PDF esistente utilizzando`Document`costruttore e passando il percorso al file PDF di input.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## Passaggio 5: estrai il testo da una pagina specifica
 Crea un`TextAbsorber` oggetto per estrarre il testo dal documento. Accetta l'assorbitore per la pagina desiderata accedendovi tramite`Pages` raccolta di`pdfDocument`.

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages[1].Accept(textAbsorber);
```

## Passaggio 6: Ottieni il testo estratto
 Accedi al testo estratto dal`TextAbsorber` oggetto.

```csharp
string extractedText = textAbsorber.Text;
```

## Passaggio 7: salvare il testo estratto
 Crea un`TextWriter` e apri il file in cui vuoi salvare il testo estratto. Scrivi il testo estratto nel file e chiudi lo stream.

```csharp
dataDir = dataDir + "extracted-text_out.txt";
TextWriter tw = new StreamWriter(dataDir);
tw.WriteLine(extractedText);
tw. Close();
```

### Esempio di codice sorgente per Extract Text Page utilizzando Aspose.PDF per .NET 
```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
// Crea un oggetto TextAbsorber per estrarre il testo
TextAbsorber textAbsorber = new TextAbsorber();
//Accetta l'assorbitore per una pagina particolare
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
Hai estratto con successo il testo da una pagina specifica di un documento PDF utilizzando Aspose.PDF per .NET. Il testo estratto è stato salvato nel file di output specificato.

### Domande frequenti

#### D: Qual è lo scopo di questo tutorial?

A: Questo tutorial ti guida attraverso il processo di estrazione del testo da una pagina specifica in un file PDF utilizzando Aspose.PDF per .NET. Il codice sorgente C# allegato illustra i passaggi richiesti per raggiungere questo obiettivo.

#### D: Quali namespace dovrei importare?

A: Nel file di codice in cui intendi estrarre il testo, includi le seguenti direttive using all'inizio del file:

```csharp
using Aspose.Pdf;
using System.IO;
```

#### D: Come faccio a specificare la directory dei documenti?

 A: Nel codice, trova la riga che dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory del documento.

#### D: Come faccio ad aprire un documento PDF esistente?

 A: Nel passaggio 4, aprirai un documento PDF esistente utilizzando`Document` costruttore e fornendo il percorso al file PDF di input.

#### D: Come faccio a estrarre il testo da una pagina specifica?

 A: Il passaggio 5 prevede la creazione di un`TextAbsorber` oggetto per estrarre il testo dal documento PDF. Accetterai quindi l'assorbitore per la pagina desiderata accedendovi tramite`Pages` raccolta di`pdfDocument`.

#### D: Come posso accedere al testo estratto?

 A: Il passaggio 6 ti guida attraverso l'accesso al testo estratto dal`TextAbsorber` oggetto.

#### D: Come posso salvare il testo estratto in un file?

 A: Nel passaggio 7, creerai un`TextWriter`, apri il file in cui vuoi salvare il testo estratto, scrivi il testo estratto nel file, quindi chiudi il flusso.

#### D: Qual è il messaggio più importante da trarre da questo tutorial?

R: Seguendo questo tutorial, hai imparato come estrarre testo da una pagina specifica di un documento PDF usando Aspose.PDF per .NET. Il testo estratto è stato salvato in un file di output specificato, consentendoti di individuare e analizzare il contenuto di testo da pagine specifiche.