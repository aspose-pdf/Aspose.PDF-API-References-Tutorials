---
title: Ottieni il fattore di zoom
linktitle: Ottieni il fattore di zoom
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come utilizzare Aspose.PDF per .NET per ottenere il fattore di zoom di un file PDF con questa guida dettagliata.
type: docs
weight: 210
url: /it/net/programming-with-document/getzoomfactor/
---
Aspose.PDF per .NET è una libreria di manipolazione PDF che offre molte funzionalità per eseguire varie operazioni sui documenti PDF. Una di queste funzionalità è la possibilità di ottenere il fattore di zoom di un file PDF. In questo tutorial, spiegheremo come utilizzare Aspose.PDF per .NET per ottenere il fattore di zoom di un file PDF utilizzando il codice sorgente C#.


## Passaggio 1: creare un'istanza del nuovo oggetto Document

 Il primo passo per ottenere il fattore di zoom di un file PDF utilizzando Aspose.PDF per .NET è creare un'istanza di un nuovo`Document` oggetto. IL`Document` oggetto rappresenta un documento PDF che può essere caricato da un file o da un flusso.

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crea un'istanza di un nuovo oggetto Document
Document doc = new Document(dataDir + "Zoomed_pdf.pdf");
```

 Nel codice sopra, abbiamo creato a`Document` oggetto passando il percorso del file PDF al costruttore del file`Document` classe. Devi sostituire "YOUR DOCUMENT DIRECTORY" con il percorso effettivo della directory in cui si trova il tuo file PDF.

## Passaggio 2: creare l'oggetto GoToAction

 Il prossimo passo è creare un file`GoToAction` oggetto. UN`GoToAction` oggetto rappresenta un'azione che va a una destinazione specifica in un documento PDF. Nel nostro caso, vogliamo ottenere il fattore di zoom del file PDF, quindi utilizzeremo il formato`OpenAction` proprietà del`Document` oggetto per ottenere il`GoToAction` oggetto.

```csharp
// Crea un oggetto GoToAction
GoToAction action = doc.OpenAction as GoToAction;
```

 Nel codice sopra, abbiamo creato a`GoToAction` oggetto lanciando il`OpenAction` proprietà del`Document` opporsi a`GoToAction`.

## Passaggio 3: ottieni il fattore di zoom del file PDF

Il terzo passaggio consiste nell'ottenere il fattore di zoom del file PDF. Possiamo ottenere il fattore di zoom del file PDF accedendo al file`Destination` proprietà del`GoToAction` oggetto e quindi trasmetterlo a`XYZExplicitDestination` . IL`XYZExplicitDestination` class rappresenta una destinazione in un documento PDF che specifica le coordinate e il fattore di zoom a cui andare.

```csharp
// Ottieni il fattore di zoom del file PDF
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Valore di zoom del documento;
```

 Nel codice sopra, abbiamo avuto accesso a`Destination` proprietà del`GoToAction` oggetto e quindi eseguirne il cast`XYZExplicitDestination` . Successivamente, abbiamo effettuato l'accesso al file`Zoom` proprietà del`XYZExplicitDestination` oggetto per ottenere il fattore di zoom del file PDF.

## Passaggio 4: emettere il fattore di zoom

 Il passaggio finale consiste nell'output del fattore di zoom del file PDF. Possiamo usare il`System.Console.WriteLine`

```csharp
// Ottieni il fattore di zoom del file PDF
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Valore di zoom del documento;
```        

### Codice sorgente di esempio per ottenere il fattore di zoom utilizzando Aspose.PDF per .NET

Ecco il codice sorgente di esempio completo per Ottieni fattore di zoom utilizzando Aspose.PDF per .NET:

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Crea un'istanza di un nuovo oggetto Document
	Document doc = new Document(dataDir + "Zoomed_pdf.pdf");

	// Crea un oggetto GoToAction
	GoToAction action = doc.OpenAction as GoToAction;
	
	// Ottieni il fattore di zoom del file PDF
	System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Valore di zoom del documento;
	
```
