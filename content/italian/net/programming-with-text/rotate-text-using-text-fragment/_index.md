---
title: Ruota il testo utilizzando il frammento di testo nel file PDF
linktitle: Ruota il testo utilizzando il frammento di testo nel file PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come ruotare il testo utilizzando frammenti di testo nel file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 390
url: /it/net/programming-with-text/rotate-text-using-text-fragment/
---
Questo tutorial spiega come utilizzare Aspose.PDF per .NET per ruotare il testo utilizzando frammenti di testo nel file PDF. Il codice sorgente C# fornito illustra il processo passo dopo passo.

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

## Passaggio 5: crea frammenti di testo

 Crea multipli`TextFragment` oggetti, impostarne il testo e le proprietà e specificarne le posizioni sulla pagina:

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

Regola il testo, le posizioni e le altre proprietà come desideri.

## Passaggio 6: crea un TextBuilder e aggiungi frammenti di testo

 Creare un`TextBuilder` oggetto utilizzando il`pdfPage` e aggiungi i frammenti di testo alla pagina PDF:

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
```

## Passaggio 7: salva il documento PDF

 Salvare il documento PDF modificato in un file utilizzando l'estensione`Save` metodo:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

 Assicurati di sostituire`"TextFragmentTests_Rotated1_out.pdf"` con il nome del file di output desiderato.

### Codice sorgente di esempio per Ruotare il testo utilizzando il frammento di testo utilizzando Aspose.PDF per .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Inizializza l'oggetto documento
Document pdfDocument = new Document();
// Ottieni una pagina particolare
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
// creare un oggetto TextBuilder
TextBuilder textBuilder = new TextBuilder(pdfPage);
// Aggiungi il frammento di testo alla pagina PDF
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
// Salva documento
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

## Conclusione

Congratulazioni! Hai imparato con successo come ruotare il testo utilizzando frammenti di testo in un documento PDF utilizzando Aspose.PDF per .NET. Questo tutorial fornisce una guida passo passo, dalla creazione del documento al salvataggio della versione modificata. Ora puoi incorporare questo codice nei tuoi progetti C# per manipolare la rotazione del testo nei file PDF.

### Domande frequenti

#### D: Qual è lo scopo del tutorial "Ruota il testo utilizzando il frammento di testo"?

R: Il tutorial "Ruota il testo utilizzando il frammento di testo" mira a guidarti attraverso il processo di utilizzo della libreria Aspose.PDF per .NET per ruotare il testo utilizzando frammenti di testo in un documento PDF. L'esercitazione fornisce istruzioni dettagliate e codice di esempio per ottenere questa funzionalità.

#### D: Cosa significa "ruotare il testo utilizzando frammenti di testo"?

R: La rotazione del testo utilizzando frammenti di testo si riferisce alla possibilità di applicare la rotazione a singoli frammenti di testo all'interno di un documento PDF utilizzando la libreria Aspose.PDF. Questa tecnica consente di controllare l'orientamento del testo a diverse angolazioni o posizioni all'interno del contenuto PDF.

#### D: Perché dovrei ruotare i frammenti di testo in un documento PDF?

R: La rotazione dei frammenti di testo in un documento PDF può essere utile per vari scopi, ad esempio enfatizzare contenuti specifici, creare progetti artistici o migliorare il layout e la leggibilità.

#### D: Come posso impostare il progetto per il tutorial?

R: Per impostare il progetto:

1. Crea un nuovo progetto C# nel tuo ambiente di sviluppo integrato (IDE) preferito.
2. Aggiungere un riferimento alla libreria Aspose.PDF per .NET.
3. Aggiungi le direttive using necessarie al tuo file C#.

#### D: Come posso creare un nuovo documento PDF?

 R: Per creare un nuovo documento PDF, inizializzare a`Document`oggetto dalla libreria Aspose.PDF. È possibile utilizzare questo oggetto per aggiungere pagine e contenuto al PDF.

#### D: Come posso ruotare i frammenti di testo utilizzando i frammenti di testo?

R: Per ruotare i frammenti di testo utilizzando frammenti di testo:

1.  Creare`TextFragment` oggetti.
2. Imposta il testo e le proprietà dei frammenti di testo.
3. Specificare le posizioni dei frammenti di testo sulla pagina.
4.  Impostare l'angolo di rotazione utilizzando`TextState.Rotation` proprietà dei frammenti di testo.
5.  Creare un`TextBuilder`oggetto e aggiungere i frammenti di testo alla pagina PDF.

#### D: Posso applicare angoli di rotazione diversi a frammenti di testo diversi?

 R: Sì, puoi applicare angoli di rotazione diversi a diversi`TextFragment` oggetti. Ogni frammento di testo può avere il proprio angolo di rotazione specificato utilizzando il comando`TextState.Rotation` proprietà.

#### D: Come posso salvare il documento PDF con frammenti di testo ruotati?

 R: Per salvare il documento PDF con frammenti di testo ruotati, utilizzare il file`Save` metodo del`Document` oggetto e fornire il percorso e il nome del file di output desiderati.