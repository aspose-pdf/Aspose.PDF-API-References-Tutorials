---
title: Ottieni segnalibri
linktitle: Ottieni segnalibri
second_title: Aspose.PDF per riferimento API .NET
description: Segna facilmente i tuoi file PDF con Aspose.PDF per .NET.
type: docs
weight: 70
url: /it/net/programming-with-bookmarks/get-bookmarks/
---

Il recupero dei segnalibri da un documento PDF può essere utile per analizzare la struttura del documento e le informazioni di navigazione. Con Aspose.PDF per .NET, puoi facilmente ottenere i segnalibri seguendo il seguente codice sorgente:

## Passaggio 1: importa le librerie richieste

Prima di iniziare, devi importare le librerie necessarie per il tuo progetto C#. Ecco la direttiva di importazione necessaria:

```csharp
using Aspose.Pdf;
```

## Passaggio 2: imposta il percorso della cartella dei documenti

 In questo passaggio, è necessario specificare il percorso della cartella contenente il file PDF da cui estrarre i segnalibri. Sostituire`"YOUR DOCUMENT DIRECTORY"` nel seguente codice con il percorso effettivo della cartella dei documenti:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 3: apri il documento PDF

Ora andiamo ad aprire il documento PDF da cui vogliamo estrarre i segnalibri utilizzando il seguente codice:

```csharp
Document pdfDocument = new Document(dataDir + "GetBookmarks.pdf");
```

## Passaggio 4: sfoglia i segnalibri

In questo passaggio, itereremo su tutti i segnalibri nel documento utilizzando a`foreach` ciclo continuo. Per ogni segnalibro, mostreremo informazioni come titolo, stile corsivo, stile grassetto e colore. Ecco il codice corrispondente:

```csharp
foreach(OutlineItemCollection outlineItem in pdfDocument.Outlines)
{
     Console.WriteLine(outlineItem.Title);
     Console.WriteLine(outlineItem.Italic);
     Console.WriteLine(outlineItem.Bold);
     Console.WriteLine(outlineItem.Color);
}
```

### Esempio di codice sorgente per Ottieni segnalibri utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "GetBookmarks.pdf");
// Passa in rassegna tutti i segnalibri
foreach (OutlineItemCollection outlineItem in pdfDocument.Outlines)
{
	Console.WriteLine(outlineItem.Title);
	Console.WriteLine(outlineItem.Italic);
	Console.WriteLine(outlineItem.Bold);
	Console.WriteLine(outlineItem.Color);
}
```

## Conclusione

Congratulazioni! Ora hai una guida passo passo per ottenere segnalibri con Aspose.PDF per .NET. È possibile utilizzare questo codice per analizzare i segnalibri ed estrarre le informazioni associate a ciascun segnalibro nei documenti PDF.

Assicurati di controllare la documentazione ufficiale di Aspose.PDF per ulteriori informazioni sulle funzionalità avanzate di manipolazione dei segnalibri.