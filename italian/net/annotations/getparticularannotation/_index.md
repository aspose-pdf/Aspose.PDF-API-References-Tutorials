---
title: Ottieni un'annotazione particolare
linktitle: Ottieni un'annotazione particolare
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come utilizzare Aspose.PDF per .NET per ottenere annotazioni particolari in un documento PDF con questa guida dettagliata.
type: docs
weight: 80
url: /it/net/annotations/getparticularannotation/
---
Se stai lavorando con PDF in .NET, potresti incontrare la necessità di ottenere una particolare annotazione da un documento PDF. In questa guida, ti mostreremo come utilizzare Aspose.PDF per .NET per ottenere una particolare annotazione da un documento PDF utilizzando C#.

Segui questi semplici passaggi per ottenere una particolare annotazione da un documento PDF:

## Passaggio 1: ottieni annotazioni particolari dal documento PDF

Innanzitutto, assicurati di avere la libreria Aspose.PDF per .NET installata e referenziata nel tuo progetto.

Successivamente, crea una nuova istanza della classe Document e carica il documento PDF utilizzando il percorso della directory del documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "GetParticularAnnotation.pdf");
```

## Passaggio 2: è possibile ottenere una particolare annotazione utilizzando il seguente codice:

```csharp
TextAnnotation textAnnotation = (TextAnnotation)pdfDocument.Pages[1].Annotations[1];
```

Questo codice recupera la seconda annotazione sulla seconda pagina del documento PDF.

## Passo 3: Infine, puoi ottenere le proprietà dell'annotazione usando il seguente codice:

```csharp
Console.WriteLine("Title : {0} ", textAnnotation.Title);
Console.WriteLine("Subject : {0} ", textAnnotation.Subject);
Console.WriteLine("Contents : {0} ", textAnnotation.Contents);
```

Questo codice visualizza il titolo, l'oggetto e il contenuto dell'annotazione nella console.


### Codice sorgente di esempio per ottenere un'annotazione particolare utilizzando Aspose.PDF per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Apri documento
Document pdfDocument = new Document(dataDir + "GetParticularAnnotation.pdf");

// Ottieni un'annotazione particolare
TextAnnotation textAnnotation = (TextAnnotation)pdfDocument.Pages[1].Annotations[1];

// Ottieni proprietà di annotazione
Console.WriteLine("Title : {0} ", textAnnotation.Title);
Console.WriteLine("Subject : {0} ", textAnnotation.Subject);
Console.WriteLine("Contents : {0} ", textAnnotation.Contents);
```

