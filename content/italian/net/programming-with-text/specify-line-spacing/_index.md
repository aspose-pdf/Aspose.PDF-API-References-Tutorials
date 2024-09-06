---
title: Specificare la spaziatura delle righe nel file PDF
linktitle: Specificare la spaziatura delle righe nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come specificare la spaziatura delle righe in un file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 510
url: /it/net/programming-with-text/specify-line-spacing/
---
Questo tutorial spiega come specificare la spaziatura delle linee in un file PDF usando Aspose.PDF per .NET. Il codice sorgente C# fornito illustra il processo passo dopo passo.

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
using System.IO;
```

## Passaggio 3: impostare il percorso della directory del documento

 Imposta il percorso della directory del documento utilizzando`dataDir` variabile:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory del documento.

## Passaggio 4: caricare il file PDF di input

 Caricare il file PDF di input utilizzando`Document` classe:

```csharp
Document doc = new Document();
```

## Passaggio 5: creare TextFormattingOptions

 Crea un`TextFormattingOptions` oggetto e imposta la modalità di spaziatura delle linee su`FullSize`:

```csharp
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
```

## Passaggio 6: creare un TextFragment

 Crea un`TextFragment` oggetto e specificare il contenuto del testo:

```csharp
TextFragment textFragment = new TextFragment("Hello world");
```

## Passaggio 7: Carica il file del font (facoltativo)

 Se si desidera utilizzare un font specifico per il testo, caricare il file del font TrueType in un`FileStream` oggetto:

```csharp
string fontFile = dataDir + "HPSimplified.TTF";
using (FileStream fontStream = File.OpenRead(fontFile))
{
    textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
}
```

 Sostituire`"HPSimplified.TTF"` con il nome effettivo del file del font.

## Passaggio 8: specificare la posizione del testo e la spaziatura delle righe

 Imposta la posizione per il frammento di testo e assegna il`TextFormattingOptions` al`TextState.FormattingOptions` proprietà:

```csharp
textFragment.Position = new Position(100, 600);
textFragment.TextState.FormattingOptions = formattingOptions;
```

## Passaggio 9: aggiungere il testo al documento

 Aggiungere il frammento di testo al documento, sia aggiungendolo a un`TextBuilder` o direttamente a una pagina`Paragraphs` collezione:

```csharp
var page = doc.Pages.Add();
page.Paragraphs.Add(textFragment);
```

## Passaggio 10: salvare il documento PDF risultante

Salvare il documento PDF modificato:

```csharp
dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
doc.Save(dataDir);
```

 Assicurati di sostituire`"SpecifyLineSpacing_out.pdf"` con il nome del file di output desiderato.

### Esempio di codice sorgente per specificare la spaziatura delle linee utilizzando Aspose.PDF per .NET 
```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string fontFile = dataDir + "HPSimplified.TTF";
// Carica il file PDF di input
Document doc = new Document();
//Crea TextFormattingOptions con LineSpacingMode.FullSize
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
// Crea un oggetto generatore di testo per la prima pagina del documento
//TextBuilder textBuilder = nuovo TextBuilder(doc.Pages[1]);
// Crea frammento di testo con stringa di esempio
TextFragment textFragment = new TextFragment("Hello world");
if (fontFile != "")
{
	// Carica il font TrueType nell'oggetto stream
	using (FileStream fontStream = System.IO.File.OpenRead(fontFile))
	{
		// Imposta il nome del font per la stringa di testo
		textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
		//Specificare la posizione per il frammento di testo
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

Congratulazioni! Hai imparato con successo come specificare la spaziatura delle linee in un documento PDF usando Aspose.PDF per .NET. Questo tutorial ha fornito una guida passo passo, dall'impostazione del progetto al salvataggio del documento modificato. Ora puoi incorporare questo codice nei tuoi progetti C# per personalizzare la spaziatura delle linee del testo nei file PDF.

### Domande frequenti

#### D: Qual è lo scopo del tutorial "Specifica l'interlinea nel file PDF"?

R: Il tutorial "Specify Line Spacing In PDF File" ha lo scopo di guidare gli utenti su come utilizzare la libreria Aspose.PDF per .NET per personalizzare la spaziatura delle linee del testo all'interno di un documento PDF. Il tutorial fornisce istruzioni dettagliate ed esempi di codice C# per dimostrare il processo.

#### D: In che modo questo tutorial aiuta a specificare la spaziatura delle linee in un documento PDF?

A: Questo tutorial aiuta gli utenti a capire come utilizzare le capacità di Aspose.PDF per .NET per specificare la spaziatura delle linee per il testo in un documento PDF. Seguendo i passaggi e gli esempi di codice forniti, gli utenti possono regolare la spaziatura delle linee in base alle proprie preferenze.

#### D: Quali prerequisiti sono richiesti per seguire questo tutorial?

R: Prima di iniziare il tutorial, dovresti avere una conoscenza di base del linguaggio di programmazione C#. Inoltre, devi avere installata la libreria Aspose.PDF per .NET. Puoi ottenerla dal sito web di Aspose o installarla nel tuo progetto usando NuGet.

#### D: Come posso impostare il mio progetto in modo che segua questo tutorial?

R: Per iniziare, crea un nuovo progetto C# nel tuo ambiente di sviluppo integrato (IDE) preferito e aggiungi un riferimento alla libreria Aspose.PDF per .NET. Ciò ti consente di sfruttare le funzionalità della libreria per lavorare con documenti PDF e personalizzare la spaziatura delle linee.

#### D: Posso usare questo tutorial per specificare la spaziatura delle righe per qualsiasi tipo di testo?

R: Sì, questo tutorial fornisce istruzioni su come specificare la spaziatura delle linee per qualsiasi contenuto di testo all'interno di un documento PDF utilizzando Aspose.PDF per .NET. Puoi utilizzare gli esempi di codice forniti per regolare la spaziatura delle linee del testo in base alle tue esigenze.

#### D: Come faccio a specificare la modalità di spaziatura delle linee nel tutorial?

 A: Il tutorial mostra come creare un`TextFormattingOptions` oggetto e imposta il suo`LineSpacing` proprietà a`TextFormattingOptions.LineSpacingMode.FullSize`Questa modalità specifica la spaziatura completa delle righe per il contenuto del testo.

#### D: Come posso caricare un font specifico per il testo?

 A: Se desideri utilizzare un font specifico per il contenuto del testo, il tutorial fornisce indicazioni su come caricare un file di font TrueType in un`FileStream` oggetto e impostarlo come font per il`TextFragment`Ciò consente di personalizzare il carattere del testo e la spaziatura delle righe.

#### D: Come posso personalizzare la posizione del testo all'interno del documento PDF?

 A: Per personalizzare la posizione del testo, crea un`TextFragment` oggetto e imposta il suo`Position`proprietà alle coordinate desiderate (X e Y). Ciò consente di controllare dove il testo viene posizionato all'interno del documento PDF.

#### D: Posso applicare queste modifiche alla spaziatura delle linee ai documenti PDF esistenti?

 R: Sì, puoi modificare la spaziatura delle righe per il testo nei documenti PDF esistenti. Il tutorial mostra come creare un`TextFragment` con la spaziatura e la posizione specificate, quindi aggiungerlo a una pagina`Paragraphs` collezione.