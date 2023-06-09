---
title: Disegna XForm sulla pagina
linktitle: Disegna XForm sulla pagina
second_title: Aspose.PDF per riferimento API .NET
description: Guida dettagliata per disegnare un modulo XForm su una pagina PDF utilizzando Aspose.PDF per .NET. Aggiungi e posiziona il modulo sulla pagina.
type: docs
weight: 10
url: /it/net/programming-with-operators/draw-xform-on-page/
---
In questo tutorial, ti forniremo una guida passo passo su come disegnare un XForm su una pagina usando Aspose.PDF per .NET. Aspose.PDF è una potente libreria che consente di creare, manipolare e convertire documenti PDF in modo programmatico. Utilizzando gli operatori forniti da Aspose.PDF, è possibile aggiungere e posizionare un modulo XForm su una pagina PDF esistente.

## Prerequisiti

Prima di iniziare, assicurati di disporre dei seguenti prerequisiti:

1. Visual Studio installato con .NET framework.
2. La libreria Aspose.PDF per .NET.

## Passaggio 1: impostazione del progetto

Per iniziare, crea un nuovo progetto in Visual Studio e aggiungi un riferimento alla libreria Aspose.PDF per .NET. Puoi scaricare la libreria dal sito Web ufficiale di Aspose e installarla sul tuo computer.

## Passaggio 2: importare gli spazi dei nomi necessari

Nel tuo file di codice C#, importa gli spazi dei nomi richiesti per accedere alle classi e ai metodi forniti da Aspose.PDF:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

## Passaggio 3: impostazione dei percorsi dei file

Definire i percorsi file per l'immagine di sfondo, il file PDF di input e il file PDF di output:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string imageFile = dataDir + "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
```

Assicurati di specificare i percorsi file effettivi sulla tua macchina.

## Passaggio 4: caricamento del file PDF di input

Utilizzare il seguente codice per caricare il file PDF di input:

```csharp
using (Document doc = new Document(inFile))
{
OperatorCollection pageContents = doc.Pages[1].Contents;
//Il codice seguente utilizza gli operatori GSave/GRestore
// Il codice utilizza l'operatore ContatenateMatrix per posizionare XForm
// Il codice usa l'operatore Do per disegnare l'XForm sulla pagina
// Gli operatori GSave/GRestore racchiudono il contenuto esistente
// questo viene fatto per ottenere lo stato grafico iniziale alla fine del contenuto esistente
// altrimenti potrebbero rimanere trasformazioni indesiderate alla fine della catena degli operatori esistenti
pageContents. Insert(1, new GSave());
pageContents. Add(new GRestore());
// Aggiungi l'operatore GSave per reimpostare correttamente lo stato della grafica dopo nuovi comandi
pageContents. Add(new GSave());

// Crea l'XForm
XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
doc.Pages[1].Resources.Forms.Add(form);
form.Contents.Add(new GSave());
// Imposta la larghezza e l'altezza dell'immagine
form.Contents.Add(new ConcatenateMatrix(200, 0, 0, 200, 0, 0));
// Carica l'immagine in un flusso
Stream imageStream = new FileStream(imageFile, FileMode.Open);
// Aggiungi l'immagine alla raccolta di immagini delle risorse XForm
form.Resources.Images.Add(imageStream);
XImage ximage = form.Resources.Images[form.Resources.Images.Count];
// Usando l'operatore Do: questo operatore disegna l'immagine
form.Contents.Add(new Do(ximage.Name));
form.Contents.Add(new GRestore());

pageContents. Add(new GSave());
// Posizionare l'XForm alle coordinate x=100 e y=500
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 500));
// Disegna l'XForm con l'operatore Do
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

pageContents. Add(new GSave());
// Posizionare l'XForm alle coordinate x=100 e y=300
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 300));
// Disegna l'XForm con l'operatore Do
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

// Ripristina lo stato della grafica con GRestore dopo GSave
pageContents. Add(new GRestore());
doc.Save(outFile);
}
```

Assicurati di specificare i percorsi file effettivi e regola il numero di pagina e le posizioni XForm secondo necessità.

### Esempio di codice sorgente per Draw XForm On Page utilizzando Aspose.PDF per .NET
 
```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string imageFile = dataDir+ "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
using (Document doc = new Document(inFile))
{
	OperatorCollection pageContents = doc.Pages[1].Contents;
	// Il campione dimostra
	// Utilizzo degli operatori GSave/GRestore
	// Utilizzo dell'operatore ContatenateMatrix per posizionare xForm
	// Utilizzare l'operatore per disegnare xForm sulla pagina
	// Racchiudi i contenuti esistenti con la coppia di operatori GSave/GRestore
	// questo per ottenere lo stato grafico iniziale alla fine dei contenuti esistenti
	// altrimenti potrebbero rimanere delle trasformazioni indesiderate alla fine della catena degli operatori esistenti
	pageContents.Insert(1, new Aspose.Pdf.Operators.GSave());
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// Aggiunto l'operatore di salvataggio dello stato della grafica per cancellare correttamente lo stato della grafica dopo i nuovi comandi
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	#region create xForm
	// Crea xForm
	XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
	doc.Pages[1].Resources.Forms.Add(form);
	form.Contents.Add(new Aspose.Pdf.Operators.GSave());
	// Definisci la larghezza e l'altezza dell'immagine
	form.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(200, 0, 0, 200, 0, 0));
	// Carica l'immagine nello stream
	Stream imageStream = new FileStream(imageFile, FileMode.Open);
	// Aggiungi l'immagine alla raccolta Images delle risorse XForm
	form.Resources.Images.Add(imageStream);
	XImage ximage = form.Resources.Images[form.Resources.Images.Count];
	// Utilizzo dell'operatore Do: questo operatore disegna un'immagine
	form.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
	form.Contents.Add(new Aspose.Pdf.Operators.GRestore());
	#endregion
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// Posiziona il modulo sulle coordinate x=100 y=500
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 500));
	// Disegna la forma con l'operatore Do
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// Posiziona il modulo sulle coordinate x=100 y=300
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 300));
	// Disegna la forma con l'operatore Do
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// Ripristina lo stato grafico con GRestore dopo il GSave
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	doc.Save(outFile);                
}

```

## Conclusione

In questo tutorial, hai imparato a disegnare un modulo XForm su una pagina PDF utilizzando Aspose.PDF per .NET. Seguendo i passaggi descritti, sarai in grado di aggiungere e posizionare un modulo XForm su una pagina esistente, dando così maggiore flessibilità ai tuoi documenti PDF.
