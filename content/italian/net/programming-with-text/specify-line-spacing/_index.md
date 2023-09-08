---
title: Specifica l'interlinea nel file PDF
linktitle: Specifica l'interlinea nel file PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come specificare l'interlinea nel file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 510
url: /it/net/programming-with-text/specify-line-spacing/
---
Questo tutorial spiega come specificare l'interlinea nel file PDF utilizzando Aspose.PDF per .NET. Il codice sorgente C# fornito illustra il processo passo dopo passo.

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
using System.IO;
```

## Passaggio 3: impostare il percorso della directory dei documenti

 Imposta il percorso della directory dei documenti utilizzando il file`dataDir` variabile:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

## Passaggio 4: carica il file PDF di input

 Caricare il file PDF di input utilizzando il file`Document` classe:

```csharp
Document doc = new Document();
```

## Passaggio 5: crea opzioni di formattazione del testo

 Creare un`TextFormattingOptions` oggetto e impostare la modalità di interlinea su`FullSize`:

```csharp
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
```

## Passaggio 6: crea un TextFragment

 Creare un`TextFragment` oggetto e specificare il contenuto del testo:

```csharp
TextFragment textFragment = new TextFragment("Hello world");
```

## Passaggio 7: caricare il file del carattere (facoltativo)

 Se desideri utilizzare un carattere specifico per il testo, carica il file dei caratteri TrueType in un file`FileStream` oggetto:

```csharp
string fontFile = dataDir + "HPSimplified.TTF";
using (FileStream fontStream = File.OpenRead(fontFile))
{
    textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
}
```

 Sostituire`"HPSimplified.TTF"` con il nome effettivo del file del carattere.

## Passaggio 8: specificare la posizione del testo e l'interlinea

 Imposta la posizione per il frammento di testo e assegna il`TextFormattingOptions` al`TextState.FormattingOptions` proprietà:

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

## Passaggio 10: salva il documento PDF risultante

Salvare il documento PDF modificato:

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
	// Carica il carattere TrueType nell'oggetto stream
	using (FileStream fontStream = System.IO.File.OpenRead(fontFile))
	{
		//Imposta il nome del carattere per la stringa di testo
		textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
		// Specificare la posizione per il frammento di testo
		textFragment.Position = new Position(100, 600);
		//Imposta TextFormattingOptions del frammento corrente su predefinito (che punta a LineSpacingMode.FullSize)
		textFragment.TextState.FormattingOptions = formattingOptions;
		// Aggiungi il testo a TextBuilder in modo che possa essere posizionato sul file PDF
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

### Domande frequenti

#### D: Qual è lo scopo del tutorial "Specifica l'interlinea nel file PDF"?

R: Il tutorial "Specifica l'interlinea nel file PDF" mira a guidare gli utenti su come utilizzare la libreria Aspose.PDF per .NET per personalizzare l'interlinea del testo all'interno di un documento PDF. L'esercitazione fornisce istruzioni dettagliate ed esempi di codice C# per dimostrare il processo.

#### D: In che modo questo tutorial aiuta a specificare l'interlinea all'interno di un documento PDF?

R: Questo tutorial aiuta gli utenti a capire come utilizzare le funzionalità di Aspose.PDF per .NET per specificare l'interlinea per il testo in un documento PDF. Seguendo i passaggi forniti e gli esempi di codice, gli utenti possono regolare l'interlinea in base alle proprie preferenze.

#### D: Quali prerequisiti sono richiesti per seguire questo tutorial?

R: Prima di iniziare il tutorial, dovresti avere una conoscenza di base del linguaggio di programmazione C#. Inoltre, è necessario che sia installata la libreria Aspose.PDF per .NET. È possibile ottenerlo dal sito Web Aspose o installarlo nel progetto utilizzando NuGet.

#### D: Come posso impostare il mio progetto per seguire questo tutorial?

R: Per iniziare, crea un nuovo progetto C# nel tuo ambiente di sviluppo integrato (IDE) preferito e aggiungi un riferimento alla libreria Aspose.PDF per .NET. Ciò consente di sfruttare le funzionalità della libreria per lavorare con documenti PDF e personalizzare l'interlinea.

#### D: Posso utilizzare questo tutorial per specificare l'interlinea per qualsiasi tipo di testo?

R: Sì, questo tutorial fornisce istruzioni su come specificare l'interlinea per qualsiasi contenuto di testo all'interno di un documento PDF utilizzando Aspose.PDF per .NET. È possibile utilizzare gli esempi di codice forniti per regolare l'interlinea del testo in base alle proprie esigenze.

#### D: Come posso specificare la modalità di interlinea nel tutorial?

 R: Il tutorial mostra come creare un file`TextFormattingOptions` oggetto e impostarlo`LineSpacing` proprietà a`TextFormattingOptions.LineSpacingMode.FullSize`. Questa modalità specifica l'interlinea completa per il contenuto del testo.

#### D: Come posso caricare un carattere specifico per il testo?

 R: Se desideri utilizzare un carattere specifico per il contenuto testuale, il tutorial fornisce indicazioni su come caricare un file di caratteri TrueType in un`FileStream` oggetto e impostarlo come carattere per il file`TextFragment`. Ciò consente di personalizzare il carattere del testo insieme alla sua interlinea.

#### D: Come posso personalizzare la posizione del testo all'interno del documento PDF?

 R: Per personalizzare la posizione del testo, crea a`TextFragment` oggetto e impostarlo`Position`proprietà alle coordinate desiderate (X e Y). Ciò consente di controllare dove viene posizionato il testo all'interno del documento PDF.

#### D: Posso applicare queste modifiche all'interlinea ai documenti PDF esistenti?

 R: Sì, puoi modificare l'interlinea per il testo nei documenti PDF esistenti. Il tutorial mostra come creare un file`TextFragment` con l'interlinea e la posizione specificate, quindi aggiungerlo a una pagina`Paragraphs` collezione.