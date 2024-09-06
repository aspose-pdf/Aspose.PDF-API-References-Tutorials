---
title: Nascondi i numeri di pagina nel sommario
linktitle: Nascondi i numeri di pagina nel sommario
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come nascondere i numeri di pagina in un indice utilizzando Aspose.PDF per .NET con questa guida dettagliata.
type: docs
weight: 220
url: /it/net/programming-with-document/hidepagenumbersintoc/
---
In questo articolo, discuteremo l'implementazione della funzionalità Hide Page Numbers In TOC di Aspose.PDF per .NET tramite C#. Inizieremo con una breve introduzione ad Aspose.PDF per .NET e poi ci immergeremo nella guida passo passo per implementare questa funzionalità. 

## Introduzione ad Aspose.PDF per .NET

Aspose.PDF per .NET è un potente componente di manipolazione PDF che consente agli sviluppatori di creare, modificare e manipolare file PDF a livello di programmazione. Fornisce un'ampia gamma di caratteristiche e funzionalità che semplificano il lavoro con i documenti PDF. Aspose.PDF per .NET supporta sia i sistemi operativi a 32 bit che a 64 bit e può essere utilizzato con le piattaforme .NET Framework, .NET Core e Xamarin. 

## Che cos'è la funzione Nascondi numeri di pagina nell'indice?

Il sommario (TOC) è una parte essenziale di un documento PDF che fornisce agli utenti una rapida panoramica del contenuto. A volte, gli utenti potrebbero voler nascondere i numeri di pagina nel TOC per renderlo più intuitivo. Aspose.PDF per .NET fornisce una funzionalità integrata per nascondere i numeri di pagina nel TOC. Questa funzionalità può essere utilizzata per creare documenti PDF più intuitivi. 

## Prerequisiti

Per seguire questo tutorial, avrai bisogno di quanto segue:

- Visual Studio 2010 o versione successiva
- Aspose.PDF per .NET installato sul tuo sistema
- Conoscenza di base del linguaggio di programmazione C#

## Guida passo passo per implementare la funzione Nascondi numeri di pagina nel sommario

Per implementare la funzionalità Nascondi numeri di pagina nel sommario utilizzando Aspose.PDF per .NET, seguire i passaggi sottostanti:

## Passaggio 1: creare una nuova applicazione console C# in Visual Studio

Aprire Visual Studio e creare una nuova applicazione console C#.

## Passaggio 2: aggiungere riferimento a Aspose.PDF per .NET

Fai clic con il pulsante destro del mouse sulla cartella Riferimenti nel tuo progetto e seleziona Aggiungi riferimento. Vai alla posizione in cui Aspose.PDF per .NET è installato sul tuo sistema e aggiungi un riferimento ad esso.

## Passaggio 1: creare un nuovo documento PDF

Crea un nuovo documento PDF utilizzando il seguente codice:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
```

## Passaggio 2: creare una pagina TOC

Crea una nuova pagina per l'indice e aggiungila al documento PDF utilizzando il seguente codice:

```csharp
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
```

## Passaggio 3: aggiungere la sezione elenco alla raccolta di sezioni del documento PDF

Aggiungere la sezione elenco alla raccolta di sezioni del documento PDF utilizzando il seguente codice:

```csharp
tocPage.TocInfo = tocInfo;
```

## Passaggio 4: definire il formato dell'elenco a quattro livelli

Definire il formato dell'elenco dei quattro livelli impostando i margini sinistri e le impostazioni del formato del testo di ciascun livello utilizzando il seguente codice:

```csharp
tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
Page page = doc.Pages.Add();
```

## Passaggio 5: aggiungere quattro titoli nella sezione

```csharp

for (int Level = 1; Level != 5; Level++)
{ 
	Heading heading2 = new Heading(Level); 
	TextSegment segment2 = new TextSegment(); 
	heading2.TocPage = tocPage; 
	heading2.Segments.Add(segment2); 
	heading2.IsAutoSequence = true; 
	segment2.Text = "this is heading of level " + Level; 
	heading2.IsInList = true; 
	page.Paragraphs.Add(heading2); 
}
doc.Save(outFile);

```

### Esempio di codice sorgente per nascondere i numeri di pagina nel sommario utilizzando Aspose.PDF per .NET

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
//Aggiungere la sezione elenco alla raccolta di sezioni del documento Pdf
tocPage.TocInfo = tocInfo;
//Definire il formato dell'elenco a quattro livelli impostando i margini sinistri e
//impostazioni del formato del testo di ogni livello

tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
Page page = doc.Pages.Add();
//Aggiungere quattro titoli nella sezione
for (int Level = 1; Level != 5; Level++)
	{ 
		Heading heading2 = new Heading(Level); 
		TextSegment segment2 = new TextSegment(); 
		heading2.TocPage = tocPage; 
		heading2.Segments.Add(segment2); 
		heading2.IsAutoSequence = true; 
		segment2.Text = "this is heading of level " + Level; 
		heading2.IsInList = true; 
		page.Paragraphs.Add(heading2); 
	}
doc.Save(outFile);
```

## Conclusione

In questo tutorial, abbiamo esplorato come lavorare con i metadati XMP in un documento PDF usando Aspose.PDF per .NET. I metadati XMP forniscono informazioni preziose sul documento PDF, tra cui il titolo, l'autore, la data di creazione e altro. Aspose.PDF per .NET consente agli sviluppatori di accedere e manipolare questi metadati, fornendo un'API flessibile e potente per lavorare con i documenti PDF.

### Domande frequenti

#### D: Cosa sono i metadati XMP in un documento PDF?

A: I metadati XMP (Extensible Metadata Platform) in un documento PDF sono un formato standard per archiviare informazioni sui metadati del documento. Include dettagli quali titolo del documento, autore, data di creazione, parole chiave e altro. I metadati XMP forniscono un modo strutturato e standardizzato per archiviare e condividere informazioni sul documento PDF.

#### D: Posso modificare i metadati XMP di un documento PDF utilizzando Aspose.PDF per .NET?

 A: Sì, puoi modificare i metadati XMP di un documento PDF a livello di programmazione utilizzando Aspose.PDF per .NET. Puoi accedere a`Info` proprietà del`Document` oggetto, che ti dà accesso alle proprietà dei metadati XMP. Puoi quindi aggiornare i valori di queste proprietà per modificare i metadati XMP del documento PDF.

#### D: Posso estrarre proprietà di metadati XMP personalizzate da un documento PDF utilizzando Aspose.PDF per .NET?

 A: Sì, puoi estrarre le proprietà dei metadati XMP personalizzati da un documento PDF utilizzando Aspose.PDF per .NET. Puoi utilizzare`Metadata` proprietà del`Document`oggetto, che fornisce accesso a tutte le proprietà dei metadati XMP del documento PDF. Puoi quindi estrarre proprietà personalizzate e utilizzare i loro valori secondo necessità.