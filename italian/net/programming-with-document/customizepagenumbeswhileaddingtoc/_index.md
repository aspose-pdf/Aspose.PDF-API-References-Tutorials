---
title: Personalizza i numeri di pagina durante l'aggiunta del TOC
linktitle: Personalizza i numeri di pagina durante l'aggiunta del TOC
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come personalizzare i numeri di pagina durante l'aggiunta di un sommario (TOC) utilizzando Aspose.PDF per .NET con questa guida dettagliata e un esempio di codice.
type: docs
weight: 100
url: /it/net/programming-with-document/customizepagenumbeswhileaddingtoc/
---
In questo tutorial, esploreremo come personalizzare i numeri di pagina durante l'aggiunta di un sommario (TOC) utilizzando Aspose.PDF per .NET. Forniremo una guida dettagliata, insieme a un esempio di codice, per aiutarti a raggiungere questo obiettivo.

## Passaggio 1: caricamento di un file PDF esistente

Innanzitutto, dobbiamo caricare un file PDF esistente. Per questo tutorial, utilizzeremo il file "42824.pdf" che si trova nella directory "YOUR DOCUMENT DIRECTORY". Sostituisci questo percorso di directory con il percorso effettivo della directory dei documenti.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "42824.pdf";
string outFile = dataDir + "42824_out.pdf";
Document doc = new Document(inFile);
```

## Passaggio 2: aggiunta di una pagina TOC

 Successivamente, dobbiamo aggiungere una nuova pagina all'inizio del documento che funga da pagina TOC. Possiamo raggiungere questo obiettivo utilizzando il`Insert()` metodo del`Pages` raccolta del`Document` oggetto.

```csharp
Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
```

## Passaggio 3: creazione di un oggetto TOC

 Per creare un oggetto TOC, dobbiamo prima creare un file`TocInfo` oggetto e impostarne le proprietà. In questo tutorial, imposteremo il titolo del TOC su "Sommario" e il prefisso del numero di pagina su "P".

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocInfo.PageNumbersPrefix = "P";
tocPage.TocInfo = tocInfo;
```

## Passaggio 4: creazione di voci TOC

Per creare voci TOC, dobbiamo scorrere tutte le pagine del documento, ad eccezione della pagina TOC, e creare un oggetto intestazione per ogni pagina. Possiamo quindi aggiungere l'oggetto intestazione alla pagina TOC e specificare la sua pagina di destinazione.

```csharp
for (int i = 1; i < doc.Pages.Count; i++)
{
    // Crea oggetto Intestazione
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);
    // Specificare la pagina di destinazione per l'oggetto intestazione
    heading2.DestinationPage = doc.Pages[i + 1];
    // Pagina di destinazione
    heading2.Top = doc.Pages[i + 1].Rect.Height;
    // Coordinate di destinazione
    segment2.Text = "Page " + i.ToString();
    // Aggiungi un'intestazione alla pagina contenente il TOC
    tocPage.Paragraphs.Add(heading2);
}
```

## Passaggio 5: salvare il documento aggiornato

Infine, dobbiamo salvare il documento aggiornato in un nuovo file. Possiamo raggiungere questo obiettivo utilizzando il`Save()` metodo del`Document` oggetto.

```csharp
doc.Save(outFile);
```

### Codice sorgente di esempio per la personalizzazione dei numeri di pagina durante l'aggiunta del sommario utilizzando Aspose.PDF per .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "42824.pdf";
string outFile = dataDir + "42824_out.pdf";
// Carica un file PDF esistente
Document doc = new Document(inFile);
// Ottieni l'accesso alla prima pagina del file PDF
Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
// Crea un oggetto per rappresentare le informazioni TOC
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
// Imposta il titolo per TOC
tocInfo.Title = title;
tocInfo.PageNumbersPrefix = "P";
tocPage.TocInfo = tocInfo;
for (int i = 1; i<doc.Pages.Count; i++)
{
	// Crea oggetto Intestazione
	Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
	TextSegment segment2 = new TextSegment();
	heading2.TocPage = tocPage;
	heading2.Segments.Add(segment2);
	// Specificare la pagina di destinazione per l'oggetto intestazione
	heading2.DestinationPage = doc.Pages[i + 1];
	// Pagina di destinazione
	heading2.Top = doc.Pages[i + 1].Rect.Height;
	// Coordinate di destinazione
	segment2.Text = "Page " + i.ToString();
	// Aggiungi un'intestazione alla pagina contenente il TOC
	tocPage.Paragraphs.Add(heading2);
}

// Salva il documento aggiornato
doc.Save(outFile);
```

## Conclusione

In questo tutorial, abbiamo fornito una guida dettagliata su come personalizzare i numeri di pagina durante l'aggiunta di un sommario utilizzando Aspose.PDF per .NET. Abbiamo anche fornito un esempio di codice che puoi usare come riferimento quando implementi questa funzione nel tuo

### FAQ

#### D: Cos'è un sommario (TOC) in un documento PDF?

R: Un sommario (TOC) in un documento PDF è un aiuto alla navigazione che fornisce un elenco organizzato di sezioni o capitoli del documento insieme ai numeri di pagina corrispondenti. Consente ai lettori di navigare rapidamente verso sezioni specifiche all'interno del documento.

#### D:Perché dovrei personalizzare i numeri di pagina in un sommario?

R: La personalizzazione dei numeri di pagina in un sommario può essere utile quando si desidera utilizzare un formato di numerazione delle pagine specifico o includere informazioni aggiuntive insieme ai numeri di pagina. Ti consente di creare un sommario più personalizzato e informativo.

#### D: Posso includere collegamenti ipertestuali nel sommario per collegare a sezioni o pagine specifiche all'interno del documento PDF?

R: Sì, Aspose.PDF per .NET consente di creare collegamenti ipertestuali nel sommario che si collegano a sezioni o pagine specifiche all'interno del documento PDF. Ciò migliora l'interattività e la navigazione del documento PDF.

#### D: Aspose.PDF per .NET è compatibile con gli standard PDF/A?

R: Sì, Aspose.PDF per .NET supporta gli standard PDF/A, inclusi PDF/A-1, PDF/A-2 e PDF/A-3. Consente di creare documenti PDF conformi ai requisiti di archiviazione e conservazione a lungo termine.

#### D: Posso aggiungere più formattazione alle voci del sommario, come stili di carattere o colori?

R: Sì, puoi aggiungere una formattazione aggiuntiva alle voci del sommario, come stili di carattere, colori e dimensioni dei caratteri, utilizzando Aspose.PDF per .NET. Ciò consente di personalizzare l'aspetto del TOC in base alle proprie esigenze.
