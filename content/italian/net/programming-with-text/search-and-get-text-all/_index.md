---
title: Cerca e ottieni tutto il testo
linktitle: Cerca e ottieni tutto il testo
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come cercare e ottenere testo da tutte le pagine di un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 420
url: /it/net/programming-with-text/search-and-get-text-all/
---
## Introduzione

Hai mai avuto bisogno di estrarre del testo specifico da un PDF ma l'hai trovato complicato? A volte i PDF possono sembrare contenitori bloccati, rendendo difficile ottenere le informazioni di cui hai bisogno. Ma ecco la buona notizia: con Aspose.PDF per .NET, puoi facilmente cercare e recuperare del testo da qualsiasi PDF. Questa potente libreria fornisce tutto ciò di cui hai bisogno per lavorare con i PDF nelle tue applicazioni .NET, rendendo l'estrazione del testo un gioco da ragazzi. In questo tutorial, ti guideremo attraverso il processo di ricerca ed estrazione del testo da un file PDF utilizzando Aspose.PDF per .NET. Che tu stia creando uno strumento di analisi del testo o che tu abbia semplicemente bisogno di automatizzare l'estrazione dei dati dai report PDF, sei nel posto giusto!

## Prerequisiti

Prima di passare al codice, assicuriamoci di aver impostato tutto:

1. Aspose.PDF per .NET: dovrai scaricare e installare Aspose.PDF per .NET. Puoi ottenerlo dalla pagina di download[Qui](https://releases.aspose.com/pdf/net/).
2. Ambiente .NET: assicurati di aver installato .NET Framework o .NET Core sul tuo computer di sviluppo.
3. Conoscenza di base di C##: si consiglia una certa familiarità con C# e con l'utilizzo di progetti .NET.
4.  Documento PDF: un file PDF di esempio da cui estrarremo il testo. In questo esempio, useremo`SearchAndGetTextFromAll.pdf`.

## Importa pacchetti

Prima di scrivere qualsiasi codice, è necessario importare gli spazi dei nomi necessari nel progetto per poter lavorare con Aspose.PDF.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

Questi namespace forniscono l'accesso al modello di oggetti del documento del PDF e consentono di manipolare il testo all'interno del file.

Scomponiamo il procedimento in semplici passaggi, così potrai seguirli con facilità.

## Passaggio 1: impostare la directory dei documenti

Per prima cosa, devi specificare il percorso della directory in cui si trova il tuo PDF. Questo aiuta l'applicazione a individuare il file da cui estrarrai il testo.

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

-  IL`dataDir` la variabile dovrebbe puntare alla directory in cui si trova il tuo`SearchAndGetTextFromAll.pdf` il file è archiviato.
-  Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della tua macchina.

## Passaggio 2: aprire il documento PDF

Successivamente, apriremo il documento PDF utilizzando Aspose.PDF`Document` oggetto.

```csharp
// Apri documento
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

-  Creiamo una nuova istanza di`Document` classe passando il percorso completo del file PDF.
- Questo caricherà il PDF nella memoria, rendendolo pronto per l'elaborazione.

## Passaggio 3: creare un assorbitore di testo

 IL`TextFragmentAbsorber` object viene utilizzato per cercare testo specifico all'interno del PDF. In questo caso, cercheremo la parola "text".

```csharp
// Crea un oggetto TextAbsorber per trovare tutte le istanze della frase di ricerca di input
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

-  IL`TextFragmentAbsorber` viene inizializzato con la stringa`"text"`Ciò significa che cercherà tutte le occorrenze della parola "testo" all'interno del documento PDF.

## Passaggio 4: accettare l'assorbitore per tutte le pagine

Ora, daremo istruzioni al documento PDF di accettare l'assorbitore e di cercare il testo in tutte le sue pagine.

```csharp
// Accetta l'assorbitore per tutte le pagine
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

-  IL`Accept` metodo viene applicato alle pagine del documento. Questo cercherà il testo specificato in tutte le pagine.

## Passaggio 5: estrai frammenti di testo

Una volta che l'assorbitore ha scansionato il documento, possiamo recuperare i frammenti di testo estratti.

```csharp
// Ottieni i frammenti di testo estratti
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

-  IL`TextFragments` proprietà del`TextFragmentAbsorber` restituisce una raccolta di tutti i frammenti di testo che corrispondono al termine di ricerca.

## Passaggio 6: scorrere i frammenti di testo

Ora che abbiamo la raccolta di frammenti di testo, li analizzeremo in modo sequenziale ed estrarremo i dettagli.

```csharp
// Fai un giro tra i frammenti
foreach (TextFragment textFragment in textFragmentCollection)
{
    Console.WriteLine("Text : {0} ", textFragment.Text);
    Console.WriteLine("Position : {0} ", textFragment.Position);
    Console.WriteLine("XIndent : {0} ", textFragment.Position.XIndent);
    Console.WriteLine("YIndent : {0} ", textFragment.Position.YIndent);
    Console.WriteLine("Font - Name : {0}", textFragment.TextState.Font.FontName);
    Console.WriteLine("Font - IsAccessible : {0} ", textFragment.TextState.Font.IsAccessible);
    Console.WriteLine("Font - IsEmbedded : {0} ", textFragment.TextState.Font.IsEmbedded);
    Console.WriteLine("Font - IsSubset : {0} ", textFragment.TextState.Font.IsSubset);
    Console.WriteLine("Font Size : {0} ", textFragment.TextState.FontSize);
    Console.WriteLine("Foreground Color : {0} ", textFragment.TextState.ForegroundColor);
}
```

-  IL`foreach` il ciclo scorre attraverso ogni`TextFragment` nella collezione.
- Stampiamo varie proprietà di ogni frammento, come il testo effettivo, la sua posizione sulla pagina, i dettagli del carattere e la dimensione del carattere.
-  IL`XIndent` E`YIndent` Le proprietà forniscono le coordinate esatte del frammento di testo all'interno del PDF.

## Conclusione

Ed ecco fatto! Con solo poche righe di codice, abbiamo cercato ed estratto con successo del testo da un PDF usando Aspose.PDF per .NET. La flessibilità di Aspose.PDF consente di manipolare i PDF in numerosi modi, rendendolo un'eccellente scelta per gli sviluppatori che necessitano di soluzioni PDF robuste in ambienti .NET. È possibile estendere facilmente questo esempio per cercare altre parole, estrarre più dettagli o persino manipolare il contenuto del PDF in base alle proprie esigenze. Speriamo che questa guida abbia fornito un approccio chiaro e diretto al lavoro con i PDF. Vai avanti e provalo con i tuoi PDF!

## Domande frequenti

### Posso cercare più parole contemporaneamente?  
 Sì, puoi modificare il`TextFragmentAbsorber` per cercare più frasi modificando di conseguenza la stringa di ricerca.

### Cosa succede se il testo si estende su più righe?  
Aspose.PDF riconoscerà ed estrarrà comunque il testo anche se si estende su più righe. Puoi gestire questi frammenti singolarmente.

### Come posso salvare il testo estratto in un file?  
 È possibile scrivere il testo estratto in un file utilizzando le operazioni I/O standard dei file C#, come ad esempio`StreamWriter`.

### Aspose.PDF supporta l'estrazione di testo da PDF scansionati?  
Aspose.PDF non supporta l'OCR. Per i PDF scansionati, avresti bisogno di uno strumento OCR per riconoscere il testo.

### Come gestire i PDF crittografati?  
Se il PDF è protetto da password, è possibile sbloccarlo utilizzando Aspose.PDF, specificando la password al momento del caricamento del documento.