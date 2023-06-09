---
title: Ottieni segnalibri per bambini
linktitle: Ottieni segnalibri per bambini
second_title: Aspose.PDF per riferimento API .NET
description: Ottieni facilmente segnalibri figlio dei tuoi file PDF con Aspose.PDF per .NET.
type: docs
weight: 80
url: /it/net/programming-with-bookmarks/get-child-bookmarks/
---

Il recupero di segnalibri secondari da un documento PDF può essere utile per esplorare la struttura gerarchica dei segnalibri. Con Aspose.PDF per .NET, puoi facilmente ottenere i segnalibri figlio seguendo il seguente codice sorgente:

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
Document pdfDocument = new Document(dataDir + "GetChildBookmarks.pdf");
```

## Passaggio 4: sfoglia i segnalibri e i segnalibri secondari

In questo passaggio, itereremo su tutti i segnalibri nel documento utilizzando a`foreach`ciclo continuo. Per ogni segnalibro, mostreremo informazioni come titolo, stile corsivo, stile grassetto e colore. Se il segnalibro ha segnalibri secondari, verranno visualizzati anche quelli. Ecco il codice corrispondente:

```csharp
foreach(OutlineItemCollection outlineItem in pdfDocument.Outlines)
{
     Console.WriteLine(outlineItem.Title);
     Console.WriteLine(outlineItem.Italic);
     Console.WriteLine(outlineItem.Bold);
     Console.WriteLine(outlineItem.Color);
    
     if (outlineItem.Count > 0)
     {
         Console.WriteLine("Child bookmarks");
        
         // Sfoglia anche i segnalibri per bambini
         foreach(OutlineItemCollection childOutline in outlineItem)
         {
             Console.WriteLine(childOutline.Title);
             Console.WriteLine(childOutline.Italic);
             Console.WriteLine(childOutline.Bold);
             Console.WriteLine(childOutline.Color);
         }
     }
}
```

### Esempio di codice sorgente per Ottieni segnalibri secondari utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "GetChildBookmarks.pdf");
// Passa in rassegna tutti i segnalibri
foreach (OutlineItemCollection outlineItem in pdfDocument.Outlines)
{
	Console.WriteLine(outlineItem.Title);
	Console.WriteLine(outlineItem.Italic);
	Console.WriteLine(outlineItem.Bold);
	Console.WriteLine(outlineItem.Color);
	if (outlineItem.Count > 0)
	{
		Console.WriteLine("Child Bookmarks");
		// Ci sono segnalibri per bambini che poi passano in rassegna anche quello
		foreach (OutlineItemCollection childOutline in outlineItem)
		{
			Console.WriteLine(childOutline.Title);
			Console.WriteLine(childOutline.Italic);
			Console.WriteLine(childOutline.Bold);
			Console.WriteLine(childOutline.Color);
		}
	}
}
```

## Conclusione

Congratulazioni! Ora hai una guida passo passo per ottenere segnalibri figlio con Aspose.PDF per .NET. È possibile utilizzare questo codice per esplorare la struttura gerarchica dei segnalibri e ottenere informazioni dettagliate su ciascun segnalibro e sui relativi segnalibri secondari nei documenti PDF.

Assicurati di controllare la documentazione ufficiale di Aspose.PDF per ulteriori informazioni sulle funzionalità avanzate di manipolazione dei segnalibri.