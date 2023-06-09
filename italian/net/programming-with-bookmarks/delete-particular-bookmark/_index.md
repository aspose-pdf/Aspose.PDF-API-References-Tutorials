---
title: Elimina segnalibro particolare
linktitle: Elimina segnalibro particolare
second_title: Aspose.PDF per riferimento API .NET
description: Elimina facilmente un particolare segnalibro dai tuoi file PDF con Aspose.PDF per .NET.
type: docs
weight: 40
url: /it/net/programming-with-bookmarks/delete-particular-bookmark/
---

Potrebbe essere necessario eliminare un particolare segnalibro da un documento PDF. Con Aspose.PDF per .NET, puoi facilmente eliminare un particolare segnalibro seguendo il seguente codice sorgente:

## Passaggio 1: importa le librerie richieste

Prima di iniziare, devi importare le librerie necessarie per il tuo progetto C#. Ecco la direttiva di importazione necessaria:

```csharp
using Aspose.Pdf;
```

## Passaggio 2: imposta il percorso della cartella dei documenti

 In questo passaggio, è necessario specificare il percorso della cartella contenente il file PDF da cui si desidera rimuovere un particolare segnalibro. Sostituire`"YOUR DOCUMENT DIRECTORY"` nel seguente codice con il percorso effettivo della cartella dei documenti:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 3: apri il documento PDF

Adesso andiamo ad aprire il documento PDF da cui vogliamo rimuovere un segnalibro usando il seguente codice:

```csharp
Document pdfDocument = new Document(dataDir + "DeleteParticularBookmark.pdf");
```

## Passaggio 4: eliminare un particolare segnalibro

 In questo passaggio, eliminiamo un particolare segnalibro utilizzando il file`Delete` metodo del`Outlines` proprietà. Specifichiamo il titolo del segnalibro da eliminare. Ecco il codice corrispondente:

```csharp
pdfDocument.Outlines.Delete("Child Outline");
```

## Passaggio 5: salvare il file aggiornato

 Infine, salviamo il file PDF aggiornato utilizzando l'estensione`Save` metodo del`pdfDocument` oggetto. Ecco il codice corrispondente:

```csharp
dataDir = dataDir + "DeleteParticularBookmark_out.pdf";
pdfDocument.Save(dataDir);
```

### Esempio di codice sorgente per Elimina particolare segnalibro utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "DeleteParticularBookmark.pdf");
// Elimina lo schema particolare per titolo
pdfDocument.Outlines.Delete("Child Outline");
dataDir = dataDir + "DeleteParticularBookmark_out.pdf";
// Salva file aggiornato
pdfDocument.Save(dataDir);
Console.WriteLine("\nParticular bookmark deleted successfully.\nFile saved at " + dataDir);
```

## Conclusione

Congratulazioni! Ora hai una guida passo passo per eliminare un particolare segnalibro con Aspose.PDF per .NET. Puoi utilizzare questo codice per indirizzare e rimuovere segnalibri specifici dai tuoi documenti PDF.

Assicurati di controllare la documentazione ufficiale di Aspose.PDF per ulteriori informazioni sulle funzionalità avanzate di manipolazione dei segnalibri.