---
title: Testo e immagine come paragrafo nel file PDF
linktitle: Testo e immagine come paragrafo nel file PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come aggiungere testo e un'immagine come paragrafi incorporati nel file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 530
url: /it/net/programming-with-text/text-and-image-as-paragraph/
---
Questo tutorial spiega come aggiungere testo e un'immagine come paragrafi incorporati nel file PDF utilizzando Aspose.PDF per .NET. Il codice sorgente C# fornito illustra il processo passo dopo passo.

## Prerequisiti

Prima di procedere con il tutorial, assicurati di avere quanto segue:

- Conoscenza base del linguaggio di programmazione C#.
- Aspose.PDF per la libreria .NET installata. Puoi ottenerlo dal sito Web Aspose o utilizzare NuGet per installarlo nel tuo progetto.

## Passaggio 1: impostare il progetto

Inizia creando un nuovo progetto C# nel tuo ambiente di sviluppo integrato (IDE) preferito e aggiungi un riferimento alla libreria Aspose.PDF per .NET.

## Passaggio 2: importa gli spazi dei nomi necessari

Aggiungi le seguenti direttive using all'inizio del file C# per importare gli spazi dei nomi richiesti:

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

## Passaggio 4: crea un nuovo documento e una nuova pagina

 Creane uno nuovo`Document` oggetto e aggiungi una pagina alla sua raccolta di pagine:

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Passaggio 5: crea un TextFragment e aggiungilo come paragrafo

 Creare un`TextFragment` oggetto e aggiungerlo alla raccolta paragrafi della pagina:

```csharp
TextFragment text = new TextFragment("Hello World.. ");
page.Paragraphs.Add(text);
```

## Passaggio 6: aggiungi un'immagine come paragrafo incorporato

 Creare un`Aspose.Pdf.Image` oggetto e impostarlo come paragrafo in linea in modo che appaia subito dopo il paragrafo precedente:

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

 Reinizializzare il`TextFragment` oggetto con contenuto diverso e aggiungilo come paragrafo in linea:

```csharp
text = new TextFragment(" Hello Again..");
text.IsInLineParagraph = true;
page.Paragraphs.Add(text);
```

## Passaggio 8: salva il documento PDF

Salvare il documento PDF modificato:

```csharp
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
```

 Assicurati di sostituire`"TextAndImageAsParagraph_out.pdf"` con il nome del file di output desiderato.

### Codice sorgente di esempio per testo e immagine come paragrafo utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Istanziare l'istanza del documento
Document doc = new Document();
// Aggiungi la raccolta di pagine a pagine dell'istanza di documento
Page page = doc.Pages.Add();
// Crea TextFragmnet
TextFragment text = new TextFragment("Hello World.. ");
// Aggiungi un frammento di testo alla raccolta di paragrafi dell'oggetto Pagina
page.Paragraphs.Add(text);
// Crea un'istanza dell'immagine
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
// Imposta l'immagine come paragrafo in linea in modo che appaia subito dopo
// L'oggetto paragrafo precedente (TextFragment)
image.IsInLineParagraph = true;
// Specificare il percorso del file immagine
image.File = dataDir + "aspose-logo.jpg";
// Imposta altezza immagine (opzionale)
image.FixHeight = 30;
// Imposta larghezza immagine (facoltativo)
image.FixWidth = 100;
// Aggiungi un'immagine alla raccolta di paragrafi dell'oggetto pagina
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

Congratulazioni! Hai imparato con successo come aggiungere testo e un'immagine come paragrafi incorporati in un documento PDF utilizzando Aspose.PDF per .NET. Questo tutorial ha fornito una guida passo passo, dall'impostazione del progetto al salvataggio del documento modificato. Ora puoi incorporare questo codice nei tuoi progetti C# per personalizzare il layout di testo e immagini nei file PDF.

### Domande frequenti

#### D: Qual è lo scopo del tutorial "Testo e immagine come paragrafo nel file PDF"?

R: Il tutorial "Testo e immagine come paragrafo nel file PDF" mira a guidare gli utenti su come aggiungere testo e immagini come paragrafi incorporati all'interno di un documento PDF utilizzando Aspose.PDF per .NET. L'esercitazione fornisce istruzioni dettagliate ed esempi di codice C# per dimostrare il processo.

#### D: In che modo questo tutorial aiuta ad aggiungere testo e immagini come paragrafi incorporati?

R: Questo tutorial aiuta gli utenti a capire come utilizzare Aspose.PDF per .NET per incorporare testo e immagini come paragrafi incorporati all'interno di un documento PDF. Seguendo i passaggi forniti e gli esempi di codice, gli utenti possono creare file PDF con layout personalizzati che combinano testo e immagini.

#### D: Quali prerequisiti sono richiesti per seguire questo tutorial?

R: Prima di iniziare il tutorial, dovresti avere una conoscenza di base del linguaggio di programmazione C#. Inoltre, è necessario che sia installata la libreria Aspose.PDF per .NET. È possibile ottenerlo dal sito Web Aspose o installarlo nel progetto utilizzando NuGet.

#### D: Come posso impostare il mio progetto per seguire questo tutorial?

R: Per iniziare, crea un nuovo progetto C# nel tuo ambiente di sviluppo integrato (IDE) preferito e aggiungi un riferimento alla libreria Aspose.PDF per .NET. Ciò consente di utilizzare le funzionalità della libreria per lavorare con documenti PDF, frammenti di testo e immagini.

#### D: Posso utilizzare questo tutorial per aggiungere più paragrafi di testo e immagini in un PDF?

R: Sì, puoi utilizzare gli esempi di codice forniti per aggiungere più istanze di paragrafi sia di testo che di immagini all'interno dello stesso documento PDF. Questo tutorial mostra come creare paragrafi in linea, semplificando l'inclusione di diverse combinazioni di testo e immagini.

#### D: Come posso specificare il contenuto e l'aspetto dei paragrafi di testo e delle immagini?

 R: Il tutorial mostra come creare`TextFragment`oggetti per rappresentare paragrafi di testo e`Aspose.Pdf.Image` oggetti per rappresentare immagini. Puoi personalizzare il contenuto, le dimensioni e l'aspetto sia del testo che delle immagini utilizzando gli esempi di codice forniti.

#### D: Posso modificare il layout dei paragrafi incorporati?

 R: Sì, puoi regolare il layout dei paragrafi in linea controllandone il posizionamento, le dimensioni e l'ordine all'interno della pagina. Il tutorial mostra come impostare gli attributi in linea, come`IsInLineParagraph`, per controllare il layout dei paragrafi di testo e immagini.

#### D: Come posso salvare il documento PDF modificato?

 R: Per salvare il documento PDF modificato, puoi utilizzare il file`Save` metodo del`Document` oggetto. L'esercitazione fornisce esempi di codice che dimostrano come salvare il documento PDF risultante.