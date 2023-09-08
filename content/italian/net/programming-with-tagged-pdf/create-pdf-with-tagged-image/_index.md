---
title: Crea PDF con immagine contrassegnata
linktitle: Crea PDF con immagine contrassegnata
second_title: Aspose.PDF per riferimento all'API .NET
description: Guida passo passo per creare PDF con immagini contrassegnate utilizzando Aspose.PDF per .NET.
type: docs
weight: 40
url: /it/net/programming-with-tagged-pdf/create-pdf-with-tagged-image/
---
In questo tutorial, ti forniremo una guida passo passo su come creare un documento PDF con un'immagine taggata utilizzando Aspose.PDF per .NET. Aspose.PDF è una potente libreria che ti consente di creare, manipolare e convertire documenti PDF a livello di codice. Utilizzando le funzionalità della struttura del contenuto con tag di Aspose.PDF, puoi aggiungere immagini taggate al tuo documento PDF.

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
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## Passaggio 3: creazione del documento PDF con un'immagine contrassegnata

Utilizza il codice seguente per creare un documento PDF con un'immagine taggata:

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

Questo codice crea un documento PDF vuoto e aggiunge un'immagine taggata utilizzando i metodi forniti da Aspose.PDF. L'immagine è specificata con testo alternativo, titolo e tag.

## Passaggio 4: salvataggio del documento PDF

Utilizzare il seguente codice per salvare il documento PDF:

```csharp
document.Save(dataDir + "PDFwithTaggedImage.pdf");
```

Questo codice salva il documento PDF con l'immagine taggata in un file specificato.

### Codice sorgente di esempio per Crea PDF con immagine contrassegnata utilizzando Aspose.PDF per .NET 
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

In questo tutorial, hai imparato come creare un documento PDF con un'immagine contrassegnata utilizzando Aspose.PDF per .NET. Le immagini contrassegnate aggiungono ulteriori informazioni strutturate al tuo documento PDF.

### Domande frequenti

#### D: Qual è lo scopo di creare un documento PDF con un'immagine taggata utilizzando Aspose.PDF per .NET?

R: La creazione di un documento PDF con un'immagine contrassegnata utilizzando Aspose.PDF per .NET consente di aggiungere immagini contrassegnate al contenuto del documento. Le immagini contrassegnate forniscono informazioni strutturate, come testo alternativo e titoli, migliorando l'accessibilità e l'organizzazione.

#### D: In che modo la libreria Aspose.PDF aiuta nella creazione di un documento PDF con un'immagine contrassegnata?

R: Aspose.PDF per .NET è una solida libreria che fornisce funzionalità per creare, manipolare e convertire documenti PDF a livello di codice. In questo tutorial, le funzionalità della struttura del contenuto con tag della libreria vengono utilizzate per aggiungere un'immagine con tag al documento PDF.

#### D: Quali sono i prerequisiti per creare un documento PDF con un'immagine contrassegnata utilizzando Aspose.PDF per .NET?

R: Prima di iniziare, assicurati di avere Visual Studio installato con .NET Framework e di avere la libreria Aspose.PDF per .NET referenziata nel tuo progetto.

#### D: in che modo il codice C# fornito crea un documento PDF con un'immagine contrassegnata?

R: Il codice dimostra come creare un documento PDF, definire un elemento immagine con tag e aggiungerlo al contenuto del documento. L'immagine taggata include testo alternativo, un titolo e un tag utilizzando i metodi forniti da Aspose.PDF.

#### D: Posso utilizzare formati immagine diversi per l'immagine taggata?

R: Sì, puoi utilizzare diversi formati immagine per l'immagine taggata, come JPEG, PNG, GIF, ecc. L'esempio di codice fornito nel tutorial utilizza un'immagine JPEG, ma puoi sostituirla con il percorso di un file immagine in il tuo formato preferito.

#### D: Come viene utilizzato il testo alternativo (testo alternativo) nelle immagini contrassegnate?

 R: Il testo alternativo fornisce una descrizione testuale dell'immagine, che viene letta ad alta voce dagli screen reader per gli utenti ipovedenti. Nel codice fornito, il testo alternativo viene impostato utilizzando il comando`AlternativeText` proprietà del`IllustrationElement` che rappresenta l'immagine taggata.

####  D: Come funziona il`SetTitle` method contribute to the PDF document's tagged image?

 R: Il`SetTitle` Il metodo imposta il titolo del contenuto taggato del documento PDF, fornendo contesto aggiuntivo per l'immagine taggata. Questo titolo può aiutare a identificare lo scopo o l'oggetto del contenuto taggato.

#### D: Posso personalizzare il tag e il titolo dell'immagine taggata?

 R: Sì, puoi personalizzare il tag e il titolo dell'immagine taggata utilizzando il file`SetTag` E`Title` metodi del`IllustrationElement`. L'esempio di codice mostra come impostare il tag su "Fig" e il titolo su "Immagine 1".

#### D: Come posso garantire che l'immagine taggata sia accessibile e conforme agli standard di accessibilità?

R: Utilizzando le funzionalità della struttura del contenuto con tag di Aspose.PDF e fornendo testo alternativo e altre informazioni pertinenti, contribuisci all'accessibilità dell'immagine taggata. Garantire la conformità agli standard di accessibilità implica seguire le migliori pratiche per il testo alternativo e la struttura del documento.

#### D: È possibile aggiungere più immagini contrassegnate allo stesso documento PDF utilizzando tecniche simili?

 R: Sì, puoi aggiungere più immagini taggate allo stesso documento PDF utilizzando tecniche simili. Creeresti ulteriori`IllustrationElement` istanze per ogni immagine taggata e personalizzarne le proprietà secondo necessità.