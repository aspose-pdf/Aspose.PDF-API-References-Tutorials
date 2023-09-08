---
title: Ruota il testo utilizzando il paragrafo nel file PDF
linktitle: Ruota il testo utilizzando il paragrafo nel file PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come ruotare il testo utilizzando i paragrafi nel file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 380
url: /it/net/programming-with-text/rotate-text-using-paragraph/
---
Questo tutorial spiega come utilizzare Aspose.PDF per .NET per ruotare il testo utilizzando i paragrafi. Il codice sorgente C# fornito illustra il processo passo dopo passo.

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
using Aspose.Pdf.Text.TextBuilder;
```

## Passaggio 3: crea il documento PDF

 Inizializza il`Document` oggetto per creare un nuovo documento PDF:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document();
```

 Assicurati di sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

## Passaggio 4: aggiungi una pagina

 Ottieni una pagina particolare dal documento utilizzando il file`Pages.Add()` metodo:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Passaggio 5: crea il paragrafo di testo

 Creare un`TextParagraph` oggetto e impostarne la posizione nella pagina:

```csharp
TextParagraph paragraph = new TextParagraph();
paragraph.Position = new Position(200, 600);
```

Regola i valori della posizione in base alle tue esigenze.

## Passaggio 6: crea e configura frammenti di testo

 Crea multipli`TextFragment` oggetti e impostarne il testo e le proprietà:

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

Modifica il testo e le altre proprietà come desideri.

## Passaggio 7: aggiungi frammenti di testo al paragrafo

 Aggiungi i frammenti di testo creati al paragrafo utilizzando il comando`AppendLine` metodo:

```csharp
paragraph.AppendLine(textFragment1);
paragraph.AppendLine(textFragment2);
paragraph.AppendLine(textFragment3);
```

## Passaggio 8: crea un TextBuilder e aggiungi il paragrafo

 Creare un`TextBuilder` oggetto utilizzando il`pdfPage` e aggiungi il paragrafo di testo alla pagina PDF:

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendParagraph(paragraph);
```

## Passaggio 9: salva il documento PDF

 Salvare il documento PDF modificato in un file utilizzando l'estensione`Save` metodo:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated2_out.pdf");
```

 Assicurati di sostituire`"TextFragmentTests_Rotated2_out.pdf"` con il nome del file di output desiderato.

### Codice sorgente di esempio per Ruota testo utilizzando il paragrafo utilizzando Aspose.PDF per .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Inizializza l'oggetto documento
Document pdfDocument = new Document();
// Ottieni una pagina particolare
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
// Aggiungi i frammenti di testo al paragrafo
paragraph.AppendLine(textFragment1);
paragraph.AppendLine(textFragment2);
paragraph.AppendLine(textFragment3);
// Crea un oggetto TextBuilder
TextBuilder textBuilder = new TextBuilder(pdfPage);
// Aggiungi il paragrafo di testo alla pagina PDF
textBuilder.AppendParagraph(paragraph);
// Salva documento
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated2_out.pdf");
```


## Conclusione

Congratulazioni! Hai imparato con successo come ruotare il testo utilizzando i paragrafi in un documento PDF utilizzando Aspose.PDF per .NET. Questo tutorial fornisce una guida passo passo, dalla creazione del documento al salvataggio della versione modificata. Ora puoi incorporare questo codice nei tuoi progetti C# per manipolare la rotazione del testo nei file PDF.

### Domande frequenti

#### D: Qual è lo scopo del tutorial "Ruota il testo utilizzando il paragrafo"?

R: Il tutorial "Ruota il testo utilizzando il paragrafo" ha lo scopo di guidarti attraverso il processo di utilizzo della libreria Aspose.PDF per .NET per ruotare il testo utilizzando i paragrafi di testo in un documento PDF. L'esercitazione fornisce istruzioni dettagliate e codice di esempio per ottenere questa funzionalità.

#### D: Cosa significa "ruotare il testo utilizzando i paragrafi"?

R: La rotazione del testo utilizzando i paragrafi si riferisce alla possibilità di applicare la rotazione al testo all'interno di un documento PDF utilizzando i paragrafi di testo. Questa tecnica consente di orientare il testo ad angoli o posizioni diversi all'interno del contenuto PDF.

#### D: Perché dovrei ruotare il testo in un documento PDF?

R: La rotazione del testo in un documento PDF può essere utile per vari scopi, ad esempio enfatizzare contenuti specifici, creare progetti artistici o migliorare il layout e la leggibilità.

#### D: Come posso creare un nuovo documento PDF?

 R: Per creare un nuovo documento PDF, inizializzare a`Document`oggetto dalla libreria Aspose.PDF. È possibile utilizzare questo oggetto per aggiungere pagine e contenuto al PDF.

#### D: Come posso ruotare il testo utilizzando i paragrafi?

R: Per ruotare il testo utilizzando i paragrafi:

1.  Creare un`TextParagraph` oggetto.
2.  Creare`TextFragment` oggetti con il testo e gli angoli di rotazione desiderati.
3. Aggiungi i frammenti di testo al paragrafo di testo.
4.  Creare un`TextBuilder` oggetto e aggiungere il paragrafo di testo a una pagina PDF specifica.

#### D: Posso controllare l'angolo di rotazione dei singoli frammenti di testo?

 R: Sì, puoi controllare l'angolo di rotazione individuale`TextFragment` oggetti impostando il file`TextState.Rotation` proprietà. I valori positivi indicano la rotazione in senso orario, mentre i valori negativi indicano la rotazione in senso antiorario.

#### D: Posso applicare angoli di rotazione diversi a frammenti di testo diversi all'interno dello stesso paragrafo?

 R: Sì, puoi applicare angoli di rotazione diversi a diversi`TextFragment` oggetti all'interno dello stesso paragrafo impostando il file`TextState.Rotation` proprietà di ciascun frammento di conseguenza.

#### D: Come posso salvare il documento PDF ruotato?

R: Per salvare il documento PDF ruotato, utilizzare il file`Save` metodo del`Document` oggetto e fornire il percorso e il nome del file di output desiderati.