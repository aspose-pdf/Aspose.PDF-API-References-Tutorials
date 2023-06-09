---
title: Segmenti di testo
linktitle: Segmenti di testo
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come cercare segmenti di testo specifici all'interno di un documento PDF utilizzando le espressioni regolari in Aspose.PDF per .NET.
type: docs
weight: 540
url: /it/net/programming-with-text/text-segments/
---

Questo tutorial spiega come cercare segmenti di testo specifici all'interno di un documento PDF utilizzando Aspose.PDF per .NET. Il codice sorgente C# fornito mostra diversi scenari usando espressioni regolari.

## Prerequisiti

Prima di procedere con il tutorial, assicurati di disporre di quanto segue:

- Conoscenza base del linguaggio di programmazione C#.
- Aspose.PDF per la libreria .NET installata. Puoi ottenerlo dal sito Web di Aspose o utilizzare NuGet per installarlo nel tuo progetto.

## Passaggio 1: impostare il progetto

Inizia creando un nuovo progetto C# nel tuo ambiente di sviluppo integrato (IDE) preferito e aggiungi un riferimento alla libreria Aspose.PDF per .NET.

## Passaggio 2: importa gli spazi dei nomi necessari

Aggiungi le seguenti direttive using all'inizio del tuo file C# per importare gli spazi dei nomi richiesti:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Passaggio 3: utilizzare TextFragmentAbsorber per la ricerca di testo

 Creare un`TextFragmentAbsorber`oggetto per cercare segmenti di testo specifici utilizzando espressioni regolari:

```csharp
TextFragmentAbsorber textFragmentAbsorber;
```

## Passaggio 4: eseguire ricerche di testo con espressioni regolari

Esegui ricerche di testo basate su diversi scenari utilizzando espressioni regolari. Ecco alcuni esempi:

- Per cercare una corrispondenza di parola esatta: 

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

- Per trovare il testo dopo una corrispondenza regex: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"(?<=word).*");
```

- Per cercare collegamenti ipertestuali/URL all'interno del documento PDF: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"(http|ftp|https):\/\/([\w\-_]+(?:(?:\.[\w\-_]+)+))([\w\-\.,@?^=%&amp;:/~\+#]*[\w\-\@?^=%&amp;/~\+#])?");
```

Sostituisci le espressioni regolari con i modelli di ricerca desiderati.

## Passaggio 5: eseguire la ricerca ed elaborare i risultati

 Eseguire la ricerca utilizzando il creato`TextFragmentAbsorber` obiettare ed elaborare i risultati in base alle vostre esigenze.

### Esempio di codice sorgente per segmenti di testo utilizzando Aspose.PDF per .NET 
```csharp
TextFragmentAbsorber textFragmentAbsorber;
// Per cercare la corrispondenza esatta di una parola, potresti prendere in considerazione l'utilizzo di un'espressione regolare.
textFragmentAbsorber = new TextFragmentAbsorber(@"\bWord\b", new TextSearchOptions(true));
//Per cercare una stringa in maiuscolo o in minuscolo, puoi prendere in considerazione l'utilizzo di un'espressione regolare.
textFragmentAbsorber = new TextFragmentAbsorber("(?i)Line", new TextSearchOptions(true));
// Per cercare tutte le stringhe (analizzare tutte le stringhe) all'interno del documento PDF, provare a utilizzare la seguente espressione regolare.
textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
// Trova la corrispondenza della stringa di ricerca e ottieni qualsiasi cosa dopo la stringa fino all'interruzione di riga.
textFragmentAbsorber = new TextFragmentAbsorber(@"(?i)the ((.)*)");
// Utilizza la seguente espressione regolare per trovare il testo che segue la corrispondenza dell'espressione regolare.
textFragmentAbsorber = new TextFragmentAbsorber(@"(?<=word).*");
// Per cercare collegamenti ipertestuali/URL all'interno del documento PDF, prova a utilizzare la seguente espressione regolare.
textFragmentAbsorber = new TextFragmentAbsorber(@"(http|ftp|https):\/\/([\w\-_]+(?:(?:\.[\w\-_]+)+))([\w\-\.,@?^=%&amp;:/~\+#]*[\w\-\@?^=%&amp;/~\+#])?");
```


## Conclusione

Congratulazioni! Hai imparato con successo come cercare segmenti di testo specifici all'interno di un documento PDF utilizzando Aspose.PDF per .NET. Questa esercitazione ha fornito esempi di diversi scenari di ricerca utilizzando espressioni regolari. Ora puoi incorporare questo codice nei tuoi progetti C# per cercare ed elaborare segmenti di testo nei file PDF.