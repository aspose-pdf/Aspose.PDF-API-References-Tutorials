---
title: Segmenti di testo nel file PDF
linktitle: Segmenti di testo nel file PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come cercare segmenti di testo specifici nel file PDF utilizzando le espressioni regolari in Aspose.PDF per .NET.
type: docs
weight: 540
url: /it/net/programming-with-text/text-segments/
---
Questo tutorial spiega come cercare segmenti di testo specifici nel file PDF utilizzando Aspose.PDF per .NET. Il codice sorgente C# fornito illustra diversi scenari utilizzando le espressioni regolari.

## Prerequisiti

Prima di procedere con il tutorial, assicurati di avere quanto segue:

- Conoscenza base del linguaggio di programmazione C#.
- Aspose.PDF per la libreria .NET installata. Puoi ottenerlo dal sito Web Aspose o utilizzare NuGet per installarlo nel tuo progetto.

## Passaggio 1: impostare il progetto

Inizia creando un nuovo progetto C# nel tuo ambiente di sviluppo integrato (IDE) preferito e aggiungi un riferimento alla libreria Aspose.PDF per .NET.

## Passaggio 2: importa gli spazi dei nomi necessari

Aggiungi le seguenti direttive using all'inizio del file C# per importare gli spazi dei nomi richiesti:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Passaggio 3: utilizzare TextFragmentAbsorber per la ricerca di testo

 Creare un`TextFragmentAbsorber` oggetto per cercare segmenti di testo specifici utilizzando espressioni regolari:

```csharp
TextFragmentAbsorber textFragmentAbsorber;
```

## Passaggio 4: esegui ricerche di testo con espressioni regolari

Esegui ricerche di testo in base a diversi scenari utilizzando le espressioni regolari. Ecco alcuni esempi:

- Per cercare una corrispondenza esatta: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"\bWord\b", new TextSearchOptions(true));
```

- Per cercare una stringa sia in maiuscolo che in minuscolo: 

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

- Per trovare il testo in seguito a una corrispondenza regex: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"(?<=word).*");
```

- Per cercare collegamenti ipertestuali/URL all'interno del documento PDF: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"(http|ftp|https):\/\/([\w\-_]+(?:(?:\.[\w\-_]+)+))([\w\-\.,@?^=%&amp;:/~\+#]*[\w\-\@?^=%&amp;/~\+#])?");
```

Sostituisci le espressioni regolari con i modelli di ricerca desiderati.

## Passaggio 5: eseguire la ricerca ed elaborare i risultati

 Esegui la ricerca utilizzando il file creato`TextFragmentAbsorber` oggetto ed elaborare i risultati in base alle vostre esigenze.

### Codice sorgente di esempio per segmenti di testo utilizzando Aspose.PDF per .NET 
```csharp
TextFragmentAbsorber textFragmentAbsorber;
// Per cercare la corrispondenza esatta di una parola, puoi prendere in considerazione l'utilizzo di un'espressione regolare.
textFragmentAbsorber = new TextFragmentAbsorber(@"\bWord\b", new TextSearchOptions(true));
// Per cercare una stringa sia in maiuscolo che in minuscolo, puoi prendere in considerazione l'utilizzo di un'espressione regolare.
textFragmentAbsorber = new TextFragmentAbsorber("(?i)Line", new TextSearchOptions(true));
//Per cercare tutte le stringhe (analizzare tutte le stringhe) all'interno del documento PDF, prova a utilizzare la seguente espressione regolare.
textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
// Trova la corrispondenza della stringa di ricerca e ottieni qualsiasi cosa dopo la stringa fino all'interruzione di riga.
textFragmentAbsorber = new TextFragmentAbsorber(@"(?i)the ((.)*)");
// Utilizza la seguente espressione regolare per trovare il testo che segue la corrispondenza regex.
textFragmentAbsorber = new TextFragmentAbsorber(@"(?<=word).*");
// Per cercare collegamenti ipertestuali/URL all'interno del documento PDF, prova a utilizzare la seguente espressione regolare.
textFragmentAbsorber = new TextFragmentAbsorber(@"(http|ftp|https):\/\/([\w\-_]+(?:(?:\.[\w\-_]+)+))([\w\-\.,@?^=%&amp;:/~\+#]*[\w\-\@?^=%&amp;/~\+#])?");
```


## Conclusione

Congratulazioni! Hai imparato con successo come cercare segmenti di testo specifici all'interno di un documento PDF utilizzando Aspose.PDF per .NET. Questo tutorial ha fornito esempi di diversi scenari di ricerca utilizzando le espressioni regolari. Ora puoi incorporare questo codice nei tuoi progetti C# per cercare ed elaborare segmenti di testo nei file PDF.

### Domande frequenti

#### D: Qual è lo scopo del tutorial "Segmenti di testo nel file PDF"?

R: Il tutorial "Segmenti di testo nel file PDF" mira a guidare gli utenti su come cercare segmenti di testo specifici all'interno di un file PDF utilizzando Aspose.PDF per .NET. L'esercitazione fornisce istruzioni dettagliate ed esempi di codice C# per eseguire ricerche di testo in base a diversi scenari utilizzando espressioni regolari.

#### D: In che modo questo tutorial aiuta nella ricerca di segmenti di testo in un documento PDF?

R: Questo tutorial aiuta gli utenti a capire come utilizzare la libreria Aspose.PDF per .NET per cercare segmenti di testo specifici all'interno di un documento PDF. Fornendo vari esempi di codice ed espressioni regolari, gli utenti possono personalizzare le query di ricerca testuale per trovare il contenuto desiderato all'interno dei file PDF.

#### D: Quali prerequisiti sono richiesti per seguire questo tutorial?

R: Prima di iniziare il tutorial, dovresti avere una conoscenza di base del linguaggio di programmazione C#. Inoltre, è necessario che sia installata la libreria Aspose.PDF per .NET. È possibile ottenerlo dal sito Web Aspose o installarlo nel progetto utilizzando NuGet.

#### D: Come posso impostare il mio progetto per seguire questo tutorial?

R: Per iniziare, crea un nuovo progetto C# nel tuo ambiente di sviluppo integrato (IDE) preferito e aggiungi un riferimento alla libreria Aspose.PDF per .NET. Ciò ti consentirà di sfruttare le funzionalità della libreria per lavorare con documenti PDF e frammenti di testo.

#### D: Come posso cercare segmenti di testo specifici all'interno di un file PDF?

 R: Per cercare segmenti di testo specifici, è necessario creare un file`TextFragmentAbsorber` oggetto. L'esercitazione fornisce vari esempi di codice utilizzando espressioni regolari per dimostrare diversi scenari di ricerca. Modificando le espressioni regolari, puoi definire i modelli di ricerca desiderati.

#### D: Quali tipi di scenari di ricerca sono trattati nel tutorial?

R: Il tutorial copre una serie di scenari di ricerca utilizzando espressioni regolari, come corrispondenze esatte di parole, ricerche senza distinzione tra maiuscole e minuscole, ricerca di tutte le stringhe all'interno di un documento, ricerca di testo dopo stringhe specifiche e ricerca di collegamenti ipertestuali/URL. Gli esempi di codice forniti possono essere personalizzati per soddisfare i tuoi requisiti di ricerca specifici.

#### D: Come posso elaborare i risultati della ricerca dopo aver eseguito la ricerca testuale?

 R: Dopo aver creato a`TextFragmentAbsorber`oggetto ed eseguendo la ricerca, è possibile elaborare i risultati della ricerca in base alle proprie esigenze. Il tutorial si concentra sulla dimostrazione del processo di ricerca stesso, mentre il modo in cui elabori e utilizzi i risultati della ricerca dipende dalle esigenze del tuo progetto.

#### D: Posso utilizzare gli esempi di codice forniti nei miei progetti?

R: Sì, puoi utilizzare gli esempi di codice forniti come riferimento nei tuoi progetti C#. Gli esempi dimostrano come impostare la ricerca, definire espressioni regolari ed eseguire ricerche di testo. Puoi adattare e integrare questo codice nelle tue applicazioni per cercare segmenti di testo specifici all'interno dei file PDF.

#### D: Dove posso trovare il tutorial completo insieme al codice di esempio?

 R: Puoi accedere al tutorial completo e visualizzare il codice C# di esempio fornito visitando il seguente collegamento:[https://bit.ly/TextSegmentsTutorial](https://bit.ly/TextSegmentsTutorial)