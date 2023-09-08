---
title: Estrai la pagina di testo nel file PDF
linktitle: Estrai la pagina di testo nel file PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come estrarre il testo da una pagina specifica nel file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 200
url: /it/net/programming-with-text/extract-text-page/
---
Questo tutorial ti guiderà attraverso il processo di estrazione del testo da una pagina specifica nel file PDF utilizzando Aspose.PDF per .NET. Il codice sorgente C# fornito illustra i passaggi necessari.

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
using System.IO;
```

## Passaggio 3: imposta la directory dei documenti
 Nel codice, individua la riga che dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso della directory in cui sono archiviati i tuoi documenti.

## Passaggio 4: apri il documento PDF
 Apri un documento PDF esistente utilizzando il file`Document`costruttore e passando il percorso al file PDF di input.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## Passaggio 5: estrai il testo da una pagina specifica
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

### Codice sorgente di esempio per la pagina di estrazione del testo utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
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
// Scrivere una riga di testo nel file
tw.WriteLine(extractedText);
// Chiudi il flusso
tw.Close();
Console.WriteLine("\nText extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

## Conclusione
Hai estratto con successo il testo da una pagina specifica di un documento PDF utilizzando Aspose.PDF per .NET. Il testo estratto è stato salvato nel file di output specificato.

### Domande frequenti

#### D: Qual è lo scopo di questo tutorial?

R: Questo tutorial ti guida attraverso il processo di estrazione del testo da una pagina specifica in un file PDF utilizzando Aspose.PDF per .NET. Il codice sorgente C# allegato illustra i passaggi necessari per eseguire questa attività.

#### D: Quali spazi dei nomi devo importare?

R: Nel file di codice in cui prevedi di estrarre il testo, includi le seguenti direttive using all'inizio del file:

```csharp
using Aspose.Pdf;
using System.IO;
```

#### D: Come posso specificare la directory dei documenti?

 A: Nel codice, trova la riga che dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

#### D: Come posso aprire un documento PDF esistente?

 R: Nel passaggio 4, aprirai un documento PDF esistente utilizzando il file`Document` costruttore e fornendo il percorso del file PDF di input.

#### D: Come posso estrarre il testo da una pagina specifica?

 R: Il passaggio 5 prevede la creazione di un file`TextAbsorber` oggetto per estrarre il testo dal documento PDF. Accetterai quindi l'assorbitore per la pagina desiderata accedendovi tramite il`Pages` raccolta del`pdfDocument`.

#### D: Come posso accedere al testo estratto?

 R: Il passaggio 6 ti guida attraverso l'accesso al testo estratto dal file`TextAbsorber` oggetto.

#### D: Come posso salvare il testo estratto in un file?

 R: Nel passaggio 7 creerai un file`TextWriter`, apri il file in cui desideri salvare il testo estratto, scrivi il testo estratto nel file, quindi chiudi lo stream.

#### D: Qual è il punto chiave di questo tutorial?

R: Seguendo questo tutorial, hai imparato come estrarre testo da una pagina specifica di un documento PDF utilizzando Aspose.PDF per .NET. Il testo estratto è stato salvato in un file di output specificato, consentendoti di individuare e analizzare il contenuto di testo da pagine specifiche.