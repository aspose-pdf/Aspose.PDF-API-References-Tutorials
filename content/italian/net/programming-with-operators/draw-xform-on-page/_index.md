---
title: Disegna XForm sulla pagina
linktitle: Disegna XForm sulla pagina
second_title: Riferimento API Aspose.PDF per .NET
description: Guida passo passo per disegnare un modulo XForm su una pagina PDF usando Aspose.PDF per .NET. Aggiungere e posizionare il modulo sulla pagina.
type: docs
weight: 10
url: /it/net/programming-with-operators/draw-xform-on-page/
---
In questo tutorial, ti forniremo una guida passo-passo su come disegnare un XForm su una pagina usando Aspose.PDF per .NET. Aspose.PDF è una potente libreria che ti consente di creare, manipolare e convertire documenti PDF a livello di programmazione. Utilizzando gli operatori forniti da Aspose.PDF, puoi aggiungere e posizionare un modulo XForm su una pagina PDF esistente.

## Prerequisiti

Prima di iniziare, assicurati di avere i seguenti prerequisiti:

1. Visual Studio installato con .NET Framework.
2. La libreria Aspose.PDF per .NET.

## Fase 1: Impostazione del progetto

Per iniziare, crea un nuovo progetto in Visual Studio e aggiungi un riferimento alla libreria Aspose.PDF per .NET. Puoi scaricare la libreria dal sito Web ufficiale di Aspose e installarla sul tuo computer.

## Passaggio 2: importare gli spazi dei nomi necessari

Nel file di codice C#, importa gli spazi dei nomi necessari per accedere alle classi e ai metodi forniti da Aspose.PDF:

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

Assicuratevi di specificare i percorsi effettivi dei file sul vostro computer.

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
//questo viene fatto per ottenere lo stato grafico iniziale alla fine del contenuto esistente
// altrimenti potrebbero esserci delle trasformazioni indesiderate rimaste alla fine della catena degli operatori esistenti
pageContents. Insert(1, new GSave());
pageContents. Add(new GRestore());
// Aggiungere l'operatore GSave per ripristinare correttamente lo stato della grafica dopo nuovi comandi
pageContents. Add(new GSave());

// Crea l'XForm
XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
doc.Pages[1].Resources.Forms.Add(form);
form.Contents.Add(new GSave());
// Imposta la larghezza e l'altezza dell'immagine
form.Contents.Add(new ConcatenateMatrix(200, 0, 0, 200, 0, 0));
// Carica l'immagine in un flusso
Stream imageStream = new FileStream(imageFile, FileMode.Open);
// Aggiungere l'immagine alla raccolta di immagini di risorse XForm
form.Resources.Images.Add(imageStream);
XImage ximage = form.Resources.Images[form.Resources.Images.Count];
// Utilizzo dell'operatore Do: questo operatore disegna l'immagine
form.Contents.Add(new Do(ximage.Name));
form.Contents.Add(new GRestore());

pageContents. Add(new GSave());
// Posizionare XForm alle coordinate x=100 e y=500
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 500));
// Disegna l'XForm con l'operatore Do
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

pageContents. Add(new GSave());
// Posizionare XForm alle coordinate x=100 e y=300
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 300));
// Disegna l'XForm con l'operatore Do
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

// Ripristina lo stato della grafica con GRestore dopo GSave
pageContents. Add(new GRestore());
doc.Save(outFile);
}
```

Assicuratevi di specificare i percorsi effettivi dei file e di modificare il numero di pagina e le posizioni XForm secondo necessità.

### Esempio di codice sorgente per disegnare XForm sulla pagina utilizzando Aspose.PDF per .NET
 
```csharp

// Percorso verso la directory dei documenti.
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
	//Utilizzare l'operatore per disegnare xForm sulla pagina
	// Avvolgere i contenuti esistenti con la coppia di operatori GSave/GRestore
	// questo serve per ottenere lo stato grafico iniziale alla fine dei contenuti esistenti
	// altrimenti potrebbero rimanere alcune trasformazioni indesiderate alla fine della catena degli operatori esistenti
	pageContents.Insert(1, new Aspose.Pdf.Operators.GSave());
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// Aggiungere l'operatore di salvataggio dello stato grafico per cancellare correttamente lo stato grafico dopo nuovi comandi
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	#region create xForm
	// Crea xForm
	XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
	doc.Pages[1].Resources.Forms.Add(form);
	form.Contents.Add(new Aspose.Pdf.Operators.GSave());
	// Definisci larghezza e altezza dell'immagine
	form.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(200, 0, 0, 200, 0, 0));
	// Carica l'immagine nel flusso
	Stream imageStream = new FileStream(imageFile, FileMode.Open);
	// Aggiungi immagine alla raccolta Immagini delle Risorse XForm
	form.Resources.Images.Add(imageStream);
	XImage ximage = form.Resources.Images[form.Resources.Images.Count];
	// Utilizzo dell'operatore Do: questo operatore disegna l'immagine
	form.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
	form.Contents.Add(new Aspose.Pdf.Operators.GRestore());
	#endregion
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// Posizionare il modulo sulle coordinate x=100 y=500
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 500));
	// Disegna il modulo con l'operatore Do
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// Posizionare il modulo sulle coordinate x=100 y=300
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 300));
	// Disegna il modulo con l'operatore Do
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// Ripristina lo stato grafico con GRestore dopo GSave
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	doc.Save(outFile);                
}

```

## Conclusione

In questo tutorial, hai imparato come disegnare un modulo XForm su una pagina PDF usando Aspose.PDF per .NET. Seguendo i passaggi descritti, sarai in grado di aggiungere e posizionare un modulo XForm su una pagina esistente, dando così maggiore flessibilità ai tuoi documenti PDF.

### FAQ per disegnare XForm sulla pagina

#### D: Che cos'è un XForm in Aspose.PDF?

R: Un XForm è un oggetto grafico riutilizzabile in un documento PDF. Consente di definire e disegnare grafica, immagini o testo complessi che possono essere riutilizzati più volte su pagine diverse.

#### D: Come posso importare gli spazi dei nomi necessari per Aspose.PDF?

 A: Nel tuo file di codice C#, usa`using` direttiva per importare gli spazi dei nomi richiesti per accedere alle classi e ai metodi forniti da Aspose.PDF:
```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

#### D: Qual è lo scopo degli operatori GSave e GRestore?

 A: Il`GSave` E`GRestore` operatori in Aspose.PDF vengono utilizzati per salvare e ripristinare lo stato della grafica. Contribuiscono a garantire che le trasformazioni e le impostazioni applicate a una sezione del contenuto non influiscano sulle sezioni successive.

#### D: Come si definisce un XForm utilizzando Aspose.PDF?

 A: Per creare un XForm, utilizzare`XForm.CreateNewForm` metodo e aggiungerlo al`Resources.Forms` raccolta di una pagina specifica. Puoi quindi aggiungere contenuti al XForm`Contents` proprietà.

#### D: Come posso disegnare un'immagine in un XForm?

A: Carica l'immagine in un flusso e aggiungila al`Resources.Images` raccolta di XForm. Utilizzare il`Do` operatore all'interno di XForm`Contents` per disegnare l'immagine.

#### D: Come posso posizionare un XForm su una pagina PDF?

 A: Per posizionare un XForm su una pagina, utilizzare`ConcatenateMatrix` operatore all'interno della pagina`Contents`. Regolare i parametri della matrice per specificare la traslazione (posizione) e il ridimensionamento dell'XForm.

#### D: Posso disegnare più XForm sulla stessa pagina?

 A: Sì, puoi disegnare più XForm sulla stessa pagina regolando il`ConcatenateMatrix` parametri per posizionare ogni XForm su coordinate diverse.

#### D: Posso modificare il contenuto di un XForm dopo averlo creato?

 A: Sì, puoi modificare il contenuto di un XForm dopo la creazione aggiungendo operatori aggiuntivi al suo`Contents` proprietà.

#### D: Cosa succede se ometto gli operatori GSave e GRestore?

R: L'omissione degli operatori GSave e GRestore può portare all'applicazione di trasformazioni o impostazioni indesiderate al contenuto successivo. Il loro utilizzo aiuta a mantenere uno stato grafico pulito.

#### D: Posso riutilizzare XForms in diverse pagine del documento PDF?

 A: Sì, puoi riutilizzare gli XForm su più pagine aggiungendo lo stesso XForm al`Resources.Forms` raccolta di pagine diverse.

#### D: Esiste un limite al numero di XForm che posso creare?

R: Sebbene non vi sia un limite rigoroso al numero di XForm che puoi creare, tieni presente che troppi XForm potrebbero avere un impatto sulle prestazioni e sull'utilizzo della memoria. Usali giudiziosamente.

#### D: Posso ruotare un XForm o applicare altre trasformazioni?

 A: Sì, puoi usare il`ConcatenateMatrix` Operatore per applicare trasformazioni quali rotazione, ridimensionamento e traslazione a un XForm.
