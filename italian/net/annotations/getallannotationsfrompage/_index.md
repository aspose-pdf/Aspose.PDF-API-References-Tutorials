---
title: Ottieni tutte le annotazioni dalla pagina
linktitle: Ottieni tutte le annotazioni dalla pagina
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come utilizzare Aspose.PDF per .NET per recuperare tutte le annotazioni da una pagina PDF con questa guida dettagliata.
type: docs
weight: 70
url: /it/net/annotations/getallannotationsfrompage/
---
Questo articolo ti guiderà attraverso il processo di estrazione di tutte le annotazioni da una pagina PDF utilizzando Aspose.PDF per .NET. Aspose.PDF per .NET è una libreria che consente agli sviluppatori di creare, modificare e convertire documenti PDF. Con l'aiuto di questa guida, sarai in grado di ottenere tutte le annotazioni da una specifica pagina PDF utilizzando il codice sorgente C# fornito.

Segui i passaggi seguenti su come ottenere tutte le annotazioni per una pagina PDF utilizzando Aspose.PDF per .NET:

## Passaggio 1: il percorso della directory dei documenti

Il primo passo per ottenere tutte le annotazioni da una pagina PDF utilizzando Aspose.PDF per .NET è impostare il percorso della directory dei documenti in cui sono archiviati i file PDF. Puoi farlo modificando la seguente riga di codice:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```
## Passaggio 2: i file PDF vengono archiviati

Sostituisci "YOUR DOCUMENT DIRECTORY" con il percorso della cartella in cui sono archiviati i tuoi file PDF. Per esempio:

```csharp
string dataDir = @"C:\Users\JohnDoe\Documents\PDFs\";
```

## Passaggio 3: apri il documento

Il passaggio successivo consiste nell'aprire il documento PDF che contiene le annotazioni che desideri estrarre. Puoi farlo aggiungendo il seguente codice:

```csharp
Document pdfDocument = new Document(dataDir + "GetAllAnnotationsFromPage.pdf");
```

Questa riga di codice inizializza una nuova istanza della classe Document e carica il documento PDF "GetAllAnnotationsFromPage.pdf". Sostituisci questo nome file con il nome del tuo file PDF.

## Passaggio 4: scorrere tutte le annotazioni

Dopo aver aperto il documento PDF, puoi scorrere tutte le annotazioni su una pagina specifica. Ad esempio, per scorrere tutte le annotazioni sulla prima pagina del documento PDF, aggiungi il seguente codice:

```csharp
foreach (MarkupAnnotation annotation in pdfDocument.Pages[1].Annotations)
{
    // Il codice va qui
}
```

Questo codice scorre tutte le annotazioni sulla prima pagina del documento PDF e assegna ciascuna annotazione alla variabile "annotazione".

## Passaggio 5: ottenere le proprietà dell'annotazione

Per estrarre le proprietà di ogni annotazione, puoi aggiungere il seguente codice all'interno del ciclo foreach:

```csharp
Console.WriteLine("Title : {0} ", annotation.Title);
Console.WriteLine("Subject : {0} ", annotation.Subject);
Console.WriteLine("Contents : {0} ", annotation.Contents);
```

Questo codice scrive il titolo, l'oggetto e il contenuto di ogni annotazione nella console.

### Codice sorgente di esempio per ottenere tutte le annotazioni dalla pagina utilizzando Aspose.PDF per .NET

Ecco il codice sorgente completo per ottenere tutte le annotazioni da una pagina PDF utilizzando Aspose.PDF per .NET:

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Apri documento
	Document pdfDocument = new Document(dataDir + "GetAllAnnotationsFromPage.pdf");

	// Passa attraverso tutte le annotazioni
	foreach (MarkupAnnotation annotation in pdfDocument.Pages[1].Annotations)
	{
		// Ottieni proprietà di annotazione
		Console.WriteLine("Title : {0} ", annotation.Title);
		Console.WriteLine("Subject : {0} ", annotation.Subject);
		Console.WriteLine("Contents : {0} ", annotation.Contents);                
	}

```
