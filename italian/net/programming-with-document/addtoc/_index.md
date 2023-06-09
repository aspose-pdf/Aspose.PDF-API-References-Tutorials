---
title: Aggiungi TOC
linktitle: Aggiungi TOC
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come aggiungere un sommario ai documenti PDF utilizzando Aspose.PDF per .NET. Guida dettagliata con codice sorgente di esempio. Potenzia la navigazione dei documenti!
type: docs
weight: 40
url: /it/net/programming-with-document/addtoc/
---

In questo tutorial, esploreremo come utilizzare la funzione Aggiungi TOC (Table of Contents) di Aspose.PDF per .NET per aggiungere un sommario ai documenti PDF. Forniremo una guida dettagliata e spiegheremo il codice sorgente C# necessario per raggiungere questo obiettivo. Alla fine di questo tutorial, sarai in grado di generare un documento PDF con un sommario utilizzando Aspose.PDF per .NET.


## Passaggio 1: carica il file PDF esistente

 Per iniziare, dobbiamo caricare un file PDF esistente. Sostituire`"YOUR DOCUMENT DIRECTORY"` nel codice seguente con il percorso effettivo del file PDF:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "AddTOC.pdf");
```

## Passaggio 2: creare una nuova pagina per il sommario

Creeremo una nuova pagina per contenere il sommario. Il codice seguente inserisce una nuova pagina all'indice 1:

```csharp
Page tocPage = doc.Pages.Insert(1);
```

## Passaggio 3: definire le informazioni del sommario

Successivamente, dobbiamo definire le informazioni del sommario. Imposteremo il titolo e altre proprietà del sommario. Aggiungi il seguente codice:

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;

tocInfo.Title = title;
tocPage.TocInfo = tocInfo;
```

## Passaggio 4: creare elementi TOC

Ora creeremo gli elementi del sommario. In questo tutorial, creeremo quattro elementi TOC corrispondenti a pagine diverse. Modifica il seguente codice in base alle tue esigenze:

```csharp
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";

for (int i = 0; i < 2; i++)
{
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);

    heading2.DestinationPage = doc.Pages[i + 2];
    heading2.Top = doc.Pages[i + 2].Rect.Height;

    segment2.Text = titles[i];
    tocPage.Paragraphs.Add(heading2);
}
```

## Passaggio 5: salvare il documento aggiornato

 Infine, dobbiamo salvare il documento modificato con l'indice. Sostituire`"YOUR DOCUMENT DIRECTORY"` nel codice seguente con il percorso del file di output desiderato:

```csharp
dataDir = dataDir + "TOC_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

### Esempio di codice sorgente per l'aggiunta di TOC ai documenti PDF utilizzando Aspose.PDF per .NET

```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Carica un file PDF esistente
Document doc = new Document(dataDir + "AddTOC.pdf");

// Ottieni l'accesso alla prima pagina del file PDF
Page tocPage = doc.Pages.Insert(1);

// Crea un oggetto per rappresentare le informazioni TOC
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;

// Imposta il titolo per TOC
tocInfo.Title = title;
tocPage.TocInfo = tocInfo;

// Crea oggetti stringa che verranno utilizzati come elementi TOC
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";
for (int i = 0; i < 2; i++)
{
	// Crea oggetto Intestazione
	Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
	TextSegment segment2 = new TextSegment();
	heading2.TocPage = tocPage;
	heading2.Segments.Add(segment2);

	// Specificare la pagina di destinazione per l'oggetto intestazione
	heading2.DestinationPage = doc.Pages[i + 2];

	// Pagina di destinazione
	heading2.Top = doc.Pages[i + 2].Rect.Height;

	// Coordinate di destinazione
	segment2.Text = titles[i];

	//Aggiungi un'intestazione alla pagina contenente il sommario
	tocPage.Paragraphs.Add(heading2);
}
dataDir = dataDir + "TOC_out.pdf";
// Salva il documento aggiornato
doc.Save(dataDir);

Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```
