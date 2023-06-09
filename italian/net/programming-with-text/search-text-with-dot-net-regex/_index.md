---
title: Cerca testo con Dot Net Regex
linktitle: Cerca testo con Dot Net Regex
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come cercare testo utilizzando le espressioni regolari .NET in un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 480
url: /it/net/programming-with-text/search-text-with-dot-net-regex/
---

Questo tutorial spiega come utilizzare Aspose.PDF per .NET per cercare testo utilizzando espressioni regolari .NET in un documento PDF. Il codice sorgente C# fornito illustra il processo passo dopo passo.

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

## Passaggio 3: impostare il percorso della directory dei documenti

 Imposta il percorso della directory dei documenti utilizzando il file`dataDir` variabile:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

## Passaggio 4: creare un oggetto Regex .NET

 Creare un`.NET Regex` oggetto per definire il modello di ricerca:

```csharp
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
```

 Sostituire`@"[\S]+"` con il modello di espressione regolare desiderato.

## Passaggio 5: caricare il documento PDF

 Carica il documento PDF utilizzando il file`Document` classe:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
```

 Sostituire`"SearchTextRegex.pdf"` con il nome effettivo del file PDF.

## Passaggio 6: ottieni una pagina specifica

Ottieni la pagina desiderata del documento:

```csharp
Page page = document.Pages[1];
```

 Sostituire`1` con il numero di pagina desiderato (indice a base 1).

## Passaggio 7: creare un TextFragmentAbsorber

 Creare un`TextFragmentAbsorber`oggetto per trovare tutte le istanze dell'espressione regolare di input:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(regex);
textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
```

## Passaggio 8: accettare l'assorbitore per la pagina

Accetta l'assorbitore per la pagina:

```csharp
page.Accept(textFragmentAbsorber);
```

## Passaggio 9: recupera i frammenti di testo estratti

 Ottieni i frammenti di testo estratti utilizzando il file`TextFragments` proprietà del`TextFragmentAbsorber` oggetto:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Passaggio 10: scorrere i frammenti di testo

Passa in rassegna i frammenti di testo recuperati ed esegui le azioni desiderate:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine(textFragment.Text);
}
```

Modifica il codice all'interno del ciclo per eseguire ulteriori azioni su ciascun frammento di testo, se necessario.

### Esempio di codice sorgente per Cerca testo con Regex Dot Net utilizzando Aspose.PDF per .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crea un oggetto Regex per trovare tutte le parole
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
// Apri documento
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
// Ottieni una pagina particolare
Page page = document.Pages[1];
// Crea un oggetto TextAbsorber per trovare tutte le istanze della regex di input
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(regex);
textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
// Accetta l'assorbitore per la pagina
page.Accept(textFragmentAbsorber);
// Ottieni i frammenti di testo estratti
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Passa attraverso i frammenti
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine(textFragment.Text);
}
```

## Conclusione

Congratulazioni! Hai imparato con successo come cercare il testo usando le espressioni regolari .NET in un documento PDF usando Aspose.PDF per .NET. Questo tutorial ha fornito una guida dettagliata, dall'impostazione del progetto all'accesso ai frammenti di testo estratti. Ora puoi incorporare questo codice nei tuoi progetti C# per eseguire ricerche di testo avanzate nei file PDF.