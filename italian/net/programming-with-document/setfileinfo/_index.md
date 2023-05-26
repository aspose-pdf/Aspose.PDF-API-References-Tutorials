---
title: Imposta informazioni file
linktitle: Imposta informazioni file
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come utilizzare Aspose.PDF per .NET per impostare le informazioni sui file nei tuoi documenti PDF con questa guida dettagliata.
type: docs
weight: 310
url: /it/net/programming-with-document/setfileinfo/
---
Se stai lavorando a un progetto che richiede la gestione di file PDF utilizzando Aspose.PDF per .NET, una delle funzionalità che potresti voler utilizzare è la possibilità di impostare le informazioni sui file per un documento PDF. Le informazioni sul file includono vari dettagli come l'autore, la data di creazione, le parole chiave, la data di modifica, l'oggetto e il titolo. Questa guida ti guiderà attraverso il processo di impostazione delle informazioni sul file per un documento PDF utilizzando il codice sorgente C# con Aspose.PDF per .NET.

## Guida dettagliata per l'impostazione delle informazioni sui file utilizzando Aspose.PDF per .NET

1. Crea un nuovo progetto C# nell'IDE di Visual Studio.
2. Aggiungi un riferimento alla libreria Aspose.PDF per .NET nel tuo progetto.
3. Creare un nuovo oggetto documento PDF fornendo il percorso del file PDF di cui si desidera modificare le informazioni sul file.

## Passaggio 1: impostare il percorso della directory dei documenti.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: apri il documento PDF

```csharp
// Apri documento
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");
```

## Passaggio 3: utilizzare l'oggetto DocumentInfo per accedere alle informazioni sul file del documento PDF.

```csharp
DocumentInfo docInfo = new DocumentInfo(pdfDocument);
```

## Passaggio 4: impostare i valori delle informazioni sul file desiderati utilizzando le proprietà dell'oggetto DocumentInfo.

```csharp
docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";
```

## Passaggio 5: salvare il documento PDF aggiornato nella posizione specificata.

```csharp
dataDir = dataDir + "SetFileInfo_out.pdf";
pdfDocument.Save(dataDir);
```

## Passaggio 6: verificare che le informazioni sul file siano state aggiornate correttamente.

```csharp
Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

Hai impostato correttamente le informazioni sul file per un documento PDF utilizzando Aspose.PDF per .NET.

## Conclusione

In conclusione, Aspose.PDF per .NET fornisce un modo semplice ed efficace per impostare le informazioni sui file per i documenti PDF. Seguendo i passaggi sopra menzionati, puoi facilmente impostare i valori delle informazioni sul file desiderati per i tuoi documenti PDF utilizzando il codice sorgente C#.

### Esempio di codice sorgente per Set File Info utilizzando Aspose.PDF per .NET


```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Apri documento
	Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");

	// Specificare le informazioni sul documento
	DocumentInfo docInfo = new DocumentInfo(pdfDocument);

	docInfo.Author = "Aspose";
	docInfo.CreationDate = DateTime.Now;
	docInfo.Keywords = "Aspose.Pdf, DOM, API";
	docInfo.ModDate = DateTime.Now;
	docInfo.Subject = "PDF Information";
	docInfo.Title = "Setting PDF Document Information";

	dataDir = dataDir + "SetFileInfo_out.pdf";
	// Salva documento di output
	pdfDocument.Save(dataDir);
	
	Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
	
```
