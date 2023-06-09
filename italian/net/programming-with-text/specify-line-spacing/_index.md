---
title: Specifica l'interlinea
linktitle: Specifica l'interlinea
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come specificare l'interlinea in un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 510
url: /it/net/programming-with-text/specify-line-spacing/
---

Questo tutorial spiega come specificare l'interlinea in un documento PDF utilizzando Aspose.PDF per .NET. Il codice sorgente C# fornito illustra il processo passo dopo passo.

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
using System.IO;
```

## Passaggio 3: impostare il percorso della directory dei documenti

 Imposta il percorso della directory dei documenti utilizzando il file`dataDir` variabile:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

## Passaggio 4: caricare il file PDF di input

 Caricare il file PDF di input utilizzando il file`Document` classe:

```csharp
Document doc = new Document();
```

## Passaggio 5: creare TextFormattingOptions

 Creare un`TextFormattingOptions` oggetto e impostare la modalità interlinea su`FullSize`:

```csharp
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
```

## Passaggio 6: creare un frammento di testo

 Creare un`TextFragment` oggetto e specificare il contenuto del testo:

```csharp
TextFragment textFragment = new TextFragment("Hello world");
```

## Passaggio 7: carica il file del carattere (facoltativo)

 Se desideri utilizzare un carattere specifico per il testo, carica il file del carattere TrueType in un file`FileStream` oggetto:

```csharp
string fontFile = dataDir + "HPSimplified.TTF";
using (FileStream fontStream = File.OpenRead(fontFile))
{
    textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
}
```

 Sostituire`"HPSimplified.TTF"`con il nome del file del carattere effettivo.

## Passaggio 8: specificare la posizione del testo e l'interlinea

 Imposta la posizione per il frammento di testo e assegna il file`TextFormattingOptions` al`TextState.FormattingOptions` proprietà:

```csharp
textFragment.Position = new Position(100, 600);
textFragment.TextState.FormattingOptions = formattingOptions;
```

## Passaggio 9: aggiungi il testo al documento

 Aggiungi il frammento di testo al documento, aggiungendolo a a`TextBuilder` o direttamente a una pagina`Paragraphs` collezione:

```csharp
var page = doc.Pages.Add();
page.Paragraphs.Add(textFragment);
```

## Passaggio 10: salvare il documento PDF risultante

Salva il documento PDF modificato:

```csharp
dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
doc.Save(dataDir);
```

 Assicurati di sostituire`"SpecifyLineSpacing_out.pdf"` con il nome del file di output desiderato.

### Codice sorgente di esempio per specificare l'interlinea utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string fontFile = dataDir + "HPSimplified.TTF";
// Carica il file PDF di input
Document doc = new Document();
//Crea TextFormattingOptions con LineSpacingMode.FullSize
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
// Crea un oggetto generatore di testo per la prima pagina del documento
//TextBuilder textBuilder = new TextBuilder(doc.Pages[1]);
// Crea un frammento di testo con una stringa di esempio
TextFragment textFragment = new TextFragment("Hello world");
if (fontFile != "")
{
	// Carica il font TrueType nell'oggetto stream
	using (FileStream fontStream = System.IO.File.OpenRead(fontFile))
	{
		// Imposta il nome del carattere per la stringa di testo
		textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
		// Specificare la posizione per Frammento di testo
		textFragment.Position = new Position(100, 600);
		//Imposta TextFormattingOptions del frammento corrente su predefinito (che punta a LineSpacingMode.FullSize)
		textFragment.TextState.FormattingOptions = formattingOptions;
		// Aggiungi il testo a TextBuilder in modo che possa essere posizionato sopra il file PDF
		//textBuilder.AppendText(textFragment);
		var page = doc.Pages.Add();
		page.Paragraphs.Add(textFragment);
	}
	dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
	// Salva il documento PDF risultante
	doc.Save(dataDir);
}
```

## Conclusione

Congratulazioni! Hai imparato con successo come specificare l'interlinea in un documento PDF utilizzando Aspose.PDF per .NET. Questo tutorial ha fornito una guida passo passo, dall'impostazione del progetto al salvataggio del documento modificato. Ora puoi incorporare questo codice nei tuoi progetti C# per personalizzare l'interlinea del testo nei file PDF.