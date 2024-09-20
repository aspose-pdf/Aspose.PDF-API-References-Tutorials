---
title: Cerca e ottieni la pagina di testo nel file PDF
linktitle: Cerca e ottieni la pagina di testo nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come cercare e ottenere testo da una pagina specifica in un file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 430
url: /it/net/programming-with-text/search-and-get-text-page/
---
## Introduzione

Ti è mai capitato di dover cercare un testo specifico all'interno di un documento PDF ed estrarlo per un ulteriore utilizzo? Forse stai creando un'app che elabora documenti e richiede un'estrazione precisa dei dati, o forse hai solo bisogno di analizzare i PDF in modo efficiente. Qualunque sia il tuo caso, sei nel posto giusto! In questo tutorial, ci immergeremo in come cercare e ottenere testo da una pagina in un file PDF utilizzando Aspose.PDF per .NET. Che tu sia un principiante o uno sviluppatore esperto, questa guida ti guiderà attraverso ogni passaggio in modo colloquiale e coinvolgente. Pronto a partire? Cominciamo!

## Prerequisiti

Prima di iniziare a scrivere codice, assicuriamoci di avere tutto ciò di cui hai bisogno:

1.  Aspose.PDF per la libreria .NET: puoi scaricarlo da[Qui](https://releases.aspose.com/pdf/net/) oppure ottieni una versione di prova gratuita dallo stesso link. Per l'acquisto, vai su[Negozio Aspose](https://purchase.aspose.com/buy).
2. .NET Framework: avrai bisogno di un ambiente di sviluppo .NET funzionante, come Visual Studio.
3. Un file PDF: avrai bisogno di un file PDF di esempio in cui possiamo cercare ed estrarre il testo. Per questo tutorial, supponiamo che il file si chiami`SearchAndGetTextPage.pdf`.

## Importa pacchetti

Per prima cosa, dobbiamo importare i namespace necessari per lavorare con Aspose.PDF per .NET. Assicurati che siano inclusi all'inizio del tuo codice.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System
```

Ora che abbiamo trattato i prerequisiti, analizziamo il codice passo dopo passo. Ogni passaggio è stato chiaramente delineato per renderlo facile da seguire.

## Passaggio 1: imposta il percorso della directory dei documenti

Prima di interagire con il tuo PDF, dovrai definire il percorso in cui è archiviato il tuo documento PDF. Questo assicura che il programma possa accedere al file.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

-  dataDir: Questo è il percorso della cartella in cui sono archiviati i file PDF. Sostituisci`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo in cui si trova il PDF.

## Passaggio 2: caricare il documento PDF

Il passo successivo è caricare il documento PDF in memoria in modo da poterci lavorare. Ecco come:

```csharp
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
```

- Documento: questa è la classe Aspose.PDF che carica il file PDF.
- pdfDocument: la variabile in cui viene memorizzato il file PDF dopo essere stato caricato.

## Passaggio 3: creare un oggetto assorbitore di testo

 IL`TextFragmentAbsorber`class consente di cercare testo specifico all'interno del PDF. Creiamo un'istanza di questa classe per trovare tutte le istanze di una data frase di ricerca.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
```

- TextFragmentAbsorber: questa classe è responsabile della ricerca e dell'estrazione del testo dal PDF.
- "Figura": sostituiscilo con il testo che desideri cercare nel PDF.

## Passaggio 4: applicare Text Absorber all'intero PDF

Una volta impostato l'assorbitore di testo, è necessario indicare al programma di cercare in tutte le pagine del PDF.

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

- Accept(): questo metodo applica l'assorbitore di testo al PDF, analizzando ogni pagina alla ricerca del testo specificato.

## Passaggio 5: recuperare e scorrere il testo estratto

Ora che abbiamo scansionato il PDF, è il momento di recuperare i risultati e visualizzarli. Faremo un loop attraverso i frammenti di testo estratti.

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

- TextFragmentCollection: questa raccolta contiene tutte le istanze dei frammenti di testo trovati dall'assorbitore di testo.

## Passaggio 6: scorrere ogni frammento ed estrarre i dati

Ora faremo un ciclo attraverso il`textFragmentCollection` ed estrarre varie proprietà di ciascun segmento di testo, come la sua posizione, i dettagli del carattere e il colore.

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text : {0} ", textSegment.Text);
		Console.WriteLine("Position : {0} ", textSegment.Position);
		Console.WriteLine("XIndent : {0} ", textSegment.Position.XIndent);
		Console.WriteLine("YIndent : {0} ", textSegment.Position.YIndent);
		Console.WriteLine("Font - Name : {0}", textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible : {0} ", textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded : {0} ", textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset : {0} ", textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size : {0} ", textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color : {0} ", textSegment.TextState.ForegroundColor);
	}
}
```

- TextFragment: ogni frammento contiene parti del testo trovato.
- TextSegment: ogni frammento può avere più segmenti, che rappresentano parti diverse del testo.
- TextState: fornisce informazioni dettagliate sul carattere, la dimensione e il colore del testo.

In questo ciclo, stampiamo dettagli come il testo effettivo, la sua posizione (coordinate X e Y), il font, se il font è incorporato nel PDF e il colore di primo piano del testo.

## Conclusione

Ed ecco fatto! Ora hai cercato ed estratto con successo del testo da un file PDF usando Aspose.PDF per .NET. È incredibile quanta flessibilità hai con questa libreria. Che tu debba cercare un testo specifico in un documento di grandi dimensioni, estrarlo o analizzarne le proprietà, Aspose.PDF rende tutto un gioco da ragazzi. Inoltre, con il codice che abbiamo trattato, sei ben equipaggiato per adattarlo alle tue esigenze. 

## Domande frequenti

### Posso cercare più frasi contemporaneamente?  
 Sì, puoi modificare il codice per cercare più frasi creando più`TextFragmentAbsorber` oggetti.

### Come posso estrarre il testo da una pagina specifica?  
 Puoi indirizzare una pagina specifica applicando il`TextFragmentAbsorber` a una singola pagina invece che all'intero documento. Ad esempio:`pdfDocument.Pages[1].Accept(textFragmentAbsorber);`.

### Aspose.PDF per .NET è gratuito?  
 Aspose.PDF è un prodotto commerciale, ma puoi utilizzarlo con un[prova gratuita](https://releases.aspose.com/).

### Posso estrarre immagini dal PDF utilizzando Aspose.PDF?  
 Sì, Aspose.PDF consente di estrarre immagini oltre al testo. Controlla la[documentazione](https://reference.aspose.com/pdf/net/) per maggiori dettagli.

### Cosa succede se ho bisogno di ulteriore aiuto o supporto?  
 Puoi sempre ottenere aiuto dal[Forum di supporto Aspose](https://forum.aspose.com/c/pdf/10).