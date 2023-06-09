---
title: Eredita Zoom
linktitle: Eredita Zoom
second_title: Aspose.PDF per riferimento API .NET
description: Eredita facilmente lo zoom dei segnalibri nei tuoi file PDF con Aspose.PDF per .NET.
type: docs
weight: 90
url: /it/net/programming-with-bookmarks/inherit-zoom/
---

L'ereditarietà dello zoom in un documento PDF consente di specificare un livello di zoom predefinito per i segnalibri. Con Aspose.PDF per .NET, puoi facilmente ereditare lo zoom seguendo il seguente codice sorgente:

## Passaggio 1: importa le librerie richieste

Prima di iniziare, devi importare le librerie necessarie per il tuo progetto C#. Ecco la direttiva di importazione necessaria:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## Passaggio 2: imposta il percorso della cartella dei documenti

In questo passaggio, è necessario specificare il percorso della cartella contenente il file PDF da cui si desidera ereditare lo zoom. Sostituire`"YOUR DOCUMENT DIRECTORY"` nel seguente codice con il percorso effettivo della cartella dei documenti:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 3: apri il documento PDF

Ora andiamo ad aprire il documento PDF su cui vogliamo ereditare lo zoom utilizzando il seguente codice:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Passaggio 4: ottieni la raccolta di segnalibri

 In questo passaggio, otterremo la raccolta di segnalibri o punti di riferimento del documento utilizzando il file`Outlines` proprietà del`doc` oggetto. Ecco il codice corrispondente:

```csharp
OutlineItemCollection item = new OutlineItemCollection(doc.Outlines);
```

## Passaggio 5: imposta il livello di zoom

 Ora imposteremo il livello di zoom creando un file`XYZExplicitDestination` oggetto con le coordinate x, y e z specificate. Qui usiamo le coordinate (100, 100, 0) con uno zoom di 2. Ecco il codice corrispondente:

```csharp
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
```

## Passaggio 6: aggiungi il livello di zoom ai segnalibri

 In questo passaggio, aggiungiamo il`XYZExplicitDestination` oggetto come un'azione ai segnalibri del`item` collezione. Ecco il codice corrispondente:

```csharp
item. Action = new GoToAction(dest);
```

## Passaggio 7: aggiungi i segnalibri aggiornati al documento

 Infine, aggiungiamo i segnalibri aggiornati alla raccolta di segnalibri del documento utilizzando il file`Add` metodo del`doc.Outlines` oggetto. Ecco il codice corrispondente:

```csharp
doc. Outlines. Add(item);
```

## Passaggio 8: salvare il file aggiornato

Ora salviamo il file PDF aggiornato utilizzando l'estensione`Save` metodo del`doc` oggetto. Ecco il codice corrispondente:

```csharp
dataDir = dataDir + "InheritZoom_out.pdf";
doc.Save(dataDir);
```

### Esempio di codice sorgente per Inherit Zoom utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document doc = new Document(dataDir + "input.pdf");
// Ottieni una raccolta di contorni/segnalibri di file PDF
OutlineItemCollection item = new OutlineItemCollection(doc.Outlines);
// Imposta il livello di zoom su 0
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
// Aggiungi XYZExplicitDestination come azione alla raccolta di contorni di PDF
item.Action = new GoToAction(dest);
// Aggiungi elemento alla raccolta di contorni del file PDF
doc.Outlines.Add(item);
dataDir = dataDir + "InheritZoom_out.pdf";
// Salva output
doc.Save(dataDir);
Console.WriteLine("\nBookmarks updated successfully.\nFile saved at " + dataDir);
```

## Conclusione

Congratulazioni! Ora hai una guida passo passo per ereditare lo zoom con Aspose.PDF per .NET. È possibile utilizzare questo codice per specificare un livello di zoom predefinito per i segnalibri nei documenti PDF.

Assicurati di controllare la documentazione ufficiale di Aspose.PDF per ulteriori informazioni sulle funzionalità avanzate di manipolazione dei segnalibri.