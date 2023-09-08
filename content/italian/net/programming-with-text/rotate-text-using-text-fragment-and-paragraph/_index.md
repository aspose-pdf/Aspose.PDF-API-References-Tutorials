---
title: Ruota il testo utilizzando il frammento di testo e il paragrafo
linktitle: Ruota il testo utilizzando il frammento di testo e il paragrafo
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come ruotare il testo utilizzando frammento di testo e paragrafo in un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 400
url: /it/net/programming-with-text/rotate-text-using-text-fragment-and-paragraph/
---
Questo tutorial spiega come utilizzare Aspose.PDF per .NET per ruotare il testo utilizzando frammento di testo e paragrafo. Il codice sorgente C# fornito illustra il processo passo dopo passo.

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

## Passaggio 5: crea frammenti di testo

 Crea multipli`TextFragment` oggetti, impostarne il testo e le proprietà e specificare l'angolo di rotazione:

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

## Passaggio 6: aggiungi frammenti di testo alla pagina

 Aggiungi i frammenti di testo creati alla pagina aggiungendoli al file`Paragraphs` collezione:

```csharp
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
```

## Passaggio 7: salva il documento PDF

 Salvare il documento PDF modificato in un file utilizzando l'estensione`Save` metodo:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

 Assicurati di sostituire`"TextFragmentTests_Rotated3_out.pdf"` con il nome del file di output desiderato.

### Codice sorgente di esempio per ruotare il testo utilizzando frammenti di testo e paragrafi utilizzando Aspose.PDF per .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Inizializza l'oggetto documento
Document pdfDocument = new Document();
// Ottieni una pagina particolare
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
// Salva documento
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

## Conclusione

Congratulazioni! Hai imparato con successo come ruotare il testo utilizzando frammenti di testo e paragrafi in un documento PDF utilizzando Aspose.PDF per .NET. Questo tutorial fornisce una guida passo passo, dalla creazione del documento al salvataggio della versione modificata. Ora puoi incorporare questo codice nei tuoi progetti C# per manipolare la rotazione del testo nei file PDF.

### Domande frequenti

#### D: Qual è lo scopo del tutorial "Ruota il testo utilizzando frammenti di testo e paragrafi"?

R: Il tutorial "Ruota il testo utilizzando frammenti di testo e paragrafi" mira a guidarti attraverso il processo di utilizzo della libreria Aspose.PDF per .NET per ruotare il testo utilizzando sia frammenti di testo che paragrafi all'interno di un documento PDF. L'esercitazione fornisce istruzioni dettagliate e codice di esempio per ottenere questa funzionalità.

#### D: In cosa differisce questo tutorial dai precedenti tutorial sulla rotazione del testo?

R: Questo tutorial combina l'uso di frammenti di testo e paragrafi per ottenere la rotazione del testo all'interno di un documento PDF. Dimostra come ruotare i frammenti di testo individualmente e quindi aggiungerli a una pagina`Paragraphs` raccolta per ottenere un effetto di rotazione del testo più completo.

#### D: Quali sono i vantaggi derivanti dall'utilizzo di frammenti e paragrafi di testo per la rotazione del testo?

R: L'utilizzo contemporaneo di frammenti di testo e paragrafi consente una maggiore flessibilità nella rotazione del testo. I frammenti di testo consentono impostazioni individuali di rotazione e formattazione, mentre i paragrafi forniscono la struttura per organizzare e posizionare i frammenti di testo all'interno di una pagina.

#### D: Posso applicare angoli di rotazione diversi a frammenti di testo diversi all'interno dello stesso paragrafo?

 R: Sì, puoi applicare angoli di rotazione diversi a diversi`TextFragment` oggetti all'interno dello stesso paragrafo. Ogni frammento di testo può avere il proprio angolo di rotazione specificato utilizzando il comando`TextState.Rotation` proprietà.

#### D: È possibile ottenere effetti di rotazione del testo complessi utilizzando questo metodo?

R: Sì, combinando frammenti di testo con vari angoli di rotazione e disponendoli all'interno dei paragrafi, puoi ottenere effetti di rotazione del testo complessi e personalizzati, migliorando l'impatto visivo dei tuoi documenti PDF.

#### D: Quali passaggi sono coinvolti nella rotazione del testo utilizzando frammenti di testo e paragrafi?

R: I passaggi includono:

1. Impostazione del progetto creando un nuovo progetto C# e aggiungendo un riferimento alla libreria Aspose.PDF per .NET.
2. Creazione del documento PDF e aggiunta di una pagina.
3. Creazione di frammenti di testo, impostazione delle loro proprietà e specificazione degli angoli di rotazione.
4.  Aggiunta di frammenti di testo alla pagina utilizzando il file`Paragraphs` collezione.
5. Salvataggio del documento PDF modificato.

#### D: Posso applicare la rotazione a interi paragrafi?

 R: Sì, puoi applicare la rotazione a interi paragrafi impostando il file`TextState.Rotation` proprietà del paragrafo stesso. Ciò ruoterà tutti i frammenti di testo all'interno di quel paragrafo.