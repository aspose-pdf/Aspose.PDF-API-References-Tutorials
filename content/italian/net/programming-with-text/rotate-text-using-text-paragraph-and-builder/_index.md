---
title: Ruota il testo utilizzando il paragrafo di testo e il generatore nel file PDF
linktitle: Ruota il testo utilizzando il paragrafo di testo e il generatore nel file PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come ruotare il testo utilizzando il paragrafo di testo e il generatore nel file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 410
url: /it/net/programming-with-text/rotate-text-using-text-paragraph-and-builder/
---
Questo tutorial spiega come utilizzare Aspose.PDF per .NET per ruotare il testo utilizzando paragrafi di testo e builder nel file PDF. Il codice sorgente C# fornito illustra il processo passo dopo passo.

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

## Passaggio 5: crea e ruota i paragrafi di testo

 Creare un`for` loop per generare più paragrafi di testo con rotazioni diverse:

```csharp
for (int i = 0; i < 4; i++)
{
	TextParagraph paragraph = new TextParagraph();
	paragraph.Position = new Position(200, 600);
	paragraph.Rotation = i * 90 + 45;
```

Regola i valori di posizione e rotazione in base alle tue esigenze.

## Passaggio 6: crea e configura frammenti di testo

 Crea multipli`TextFragment` oggetti, impostarne il testo e le proprietà:

```csharp
TextFragment textFragment1 = new TextFragment("Paragraph Text");
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment1.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment1.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;

TextFragment textFragment2 = new TextFragment("Second line of text");
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment2.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;

TextFragment textFragment3 = new TextFragment("And some more text...");
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment3.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
textFragment3.TextState.Underline = true;
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
}
```

## Passaggio 9: salva il documento PDF

 Salvare il documento PDF modificato in un file utilizzando l'estensione`Save` metodo:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated4_out.pdf");
```

 Assicurati di sostituire`"TextFragmentTests_Rotated4_out.pdf"` con il nome del file di output desiderato.

### Codice sorgente di esempio per ruotare il testo utilizzando il paragrafo di testo e il generatore utilizzando Aspose.PDF per .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Inizializza l'oggetto documento
Document pdfDocument = new Document();
// Ottieni una pagina particolare
Page pdfPage = (Page)pdfDocument.Pages.Add();
for (int i = 0; i < 4; i++)
{
	TextParagraph paragraph = new TextParagraph();
	paragraph.Position = new Position(200, 600);
	// Specificare la rotazione
	paragraph.Rotation = i * 90 + 45;
	// Crea frammento di testo
	TextFragment textFragment1 = new TextFragment("Paragraph Text");
	// Crea frammento di testo
	textFragment1.TextState.FontSize = 12;
	textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
	textFragment1.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
	textFragment1.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	// Crea frammento di testo
	TextFragment textFragment2 = new TextFragment("Second line of text");
	// Imposta le proprietà del testo
	textFragment2.TextState.FontSize = 12;
	textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
	textFragment2.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
	textFragment2.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	// Crea frammento di testo
	TextFragment textFragment3 = new TextFragment("And some more text...");
	// Imposta le proprietà del testo
	textFragment3.TextState.FontSize = 12;
	textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
	textFragment3.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
	textFragment3.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	textFragment3.TextState.Underline = true;
	paragraph.AppendLine(textFragment1);
	paragraph.AppendLine(textFragment2);
	paragraph.AppendLine(textFragment3);
	// Crea un oggetto TextBuilder
	TextBuilder textBuilder = new TextBuilder(pdfPage);
	// Aggiungi il frammento di testo alla pagina PDF
	textBuilder.AppendParagraph(paragraph);
}
// Salva documento
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated4_out.pdf");
```

## Conclusione

Congratulazioni! Hai imparato con successo come ruotare il testo utilizzando paragrafi di testo e builder in un documento PDF utilizzando Aspose.PDF per .NET. Questo tutorial fornisce una guida passo passo, dalla creazione del documento al salvataggio della versione modificata. Ora puoi incorporare questo codice nei tuoi progetti C# per manipolare la rotazione del testo nei file PDF.

### Domande frequenti

#### D: Qual è lo scopo del tutorial "Ruota il testo utilizzando il paragrafo e il generatore di testo"?

R: Il tutorial "Ruota il testo utilizzando paragrafi di testo e builder" fornisce una guida completa su come utilizzare la libreria Aspose.PDF per .NET per ruotare il testo utilizzando paragrafi di testo e builder all'interno di un documento PDF. L'esercitazione illustra istruzioni dettagliate e include codice C# di esempio per ottenere la rotazione del testo con paragrafi e formattazione personalizzata.

#### D: In cosa differisce questo tutorial dai precedenti tutorial sulla rotazione del testo?

R: A differenza dei tutorial precedenti, questo tutorial combina l'uso di paragrafi di testo, builder e angoli di rotazione per ottenere un effetto di rotazione del testo più avanzato. Dimostra come generare più paragrafi di testo con angoli di rotazione diversi e applicare la formattazione personalizzata a singoli frammenti di testo.

#### D: Qual è il significato dell'utilizzo di paragrafi di testo e builder per la rotazione del testo?

R: L'utilizzo di paragrafi e generatori di testo consente un maggiore controllo sulla rotazione e la formattazione del testo. I paragrafi di testo offrono un modo strutturato per organizzare i frammenti di testo, mentre i builder facilitano la creazione e la manipolazione del contenuto di testo all'interno del documento PDF.

#### D: Posso applicare angoli di rotazione diversi a ciascun paragrafo di testo?

 R: Sì, puoi applicare diversi angoli di rotazione a ciascun paragrafo di testo impostando il`Rotation` proprietà del`TextParagraph` oggetto. Ciò consente di creare effetti di rotazione del testo diversi e dinamici all'interno del documento PDF.

#### D: Come posso personalizzare la formattazione dei frammenti di testo all'interno dei paragrafi di testo?

 R: Puoi personalizzare la formattazione dei frammenti di testo impostando varie proprietà del file`TextState` all'interno di ciascuno`TextFragment` oggetto. Proprietà come la dimensione del carattere, il tipo di carattere, i colori di primo piano e di sfondo e la sottolineatura possono essere regolati per ottenere l'effetto visivo desiderato.

#### D: Posso creare effetti di rotazione del testo più complessi utilizzando questo metodo?

R: Assolutamente. Creando in modo iterativo più paragrafi di testo con diversi angoli di rotazione e opzioni di formattazione, puoi ottenere effetti di rotazione del testo complessi e visivamente accattivanti che possono migliorare la leggibilità e l'estetica dei tuoi documenti PDF.

#### D: È possibile combinare la rotazione del testo con altre tecniche di manipolazione del testo?

R: Sì, puoi combinare la rotazione del testo con altre tecniche di manipolazione del testo fornite dalla libreria Aspose.PDF. Ciò include l'aggiunta di tabelle, immagini, collegamenti ipertestuali e altro per creare documenti PDF ricchi e informativi.

#### D: Ho bisogno di una licenza speciale per utilizzare la libreria Aspose.PDF nel mio progetto?

R: Sì, è necessaria una licenza Aspose valida per utilizzare la libreria Aspose.PDF nel tuo progetto. Puoi ottenere una licenza dal sito web Aspose, che ti fornirà le credenziali necessarie per integrare e utilizzare la libreria in modo efficace.