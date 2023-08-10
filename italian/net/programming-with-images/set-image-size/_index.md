---
title: Imposta la dimensione dell'immagine nel file PDF
linktitle: Imposta la dimensione dell'immagine nel file PDF
second_title: Aspose.PDF per riferimento API .NET
description: Guida passo-passo per impostare la dimensione di un'immagine nel file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 270
url: /it/net/programming-with-images/set-image-size/
---
In questo tutorial, ti illustreremo come impostare la dimensione di un'immagine in un file PDF utilizzando Aspose.PDF per .NET. Segui questi passaggi per eseguire facilmente questa operazione.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

- Visual Studio o qualsiasi altro ambiente di sviluppo installato e configurato.
- Conoscenza di base del linguaggio di programmazione C#.
- Libreria Aspose.PDF per .NET installata. Puoi scaricarlo dal sito ufficiale di Aspose.

## Passaggio 1: Creazione del documento PDF

Per iniziare, utilizza il seguente codice per creare un nuovo documento PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Crea un'istanza di un oggetto Document
Document doc = new Document();

// Aggiungi una pagina alla raccolta di pagine del file PDF
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Passaggio 2: immagine aggiunta

Successivamente, aggiungeremo un'immagine alla pagina del documento PDF. Usa il seguente codice:

```csharp
// Crea un'istanza di immagine
Aspose.Pdf.Image img = new Aspose.Pdf.Image();

// Imposta la larghezza e l'altezza dell'immagine in punti
img. FixWidth = 100;
img. FixHeight = 100;

// Imposta il tipo di immagine su sconosciuto (Sconosciuto)
img.FileType = Aspose.Pdf.ImageFileType.Unknown;

//Percorso del file di origine dell'immagine
img.File = dataDir + "aspose-logo.jpg";

// Aggiungi l'immagine alla raccolta di paragrafi della pagina
page.Paragraphs.Add(img);
```

Assicurati di fornire il percorso corretto al file di origine dell'immagine.

## Passaggio 3: impostazione delle proprietà della pagina

Infine, imposteremo le proprietà della pagina, inclusa la larghezza e l'altezza. Usa il seguente codice:

```csharp
// Imposta le proprietà della pagina
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
```

### Esempio di codice sorgente per Imposta dimensione immagine utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crea un'istanza dell'oggetto Document
Document doc = new Document();
// aggiungi pagina alla raccolta di pagine di file PDF
Aspose.Pdf.Page page = doc.Pages.Add();
// Crea un'istanza di immagine
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
// Imposta la larghezza e l'altezza dell'immagine in punti
img.FixWidth = 100;
img.FixHeight = 100;
// Imposta il tipo di immagine come SVG
img.FileType = Aspose.Pdf.ImageFileType.Unknown;
// Percorso per il file di origine
img.File = dataDir + "aspose-logo.jpg";
page.Paragraphs.Add(img);
//Imposta le proprietà della pagina
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
dataDir = dataDir + "SetImageSize_out.pdf";
// salvare il file PDF risultante
doc.Save(dataDir);
Console.WriteLine("\nImage size added successfully.\nFile saved at " + dataDir);
```

## Conclusione

Congratulazioni! Hai impostato correttamente la dimensione di un'immagine in un documento PDF utilizzando Aspose.PDF per .NET. Ora puoi applicare questo metodo ai tuoi progetti per regolare la dimensione delle immagini nei file PDF.

### Domande frequenti per impostare la dimensione dell'immagine nel file PDF

#### D: Qual è lo scopo di impostare la dimensione di un'immagine in un documento PDF utilizzando Aspose.PDF per .NET?

R: Lo scopo dell'impostazione delle dimensioni di un'immagine in un documento PDF è controllare le dimensioni dell'immagine quando viene aggiunta al PDF. Ciò consente di regolare l'aspetto e il layout delle immagini all'interno dei file PDF.

#### D: Come funziona il processo di impostazione delle dimensioni di un'immagine in un documento PDF?

 R: Il processo prevede la creazione di un file`Aspose.Pdf.Image` istanza, specificandone la larghezza e l'altezza utilizzando il file`FixWidth` E`FixHeight` properties e quindi aggiungere l'immagine al documento PDF. Inoltre, puoi impostare le dimensioni della pagina stessa per accogliere l'immagine.

#### D: Posso impostare la dimensione di un'immagine su una percentuale specifica delle dimensioni della pagina?

R: Il codice fornito imposta la larghezza e l'altezza assolute dell'immagine in punti. Se desideri impostare la dimensione di un'immagine in base a una percentuale delle dimensioni della pagina, dovrai calcolare le dimensioni di conseguenza e adattare il codice di conseguenza.

####  D: Qual è il significato del`FileType` property when adding an image to the PDF document?

 R: Il`FileType`La proprietà specifica il tipo di immagine da aggiungere al documento PDF. Nel codice fornito, il valore`Unknown` indica che il tipo di immagine è sconosciuto e Aspose.PDF tenterà di determinare il tipo di immagine in base all'estensione del file.

#### D: Posso aggiungere più immagini a una singola pagina utilizzando questo metodo?

 R: Sì, puoi aggiungere più immagini a una singola pagina creando più immagini`Aspose.Pdf.Image` istanze e aggiungendole alla raccolta di paragrafi della pagina. Assicurati di regolare il posizionamento e il layout delle immagini secondo necessità.

#### D: Come posso controllare il posizionamento e l'allineamento dell'immagine aggiunta sulla pagina?

 R: Il posizionamento e l'allineamento dell'immagine aggiunta possono essere controllati regolando le coordinate e il layout dell'immagine utilizzando proprietà come`img.Left`, `img.Top`e proprietà di formattazione del paragrafo.

####  D: Qual è lo scopo dell'impostazione delle proprietà della pagina utilizzando`page.PageInfo.Width` and `page.PageInfo.Height`?

R: L'impostazione delle proprietà della pagina consente di definire le dimensioni della pagina stessa. Ciò garantisce che le dimensioni della pagina si adattino all'immagine aggiunta e a qualsiasi altro contenuto che potresti avere sulla pagina.

#### D: Posso impostare dimensioni diverse per immagini diverse all'interno dello stesso documento PDF?

 A: Sì, puoi impostare dimensioni diverse per immagini diverse creando immagini separate`Aspose.Pdf.Image` istanze e regolazione del`FixWidth`, `FixHeight`e proprietà di posizionamento per ogni immagine.

#### D: Come posso integrare questo metodo nei miei progetti per impostare le dimensioni delle immagini nei file PDF?

R: Per integrare questo metodo nei tuoi progetti, segui i passaggi descritti e modifica il codice secondo necessità. È possibile utilizzare questo metodo per aggiungere immagini di dimensioni specifiche ai documenti PDF in base ai requisiti dell'applicazione.