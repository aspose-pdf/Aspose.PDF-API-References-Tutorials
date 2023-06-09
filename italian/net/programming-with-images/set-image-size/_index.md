---
title: Imposta la dimensione dell'immagine
linktitle: Imposta la dimensione dell'immagine
second_title: Aspose.PDF per riferimento API .NET
description: Guida dettagliata per impostare la dimensione di un'immagine in un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 270
url: /it/net/programming-with-images/set-image-size/
---

In questo tutorial, ti illustreremo come impostare la dimensione di un'immagine in un documento PDF utilizzando Aspose.PDF per .NET. Segui questi passaggi per eseguire facilmente questa operazione.

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

// Percorso del file di origine dell'immagine
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
//aggiungi pagina alla raccolta di pagine di file PDF
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