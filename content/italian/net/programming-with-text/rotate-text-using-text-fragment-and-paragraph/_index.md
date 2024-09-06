---
title: Ruota il testo usando il frammento di testo e il paragrafo
linktitle: Ruota il testo usando il frammento di testo e il paragrafo
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come ruotare il testo utilizzando frammenti di testo e paragrafi in un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 400
url: /it/net/programming-with-text/rotate-text-using-text-fragment-and-paragraph/
---
Questo tutorial spiega come usare Aspose.PDF per .NET per ruotare il testo usando frammento di testo e paragrafo. Il codice sorgente C# fornito illustra il processo passo dopo passo.

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

 Crea più`TextFragment` oggetti, impostarne il testo e le proprietà e specificare l'angolo di rotazione:

```csharp
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 315;

TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 270;
```

Regola il testo, l'angolo di rotazione e altre proprietà come desideri.

## Passaggio 6: aggiungere frammenti di testo alla pagina

 Aggiungere i frammenti di testo creati alla pagina aggiungendoli al`Paragraphs` collezione:

```csharp
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
```

## Passaggio 7: Salvare il documento PDF

 Salvare il documento PDF modificato in un file utilizzando`Save` metodo:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

 Assicurati di sostituire`"TextFragmentTests_Rotated3_out.pdf"` con il nome del file di output desiderato.

### Esempio di codice sorgente per Ruota testo usando frammento di testo e paragrafo usando Aspose.PDF per .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Inizializza l'oggetto documento
Document pdfDocument = new Document();
// Ottieni una pagina specifica
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Crea frammento di testo
TextFragment textFragment1 = new TextFragment("main text");
// Imposta le proprietà del testo
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Crea frammento di testo
TextFragment textFragment2 = new TextFragment("rotated text");
// Imposta le proprietà del testo
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Imposta la rotazione
textFragment2.TextState.Rotation = 315;
// Crea frammento di testo
TextFragment textFragment3 = new TextFragment("rotated text");
// Imposta le proprietà del testo
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Imposta la rotazione
textFragment3.TextState.Rotation = 270;
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
// Salvare il documento
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

## Conclusione

Congratulazioni! Hai imparato con successo come ruotare il testo usando frammenti di testo e paragrafi in un documento PDF usando Aspose.PDF per .NET. Questo tutorial ha fornito una guida passo passo, dalla creazione del documento al salvataggio della versione modificata. Ora puoi incorporare questo codice nei tuoi progetti C# per manipolare la rotazione del testo nei file PDF.

### Domande frequenti

#### D: Qual è lo scopo del tutorial "Ruotare il testo utilizzando frammenti di testo e paragrafi"?

R: Il tutorial "Ruota testo usando frammento di testo e paragrafo" mira a guidarti attraverso il processo di utilizzo della libreria Aspose.PDF per .NET per ruotare il testo usando sia frammenti di testo che paragrafi all'interno di un documento PDF. Il tutorial fornisce istruzioni dettagliate e codice di esempio per ottenere questa funzionalità.

#### D: In che cosa questo tutorial si differenzia dai precedenti tutorial sulla rotazione del testo?

A: Questo tutorial combina l'uso di frammenti di testo e paragrafi per ottenere la rotazione del testo all'interno di un documento PDF. Dimostra come ruotare i frammenti di testo singolarmente e poi aggiungerli a una pagina`Paragraphs` raccolta per ottenere un effetto di rotazione del testo più completo.

#### D: Quali sono i vantaggi dell'utilizzo di frammenti di testo e paragrafi per la rotazione del testo?

R: L'uso di frammenti di testo e paragrafi insieme consente una maggiore flessibilità nella rotazione del testo. I frammenti di testo consentono impostazioni di rotazione e formattazione individuali, mentre i paragrafi forniscono una struttura per organizzare e posizionare i frammenti di testo all'interno di una pagina.

#### D: Posso applicare angoli di rotazione diversi a diversi frammenti di testo all'interno dello stesso paragrafo?

 A: Sì, puoi applicare diversi angoli di rotazione a diversi`TextFragment` oggetti all'interno dello stesso paragrafo. Ogni frammento di testo può avere il proprio angolo di rotazione specificato utilizzando`TextState.Rotation` proprietà.

#### D: È possibile ottenere effetti di rotazione del testo complessi utilizzando questo metodo?

R: Sì, combinando frammenti di testo con diversi angoli di rotazione e disponendoli all'interno dei paragrafi, puoi ottenere effetti di rotazione del testo complessi e personalizzati, migliorando l'aspetto visivo dei tuoi documenti PDF.

#### D: Quali sono i passaggi necessari per ruotare il testo utilizzando frammenti di testo e paragrafi?

A: I passaggi includono:

1. Impostazione del progetto mediante la creazione di un nuovo progetto C# e l'aggiunta di un riferimento alla libreria Aspose.PDF per .NET.
2. Creazione del documento PDF e aggiunta di una pagina.
3. Creazione di frammenti di testo, impostazione delle relative proprietà e specificazione degli angoli di rotazione.
4.  Aggiungere frammenti di testo alla pagina utilizzando`Paragraphs` collezione.
5. Salvataggio del documento PDF modificato.

#### D: Posso applicare la rotazione a interi paragrafi?

 A: Sì, puoi applicare la rotazione a interi paragrafi impostando`TextState.Rotation` proprietà del paragrafo stesso. Questo ruoterà tutti i frammenti di testo all'interno di quel paragrafo.