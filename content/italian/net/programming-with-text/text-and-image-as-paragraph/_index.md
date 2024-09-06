---
title: Testo e immagine come paragrafo nel file PDF
linktitle: Testo e immagine come paragrafo nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come aggiungere testo e un'immagine come paragrafi in linea in un file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 530
url: /it/net/programming-with-text/text-and-image-as-paragraph/
---
Questo tutorial spiega come aggiungere testo e un'immagine come paragrafi in linea in un file PDF usando Aspose.PDF per .NET. Il codice sorgente C# fornito illustra il processo passo dopo passo.

## Prerequisiti

Prima di procedere con il tutorial, assicurati di avere quanto segue:

- Conoscenza di base del linguaggio di programmazione C#.
- Aspose.PDF per la libreria .NET installata. Puoi ottenerla dal sito web di Aspose o usare NuGet per installarla nel tuo progetto.

## Passaggio 1: impostare il progetto

Inizia creando un nuovo progetto C# nel tuo ambiente di sviluppo integrato (IDE) preferito e aggiungi un riferimento alla libreria Aspose.PDF per .NET.

## Passaggio 2: importare gli spazi dei nomi necessari

Aggiungere le seguenti direttive using all'inizio del file C# per importare gli spazi dei nomi richiesti:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Drawing;
```

## Passaggio 3: impostare il percorso della directory del documento

 Imposta il percorso della directory del documento utilizzando`dataDir` variabile:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory del documento.

## Passaggio 4: creare un nuovo documento e una nuova pagina

 Crea un nuovo`Document` oggetto e aggiungi una pagina alla sua raccolta di pagine:

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Passaggio 5: crea un TextFragment e aggiungilo come paragrafo

 Crea un`TextFragment` oggetto e aggiungerlo alla raccolta dei paragrafi della pagina:

```csharp
TextFragment text = new TextFragment("Hello World.. ");
page.Paragraphs.Add(text);
```

## Passaggio 6: aggiungere un'immagine come paragrafo in linea

 Crea un`Aspose.Pdf.Image` oggetto e impostarlo come paragrafo in linea in modo che appaia subito dopo il paragrafo precedente:

```csharp
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
image.IsInLineParagraph = true;
image.File = dataDir + "aspose-logo.jpg";
image.FixHeight = 30; // Facoltativo: imposta l'altezza dell'immagine
image.FixWidth = 100; // Facoltativo: imposta la larghezza dell'immagine
page.Paragraphs.Add(image);
```

 Sostituire`"aspose-logo.jpg"` con il nome effettivo del file immagine e regola l'altezza e la larghezza opzionali dell'immagine come desiderato.

## Passaggio 7: aggiungere un altro TextFragment come paragrafo in linea

 Reinizializzare il`TextFragment` oggetto con contenuto diverso e aggiungerlo come paragrafo in linea:

```csharp
text = new TextFragment(" Hello Again..");
text.IsInLineParagraph = true;
page.Paragraphs.Add(text);
```

## Passaggio 8: Salvare il documento PDF

Salvare il documento PDF modificato:

```csharp
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
```

 Assicurati di sostituire`"TextAndImageAsParagraph_out.pdf"` con il nome del file di output desiderato.

### Esempio di codice sorgente per testo e immagine come paragrafo utilizzando Aspose.PDF per .NET 
```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crea un'istanza del documento
Document doc = new Document();
// Aggiungi pagina alla raccolta di pagine dell'istanza del documento
Page page = doc.Pages.Add();
// Crea TextFragmnet
TextFragment text = new TextFragment("Hello World.. ");
// Aggiungi frammento di testo alla raccolta di paragrafi dell'oggetto Pagina
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
// Imposta la larghezza dell'immagine (facoltativo)
image.FixWidth = 100;
// Aggiungi immagine alla raccolta di paragrafi dell'oggetto pagina
page.Paragraphs.Add(image);
// Reinizializza l'oggetto TextFragment con contenuti diversi
text = new TextFragment(" Hello Again..");
// Imposta TextFragment come paragrafo in linea
text.IsInLineParagraph = true;
// Aggiungi il TextFragment appena creato alla raccolta di paragrafi della pagina
page.Paragraphs.Add(text);
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nText and image added successfully as an inline paragraphs.\nFile saved at " + dataDir);
```

## Conclusione

Congratulazioni! Hai imparato con successo come aggiungere testo e un'immagine come paragrafi in linea in un documento PDF usando Aspose.PDF per .NET. Questo tutorial ha fornito una guida passo passo, dall'impostazione del progetto al salvataggio del documento modificato. Ora puoi incorporare questo codice nei tuoi progetti C# per personalizzare il layout di testo e immagini nei file PDF.

### Domande frequenti

#### D: Qual è lo scopo del tutorial "Testo e immagine come paragrafo in un file PDF"?

R: Il tutorial "Testo e immagine come paragrafo nel file PDF" mira a guidare gli utenti su come aggiungere sia testo che immagini come paragrafi in linea all'interno di un documento PDF utilizzando Aspose.PDF per .NET. Il tutorial fornisce istruzioni dettagliate ed esempi di codice C# per dimostrare il processo.

#### D: In che modo questo tutorial aiuta ad aggiungere testo e immagini come paragrafi in linea?

R: Questo tutorial aiuta gli utenti a capire come usare Aspose.PDF per .NET per incorporare sia testo che immagini come paragrafi in linea in un documento PDF. Seguendo i passaggi e gli esempi di codice forniti, gli utenti possono creare file PDF con layout personalizzati che combinano testo e immagini.

#### D: Quali prerequisiti sono richiesti per seguire questo tutorial?

R: Prima di iniziare il tutorial, dovresti avere una conoscenza di base del linguaggio di programmazione C#. Inoltre, devi avere installata la libreria Aspose.PDF per .NET. Puoi ottenerla dal sito web di Aspose o installarla nel tuo progetto usando NuGet.

#### D: Come posso impostare il mio progetto in modo che segua questo tutorial?

R: Per iniziare, crea un nuovo progetto C# nel tuo ambiente di sviluppo integrato (IDE) preferito e aggiungi un riferimento alla libreria Aspose.PDF per .NET. Ciò ti consente di utilizzare le funzionalità della libreria per lavorare con documenti PDF, frammenti di testo e immagini.

#### D: Posso usare questo tutorial per aggiungere più paragrafi di testo e immagini in un PDF?

R: Sì, puoi usare gli esempi di codice forniti per aggiungere più istanze di paragrafi di testo e immagini all'interno dello stesso documento PDF. Questo tutorial mostra come creare paragrafi in linea, rendendo semplice includere diverse combinazioni di testo e immagini.

#### D: Come posso specificare il contenuto e l'aspetto dei paragrafi di testo e delle immagini?

 A: Il tutorial mostra come creare`TextFragment`oggetti per rappresentare paragrafi di testo e`Aspose.Pdf.Image` oggetti per rappresentare immagini. Puoi personalizzare il contenuto, le dimensioni e l'aspetto sia del testo che delle immagini utilizzando gli esempi di codice forniti.

#### D: Posso modificare il layout dei paragrafi in linea?

 R: Sì, puoi modificare il layout dei paragrafi in linea controllandone il posizionamento, le dimensioni e l'ordine all'interno della pagina. Il tutorial mostra come impostare gli attributi in linea, come`IsInLineParagraph`, per controllare il layout dei paragrafi di testo e immagini.

#### D: Come posso salvare il documento PDF modificato?

 A: Per salvare il documento PDF modificato, puoi utilizzare`Save` metodo del`Document` oggetto. Il tutorial fornisce esempi di codice che dimostrano come salvare il documento PDF risultante.