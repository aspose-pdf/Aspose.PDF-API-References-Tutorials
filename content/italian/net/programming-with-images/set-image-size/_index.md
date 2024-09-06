---
title: Imposta la dimensione dell'immagine nel file PDF
linktitle: Imposta la dimensione dell'immagine nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Guida passo passo per impostare la dimensione di un'immagine in un file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 270
url: /it/net/programming-with-images/set-image-size/
---
In questo tutorial, ti guideremo attraverso come impostare la dimensione di un'immagine in un file PDF usando Aspose.PDF per .NET. Segui questi passaggi per eseguire questa operazione facilmente.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

- Visual Studio o qualsiasi altro ambiente di sviluppo installato e configurato.
- Conoscenza di base del linguaggio di programmazione C#.
- Libreria Aspose.PDF per .NET installata. Puoi scaricarla dal sito ufficiale di Aspose.

## Fase 1: Creazione del documento PDF

Per iniziare, utilizza il seguente codice per creare un nuovo documento PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Istanziare un oggetto Documento
Document doc = new Document();

// Aggiungere una pagina alla raccolta di pagine del file PDF
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Passaggio 2: aggiunta immagine

Successivamente, aggiungeremo un'immagine alla pagina del documento PDF. Utilizza il seguente codice:

```csharp
// Crea un'istanza di immagine
Aspose.Pdf.Image img = new Aspose.Pdf.Image();

// Imposta la larghezza e l'altezza dell'immagine in punti
img. FixWidth = 100;
img. FixHeight = 100;

//Imposta il tipo di immagine su sconosciuto (Sconosciuto)
img.FileType = Aspose.Pdf.ImageFileType.Unknown;

// Percorso al file sorgente dell'immagine
img.File = dataDir + "aspose-logo.jpg";

// Aggiungere l'immagine alla raccolta di paragrafi della pagina
page.Paragraphs.Add(img);
```

Assicuratevi di fornire il percorso corretto al file sorgente dell'immagine.

## Passaggio 3: impostazione delle proprietà della pagina

Infine, imposteremo le proprietà della pagina, tra cui larghezza e altezza. Utilizza il seguente codice:

```csharp
// Imposta le proprietà della pagina
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
```

### Esempio di codice sorgente per impostare le dimensioni dell'immagine utilizzando Aspose.PDF per .NET 
```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crea un'istanza dell'oggetto Documento
Document doc = new Document();
// aggiungi pagina alla raccolta di pagine del file PDF
Aspose.Pdf.Page page = doc.Pages.Add();
// Crea un'istanza di immagine
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
// Imposta la larghezza e l'altezza dell'immagine in punti
img.FixWidth = 100;
img.FixHeight = 100;
// Imposta il tipo di immagine come SVG
img.FileType = Aspose.Pdf.ImageFileType.Unknown;
// Percorso per il file sorgente
img.File = dataDir + "aspose-logo.jpg";
page.Paragraphs.Add(img);
//Imposta le proprietà della pagina
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
dataDir = dataDir + "SetImageSize_out.pdf";
// salva il file PDF risultante
doc.Save(dataDir);
Console.WriteLine("\nImage size added successfully.\nFile saved at " + dataDir);
```

## Conclusione

Congratulazioni! Hai impostato con successo la dimensione di un'immagine in un documento PDF usando Aspose.PDF per .NET. Ora puoi applicare questo metodo ai tuoi progetti per regolare la dimensione delle immagini nei file PDF.

### FAQ per impostare la dimensione dell'immagine nel file PDF

#### D: Qual è lo scopo dell'impostazione della dimensione di un'immagine in un documento PDF utilizzando Aspose.PDF per .NET?

R: Lo scopo dell'impostazione delle dimensioni di un'immagine in un documento PDF è di controllare le dimensioni dell'immagine quando viene aggiunta al PDF. Ciò consente di regolare l'aspetto e il layout delle immagini nei file PDF.

#### D: Come funziona il processo di impostazione delle dimensioni di un'immagine in un documento PDF?

 A: Il processo prevede la creazione di un`Aspose.Pdf.Image` istanza, specificandone larghezza e altezza utilizzando il`FixWidth` E`FixHeight` proprietà, e quindi aggiungendo l'immagine al documento PDF. Inoltre, puoi impostare le dimensioni della pagina stessa per adattarle all'immagine.

#### D: Posso impostare la dimensione di un'immagine su una percentuale specifica delle dimensioni della pagina?

A: Il codice fornito imposta la larghezza e l'altezza assolute dell'immagine in punti. Se vuoi impostare la dimensione di un'immagine in base a una percentuale delle dimensioni della pagina, dovrai calcolare le dimensioni di conseguenza e adattare il codice di conseguenza.

####  D: Qual è il significato del`FileType` property when adding an image to the PDF document?

 A: Il`FileType`proprietà specifica il tipo di immagine che viene aggiunta al documento PDF. Nel codice fornito, il valore`Unknown` indica che il tipo di immagine è sconosciuto e Aspose.PDF tenterà di determinarlo in base all'estensione del file.

#### D: Posso aggiungere più immagini a una singola pagina utilizzando questo metodo?

 A: Sì, puoi aggiungere più immagini a una singola pagina creando più`Aspose.Pdf.Image` istanze e aggiungendole alla raccolta di paragrafi della pagina. Assicurati di regolare il posizionamento e il layout delle immagini come necessario.

#### D: Come posso controllare il posizionamento e l'allineamento dell'immagine aggiunta sulla pagina?

 A: Il posizionamento e l'allineamento dell'immagine aggiunta possono essere controllati regolando le coordinate e il layout dell'immagine utilizzando proprietà come`img.Left`, `img.Top`e proprietà di formattazione del paragrafo.

####  D: Qual è lo scopo dell'impostazione delle proprietà della pagina utilizzando`page.PageInfo.Width` and `page.PageInfo.Height`?

A: Impostando le proprietà della pagina puoi definire le dimensioni della pagina stessa. Questo assicura che le dimensioni della pagina siano adatte all'immagine aggiunta e a qualsiasi altro contenuto tu possa avere sulla pagina.

#### D: Posso impostare dimensioni diverse per immagini diverse all'interno dello stesso documento PDF?

 A: Sì, puoi impostare dimensioni diverse per immagini diverse creando file separati`Aspose.Pdf.Image` istanze e regolazione del`FixWidth`, `FixHeight`e proprietà di posizionamento per ciascuna immagine.

#### D: Come posso integrare questo metodo nei miei progetti per impostare le dimensioni delle immagini nei file PDF?

R: Per integrare questo metodo nei tuoi progetti, segui i passaggi descritti e modifica il codice come necessario. Puoi usare questo metodo per aggiungere immagini di dimensioni specifiche ai tuoi documenti PDF in base ai requisiti della tua applicazione.