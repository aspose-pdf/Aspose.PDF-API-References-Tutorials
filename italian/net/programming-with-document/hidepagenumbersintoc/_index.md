---
title: Nascondi i numeri di pagina nel sommario
linktitle: Nascondi i numeri di pagina nel sommario
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come nascondere i numeri di pagina in un sommario utilizzando Aspose.PDF per .NET con questa guida dettagliata.
type: docs
weight: 220
url: /it/net/programming-with-document/hidepagenumbersintoc/
---
In questo articolo, discuteremo l'implementazione della funzione Nascondi i numeri di pagina nel sommario di Aspose.PDF per .NET utilizzando C#. Inizieremo con una breve introduzione ad Aspose.PDF per .NET e poi ci immergeremo nella guida passo-passo per implementare questa funzione. 

## Introduzione a Aspose.PDF per .NET

Aspose.PDF per .NET è un potente componente di manipolazione PDF che consente agli sviluppatori di creare, modificare e manipolare file PDF a livello di codice. Fornisce una vasta gamma di caratteristiche e funzionalità che semplificano il lavoro con i documenti PDF. Aspose.PDF per .NET supporta entrambi i sistemi operativi a 32 e 64 bit e può essere utilizzato con le piattaforme .NET Framework, .NET Core e Xamarin. 

## Cos'è la funzione Nascondi i numeri di pagina nel sommario?

Il sommario (TOC) è una parte essenziale di un documento PDF che fornisce agli utenti una rapida panoramica del contenuto. A volte, gli utenti potrebbero voler nascondere i numeri di pagina nel sommario per renderlo più intuitivo. Aspose.PDF per .NET fornisce una funzionalità integrata per nascondere i numeri di pagina nel TOC. Questa funzione può essere utilizzata per creare documenti PDF più intuitivi. 

## Prerequisiti

Per seguire questo tutorial, avrai bisogno di quanto segue:

- Visual Studio 2010 o versioni successive
- Aspose.PDF per .NET installato sul tuo sistema
- Conoscenza base del linguaggio di programmazione C#

## Guida dettagliata per implementare la funzione Nascondi i numeri di pagina nel sommario

Seguire i passaggi seguenti per implementare la funzione Nascondi i numeri di pagina nel sommario utilizzando Aspose.PDF per .NET:

## Passaggio 1: creare una nuova applicazione console C# in Visual Studio

Apri Visual Studio e crea una nuova applicazione console C#.

## Passaggio 2: aggiungere un riferimento a Aspose.PDF per .NET

Fai clic con il pulsante destro del mouse sulla cartella Riferimenti nel tuo progetto e seleziona Aggiungi riferimento. Passare alla posizione in cui Aspose.PDF per .NET è installato sul sistema e aggiungere un riferimento ad esso.

## Passaggio 1: crea un nuovo documento PDF

Crea un nuovo documento PDF utilizzando il seguente codice:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
```

## Passaggio 2: creare una pagina TOC

Crea una nuova pagina per il sommario e aggiungila al documento PDF utilizzando il seguente codice:

```csharp
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
```

## Passaggio 3: aggiungi la sezione dell'elenco alla raccolta delle sezioni del documento PDF

Aggiungi la sezione elenco alla raccolta sezioni del documento PDF utilizzando il seguente codice:

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
//Aggiungi la sezione dell'elenco alla raccolta delle sezioni del documento Pdf
tocPage.TocInfo = tocInfo;
//Definire il formato dell'elenco a quattro livelli impostando i margini sinistri e
//impostazioni del formato di testo di ciascun livello

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
//Aggiungi quattro intestazioni nella sezione
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
