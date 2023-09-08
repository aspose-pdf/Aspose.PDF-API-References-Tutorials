---
title: Nascondi i numeri di pagina nel sommario
linktitle: Nascondi i numeri di pagina nel sommario
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come nascondere i numeri di pagina in un sommario utilizzando Aspose.PDF per .NET con questa guida passo passo.
type: docs
weight: 220
url: /it/net/programming-with-document/hidepagenumbersintoc/
---
In questo articolo, discuteremo dell'implementazione della funzione Nascondi numeri di pagina nel sommario di Aspose.PDF per .NET utilizzando C#. Inizieremo con una breve introduzione ad Aspose.PDF per .NET e poi ci immergeremo nella guida passo passo per implementare questa funzionalità. 

## Introduzione ad Aspose.PDF per .NET

Aspose.PDF per .NET è un potente componente di manipolazione PDF che consente agli sviluppatori di creare, modificare e manipolare file PDF a livello di codice. Fornisce un'ampia gamma di caratteristiche e funzionalità che semplificano il lavoro con i documenti PDF. Aspose.PDF per .NET supporta sia i sistemi operativi a 32 bit che a 64 bit e può essere utilizzato con le piattaforme .NET Framework, .NET Core e Xamarin. 

## Che cos'è la funzione Nascondi i numeri di pagina nel sommario?

Il sommario (TOC) è una parte essenziale di un documento PDF che fornisce agli utenti una rapida panoramica del contenuto. A volte, gli utenti potrebbero voler nascondere i numeri di pagina nel sommario per renderlo più facile da usare. Aspose.PDF per .NET fornisce una funzionalità integrata per nascondere i numeri di pagina nel sommario. Questa funzione può essere utilizzata per creare documenti PDF più intuitivi. 

## Prerequisiti

Per seguire questo tutorial, avrai bisogno di quanto segue:

- Visual Studio 2010 o versione successiva
- Aspose.PDF per .NET installato sul tuo sistema
- Conoscenza base del linguaggio di programmazione C#

## Guida passo passo per implementare la funzione Nascondi i numeri di pagina nel sommario

Seguire i passaggi seguenti per implementare la funzione Nascondi numeri di pagina nel sommario utilizzando Aspose.PDF per .NET:

## Passaggio 1: creare una nuova applicazione console C# in Visual Studio

Apri Visual Studio e crea una nuova applicazione console C#.

## Passaggio 2: aggiungere riferimento ad Aspose.PDF per .NET

Fai clic con il pulsante destro del mouse sulla cartella Riferimenti nel progetto e seleziona Aggiungi riferimento. Passare alla posizione in cui Aspose.PDF per .NET è installato sul sistema e aggiungere un riferimento ad esso.

## Passaggio 1: crea un nuovo documento PDF

Crea un nuovo documento PDF utilizzando il seguente codice:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
```

## Passaggio 2: crea una pagina di sommario

Crea una nuova pagina per il sommario e aggiungila al documento PDF utilizzando il seguente codice:

```csharp
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
```

## Passaggio 3: aggiungi la sezione elenco alla raccolta di sezioni del documento PDF

Aggiungi la sezione elenco alla raccolta sezioni del documento PDF utilizzando il seguente codice:

```csharp
tocPage.TocInfo = tocInfo;
```

## Passaggio 4: Definire il formato dell'elenco dei quattro livelli

Definisci il formato dell'elenco dei quattro livelli impostando i margini sinistri e le impostazioni del formato del testo di ciascun livello utilizzando il seguente codice:

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

## Passaggio 5: aggiungi quattro intestazioni nella sezione

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
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
//Aggiungi la sezione elenco alla raccolta sezioni del documento Pdf
tocPage.TocInfo = tocInfo;
//Definire il formato dell'elenco dei quattro livelli impostando i margini sinistri e
//impostazioni del formato testo di ciascun livello

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
//Aggiungi quattro titoli nella sezione
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

In questo tutorial, abbiamo esplorato come lavorare con i metadati XMP in un documento PDF utilizzando Aspose.PDF per .NET. I metadati XMP forniscono informazioni preziose sul documento PDF, inclusi titolo, autore, data di creazione e altro ancora. Aspose.PDF per .NET consente agli sviluppatori di accedere e manipolare questi metadati, fornendo un'API flessibile e potente per lavorare con documenti PDF.

### Domande frequenti

#### D: Cosa sono i metadati XMP in un documento PDF?

R: I metadati XMP (Extensible Metadata Platform) in un documento PDF sono un formato standard per l'archiviazione delle informazioni sui metadati del documento. Include dettagli come titolo del documento, autore, data di creazione, parole chiave e altro. I metadati XMP forniscono un modo strutturato e standardizzato per archiviare e condividere informazioni sul documento PDF.

#### D: Posso modificare i metadati XMP di un documento PDF utilizzando Aspose.PDF per .NET?

 R: Sì, è possibile modificare i metadati XMP di un documento PDF a livello di codice utilizzando Aspose.PDF per .NET. Puoi accedere al`Info` proprietà del`Document` oggetto, che ti dà accesso alle proprietà dei metadati XMP. È quindi possibile aggiornare i valori di queste proprietà per modificare i metadati XMP del documento PDF.

#### D: Posso estrarre proprietà di metadati XMP personalizzate da un documento PDF utilizzando Aspose.PDF per .NET?

 R: Sì, puoi estrarre proprietà di metadati XMP personalizzate da un documento PDF utilizzando Aspose.PDF per .NET. Puoi usare il`Metadata` proprietà del`Document`oggetto, che fornisce l'accesso a tutte le proprietà dei metadati XMP del documento PDF. È quindi possibile estrarre le proprietà personalizzate e utilizzarne i valori secondo necessità.