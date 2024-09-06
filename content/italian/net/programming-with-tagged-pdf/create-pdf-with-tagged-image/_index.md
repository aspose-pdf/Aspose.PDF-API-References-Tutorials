---
title: Crea PDF con immagine taggata
linktitle: Crea PDF con immagine taggata
second_title: Riferimento API Aspose.PDF per .NET
description: Guida passo passo per creare un PDF con immagini taggate utilizzando Aspose.PDF per .NET.
type: docs
weight: 40
url: /it/net/programming-with-tagged-pdf/create-pdf-with-tagged-image/
---
In questo tutorial, ti forniremo una guida passo passo su come creare un documento PDF con un'immagine taggata usando Aspose.PDF per .NET. Aspose.PDF è una potente libreria che ti consente di creare, manipolare e convertire documenti PDF in modo programmatico. Utilizzando le funzionalità di struttura del contenuto taggato di Aspose.PDF, puoi aggiungere immagini taggate al tuo documento PDF.

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
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## Fase 3: Creazione del documento PDF con un'immagine taggata

Utilizzare il seguente codice per creare un documento PDF con un'immagine taggata:

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

Questo codice crea un documento PDF vuoto e aggiunge un'immagine taggata usando i metodi forniti da Aspose.PDF. L'immagine è specificata con testo alt, titolo e tag.

## Passaggio 4: salvataggio del documento PDF

Utilizzare il seguente codice per salvare il documento PDF:

```csharp
document.Save(dataDir + "PDFwithTaggedImage.pdf");
```

Questo codice salva il documento PDF con l'immagine taggata in un file specificato.

### Esempio di codice sorgente per creare PDF con immagine taggata utilizzando Aspose.PDF per .NET 
```csharp

// Percorso verso la directory dei documenti.
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
// Aggiungi immagine con risoluzione 300 DPI (di default)
figure1.SetImage(dataDir + @"aspose-logo.jpg");
// Salva documento PDF
document.Save(dataDir + "PDFwithTaggedImage.pdf");

```

## Conclusione

In questo tutorial, hai imparato come creare un documento PDF con un'immagine taggata usando Aspose.PDF per .NET. Le immagini taggate aggiungono informazioni aggiuntive e strutturate al tuo documento PDF.

### Domande frequenti

#### D: Qual è lo scopo della creazione di un documento PDF con un'immagine taggata utilizzando Aspose.PDF per .NET?

R: Creare un documento PDF con un'immagine taggata usando Aspose.PDF per .NET consente di aggiungere immagini taggate al contenuto del documento. Le immagini taggate forniscono informazioni strutturate, come testo alternativo e titoli, migliorando l'accessibilità e l'organizzazione.

#### D: In che modo la libreria Aspose.PDF aiuta a creare un documento PDF con un'immagine taggata?

R: Aspose.PDF per .NET è una libreria robusta che fornisce funzionalità per creare, manipolare e convertire documenti PDF a livello di programmazione. In questo tutorial, le funzionalità di struttura del contenuto taggato della libreria vengono utilizzate per aggiungere un'immagine taggata al documento PDF.

#### D: Quali sono i prerequisiti per creare un documento PDF con un'immagine taggata utilizzando Aspose.PDF per .NET?

R: Prima di iniziare, assicurati di aver installato Visual Studio con .NET Framework e di aver fatto riferimento alla libreria Aspose.PDF per .NET nel tuo progetto.

#### D: In che modo il codice C# fornito crea un documento PDF con un'immagine taggata?

R: Il codice dimostra come creare un documento PDF, definire un elemento immagine taggato e aggiungerlo al contenuto del documento. L'immagine taggata include testo alternativo, un titolo e un tag utilizzando metodi forniti da Aspose.PDF.

#### D: Posso usare formati immagine diversi per l'immagine taggata?

R: Sì, puoi utilizzare diversi formati di immagine per l'immagine taggata, come JPEG, PNG, GIF, ecc. L'esempio di codice fornito nel tutorial utilizza un'immagine JPEG, ma puoi sostituirlo con il percorso di un file immagine nel formato che preferisci.

#### D: Come viene utilizzato il testo alternativo (alt text) nelle immagini taggate?

 A: Il testo alternativo fornisce una descrizione testuale dell'immagine, che viene letta ad alta voce dagli screen reader per gli utenti ipovedenti. Nel codice fornito, il testo alternativo viene impostato utilizzando`AlternativeText` proprietà del`IllustrationElement` che rappresenta l'immagine taggata.

####  D: Come funziona il`SetTitle` method contribute to the PDF document's tagged image?

 A: Il`SetTitle` imposta il titolo del contenuto taggato del documento PDF, fornendo contesto aggiuntivo per l'immagine taggata. Questo titolo può aiutare a identificare lo scopo o l'oggetto del contenuto taggato.

#### D: Posso personalizzare il tag e il titolo dell'immagine taggata?

 A: Sì, puoi personalizzare il tag e il titolo dell'immagine taggata utilizzando`SetTag` E`Title` metodi di`IllustrationElement`L'esempio di codice mostra come impostare il tag su "Fig" e il titolo su "Immagine 1".

#### D: Come posso assicurarmi che l'immagine taggata sia accessibile e conforme agli standard di accessibilità?

R: Utilizzando le funzionalità di struttura del contenuto taggato di Aspose.PDF e fornendo testo alternativo e altre informazioni pertinenti, contribuisci all'accessibilità dell'immagine taggata. Garantire la conformità agli standard di accessibilità implica seguire le best practice per il testo alternativo e la struttura del documento.

#### D: È possibile aggiungere più immagini taggate allo stesso documento PDF utilizzando tecniche simili?

 R: Sì, puoi aggiungere più immagini taggate allo stesso documento PDF utilizzando tecniche simili. Creeresti ulteriori`IllustrationElement` istanze per ogni immagine taggata e personalizzarne le proprietà in base alle esigenze.