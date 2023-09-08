---
title: Disegna XForm sulla pagina
linktitle: Disegna XForm sulla pagina
second_title: Aspose.PDF per riferimento all'API .NET
description: Guida passo passo per disegnare un modulo XForm su una pagina PDF utilizzando Aspose.PDF per .NET. Aggiungi e posiziona il modulo sulla pagina.
type: docs
weight: 10
url: /it/net/programming-with-operators/draw-xform-on-page/
---
In questo tutorial ti forniremo una guida passo passo su come disegnare un XForm su una pagina utilizzando Aspose.PDF per .NET. Aspose.PDF è una potente libreria che ti consente di creare, manipolare e convertire documenti PDF a livello di codice. Utilizzando gli operatori forniti da Aspose.PDF, è possibile aggiungere e posizionare un modulo XForm su una pagina PDF esistente.

## Prerequisiti

Prima di iniziare, assicurati di disporre dei seguenti prerequisiti:

1. Visual Studio installato con .NET framework.
2. La libreria Aspose.PDF per .NET.

## Passaggio 1: impostazione del progetto

Per iniziare, crea un nuovo progetto in Visual Studio e aggiungi un riferimento alla libreria Aspose.PDF per .NET. Puoi scaricare la libreria dal sito Web ufficiale di Aspose e installarla sul tuo computer.

## Passaggio 2: importa gli spazi dei nomi necessari

Nel file di codice C#, importa gli spazi dei nomi richiesti per accedere alle classi e ai metodi forniti da Aspose.PDF:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

## Passaggio 3: impostazione dei percorsi dei file

Definire i percorsi dei file per l'immagine di sfondo, il file PDF di input e il file PDF di output:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string imageFile = dataDir + "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
```

Assicurati di specificare i percorsi effettivi dei file sul tuo computer.

## Passaggio 4: caricamento del file PDF di input

Utilizzare il seguente codice per caricare il file PDF di input:

```csharp
using (Document doc = new Document(inFile))
{
OperatorCollection pageContents = doc.Pages[1].Contents;
// Il codice seguente utilizza gli operatori GSave/GRestore
// Il codice utilizza l'operatore ContatenateMatrix per posizionare XForm
// Il codice utilizza l'operatore Do per disegnare l'XForm sulla pagina
// Gli operatori GSave/GRestore racchiudono il contenuto esistente
// questo viene fatto per ottenere lo stato grafico iniziale alla fine del contenuto esistente
// in caso contrario potrebbero rimanere trasformazioni indesiderate alla fine della catena degli operatori esistenti
pageContents. Insert(1, new GSave());
pageContents. Add(new GRestore());
// Aggiunto l'operatore GSave per reimpostare correttamente lo stato della grafica dopo nuovi comandi
pageContents. Add(new GSave());

// Crea l'XForm
XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
doc.Pages[1].Resources.Forms.Add(form);
form.Contents.Add(new GSave());
// Imposta la larghezza e l'altezza dell'immagine
form.Contents.Add(new ConcatenateMatrix(200, 0, 0, 200, 0, 0));
// Carica l'immagine in uno stream
Stream imageStream = new FileStream(imageFile, FileMode.Open);
// Aggiungi l'immagine alla raccolta di immagini di risorse XForm
form.Resources.Images.Add(imageStream);
XImage ximage = form.Resources.Images[form.Resources.Images.Count];
// Utilizzando l'operatore Do: questo operatore disegna l'immagine
form.Contents.Add(new Do(ximage.Name));
form.Contents.Add(new GRestore());

pageContents. Add(new GSave());
//Posiziona l'XForm alle coordinate x=100 e y=500
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 500));
// Disegna l'XForm con l'operatore Do
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

pageContents. Add(new GSave());
// Posiziona l'XForm alle coordinate x=100 e y=300
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 300));
// Disegna l'XForm con l'operatore Do
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

// Ripristina lo stato della grafica con GRestore dopo GSave
pageContents. Add(new GRestore());
doc.Save(outFile);
}
```

Assicurati di specificare i percorsi effettivi dei file e di regolare il numero di pagina e le posizioni XForm secondo necessità.

### Codice sorgente di esempio per Draw XForm On Page utilizzando Aspose.PDF per .NET
 
```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string imageFile = dataDir+ "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
using (Document doc = new Document(inFile))
{
	OperatorCollection pageContents = doc.Pages[1].Contents;
	// Il campione lo dimostra
	// Utilizzo degli operatori GSave/GRestore
	// Utilizzo dell'operatore ContatenateMatrix per posizionare xForm
	// Esegui l'utilizzo dell'operatore per disegnare xForm sulla pagina
	// Avvolgi i contenuti esistenti con la coppia di operatori GSave/GRestore
	// questo per ottenere lo stato grafico iniziale alla fine dei contenuti esistenti
	// altrimenti potrebbero permanere alcune trasformazioni indesiderate alla fine della catena degli operatori esistenti
	pageContents.Insert(1, new Aspose.Pdf.Operators.GSave());
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// Aggiunto l'operatore Salva stato grafico per cancellare correttamente lo stato grafico dopo nuovi comandi
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	#region create xForm
	// Crea xForm
	XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
	doc.Pages[1].Resources.Forms.Add(form);
	form.Contents.Add(new Aspose.Pdf.Operators.GSave());
	// Definire la larghezza e l'altezza dell'immagine
	form.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(200, 0, 0, 200, 0, 0));
	// Carica l'immagine nello stream
	Stream imageStream = new FileStream(imageFile, FileMode.Open);
	//Aggiungi un'immagine alla raccolta Images delle risorse XForm
	form.Resources.Images.Add(imageStream);
	XImage ximage = form.Resources.Images[form.Resources.Images.Count];
	// Utilizzo dell'operatore Do: questo operatore disegna l'immagine
	form.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
	form.Contents.Add(new Aspose.Pdf.Operators.GRestore());
	#endregion
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// Posiziona il modulo sulle coordinate x=100 y=500
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 500));
	// Disegna il modulo con l'operatore Do
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// Posiziona il modulo sulle coordinate x=100 y=300
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 300));
	// Disegna il modulo con l'operatore Do
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// Ripristina lo stato della grafica con GRestore dopo il GSave
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	doc.Save(outFile);                
}

```

## Conclusione

In questo tutorial, hai imparato come disegnare un modulo XForm su una pagina PDF utilizzando Aspose.PDF per .NET. Seguendo i passaggi descritti, potrai aggiungere e posizionare un modulo XForm su una pagina esistente, dando così maggiore flessibilità ai tuoi documenti PDF.

### Domande frequenti su Draw XForm a pagina

#### D: Cos'è un XForm in Aspose.PDF?

R: Un XForm è un oggetto grafico riutilizzabile in un documento PDF. Ti consente di definire e disegnare grafica, immagini o testo complessi che possono essere riutilizzati più volte su pagine diverse.

#### D: Come posso importare gli spazi dei nomi necessari per Aspose.PDF?

 R: Nel file di codice C#, utilizzare il file`using` direttiva per importare gli spazi dei nomi richiesti per accedere alle classi e ai metodi forniti da Aspose.PDF:
```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

#### D: Qual è lo scopo degli operatori GSave e GRestore?

 R: Il`GSave` E`GRestore`gli operatori in Aspose.PDF vengono utilizzati per salvare e ripristinare lo stato della grafica. Contribuiscono a garantire che le trasformazioni e le impostazioni applicate a una sezione del contenuto non influiscano sulle sezioni successive.

#### D: Come definisco un XForm utilizzando Aspose.PDF?

 R: Per creare un XForm, utilizzare il file`XForm.CreateNewForm` metodo e aggiungerlo al file`Resources.Forms` raccolta di una pagina specifica. È quindi possibile aggiungere contenuto agli XForm`Contents` proprietà.

#### D: Come posso disegnare un'immagine all'interno di un XForm?

 R: Carica l'immagine in uno stream e aggiungila al file`Resources.Images` raccolta dell'XForm. Usa il`Do` operatore all'interno dell'XForm`Contents` per disegnare l'immagine.

#### D: Come posso posizionare un XForm su una pagina PDF?

 R: Per posizionare un XForm su una pagina, utilizzare il file`ConcatenateMatrix` operatore all'interno della pagina`Contents`. Regolare i parametri della matrice per specificare la traslazione (posizione) e il ridimensionamento dell'XForm.

#### D: Posso disegnare più XForm sulla stessa pagina?

 R: Sì, puoi disegnare più XForm sulla stessa pagina regolando il file`ConcatenateMatrix`parametri per posizionare ciascun XForm a coordinate diverse.

#### D: Posso modificare il contenuto di un XForm dopo che è stato creato?

 R: Sì, puoi modificare il contenuto di un XForm dopo la creazione aggiungendovi ulteriori operatori`Contents` proprietà.

#### D: Cosa succede se ometto gli operatori GSave e GRestore?

R: L'omissione degli operatori GSave e GRestore può portare all'applicazione di trasformazioni o impostazioni indesiderate al contenuto successivo. Usarli aiuta a mantenere uno stato grafico pulito.

#### D: Posso riutilizzare gli XForm su pagine diverse del documento PDF?

 R: Sì, puoi riutilizzare gli XForm su più pagine aggiungendo lo stesso XForm al file`Resources.Forms` raccolta di pagine diverse.

#### D: Esiste un limite al numero di XForm che posso creare?

R: Anche se non esiste un limite rigido al numero di XForm che puoi creare, tieni presente che troppi XForm potrebbero influire sulle prestazioni e sull'utilizzo della memoria. Usateli con giudizio.

#### D: Posso ruotare un XForm o applicare altre trasformazioni?

 R: Sì, puoi utilizzare il`ConcatenateMatrix`operatore per applicare trasformazioni come rotazione, ridimensionamento e traslazione a un XForm.
