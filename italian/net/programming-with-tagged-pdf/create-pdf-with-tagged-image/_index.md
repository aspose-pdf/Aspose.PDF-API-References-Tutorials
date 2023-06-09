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
