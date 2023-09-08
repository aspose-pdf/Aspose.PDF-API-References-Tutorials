---
title: Estrai il testo delle colonne nel file PDF
linktitle: Estrai il testo delle colonne nel file PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come estrarre il testo delle colonne nel file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 150
url: /it/net/programming-with-text/extract-columns-text/
---
Questo tutorial ti guiderà attraverso il processo di estrazione del testo delle colonne nel file PDF utilizzando Aspose.PDF per .NET. Il codice sorgente C# fornito illustra i passaggi necessari.

## Requisiti
Prima di iniziare, assicurati di avere quanto segue:

- Visual Studio o qualsiasi altro compilatore C# installato sul tuo computer.
- Aspose.PDF per la libreria .NET. Puoi scaricarlo dal sito Web ufficiale di Aspose o utilizzare un gestore di pacchetti come NuGet per installarlo.

## Passaggio 1: impostare il progetto
1. Crea un nuovo progetto C# nel tuo ambiente di sviluppo preferito.
2. Aggiungere un riferimento alla libreria Aspose.PDF per .NET.

## Passaggio 2: importa gli spazi dei nomi richiesti
Nel file di codice in cui desideri estrarre il testo delle colonne, aggiungi le seguenti direttive using nella parte superiore del file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

## Passaggio 3: imposta la directory dei documenti
 Nel codice, individua la riga che dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso della directory in cui sono archiviati i tuoi documenti.

## Passaggio 4: apri il documento PDF
 Apri un documento PDF esistente utilizzando il file`Document`costruttore e passando il percorso al file PDF di input.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## Passaggio 5: regola la dimensione del carattere
Ridurre la dimensione del carattere dei frammenti di testo di un fattore pari a 0,7 per migliorare la leggibilità e rappresentare meglio il testo in colonne.

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
foreach(TextFragment tf in tfc)
{
     tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
```

## Passaggio 6: estrai il testo dalle colonne
 Salva il documento PDF modificato in un flusso di memoria e ricaricalo come nuovo documento. Quindi, utilizzare il`TextAbsorber` classe per estrarre il testo dalle colonne.

```csharp
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
textAbsorber.Visit(pdfDocument);
```

## Passaggio 7: salva il testo estratto
Salva il testo estratto in un file di testo nel percorso del file di output specificato.

```csharp
dataDir = dataDir + "ExtractColumnsText_out.txt";
File.WriteAllText(dataDir, extractedText);
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

### Codice sorgente di esempio per estrarre colonne di testo utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
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

R: Questo tutorial offre una guida passo passo sull'estrazione di colonne di testo da un file PDF utilizzando Aspose.PDF per .NET. Il codice sorgente C# allegato fornisce una dimostrazione pratica delle procedure richieste.

#### D: Quali spazi dei nomi devo importare?

R: Nel file di codice in cui intendi estrarre colonne di testo, includi le seguenti direttive using all'inizio del file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

#### D: Come posso specificare la directory dei documenti?

 R: Individua la linea`string dataDir = "YOUR DOCUMENT DIRECTORY";` nel codice e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

#### D: Come posso aprire un documento PDF esistente?

 R: Nel passaggio 4, aprirai un documento PDF esistente utilizzando il file`Document` costruttore e fornendo il percorso del file PDF di input.

#### D: Perché la dimensione del carattere viene modificata?

R: Il passaggio 5 prevede la riduzione della dimensione del carattere dei frammenti di testo di un fattore pari a 0,7. Questa regolazione migliora la leggibilità e rappresenta in modo più accurato il testo in colonne.

#### D: Come estraggo il testo dalle colonne?

 R: Il passaggio 6 consiste nel salvare il documento PDF modificato in un flusso di memoria, ricaricarlo come nuovo documento e quindi utilizzare il`TextAbsorber` classe per estrarre il testo dalle colonne.

#### D: Qual è lo scopo del salvataggio del testo estratto?

R: Nel passaggio 7, salverai il testo estratto in un file di testo nel percorso del file di output specificato.

#### D: Perché ridurre la dimensione del carattere prima dell'estrazione?

R: Ridurre la dimensione del carattere aiuta a garantire che il testo estratto sia allineato correttamente all'interno delle colonne, fornendo una rappresentazione più accurata del layout originale.

#### D: Qual è il punto chiave di questo tutorial?

R: Seguendo questo tutorial, hai acquisito le conoscenze e le competenze necessarie per estrarre colonne di testo da un documento PDF utilizzando Aspose.PDF per .NET. Il testo risultante è stato salvato nel file di output specificato.