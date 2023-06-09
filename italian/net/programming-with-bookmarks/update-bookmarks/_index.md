---
title: Aggiorna segnalibri
linktitle: Aggiorna segnalibri
second_title: Aspose.PDF per riferimento API .NET
description: Aggiorna facilmente i segnalibri nei tuoi file PDF con Aspose.PDF per .NET.
type: docs
weight: 100
url: /it/net/programming-with-bookmarks/update-bookmarks/
---

L'aggiornamento dei segnalibri in un documento PDF è spesso necessario per riflettere modifiche o aggiornamenti nella struttura o nel contenuto del documento. Con Aspose.PDF per .NET, puoi facilmente aggiornare i segnalibri seguendo il seguente codice sorgente:

## Passaggio 1: importa le librerie richieste

Prima di iniziare, devi importare le librerie necessarie per il tuo progetto C#. Ecco la direttiva di importazione necessaria:

```csharp
using Aspose.Pdf;
```

## Passaggio 2: imposta il percorso della cartella dei documenti

 In questo passaggio, è necessario specificare il percorso della cartella contenente il file PDF che si desidera aggiornare. Sostituire`"YOUR DOCUMENT DIRECTORY"` nel seguente codice con il percorso effettivo della cartella dei documenti:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 3: apri il documento PDF

Ora apriremo il documento PDF che vogliamo aggiornare utilizzando il seguente codice:

```csharp
Document pdfDocument = new Document(dataDir + "UpdateBookmarks.pdf");
```

## Passaggio 4: ottieni l'oggetto segnalibro

In questo passaggio, otterremo l'oggetto segnalibro specifico che vogliamo aggiornare. Nell'esempio seguente, recuperiamo il segnalibro all'indice 1 (il secondo segnalibro nella raccolta dei segnalibri). È possibile regolare l'indice in base alle proprie esigenze. Ecco il codice corrispondente:

```csharp
OutlineItemCollection pdfOutline = pdfDocument.Outlines[1];
```

## Passaggio 5: aggiorna le proprietà dei segnalibri

Ora aggiorniamo le proprietà del segnalibro come titolo, stile corsivo e stile grassetto. È possibile regolare queste proprietà in base alle proprie esigenze. Ecco il codice corrispondente:

```csharp
pdfOutline.Title = "Updated Outline";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
```

## Passaggio 6: salvare il file aggiornato

Ora salviamo il file PDF aggiornato utilizzando l'estensione`Save` metodo del`pdfDocument` oggetto. Ecco il codice corrispondente:

```csharp
dataDir = dataDir + "UpdateBookmarks_out.pdf";
pdfDocument.Save(dataDir);
```

### Esempio di codice sorgente per l'aggiornamento dei segnalibri utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "UpdateBookmarks.pdf");
// Ottieni un oggetto segnalibro
OutlineItemCollection pdfOutline = pdfDocument.Outlines[1];
pdfOutline.Title = "Updated Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;
dataDir = dataDir + "UpdateBookmarks_out.pdf";
// Salva output
pdfDocument.Save(dataDir);
Console.WriteLine("\nBookmarks updated successfully.\nFile saved at " + dataDir);
```

## Conclusione

Congratulazioni! Ora hai una guida passo passo per aggiornare i segnalibri con Aspose.PDF per .NET. È possibile utilizzare questo codice per modificare i titoli e gli stili dei segnalibri nei documenti PDF.

Assicurati di controllare la documentazione ufficiale di Aspose.PDF per ulteriori informazioni sulle funzionalità avanzate di manipolazione dei segnalibri.