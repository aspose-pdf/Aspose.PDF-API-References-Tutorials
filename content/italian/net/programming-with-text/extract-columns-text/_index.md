---
title: Estrai testo colonne nel file PDF
linktitle: Estrai testo colonne nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come estrarre il testo delle colonne in un file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 150
url: /it/net/programming-with-text/extract-columns-text/
---
Questo tutorial ti guiderà attraverso il processo di estrazione del testo delle colonne in un file PDF utilizzando Aspose.PDF per .NET. Il codice sorgente C# fornito illustra i passaggi necessari.

## Requisiti
Prima di iniziare, assicurati di avere quanto segue:

- Visual Studio o qualsiasi altro compilatore C# installato sul computer.
- Aspose.PDF per la libreria .NET. Puoi scaricarlo dal sito web ufficiale di Aspose o usare un gestore di pacchetti come NuGet per installarlo.

## Passaggio 1: impostare il progetto
1. Crea un nuovo progetto C# nel tuo ambiente di sviluppo preferito.
2. Aggiungere un riferimento alla libreria Aspose.PDF per .NET.

## Passaggio 2: importare gli spazi dei nomi richiesti
Nel file di codice in cui si desidera estrarre il testo delle colonne, aggiungere le seguenti direttive using all'inizio del file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

## Passaggio 3: impostare la directory del documento
 Nel codice, individua la riga che dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso della directory in cui sono archiviati i tuoi documenti.

## Passaggio 4: aprire il documento PDF
 Aprire un documento PDF esistente utilizzando`Document` costruttore e passando il percorso al file PDF di input.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## Passaggio 5: regola la dimensione del carattere
Ridurre la dimensione del carattere dei frammenti di testo di un fattore 0,7 per migliorarne la leggibilità e rappresentare meglio il testo in colonne.

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
foreach(TextFragment tf in tfc)
{
     tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
```

## Passaggio 6: estrarre il testo dalle colonne
 Salva il documento PDF modificato in un flusso di memoria e ricaricalo come un nuovo documento. Quindi, usa il`TextAbsorber` classe per estrarre il testo dalle colonne.

```csharp
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
textAbsorber.Visit(pdfDocument);
```

## Passaggio 7: salvare il testo estratto
Salva il testo estratto in un file di testo nel percorso del file di output specificato.

```csharp
dataDir = dataDir + "ExtractColumnsText_out.txt";
File.WriteAllText(dataDir, extractedText);
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

### Esempio di codice sorgente per estrarre il testo delle colonne utilizzando Aspose.PDF per .NET 
```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");                
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
foreach (TextFragment tf in tfc)
{
	// È necessario ridurre la dimensione del carattere almeno del 70%
	tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
textAbsorber.Visit(pdfDocument); 
dataDir = dataDir + "ExtractColumnsText_out.txt";
System.IO.File.WriteAllText(dataDir, extractedText);           
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

## Conclusione
Hai estratto con successo il testo delle colonne da un documento PDF utilizzando Aspose.PDF per .NET. Il testo estratto è stato salvato nel file di output specificato.

### Domande frequenti

#### D: Qual è lo scopo di questo tutorial?

A: Questo tutorial offre una guida passo passo sull'estrazione di colonne di testo da un file PDF utilizzando Aspose.PDF per .NET. Il codice sorgente C# allegato fornisce una dimostrazione pratica delle procedure richieste.

#### D: Quali namespace dovrei importare?

A: Nel file di codice in cui intendi estrarre colonne di testo, includi le seguenti direttive using all'inizio del file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

#### D: Come faccio a specificare la directory dei documenti?

 A: Individua la linea`string dataDir = "YOUR DOCUMENT DIRECTORY";` nel codice e sostituisci`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory del documento.

#### D: Come faccio ad aprire un documento PDF esistente?

 A: Nel passaggio 4, aprirai un documento PDF esistente utilizzando`Document` costruttore e fornendo il percorso al file PDF di input.

#### D: Perché la dimensione del carattere è stata modificata?

R: Il passaggio 5 prevede la riduzione della dimensione del carattere dei frammenti di testo di un fattore pari a 0,7. Questa regolazione migliora la leggibilità e rappresenta con maggiore accuratezza il testo in colonne.

#### D: Come faccio a estrarre il testo dalle colonne?

 A: Il passaggio 6 consiste nel salvare il documento PDF modificato in un flusso di memoria, ricaricarlo come nuovo documento e quindi utilizzare il`TextAbsorber` classe per estrarre il testo dalle colonne.

#### D: Qual è lo scopo del salvataggio del testo estratto?

A: Nel passaggio 7, salverai il testo estratto in un file di testo nel percorso del file di output specificato.

#### D: Perché ridurre la dimensione del carattere prima dell'estrazione?

R: Ridurre la dimensione del carattere aiuta a garantire che il testo estratto si allinei correttamente all'interno delle colonne, fornendo una rappresentazione più accurata del layout originale.

#### D: Qual è il messaggio più importante da trarre da questo tutorial?

A: Seguendo questo tutorial, hai acquisito le conoscenze e le competenze necessarie per estrarre colonne di testo da un documento PDF utilizzando Aspose.PDF per .NET. Il testo risultante è stato salvato nel file di output specificato.