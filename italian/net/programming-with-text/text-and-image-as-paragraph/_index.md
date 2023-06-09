---
title: Testo e immagine come paragrafo
linktitle: Testo e immagine come paragrafo
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come aggiungere testo e un'immagine come paragrafi in linea in un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 530
url: /it/net/programming-with-text/text-and-image-as-paragraph/
---

Questo tutorial spiega come aggiungere testo e un'immagine come paragrafi in linea in un documento PDF utilizzando Aspose.PDF per .NET. Il codice sorgente C# fornito illustra il processo passo dopo passo.

## Prerequisiti

Prima di procedere con il tutorial, assicurati di disporre di quanto segue:

- Conoscenza base del linguaggio di programmazione C#.
- Aspose.PDF per la libreria .NET installata. Puoi ottenerlo dal sito Web di Aspose o utilizzare NuGet per installarlo nel tuo progetto.

## Passaggio 1: impostare il progetto

Inizia creando un nuovo progetto C# nel tuo ambiente di sviluppo integrato (IDE) preferito e aggiungi un riferimento alla libreria Aspose.PDF per .NET.

## Passaggio 2: importa gli spazi dei nomi necessari

Aggiungi le seguenti direttive using all'inizio del tuo file C# per importare gli spazi dei nomi richiesti:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Drawing;
```

## Passaggio 3: impostare il percorso della directory dei documenti

 Imposta il percorso della directory dei documenti utilizzando il file`dataDir` variabile:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

## Passaggio 4: creare un nuovo documento e una nuova pagina

 Crea un nuovo`Document` oggetto e aggiungi una pagina alla sua raccolta di pagine:

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Passaggio 5: crea un TextFragment e aggiungilo come paragrafo

 Creare un`TextFragment`object e aggiungerlo alla raccolta dei paragrafi della pagina:

```csharp
TextFragment text = new TextFragment("Hello World.. ");
page.Paragraphs.Add(text);
```

## Passaggio 6: aggiungi un'immagine come paragrafo in linea

 Creare un`Aspose.Pdf.Image` oggetto e impostalo come paragrafo in linea in modo che appaia subito dopo il paragrafo precedente:

```csharp
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
image.IsInLineParagraph = true;
image.File = dataDir + "aspose-logo.jpg";
image.FixHeight = 30; // Facoltativo: imposta l'altezza dell'immagine
image.FixWidth = 100; // Facoltativo: imposta la larghezza dell'immagine
page.Paragraphs.Add(image);
```

 Sostituire`"aspose-logo.jpg"` con il nome effettivo del file immagine e regolare l'altezza e la larghezza opzionali dell'immagine come desiderato.

## Passaggio 7: aggiungi un altro TextFragment come paragrafo in linea

 Reinizializzare il`TextFragment` oggetto con contenuto diverso e aggiungilo come paragrafo incorporato:

```csharp
text = new TextFragment(" Hello Again..");
text.IsInLineParagraph = true;
page.Paragraphs.Add(text);
```

## Passaggio 8: salvare il documento PDF

Salva il documento PDF modificato:

```csharp
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
```

 Assicurati di sostituire`"TextAndImageAsParagraph_out.pdf"` con il nome del file di output desiderato.

### Esempio di codice sorgente per testo e immagine come paragrafo utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Istanza documento istanza
Document doc = new Document();
// Aggiungi la pagina alla raccolta di pagine dell'istanza del documento
Page page = doc.Pages.Add();
// Crea TextFragmnet
TextFragment text = new TextFragment("Hello World.. ");
// Aggiungi un frammento di testo alla raccolta di paragrafi dell'oggetto Page
page.Paragraphs.Add(text);
// Crea un'istanza di immagine
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
// Imposta l'immagine come paragrafo in linea in modo che appaia subito dopo
// L'oggetto paragrafo precedente (TextFragment)
image.IsInLineParagraph = true;
// Specificare il percorso del file immagine
image.File = dataDir + "aspose-logo.jpg";
// Imposta l'altezza dell'immagine (facoltativo)
image.FixHeight = 30;
// Imposta larghezza immagine (opzionale)
image.FixWidth = 100;
//Aggiungi un'immagine alla raccolta di paragrafi dell'oggetto della pagina
page.Paragraphs.Add(image);
// Reinizializza l'oggetto TextFragment con contenuti diversi
text = new TextFragment(" Hello Again..");
// Imposta TextFragment come paragrafo in linea
text.IsInLineParagraph = true;
// Aggiungi TextFragment appena creato alla raccolta di paragrafi della pagina
page.Paragraphs.Add(text);
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nText and image added successfully as an inline paragraphs.\nFile saved at " + dataDir);
```

## Conclusione

Congratulazioni! Hai imparato con successo come aggiungere testo e un'immagine come paragrafi in linea in un documento PDF utilizzando Aspose.PDF per .NET. Questo tutorial ha fornito una guida passo passo, dall'impostazione del progetto al salvataggio del documento modificato. Ora puoi incorporare questo codice nei tuoi progetti C# per personalizzare il layout di testo e immagini nei file PDF.