---
title: Aggiungi segnalibro
linktitle: Aggiungi segnalibro
second_title: Aspose.PDF per riferimento API .NET
description: Aggiungi facilmente segnalibri ai tuoi file PDF per una migliore navigazione con Aspose.PDF per .NET.
type: docs
weight: 10
url: /it/net/programming-with-bookmarks/add-bookmark/
---

L'aggiunta di segnalibri in un documento PDF consente una navigazione facile e veloce. Con Aspose.PDF per .NET, puoi facilmente aggiungere un segnalibro seguendo il seguente codice sorgente:

## Passaggio 1: importa le librerie richieste

Prima di iniziare, devi importare le librerie necessarie per il tuo progetto C#. Ecco la direttiva di importazione necessaria:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## Passaggio 2: imposta il percorso della cartella dei documenti

 In questo passaggio, è necessario specificare il percorso della cartella contenente il file PDF a cui si desidera aggiungere un segnalibro. Sostituire`"YOUR DOCUMENT DIRECTORY"` nel seguente codice con il percorso effettivo della cartella dei documenti:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 3: apri il documento PDF

Ora apriremo il documento PDF a cui vogliamo aggiungere un segnalibro usando il seguente codice:

```csharp
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
```

## Passaggio 4: creare un oggetto segnalibro

 In questo passaggio, creeremo un oggetto segnalibro utilizzando`OutlineItemCollection` class e impostarne le proprietà come titolo, attributo corsivo, attributo grassetto e azione da eseguire quando si fa clic. Ecco il codice corrispondente:

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
```

## Passaggio 5: aggiungi un segnalibro al documento

 Infine, aggiungiamo il segnalibro creato alla raccolta di segnalibri del documento utilizzando il file`Add` metodo del`Outlines` proprietà. Ecco il codice corrispondente:

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

### Esempio di codice sorgente per Aggiungi segnalibro utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
// Crea un oggetto segnalibro
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;
// Impostare il numero della pagina di destinazione
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
// Aggiungi segnalibro nella raccolta di schemi del documento.
pdfDocument.Outlines.Add(pdfOutline);
dataDir = dataDir + "AddBookmark_out.pdf";
// Salva output
pdfDocument.Save(dataDir);
Console.WriteLine("\nBookmark added successfully.\nFile saved at " + dataDir);
```

## Conclusione

Congratulazioni! Ora hai una guida passo passo per aggiungere un segnalibro usando Aspose.PDF per .NET. Puoi utilizzare questo codice per migliorare la navigazione nei tuoi documenti PDF aggiungendo segnalibri personalizzati.

Assicurati di controllare la documentazione ufficiale di Aspose.PDF per ulteriori informazioni sulle funzionalità avanzate di manipolazione dei segnalibri.