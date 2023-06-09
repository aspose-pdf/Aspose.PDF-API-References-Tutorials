---
title: Elimina tutti i segnalibri
linktitle: Elimina tutti i segnalibri
second_title: Aspose.PDF per riferimento API .NET
description: Elimina facilmente tutti i segnalibri dai tuoi file PDF con Aspose.PDF per .NET.
type: docs
weight: 30
url: /it/net/programming-with-bookmarks/delete-all-bookmarks/
---

# Elimina tutti i segnalibri con Aspose.PDF per .NET

In alcuni casi potrebbe essere necessario eliminare i segnalibri da un documento PDF. Con Aspose.PDF per .NET, puoi rimuovere facilmente tutti i segnalibri seguendo il seguente codice sorgente:

## Passaggio 1: importa le librerie richieste

Prima di iniziare, devi importare le librerie necessarie per il tuo progetto C#. Ecco la direttiva di importazione necessaria:

```csharp
using Aspose.Pdf;
```

## Passaggio 2: imposta il percorso della cartella dei documenti

 In questo passaggio, è necessario specificare il percorso della cartella contenente il file PDF da cui si desidera rimuovere i segnalibri. Sostituire`"YOUR DOCUMENT DIRECTORY"` nel seguente codice con il percorso effettivo della cartella dei documenti:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 3: apri il documento PDF

Adesso andiamo ad aprire il documento PDF dal quale vogliamo rimuovere i segnalibri utilizzando il seguente codice:

```csharp
Document pdfDocument = new Document(dataDir + "DeleteAllBookmarks.pdf");
```

## Passaggio 4: elimina tutti i segnalibri

 In questo passaggio, eliminiamo tutti i segnalibri dal documento utilizzando il file`Delete` metodo del`Outlines` proprietà. Ecco il codice corrispondente:

```csharp
pdfDocument.Outlines.Delete();
```

## Passaggio 5: salvare il file aggiornato

 Infine, salviamo il file PDF aggiornato utilizzando l'estensione`Save` metodo del`pdfDocument` oggetto. Ecco il codice corrispondente:

```csharp
dataDir = dataDir + "DeleteAllBookmarks_out.pdf";
pdfDocument.Save(dataDir);
```

### Esempio di codice sorgente per Elimina tutti i segnalibri utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "DeleteAllBookmarks.pdf");
// Elimina tutti i segnalibri
pdfDocument.Outlines.Delete();
dataDir = dataDir + "DeleteAllBookmarks_out.pdf";
// Salva file aggiornato
pdfDocument.Save(dataDir);
Console.WriteLine("\nAll bookmarks deleted successfully.\nFile saved at " + dataDir);
```

## Conclusione

Congratulazioni! Ora hai una guida passo passo per rimuovere tutti i segnalibri con Aspose.PDF per .NET. Puoi utilizzare questo codice per ripulire i tuoi documenti PDF eliminando tutti i segnalibri esistenti.

Assicurati di controllare la documentazione ufficiale di Aspose.PDF per ulteriori informazioni sulle funzionalità avanzate di manipolazione dei segnalibri.