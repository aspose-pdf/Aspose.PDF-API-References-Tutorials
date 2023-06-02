---
title: Imposta il fattore di ingrandimento
linktitle: Imposta il fattore di ingrandimento
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come impostare il fattore di zoom per i file PDF utilizzando Aspose.PDF per .NET con la nostra guida dettagliata.
type: docs
weight: 340
url: /it/net/programming-with-document/setzoomfactor/
---
Aspose.PDF per .NET è una potente API che consente agli sviluppatori di lavorare con documenti PDF nelle loro applicazioni .NET. Una delle funzionalità che offre è la possibilità di impostare il fattore di zoom di un documento PDF. In questa guida dettagliata, spiegheremo come utilizzare Aspose.PDF per .NET per impostare il fattore di zoom di un documento PDF utilizzando il codice sorgente C# fornito.

## Passaggio 1: impostare il percorso della directory dei documenti

 Il primo passaggio consiste nell'impostare il percorso della directory in cui si trova il documento PDF. Questo può essere fatto impostando il`dataDir` variabile al percorso della directory. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Sostituisci "YOUR DOCUMENT DIRECTORY" con il percorso effettivo della directory in cui si trova il tuo documento PDF.

## Passaggio 2: creare un'istanza di un nuovo oggetto Document

 Per lavorare con un documento PDF utilizzando Aspose.PDF per .NET, è necessario creare un nuovo file`Document` oggetto e caricare il file PDF in esso. 

```csharp
Document doc = new Document(dataDir + "SetZoomFactor.pdf");
```

 Questo codice creerà un nuovo file`Document`oggetto e caricare il file PDF denominato "SetZoomFactor.pdf" dal file`dataDir` directory in esso.

## Passaggio 3: impostare il fattore di zoom

 Una volta il`Document` viene creato l'oggetto, possiamo impostare il fattore di zoom del documento PDF. Nel codice seguente impostiamo il fattore di zoom al 50%.

```csharp
GoToAction action = new GoToAction(new XYZExplicitDestination(1, 0, 0, .5));
doc.OpenAction = action;
```

 Questo codice imposta il fattore di zoom al 50% creando un nuovo`GoToAction` oggetto e passando a`XYZExplicitDestination` oggetto con un fattore di zoom del 50%. IL`OpenAction` proprietà del`Document` oggetto viene quindi impostato su this`GoToAction` oggetto.

## Passaggio 4: salvare il documento PDF

 Infine, possiamo salvare il documento PDF modificato in un nuovo file. Nel codice seguente, salviamo il documento PDF in un nuovo file denominato "Zoomed_pdf_out.pdf" nel`dataDir` directory.

```csharp
dataDir = dataDir + "Zoomed_pdf_out.pdf";
doc.Save(dataDir);
```

### Esempio di codice sorgente per Imposta fattore di zoom utilizzando Aspose.PDF per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crea un'istanza di un nuovo oggetto Document
Document doc = new Document(dataDir + "SetZoomFactor.pdf");

GoToAction action = new GoToAction(new XYZExplicitDestination(1, 0, 0, .5));
doc.OpenAction = action;
dataDir = dataDir + "Zoomed_pdf_out.pdf";
// Salva il documento
doc.Save(dataDir);
```

## Conclusione

Aspose.PDF per .NET fornisce un modo semplice ed efficiente per impostare il fattore di zoom di un documento PDF utilizzando il codice C#. Seguendo i passaggi precedenti, puoi facilmente modificare il fattore di zoom di qualsiasi documento PDF nella tua applicazione .NET.