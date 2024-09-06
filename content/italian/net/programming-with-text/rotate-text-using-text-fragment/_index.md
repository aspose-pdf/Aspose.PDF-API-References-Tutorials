---
title: Ruota il testo utilizzando il frammento di testo nel file PDF
linktitle: Ruota il testo utilizzando il frammento di testo nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come ruotare il testo utilizzando frammenti di testo in un file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 390
url: /it/net/programming-with-text/rotate-text-using-text-fragment/
---
Questo tutorial spiega come usare Aspose.PDF per .NET per ruotare il testo usando frammenti di testo in un file PDF. Il codice sorgente C# fornito illustra il processo passo dopo passo.

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

## Passaggio 5: creare frammenti di testo

 Crea più`TextFragment` oggetti, impostarne il testo e le proprietà e specificarne la posizione sulla pagina:

```csharp
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.Position = new Position(100, 600);
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.Position = new Position(200, 600);
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;

TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.Position = new Position(300, 600);
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
```

Regola il testo, le posizioni e altre proprietà come desideri.

## Passaggio 6: creare un TextBuilder e aggiungere frammenti di testo

 Crea un`TextBuilder` oggetto utilizzando il`pdfPage` e aggiungere i frammenti di testo alla pagina PDF:

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
```

## Passaggio 7: Salvare il documento PDF

 Salvare il documento PDF modificato in un file utilizzando`Save` metodo:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

 Assicurati di sostituire`"TextFragmentTests_Rotated1_out.pdf"` con il nome del file di output desiderato.

### Esempio di codice sorgente per Ruota testo usando frammento di testo usando Aspose.PDF per .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Inizializza l'oggetto documento
Document pdfDocument = new Document();
// Ottieni una pagina specifica
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Crea frammento di testo
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.Position = new Position(100, 600);
// Imposta le proprietà del testo
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Crea frammento di testo ruotato
TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.Position = new Position(200, 600);
// Imposta le proprietà del testo
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;
// Crea frammento di testo ruotato
TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.Position = new Position(300, 600);
// Imposta le proprietà del testo
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
// crea oggetto TextBuilder
TextBuilder textBuilder = new TextBuilder(pdfPage);
// Aggiungere il frammento di testo alla pagina PDF
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
// Salvare il documento
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

## Conclusione

Congratulazioni! Hai imparato con successo come ruotare il testo usando frammenti di testo in un documento PDF usando Aspose.PDF per .NET. Questo tutorial ha fornito una guida passo passo, dalla creazione del documento al salvataggio della versione modificata. Ora puoi incorporare questo codice nei tuoi progetti C# per manipolare la rotazione del testo nei file PDF.

### Domande frequenti

#### D: Qual è lo scopo del tutorial "Ruota il testo utilizzando un frammento di testo"?

R: Il tutorial "Ruota testo usando frammenti di testo" mira a guidarti attraverso il processo di utilizzo della libreria Aspose.PDF per .NET per ruotare il testo usando frammenti di testo in un documento PDF. Il tutorial fornisce istruzioni dettagliate e codice di esempio per ottenere questa funzionalità.

#### D: Cosa si intende per "rotazione del testo mediante frammenti di testo"?

A: La rotazione del testo tramite frammenti di testo si riferisce alla capacità di applicare la rotazione a singoli frammenti di testo all'interno di un documento PDF tramite la libreria Aspose.PDF. Questa tecnica consente di controllare l'orientamento del testo a diverse angolazioni o posizioni all'interno del contenuto PDF.

#### D: Perché dovrei voler ruotare frammenti di testo in un documento PDF?

R: Ruotare frammenti di testo in un documento PDF può essere utile per vari scopi, ad esempio per enfatizzare contenuti specifici, creare design artistici o migliorare il layout e la leggibilità.

#### D: Come posso impostare il progetto per il tutorial?

A: Per impostare il progetto:

1. Crea un nuovo progetto C# nel tuo ambiente di sviluppo integrato (IDE) preferito.
2. Aggiungere un riferimento alla libreria Aspose.PDF per .NET.
3. Aggiungere le direttive using necessarie al file C#.

#### D: Come posso creare un nuovo documento PDF?

 A: Per creare un nuovo documento PDF, inizializza un`Document`oggetto dalla libreria Aspose.PDF. Puoi usare questo oggetto per aggiungere pagine e contenuti al PDF.

#### D: Come faccio a ruotare frammenti di testo utilizzando frammenti di testo?

A: Per ruotare frammenti di testo utilizzando frammenti di testo:

1.  Creare`TextFragment` oggetti.
2. Imposta il testo e le proprietà dei frammenti di testo.
3. Specificare le posizioni dei frammenti di testo sulla pagina.
4.  Impostare l'angolo di rotazione utilizzando`TextState.Rotation` proprietà dei frammenti di testo.
5.  Crea un`TextBuilder`oggetto e aggiungere i frammenti di testo alla pagina PDF.

#### D: Posso applicare angoli di rotazione diversi a diversi frammenti di testo?

 A: Sì, puoi applicare diversi angoli di rotazione a diversi`TextFragment` oggetti. Ogni frammento di testo può avere il proprio angolo di rotazione specificato utilizzando`TextState.Rotation` proprietà.

#### D: Come posso salvare il documento PDF con frammenti di testo ruotati?

 A: Per salvare il documento PDF con frammenti di testo ruotati, utilizzare`Save` metodo del`Document` oggetto e fornire il percorso e il nome del file di output desiderati.