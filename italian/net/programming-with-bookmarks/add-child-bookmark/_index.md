---
title: Aggiungi segnalibro figlio
linktitle: Aggiungi segnalibro figlio
second_title: Aspose.PDF per riferimento API .NET
description: Aggiungi facilmente un segnalibro figlio ai tuoi file PDF per una navigazione più organizzata con Aspose.PDF per .NET.
type: docs
weight: 20
url: /it/net/programming-with-bookmarks/add-child-bookmark/
---

L'aggiunta di segnalibri secondari a un documento PDF consente un'organizzazione e una navigazione più strutturate. Con Aspose.PDF per .NET, puoi facilmente aggiungere un sotto-segnalibro seguendo il seguente codice sorgente:

## Passaggio 1: importa le librerie richieste

Prima di iniziare, devi importare le librerie necessarie per il tuo progetto C#. Ecco la direttiva di importazione necessaria:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## Passaggio 2: imposta il percorso della cartella dei documenti

 In questo passaggio, è necessario specificare il percorso della cartella contenente il file PDF a cui si desidera aggiungere un sotto-segnalibro. Sostituire`"YOUR DOCUMENT DIRECTORY"` nel seguente codice con il percorso effettivo della cartella dei documenti:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 3: apri il documento PDF

Ora apriremo il documento PDF a cui vogliamo aggiungere un sub-bookmark utilizzando il seguente codice:

```csharp
Document pdfDocument = new Document(dataDir + "AddChildBookmark.pdf");
```

## Passaggio 4: creare un oggetto segnalibro principale

 In questo passaggio, creeremo un oggetto segnalibro principale utilizzando il file`OutlineItemCollection` class e impostarne le proprietà come titolo, attributo corsivo e attributo grassetto. Ecco il codice corrispondente:

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Parent bookmark";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
```

## Passaggio 5: creare un oggetto segnalibro figlio

In questo passaggio, creeremo nuovamente un oggetto sub-bookmark utilizzando il file`OutlineItemCollection` class e impostarne le proprietà. Ecco il codice corrispondente:

```csharp
OutlineItemCollection pdfChildOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfChildOutline.Title = "Sub Bookmark";
pdfChildOutline. Italic = true;
pdfChildOutline. Bold = true;
```

## Passaggio 6: aggiungi il sotto-segnalibro al segnalibro principale

 Infine, aggiungiamo il subbookmark creato alla raccolta di subbookmark del segnalibro principale utilizzando il file`Add` metodo dell'oggetto padre. Ecco il codice corrispondente:

```csharp
pdfOutline.Add(pdfChildOutline);
```

## Passaggio 7: aggiungere il segnalibro principale alla raccolta di segnalibri del documento

 Infine, aggiungiamo il segnalibro principale alla raccolta di segnalibri del documento utilizzando il file`Add` metodo del`Outlines` proprietà. Ecco il codice corrispondente:

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

### Esempio di codice sorgente per Aggiungi segnalibro figlio utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "AddChildBookmark.pdf");
// Crea un oggetto segnalibro principale
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Parent Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;      
// Crea un oggetto segnalibro figlio
OutlineItemCollection pdfChildOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfChildOutline.Title = "Child Outline";
pdfChildOutline.Italic = true;
pdfChildOutline.Bold = true;
// Aggiungi segnalibro figlio nella raccolta di segnalibri genitore
pdfOutline.Add(pdfChildOutline);
// Aggiungi un segnalibro principale nella raccolta di schemi del documento.
pdfDocument.Outlines.Add(pdfOutline);
dataDir = dataDir + "AddChildBookmark_out.pdf";
// Salva output
pdfDocument.Save(dataDir);
Console.WriteLine("\nChild bookmark added successfully.\nFile saved at " + dataDir);
```

## Conclusione

Congratulazioni! Ora hai una guida passo passo per aggiungere un sotto-segnalibro con Aspose.PDF per .NET. Puoi usare questo codice per organizzare e strutturare i tuoi segnalibri nei tuoi documenti PDF.

Assicurati di controllare la documentazione ufficiale di Aspose.PDF per ulteriori informazioni sulle funzionalità avanzate di manipolazione dei segnalibri.