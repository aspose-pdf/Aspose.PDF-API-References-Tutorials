---
title: Ruota il testo usando il paragrafo del testo e il generatore
linktitle: Ruota il testo usando il paragrafo del testo e il generatore
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come ruotare il testo utilizzando il paragrafo di testo e il generatore in un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 410
url: /it/net/programming-with-text/rotate-text-using-text-paragraph-and-builder/
---

Questo tutorial spiega come utilizzare Aspose.PDF per .NET per ruotare il testo utilizzando paragrafi di testo e costruttori. Il codice sorgente C# fornito illustra il processo passo dopo passo.

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
using Aspose.Pdf.Text.TextBuilder;
```

## Passaggio 3: creare il documento PDF

 Inizializza il`Document` oggetto per creare un nuovo documento PDF:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document();
```

 Assicurati di sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

## Passaggio 4: aggiungi una pagina

 Ottenere una pagina particolare dal documento utilizzando il file`Pages.Add()` metodo:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Passaggio 5: crea e ruota i paragrafi di testo

 Creare un`for` loop per generare più paragrafi di testo con diverse rotazioni:

```csharp
for (int i = 0; i < 4; i++)
{
	TextParagraph paragraph = new TextParagraph();
	paragraph.Position = new Position(200, 600);
	paragraph.Rotation = i * 90 + 45;
```

Regola i valori di posizione e rotazione in base alle tue esigenze.

## Passaggio 6: creare e configurare frammenti di testo

 Crea multipli`TextFragment`oggetti, impostarne il testo e le proprietà:

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

Regola il testo e altre proprietà come desiderato.

## Passaggio 7: aggiungi frammenti di testo al paragrafo

 Aggiungi i frammenti di testo creati al paragrafo usando il`AppendLine` metodo:

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

## Passaggio 9: salvare il documento PDF

 Salva il documento PDF modificato in un file utilizzando il formato`Save` metodo:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated4_out.pdf");
```

 Assicurati di sostituire`"TextFragmentTests_Rotated4_out.pdf"` con il nome del file di output desiderato.

## Conclusione

Congratulazioni! Hai imparato con successo come ruotare il testo utilizzando paragrafi di testo e costruttori in un documento PDF utilizzando Aspose.PDF per .NET. Questo tutorial ha fornito una guida passo passo, dalla creazione del documento al salvataggio della versione modificata. Ora puoi incorporare questo codice nei tuoi progetti C# per manipolare la rotazione del testo nei file PDF.

### Esempio di codice sorgente per Ruota testo utilizzando il paragrafo di testo e il generatore utilizzando Aspose.PDF per .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Inizializza oggetto documento
Document pdfDocument = new Document();
// Ottieni una pagina particolare
Page pdfPage = (Page)pdfDocument.Pages.Add();
for (int i = 0; i < 4; i++)
{
	TextParagraph paragraph = new TextParagraph();
	paragraph.Position = new Position(200, 600);
	// Specificare la rotazione
	paragraph.Rotation = i * 90 + 45;
	// Crea un frammento di testo
	TextFragment textFragment1 = new TextFragment("Paragraph Text");
	// Crea un frammento di testo
	textFragment1.TextState.FontSize = 12;
	textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
	textFragment1.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
	textFragment1.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	// Crea un frammento di testo
	TextFragment textFragment2 = new TextFragment("Second line of text");
	// Imposta le proprietà del testo
	textFragment2.TextState.FontSize = 12;
	textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
	textFragment2.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
	textFragment2.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	// Crea un frammento di testo
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