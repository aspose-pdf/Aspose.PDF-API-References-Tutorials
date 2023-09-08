---
title: Estrai testo dall'area della pagina nel file PDF
linktitle: Estrai testo dall'area della pagina nel file PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come estrarre il testo da un'area specifica su una pagina nel file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 190
url: /it/net/programming-with-text/extract-text-from-page-region/
---
Questo tutorial ti guiderà attraverso il processo di estrazione del testo da un'area specifica su una pagina in un file PDF utilizzando Aspose.PDF per .NET. Il codice sorgente C# fornito illustra i passaggi necessari.

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
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
```

## Passaggio 5: estrai il testo da un'area della pagina
 Creare un`TextAbsorber` oggetto per estrarre il testo dal documento. Configura il`TextSearchOptions` per limitare la ricerca a un'area specifica della pagina definita da un rettangolo.

```csharp
TextAbsorber absorb = new TextAbsorber();
absorb.TextSearchOptions.LimitToPageBounds = true;
absorb.TextSearchOptions.Rectangle = new Aspose.Pdf.Rectangle(100, 200, 250, 350);
pdfDocument.Pages[1].Accept(absorb);
```

## Passaggio 6: ottieni il testo estratto
 Accedi al testo estratto dal file`TextAbsorber` oggetto.

```csharp
string extractedText = absorb.Text;
```

## Passaggio 7: salva il testo estratto
 Creare un`TextWriter` e apri il file in cui vuoi salvare il testo estratto. Scrivi il testo estratto nel file e chiudi lo stream.

```csharp
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
tw.WriteLine(extractedText);
tw. Close();
```

### Codice sorgente di esempio per Estrai testo dall'area della pagina utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
// Crea un oggetto TextAbsorber per estrarre il testo
TextAbsorber absorber = new TextAbsorber();
absorber.TextSearchOptions.LimitToPageBounds = true;
absorber.TextSearchOptions.Rectangle = new Aspose.Pdf.Rectangle(100, 200, 250, 350);
// Accettare l'assorbitore per la prima pagina
pdfDocument.Pages[1].Accept(absorber);
// Ottieni il testo estratto
string extractedText = absorber.Text;
// Crea uno scrittore e apri il file
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
// Scrivere una riga di testo nel file
tw.WriteLine(extractedText);
// Chiudi il flusso
tw.Close();
```

## Conclusione
Hai estratto con successo il testo da un'area specifica su una pagina di un documento PDF utilizzando Aspose.PDF per .NET. Il testo estratto è stato salvato nel file di output specificato.

### Domande frequenti

#### D: Qual è lo scopo di questo tutorial?

R: Questo tutorial ha lo scopo di guidarti attraverso il processo di estrazione del testo da un'area specifica su una pagina in un file PDF utilizzando Aspose.PDF per .NET. Il codice sorgente C# allegato fornisce istruzioni dettagliate per eseguire questa attività.

#### D: Quali spazi dei nomi devo importare?

R: Nel file di codice in cui intendi estrarre il testo, includi le seguenti direttive using all'inizio del file:

```csharp
using Aspose.Pdf;
using System.IO;
```

#### D: Come posso specificare la directory dei documenti?

 R: Individua la linea`string dataDir = "YOUR DOCUMENT DIRECTORY";` nel codice e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

#### D: Come posso aprire un documento PDF esistente?

 R: Nel passaggio 4, aprirai un documento PDF esistente utilizzando il file`Document` costruttore e fornendo il percorso del file PDF di input.

#### D: Come posso estrarre il testo da un'area specifica della pagina?

 R: Il passaggio 5 prevede la creazione di un file`TextAbsorber`oggetto per estrarre il testo dal documento PDF. Potrai quindi configurare il file`TextSearchOptions` per definire un'area rettangolare specifica sulla pagina utilizzando le coordinate.

#### D: Come posso accedere al testo estratto?

 R: Il passaggio 6 ti guida attraverso l'accesso al testo estratto dal file`TextAbsorber` oggetto.

#### D: Come posso salvare il testo estratto in un file?

 R: Nel passaggio 7 creerai un file`TextWriter`, apri il file in cui desideri salvare il testo estratto, scrivi il testo estratto nel file, quindi chiudi lo stream.

#### D: Qual è il punto chiave di questo tutorial?

R: Seguendo questo tutorial, hai imparato come estrarre il testo da un'area specifica su una pagina di un documento PDF utilizzando Aspose.PDF per .NET. Il testo estratto è stato salvato in un file di output specificato, consentendoti di individuare e analizzare con precisione il contenuto testuale desiderato.