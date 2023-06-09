---
title: Aggiorna segnalibri figlio
linktitle: Aggiorna segnalibri figlio
second_title: Aspose.PDF per riferimento API .NET
description: Aggiorna facilmente i segnalibri figlio nei tuoi file PDF con Aspose.PDF per .NET.
type: docs
weight: 110
url: /it/net/programming-with-bookmarks/update-child-bookmarks/
---

L'aggiornamento dei segnalibri secondari in un documento PDF consente di modificare le proprietà di segnalibri specifici all'interno di un segnalibro principale. Con Aspose.PDF per .NET, puoi facilmente aggiornare i segnalibri figli seguendo il seguente codice sorgente:

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
Document pdfDocument = new Document(dataDir + "UpdateChildBookmarks.pdf");
```

## Passaggio 4: ottieni l'oggetto segnalibro principale

In questo passaggio, otterremo l'oggetto segnalibro principale specifico da cui vogliamo aggiornare i segnalibri secondari. Nell'esempio seguente, recuperiamo il segnalibro principale all'indice 1 (il secondo segnalibro nella raccolta dei segnalibri). È possibile regolare l'indice in base alle proprie esigenze. Ecco il codice corrispondente:

```csharp
OutlineItemCollection pdfOutline = pdfDocument.Outlines[1];
```

## Passaggio 5: ottieni l'oggetto segnalibro figlio

Ora prendiamo l'oggetto segnalibro figlio specifico che vogliamo aggiornare. Nell'esempio seguente, recuperiamo il segnalibro figlio all'indice 1 (il secondo segnalibro figlio nella raccolta di segnalibri figlio del segnalibro padre). È possibile regolare l'indice in base alle proprie esigenze. Ecco il codice corrispondente:

```csharp
OutlineItemCollection childOutline = pdfOutline[1];
```

## Passaggio 6: aggiorna le proprietà del segnalibro figlio

Ora aggiorniamo le proprietà del segnalibro figlio come titolo, stile corsivo e stile grassetto. È possibile regolare queste proprietà in base alle proprie esigenze. Ecco il codice corrispondente:

```csharp
childOutline.Title = "Updated Outline";
childOutline. Italic = true;
childOutline. Bold = true;
```

## Passaggio 7: salvare il file aggiornato

Ora salviamo il file PDF aggiornato utilizzando l'estensione`Save` metodo del`pdfDocument` oggetto. Ecco il codice corrispondente:

```csharp
dataDir = dataDir + "UpdateChildBookmarks_out.pdf";
pdfDocument.Save(dataDir);
```

### Esempio di codice sorgente per l'aggiornamento dei segnalibri secondari utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "UpdateChildBookmarks.pdf");
// Ottieni un oggetto segnalibro
OutlineItemCollection pdfOutline = pdfDocument.Outlines[1];
// Ottieni oggetto segnalibro figlio
OutlineItemCollection childOutline = pdfOutline[1];
childOutline.Title = "Updated Outline";
childOutline.Italic = true;
childOutline.Bold = true;
dataDir = dataDir + "UpdateChildBookmarks_out.pdf";            
// Salva output
pdfDocument.Save(dataDir);
Console.WriteLine("\nChild bookmarks updated successfully.\nFile saved at " + dataDir);
```

## Conclusione

Congratulazioni! Ora hai una guida passo passo per l'aggiornamento dei segnalibri figlio con Aspose.PDF per .NET. È possibile utilizzare questo codice per modificare le proprietà dei segnalibri secondari nei documenti PDF.

Assicurati di controllare la documentazione ufficiale di Aspose.PDF per ulteriori informazioni sulle funzionalità avanzate di manipolazione dei segnalibri.