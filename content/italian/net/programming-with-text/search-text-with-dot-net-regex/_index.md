---
title: Cerca testo con Dot Net Regex
linktitle: Cerca testo con Dot Net Regex
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come cercare testo utilizzando espressioni regolari .NET in un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 480
url: /it/net/programming-with-text/search-text-with-dot-net-regex/
---
Questo tutorial spiega come usare Aspose.PDF per .NET per cercare testo usando espressioni regolari .NET in un documento PDF. Il codice sorgente C# fornito illustra il processo passo dopo passo.

## Prerequisiti

Prima di procedere con il tutorial, assicurati di avere quanto segue:

- Conoscenza di base del linguaggio di programmazione C#.
- Aspose.PDF per la libreria .NET installata. Puoi ottenerla dal sito web di Aspose o usare NuGet per installarla nel tuo progetto.

## Passaggio 1: impostare il progetto

Inizia creando un nuovo progetto C# nel tuo ambiente di sviluppo integrato (IDE) preferito e aggiungi un riferimento alla libreria Aspose.PDF per .NET.

## Passaggio 2: importare gli spazi dei nomi necessari

Aggiungere le seguenti direttive using all'inizio del file C# per importare gli spazi dei nomi richiesti:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Passaggio 3: impostare il percorso della directory del documento

 Imposta il percorso della directory del documento utilizzando`dataDir` variabile:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory del documento.

## Passaggio 4: creare un oggetto .NET Regex

 Crea un`.NET Regex` oggetto per definire il modello di ricerca:

```csharp
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
```

 Sostituire`@"[\S]+"` con il modello di espressione regolare desiderato.

## Passaggio 5: caricare il documento PDF

 Caricare il documento PDF utilizzando`Document` classe:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
```

 Sostituire`"SearchTextRegex.pdf"` con il nome effettivo del file PDF.

## Passaggio 6: Ottieni una pagina specifica

Ottieni la pagina desiderata del documento:

```csharp
Page page = document.Pages[1];
```

 Sostituire`1` con il numero di pagina desiderato (indice a partire da 1).

## Passaggio 7: creare un TextFragmentAbsorber

 Crea un`TextFragmentAbsorber` oggetto per trovare tutte le istanze dell'espressione regolare di input:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(regex);
textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
```

## Fase 8: Accettare l'assorbitore per la pagina

Accetta l'assorbitore per la pagina:

```csharp
page.Accept(textFragmentAbsorber);
```

## Passaggio 9: recuperare i frammenti di testo estratti

 Ottieni i frammenti di testo estratti utilizzando`TextFragments` proprietà del`TextFragmentAbsorber` oggetto:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Passaggio 10: scorrere i frammenti di testo

Scorrere i frammenti di testo recuperati ed eseguire le azioni desiderate:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine(textFragment.Text);
}
```

Se necessario, modificare il codice all'interno del ciclo per eseguire ulteriori azioni su ciascun frammento di testo.

### Esempio di codice sorgente per la ricerca di testo con Dot Net Regex utilizzando Aspose.PDF per .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crea un oggetto Regex per trovare tutte le parole
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
// Apri documento
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
// Ottieni una pagina specifica
Page page = document.Pages[1];
// Crea un oggetto TextAbsorber per trovare tutte le istanze dell'espressione regolare di input
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(regex);
textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
// Accetta l'assorbitore per la pagina
page.Accept(textFragmentAbsorber);
// Ottieni i frammenti di testo estratti
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Fai un giro tra i frammenti
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine(textFragment.Text);
}
```

## Conclusione

Congratulazioni! Hai imparato con successo come cercare testo usando espressioni regolari .NET in un documento PDF usando Aspose.PDF per .NET. Questo tutorial ha fornito una guida passo passo, dall'impostazione del progetto all'accesso ai frammenti di testo estratti. Ora puoi incorporare questo codice nei tuoi progetti C# per eseguire ricerche di testo avanzate nei file PDF.

### Domande frequenti

#### D: Qual è lo scopo del tutorial "Cerca testo con regex dot-net"?

R: Il tutorial "Search Text With Dot Net Regex" mira a guidare gli utenti nell'uso della libreria Aspose.PDF per .NET per cercare testo all'interno di un documento PDF usando espressioni regolari .NET. Il tutorial fornisce istruzioni dettagliate ed esempi di codice C# per dimostrare il processo.

#### D: In che modo questo tutorial aiuta a cercare testo utilizzando espressioni regolari .NET in un PDF?

R: Questo tutorial aiuta gli utenti a capire come sfruttare le capacità di Aspose.PDF per .NET per cercare testo usando espressioni regolari .NET all'interno di un documento PDF. Seguendo i passaggi e gli esempi di codice forniti, gli utenti possono cercare in modo efficace modelli di testo che corrispondono alle loro espressioni regolari specificate.

#### D: Quali prerequisiti sono richiesti per seguire questo tutorial?

R: Prima di iniziare il tutorial, dovresti avere una conoscenza di base del linguaggio di programmazione C#. Inoltre, devi avere installata la libreria Aspose.PDF per .NET. Puoi ottenerla dal sito web di Aspose o installarla nel tuo progetto usando NuGet.

#### D: Come posso impostare il mio progetto in modo che segua questo tutorial?

R: Per iniziare, crea un nuovo progetto C# nel tuo ambiente di sviluppo integrato (IDE) preferito e aggiungi un riferimento alla libreria Aspose.PDF per .NET. Ciò ti consentirà di utilizzare le funzionalità della libreria per cercare e lavorare con documenti PDF.

#### D: Posso usare questo tutorial per cercare qualsiasi tipo specifico di testo utilizzando le espressioni regolari .NET?

 R: Sì, questo tutorial fornisce istruzioni su come cercare testo usando espressioni regolari .NET all'interno di un documento PDF. Puoi personalizzare il`.NET Regex` oggetto per definire lo specifico modello di ricerca che si desidera utilizzare.

#### D: Come faccio a specificare il modello di espressione regolare .NET da ricercare in questo tutorial?

 A: Per specificare il modello di espressione regolare .NET che si desidera cercare, creare un`.NET Regex` oggetto e imposta il suo pattern usando la sintassi appropriata dell'espressione regolare. Sostituisci il valore predefinito`@"[\S]+"` nel codice del tutorial con l'espressione regolare desiderata.

#### D: Come posso recuperare le proprietà dei frammenti di testo estratti?

 A: Dopo aver accettato il`TextFragmentAbsorber` per una pagina specifica del PDF, è possibile recuperare i frammenti di testo estratti utilizzando`TextFragments` proprietà dell'oggetto assorbitore. Ciò fornisce l'accesso a una raccolta di frammenti di testo che corrispondono all'espressione regolare .NET specificata.

#### D: Posso personalizzare il codice per eseguire azioni aggiuntive su ogni frammento di testo estratto?

R: Certamente. Il codice di esempio del tutorial include un ciclo per scorrere i frammenti di testo recuperati. Puoi personalizzare il codice all'interno di questo ciclo per eseguire azioni aggiuntive su ogni frammento di testo estratto in base ai requisiti del tuo progetto.

#### D: Come posso salvare il documento PDF modificato dopo aver estratto i frammenti di testo?

R: Questo tutorial si concentra principalmente sulla ricerca di testo tramite espressioni regolari .NET e sul recupero di frammenti di testo. Se intendi apportare modifiche al PDF, puoi fare riferimento ad altra documentazione di Aspose.PDF per imparare come manipolare e salvare il documento in base alle tue esigenze specifiche.