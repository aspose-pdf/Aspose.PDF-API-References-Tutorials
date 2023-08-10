---
title: Crea PDF con immagine taggata
linktitle: Crea PDF con immagine taggata
second_title: Aspose.PDF per riferimento API .NET
description: Guida passo passo per creare PDF con immagine contrassegnata utilizzando Aspose.PDF per .NET.
type: docs
weight: 40
url: /it/net/programming-with-tagged-pdf/create-pdf-with-tagged-image/
---
In questo tutorial, ti forniremo una guida passo-passo su come creare un documento PDF con un'immagine con tag utilizzando Aspose.PDF per .NET. Aspose.PDF è una potente libreria che consente di creare, manipolare e convertire documenti PDF in modo programmatico. Utilizzando le funzionalità della struttura del contenuto con tag di Aspose.PDF, è possibile aggiungere immagini con tag al documento PDF.

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
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## Passaggio 3: creazione del documento PDF con un'immagine contrassegnata

Utilizzare il seguente codice per creare un documento PDF con un'immagine contrassegnata:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Creating a PDF with a tagged image");
taggedContent.SetLanguage("fr-FR");

IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
figure1.AlternativeText = "Aspose Logo";
figure1.Title = "Picture 1";
figure1.SetTag("Fig");
figure1.SetImage(dataDir + @"aspose-logo.jpg");
```

Questo codice crea un documento PDF vuoto e aggiunge un'immagine con tag utilizzando i metodi forniti da Aspose.PDF. L'immagine è specificata con testo alternativo, titolo e tag.

## Passaggio 4: salvare il documento PDF

Utilizzare il seguente codice per salvare il documento PDF:

```csharp
document.Save(dataDir + "PDFwithTaggedImage.pdf");
```

Questo codice salva il documento PDF con l'immagine contrassegnata in un file specificato.

### Esempio di codice sorgente per Crea PDF con immagine con tag utilizzando Aspose.PDF per .NET 
```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("CreatePDFwithTaggedImage");
taggedContent.SetLanguage("en-US");
IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
figure1.AlternativeText = "Aspose Logo";
figure1.Title = "Image 1";
figure1.SetTag("Fig");
// Aggiungi immagine con risoluzione 300 DPI (per impostazione predefinita)
figure1.SetImage(dataDir + @"aspose-logo.jpg");
// Salva documento PDF
document.Save(dataDir + "PDFwithTaggedImage.pdf");

```

## Conclusione

In questo tutorial, hai imparato come creare un documento PDF con un'immagine con tag utilizzando Aspose.PDF per .NET. Le immagini con tag aggiungono ulteriori informazioni strutturate al tuo documento PDF.

### FAQ

#### D: Qual è lo scopo della creazione di un documento PDF con un'immagine contrassegnata utilizzando Aspose.PDF per .NET?

R: La creazione di un documento PDF con un'immagine con tag utilizzando Aspose.PDF per .NET consente di aggiungere immagini con tag al contenuto del documento. Le immagini con tag forniscono informazioni strutturate, come testo alternativo e titoli, migliorando l'accessibilità e l'organizzazione.

#### D: In che modo la libreria Aspose.PDF aiuta nella creazione di un documento PDF con un'immagine contrassegnata?

R: Aspose.PDF per .NET è una solida libreria che fornisce funzionalità per la creazione, la manipolazione e la conversione di documenti PDF in modo programmatico. In questa esercitazione, le funzionalità della struttura del contenuto con tag della libreria vengono utilizzate per aggiungere un'immagine con tag al documento PDF.

#### D: Quali sono i prerequisiti per la creazione di un documento PDF con un'immagine contrassegnata utilizzando Aspose.PDF per .NET?

R: Prima di iniziare, assicurati di aver installato Visual Studio con .NET Framework e di avere la libreria Aspose.PDF per .NET referenziata nel tuo progetto.

#### D: In che modo il codice C# fornito crea un documento PDF con un'immagine con tag?

R: Il codice mostra come creare un documento PDF, definire un elemento immagine con tag e aggiungerlo al contenuto del documento. L'immagine con tag include testo alternativo, un titolo e un tag utilizzando i metodi forniti da Aspose.PDF.

#### D: Posso utilizzare diversi formati di immagine per l'immagine taggata?

R: Sì, puoi utilizzare diversi formati di immagine per l'immagine con tag, come JPEG, PNG, GIF, ecc. L'esempio di codice fornito nel tutorial utilizza un'immagine JPEG, ma puoi sostituirla con il percorso di un file immagine in il tuo formato preferito.

#### D: Come viene utilizzato il testo alternativo (alt text) nelle immagini contrassegnate?

 R: Il testo alternativo fornisce una descrizione testuale dell'immagine, che viene letta ad alta voce dagli screen reader per gli utenti ipovedenti. Nel codice fornito, il testo alternativo viene impostato utilizzando il file`AlternativeText` proprietà del`IllustrationElement` che rappresenta l'immagine contrassegnata.

####  D: Come funziona il`SetTitle` method contribute to the PDF document's tagged image?

 R: Il`SetTitle` Il metodo imposta il titolo del contenuto con tag del documento PDF, fornendo un contesto aggiuntivo per l'immagine con tag. Questo titolo può aiutare a identificare lo scopo o l'oggetto del contenuto taggato.

#### D: Posso personalizzare il tag e il titolo dell'immagine taggata?

 R: Sì, puoi personalizzare il tag e il titolo dell'immagine taggata utilizzando il file`SetTag` E`Title` metodi del`IllustrationElement`. L'esempio di codice mostra come impostare il tag su "Fig" e il titolo su "Picture 1".

#### D: Come posso assicurarmi che l'immagine taggata sia accessibile e conforme agli standard di accessibilità?

R: Utilizzando le caratteristiche della struttura del contenuto con tag di Aspose.PDF e fornendo testo alternativo e altre informazioni pertinenti, contribuisci all'accessibilità dell'immagine con tag. Garantire la conformità agli standard di accessibilità implica seguire le migliori pratiche per il testo alternativo e la struttura del documento.

#### D: È possibile aggiungere più immagini con tag allo stesso documento PDF utilizzando tecniche simili?

 R: Sì, puoi aggiungere più immagini con tag allo stesso documento PDF utilizzando tecniche simili. Creeresti ulteriori`IllustrationElement` istanze per ogni immagine contrassegnata e personalizzarne le proprietà in base alle esigenze.