---
title: Ruotare il testo utilizzando il paragrafo nel file PDF
linktitle: Ruotare il testo utilizzando il paragrafo nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come ruotare il testo utilizzando i paragrafi in un file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 380
url: /it/net/programming-with-text/rotate-text-using-paragraph/
---
Questo tutorial spiega come usare Aspose.PDF per .NET per ruotare il testo usando i paragrafi. Il codice sorgente C# fornito illustra il processo passo dopo passo.

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
using Aspose.Pdf.Text.TextBuilder;
```

## Passaggio 3: creare il documento PDF

 Inizializzare il`Document` oggetto per creare un nuovo documento PDF:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document();
```

 Assicurati di sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory del documento.

## Passaggio 4: aggiungere una pagina

 Ottieni una pagina specifica dal documento utilizzando`Pages.Add()` metodo:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Passaggio 5: creare il paragrafo di testo

 Crea un`TextParagraph` oggetto e imposta la sua posizione sulla pagina:

```csharp
TextParagraph paragraph = new TextParagraph();
paragraph.Position = new Position(200, 600);
```

Adatta i valori di posizione in base alle tue esigenze.

## Passaggio 6: creare e configurare frammenti di testo

 Crea più`TextFragment` oggetti e impostarne il testo e le proprietà:

```csharp
TextFragment textFragment1 = new TextFragment("rotated text");
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment1.TextState.Rotation = 45;

TextFragment textFragment2 = new TextFragment("main text");
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment3 = new TextFragment("another rotated text");
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = -45;
```

Modifica il testo e le altre proprietà come preferisci.

## Passaggio 7: aggiungere frammenti di testo al paragrafo

 Aggiungere i frammenti di testo creati al paragrafo utilizzando`AppendLine` metodo:

```csharp
paragraph.AppendLine(textFragment1);
paragraph.AppendLine(textFragment2);
paragraph.AppendLine(textFragment3);
```

## Passaggio 8: creare un TextBuilder e aggiungere il paragrafo

 Crea un`TextBuilder` oggetto utilizzando il`pdfPage` e aggiungere il paragrafo di testo alla pagina PDF:

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendParagraph(paragraph);
```

## Passaggio 9: Salvare il documento PDF

 Salvare il documento PDF modificato in un file utilizzando`Save` metodo:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated2_out.pdf");
```

 Assicurati di sostituire`"TextFragmentTests_Rotated2_out.pdf"` con il nome del file di output desiderato.

### Esempio di codice sorgente per Ruota testo tramite paragrafo utilizzando Aspose.PDF per .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Inizializza l'oggetto documento
Document pdfDocument = new Document();
// Ottieni una pagina specifica
Page pdfPage = (Page)pdfDocument.Pages.Add();
TextParagraph paragraph = new TextParagraph();
paragraph.Position = new Position(200, 600);
// Crea frammento di testo
TextFragment textFragment1 = new TextFragment("rotated text");
// Imposta le proprietà del testo
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Imposta la rotazione
textFragment1.TextState.Rotation = 45;
// Crea frammento di testo
TextFragment textFragment2 = new TextFragment("main text");
// Imposta le proprietà del testo
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Crea frammento di testo
TextFragment textFragment3 = new TextFragment("another rotated text");
// Imposta le proprietà del testo
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Imposta la rotazione
textFragment3.TextState.Rotation = -45;
// Aggiungere i frammenti di testo al paragrafo
paragraph.AppendLine(textFragment1);
paragraph.AppendLine(textFragment2);
paragraph.AppendLine(textFragment3);
// Crea oggetto TextBuilder
TextBuilder textBuilder = new TextBuilder(pdfPage);
// Aggiungere il paragrafo di testo alla pagina PDF
textBuilder.AppendParagraph(paragraph);
// Salvare il documento
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated2_out.pdf");
```


## Conclusione

Congratulazioni! Hai imparato con successo come ruotare il testo usando i paragrafi in un documento PDF usando Aspose.PDF per .NET. Questo tutorial ha fornito una guida passo passo, dalla creazione del documento al salvataggio della versione modificata. Ora puoi incorporare questo codice nei tuoi progetti C# per manipolare la rotazione del testo nei file PDF.

### Domande frequenti

#### D: Qual è lo scopo del tutorial "Ruotare il testo utilizzando il paragrafo"?

R: Il tutorial "Ruota testo tramite paragrafo" mira a guidarti attraverso il processo di utilizzo della libreria Aspose.PDF per .NET per ruotare il testo utilizzando paragrafi di testo in un documento PDF. Il tutorial fornisce istruzioni dettagliate e codice di esempio per ottenere questa funzionalità.

#### D: Cosa si intende per "rotazione del testo tramite paragrafi"?

A: La rotazione del testo tramite paragrafi si riferisce alla capacità di applicare la rotazione al testo all'interno di un documento PDF tramite paragrafi di testo. Questa tecnica consente di orientare il testo in diverse angolazioni o posizioni all'interno del contenuto PDF.

#### D: Perché dovrei voler ruotare il testo in un documento PDF?

R: Ruotare il testo in un documento PDF può essere utile per vari scopi, ad esempio per enfatizzare contenuti specifici, creare design artistici o migliorare il layout e la leggibilità.

#### D: Come posso creare un nuovo documento PDF?

 A: Per creare un nuovo documento PDF, inizializza un`Document`oggetto dalla libreria Aspose.PDF. Puoi usare questo oggetto per aggiungere pagine e contenuti al PDF.

#### D: Come faccio a ruotare il testo utilizzando i paragrafi?

A: Per ruotare il testo utilizzando i paragrafi:

1.  Crea un`TextParagraph` oggetto.
2.  Creare`TextFragment` oggetti con il testo e gli angoli di rotazione desiderati.
3. Aggiungere i frammenti di testo al paragrafo di testo.
4.  Crea un`TextBuilder` oggetto e aggiungere il paragrafo di testo a una pagina PDF specifica.

#### D: Posso controllare l'angolo di rotazione dei singoli frammenti di testo?

 A: Sì, puoi controllare l'angolo di rotazione dei singoli`TextFragment` oggetti impostando il`TextState.Rotation` proprietà. I valori positivi indicano la rotazione in senso orario, mentre i valori negativi indicano la rotazione in senso antiorario.

#### D: Posso applicare angoli di rotazione diversi a diversi frammenti di testo all'interno dello stesso paragrafo?

 A: Sì, puoi applicare diversi angoli di rotazione a diversi`TextFragment` oggetti all'interno dello stesso paragrafo impostando l'`TextState.Rotation` proprietà di ciascun frammento di conseguenza.

#### D: Come posso salvare il documento PDF ruotato?

A: Per salvare il documento PDF ruotato, utilizzare`Save` metodo del`Document` oggetto e fornire il percorso e il nome del file di output desiderati.