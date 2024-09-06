---
title: Estrai testo dall'area della pagina nel file PDF
linktitle: Estrai testo dall'area della pagina nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come estrarre il testo da un'area specifica di una pagina in un file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 190
url: /it/net/programming-with-text/extract-text-from-page-region/
---
Questo tutorial ti guiderà attraverso il processo di estrazione del testo da una regione specifica su una pagina in un file PDF utilizzando Aspose.PDF per .NET. Il codice sorgente C# fornito dimostra i passaggi necessari.

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
 Aprire un documento PDF esistente utilizzando`Document` costruttore e passando il percorso al file PDF di input.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
```

## Passaggio 5: estrarre il testo da un'area della pagina
 Crea un`TextAbsorber` oggetto per estrarre il testo dal documento. Configurare il`TextSearchOptions` per limitare la ricerca a una specifica area della pagina definita da un rettangolo.

```csharp
TextAbsorber absorb = new TextAbsorber();
absorb.TextSearchOptions.LimitToPageBounds = true;
absorb.TextSearchOptions.Rectangle = new Aspose.Pdf.Rectangle(100, 200, 250, 350);
pdfDocument.Pages[1].Accept(absorb);
```

## Passaggio 6: Ottieni il testo estratto
 Accedi al testo estratto dal`TextAbsorber` oggetto.

```csharp
string extractedText = absorb.Text;
```

## Passaggio 7: salvare il testo estratto
 Crea un`TextWriter` e apri il file in cui vuoi salvare il testo estratto. Scrivi il testo estratto nel file e chiudi lo stream.

```csharp
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
tw.WriteLine(extractedText);
tw. Close();
```

### Esempio di codice sorgente per estrarre il testo dall'area della pagina utilizzando Aspose.PDF per .NET 
```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
// Crea un oggetto TextAbsorber per estrarre il testo
TextAbsorber absorber = new TextAbsorber();
absorber.TextSearchOptions.LimitToPageBounds = true;
absorber.TextSearchOptions.Rectangle = new Aspose.Pdf.Rectangle(100, 200, 250, 350);
// Accetta l'assorbitore per la prima pagina
pdfDocument.Pages[1].Accept(absorber);
// Ottieni il testo estratto
string extractedText = absorber.Text;
// Crea uno scrittore e apri il file
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
// Scrivi una riga di testo nel file
tw.WriteLine(extractedText);
// Chiudi il flusso
tw.Close();
```

## Conclusione
Hai estratto con successo del testo da una regione specifica su una pagina di un documento PDF usando Aspose.PDF per .NET. Il testo estratto è stato salvato nel file di output specificato.

### Domande frequenti

#### D: Qual è lo scopo di questo tutorial?

R: Questo tutorial ha lo scopo di guidarti attraverso il processo di estrazione di testo da una regione specifica su una pagina in un file PDF utilizzando Aspose.PDF per .NET. Il codice sorgente C# allegato fornisce istruzioni dettagliate per portare a termine questa attività.

#### D: Quali namespace dovrei importare?

A: Nel file di codice da cui intendi estrarre il testo, includi le seguenti direttive using all'inizio del file:

```csharp
using Aspose.Pdf;
using System.IO;
```

#### D: Come faccio a specificare la directory dei documenti?

 A: Individua la linea`string dataDir = "YOUR DOCUMENT DIRECTORY";` nel codice e sostituisci`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory del documento.

#### D: Come faccio ad aprire un documento PDF esistente?

 A: Nel passaggio 4, aprirai un documento PDF esistente utilizzando`Document` costruttore e fornendo il percorso al file PDF di input.

#### D: Come faccio a estrarre il testo da un'area specifica della pagina?

 A: Il passaggio 5 prevede la creazione di un`TextAbsorber`oggetto per estrarre il testo dal documento PDF. Quindi configurerai il`TextSearchOptions` per definire una specifica area rettangolare sulla pagina utilizzando le coordinate.

#### D: Come posso accedere al testo estratto?

 A: Il passaggio 6 ti guida attraverso l'accesso al testo estratto dal`TextAbsorber` oggetto.

#### D: Come posso salvare il testo estratto in un file?

 A: Nel passaggio 7, creerai un`TextWriter`, apri il file in cui vuoi salvare il testo estratto, scrivi il testo estratto nel file, quindi chiudi il flusso.

#### D: Qual è il messaggio più importante da trarre da questo tutorial?

R: Seguendo questo tutorial, hai imparato come estrarre testo da una regione specifica su una pagina di un documento PDF usando Aspose.PDF per .NET. Il testo estratto è stato salvato in un file di output specificato, consentendoti di indirizzare e analizzare con precisione il contenuto testuale desiderato.