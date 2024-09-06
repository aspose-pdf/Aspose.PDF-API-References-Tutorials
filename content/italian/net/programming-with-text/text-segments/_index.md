---
title: Segmenti di testo nel file PDF
linktitle: Segmenti di testo nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come cercare segmenti di testo specifici in un file PDF utilizzando espressioni regolari in Aspose.PDF per .NET.
type: docs
weight: 540
url: /it/net/programming-with-text/text-segments/
---
Questo tutorial spiega come cercare segmenti di testo specifici in un file PDF usando Aspose.PDF per .NET. Il codice sorgente C# fornito illustra diversi scenari usando espressioni regolari.

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

## Passaggio 3: utilizzare TextFragmentAbsorber per la ricerca di testo

 Crea un`TextFragmentAbsorber` oggetto per cercare segmenti di testo specifici utilizzando espressioni regolari:

```csharp
TextFragmentAbsorber textFragmentAbsorber;
```

## Passaggio 4: eseguire ricerche di testo con espressioni regolari

Esegui ricerche di testo basate su diversi scenari utilizzando espressioni regolari. Ecco alcuni esempi:

- Per cercare una corrispondenza esatta della parola: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"\bWord\b", new TextSearchOptions(true));
```

- Per cercare una stringa in maiuscolo o minuscolo: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber("(?i)Line", new TextSearchOptions(true));
```

- Per cercare tutte le stringhe all'interno del documento PDF: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

- Per trovare il testo dopo una stringa specifica fino a un'interruzione di riga: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"(?i)the ((.)*)");
```

- Per trovare il testo che segue una corrispondenza regex: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"(?<=word).*");
```

- Per cercare collegamenti ipertestuali/URL all'interno del documento PDF: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"(http|ftp|https):\/\/([\w\-_]+(?:(?:\.[\w\-_]+)+))([\w\-\.,@?^=%&amp;:/~\+#]*[\w\-\@?^=%&amp;/~\+#])?");
```

Sostituisci le espressioni regolari con i modelli di ricerca desiderati.

## Fase 5: Eseguire la ricerca ed elaborare i risultati

 Esegui la ricerca utilizzando il file creato`TextFragmentAbsorber` oggetto ed elabora i risultati in base alle tue esigenze.

### Esempio di codice sorgente per segmenti di testo utilizzando Aspose.PDF per .NET 
```csharp
TextFragmentAbsorber textFragmentAbsorber;
// Per cercare la corrispondenza esatta di una parola, puoi prendere in considerazione l'utilizzo di espressioni regolari.
textFragmentAbsorber = new TextFragmentAbsorber(@"\bWord\b", new TextSearchOptions(true));
// Per cercare una stringa sia in maiuscolo che in minuscolo, puoi prendere in considerazione l'utilizzo di un'espressione regolare.
textFragmentAbsorber = new TextFragmentAbsorber("(?i)Line", new TextSearchOptions(true));
//Per cercare tutte le stringhe (analizzare tutte le stringhe) all'interno del documento PDF, provare a utilizzare la seguente espressione regolare.
textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
// Trova la corrispondenza della stringa di ricerca e ricava tutto ciò che segue la stringa fino all'interruzione di riga.
textFragmentAbsorber = new TextFragmentAbsorber(@"(?i)the ((.)*)");
// Utilizzare la seguente espressione regolare per trovare il testo successivo alla corrispondenza regex.
textFragmentAbsorber = new TextFragmentAbsorber(@"(?<=word).*");
// Per cercare collegamenti ipertestuali/URL all'interno di un documento PDF, prova a utilizzare la seguente espressione regolare.
textFragmentAbsorber = new TextFragmentAbsorber(@"(http|ftp|https):\/\/([\w\-_]+(?:(?:\.[\w\-_]+)+))([\w\-\.,@?^=%&amp;:/~\+#]*[\w\-\@?^=%&amp;/~\+#])?");
```


## Conclusione

Congratulazioni! Hai imparato con successo come cercare segmenti di testo specifici all'interno di un documento PDF usando Aspose.PDF per .NET. Questo tutorial ha fornito esempi di diversi scenari di ricerca usando espressioni regolari. Ora puoi incorporare questo codice nei tuoi progetti C# per cercare ed elaborare segmenti di testo nei file PDF.

### Domande frequenti

#### D: Qual è lo scopo del tutorial "Segmenti di testo in file PDF"?

R: Il tutorial "Text Segments In PDF File" mira a guidare gli utenti su come cercare specifici segmenti di testo all'interno di un file PDF utilizzando Aspose.PDF per .NET. Il tutorial fornisce istruzioni dettagliate ed esempi di codice C# per eseguire ricerche di testo basate su diversi scenari utilizzando espressioni regolari.

#### D: In che modo questo tutorial aiuta a cercare segmenti di testo in un documento PDF?

R: Questo tutorial aiuta gli utenti a capire come utilizzare la libreria Aspose.PDF per .NET per cercare segmenti di testo specifici all'interno di un documento PDF. Fornendo vari esempi di codice ed espressioni regolari, gli utenti possono personalizzare le loro query di ricerca di testo per trovare il contenuto desiderato all'interno dei file PDF.

#### D: Quali prerequisiti sono richiesti per seguire questo tutorial?

R: Prima di iniziare il tutorial, dovresti avere una conoscenza di base del linguaggio di programmazione C#. Inoltre, devi avere installata la libreria Aspose.PDF per .NET. Puoi ottenerla dal sito web di Aspose o installarla nel tuo progetto usando NuGet.

#### D: Come posso impostare il mio progetto in modo che segua questo tutorial?

R: Per iniziare, crea un nuovo progetto C# nel tuo ambiente di sviluppo integrato (IDE) preferito e aggiungi un riferimento alla libreria Aspose.PDF per .NET. Ciò ti consentirà di sfruttare la funzionalità della libreria per lavorare con documenti PDF e frammenti di testo.

#### D: Come posso cercare specifici segmenti di testo all'interno di un file PDF?

 A: Per cercare segmenti di testo specifici, è necessario creare un`TextFragmentAbsorber` object. Il tutorial fornisce vari esempi di codice che utilizzano espressioni regolari per dimostrare diversi scenari di ricerca. Modificando le espressioni regolari, puoi definire i tuoi modelli di ricerca desiderati.

#### D: Quali tipi di scenari di ricerca vengono trattati nel tutorial?

R: Il tutorial copre una gamma di scenari di ricerca che utilizzano espressioni regolari, come corrispondenze esatte di parole, ricerche senza distinzione tra maiuscole e minuscole, ricerca di tutte le stringhe all'interno di un documento, ricerca di testo dopo stringhe specifiche e ricerca di collegamenti ipertestuali/URL. Gli esempi di codice forniti possono essere personalizzati per soddisfare i tuoi requisiti di ricerca specifici.

#### D: Come posso elaborare i risultati della ricerca dopo aver eseguito la ricerca di testo?

 A: Dopo aver creato un`TextFragmentAbsorber`oggetto ed eseguendo la ricerca, puoi elaborare i risultati della ricerca in base alle tue esigenze. Il tutorial si concentra sulla dimostrazione del processo di ricerca stesso, mentre il modo in cui elabori e utilizzi i risultati della ricerca dipende dalle esigenze del tuo progetto.

#### D: Posso utilizzare gli esempi di codice forniti nei miei progetti?

R: Sì, puoi usare gli esempi di codice forniti come riferimento nei tuoi progetti C#. Gli esempi mostrano come impostare la ricerca, definire espressioni regolari ed eseguire ricerche di testo. Puoi adattare e integrare questo codice nelle tue applicazioni per cercare segmenti di testo specifici all'interno di file PDF.

#### D: Dove posso trovare il tutorial completo insieme al codice di esempio?

 R: È possibile accedere al tutorial completo e visualizzare il codice C# di esempio fornito visitando il seguente collegamento:[https://bit.ly/TextSegmentsTutorial](https://bit.ly/TextSegmentsTutorial)