---
title: Margini o riempimento
linktitle: Margini o riempimento
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come impostare margini o spaziatura in una tabella utilizzando Aspose.PDF per .NET.
type: docs
weight: 140
url: /it/net/programming-with-tables/margins-or-padding/
---
In questo tutorial, ti guideremo passo dopo passo nel processo di utilizzo di Aspose.PDF per .NET per impostare margini o padding in una tabella. Forniremo spiegazioni e frammenti di codice per aiutarti a comprendere e implementare questa funzionalità nel tuo codice sorgente C#.

## Passaggio 1: impostazione del documento e della pagina
Per iniziare, è necessario impostare il documento e la pagina utilizzando il seguente codice:

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crea un'istanza dell'oggetto Document chiamando il suo costruttore vuoto
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Passaggio 2: creazione di una tabella
Successivamente, creeremo un oggetto tabella utilizzando la classe Aspose.Pdf.Table:

```csharp
// Creare un'istanza di un oggetto tabella
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Aggiungere la tabella alla raccolta di paragrafi della sezione desiderata
page.Paragraphs.Add(tab1);
```

## Passaggio 3: impostazione della larghezza delle colonne e del bordo predefinito delle celle
Per impostare la larghezza delle colonne e il bordo predefinito delle celle della tabella, utilizzare il seguente codice:

```csharp
// Imposta la larghezza delle colonne della tabella
tab1. ColumnWidths = "50 50 50";
// Imposta il bordo predefinito della cella utilizzando l'oggetto BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## Passaggio 4: impostazione del bordo della tabella e della spaziatura delle celle
Per impostare il bordo della tabella e la spaziatura delle celle, crea un oggetto MarginInfo e impostane le proprietà:

```csharp
// Crea un oggetto MarginInfo e imposta i suoi margini sinistro, inferiore, destro e superiore
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;

// Imposta la spaziatura predefinita delle celle sull'oggetto MarginInfo
tab1. DefaultCellPadding = margin;

// Imposta il bordo della tabella utilizzando un altro oggetto BorderInfo personalizzato
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
```

## Passaggio 5: aggiunta di righe e celle
Ora, aggiungiamo righe e celle alla tabella. Creeremo una nuova riga e vi aggiungeremo celle:

```csharp
// Crea righe nella tabella e poi celle nelle righe
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add();
```

## Passaggio 6: aggiunta di testo alle celle
Per aggiungere testo a una cella, crea un oggetto TextFragment e aggiungilo alla cella desiderata:

```csharp
TextFragment mytext = new TextFragment("col3 with large text string");
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
```

## Passaggio 7: salvataggio del PDF
Per salvare il documento PDF, utilizzare il seguente codice:

```csharp
dataDir = dataDir + "MarginsOrPadding_out.pdf";
// Salva il PDF
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir);
```

### Esempio di codice sorgente per margini o riempimento utilizzando Aspose.PDF per .NET

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Istanziare l'oggetto Document chiamando il suo costruttore vuoto
Document doc = new Document();
Page page = doc.Pages.Add();
// Creare un'istanza di un oggetto tabella
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Aggiungere la tabella nella raccolta di paragrafi della sezione desiderata
page.Paragraphs.Add(tab1);
// Impostato con le larghezze delle colonne della tabella
tab1.ColumnWidths = "50 50 50";
// Imposta il bordo predefinito della cella utilizzando l'oggetto BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// Imposta il bordo della tabella utilizzando un altro oggetto BorderInfo personalizzato
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// Crea l'oggetto MarginInfo e imposta i suoi margini sinistro, inferiore, destro e superiore
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Imposta la spaziatura predefinita delle celle sull'oggetto MarginInfo
tab1.DefaultCellPadding = margin;
// Crea righe nella tabella e poi celle nelle righe
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add();
TextFragment mytext = new TextFragment("col3 with large text string");
// Row1.Cells.Add("col3 con stringa di testo di grandi dimensioni da posizionare all'interno della cella");
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
// Riga1.Celle[2].Paragrafi[0].LarghezzaFissa= 80;
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
dataDir = dataDir + "MarginsOrPadding_out.pdf";
// Salva il PDF
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir); 
```

## Conclusione
Congratulazioni! Hai imparato con successo come impostare margini o padding in una tabella usando Aspose.PDF per .NET. Questa conoscenza ti aiuterà a migliorare le tue capacità di formattazione dei documenti e a rendere le tue tabelle visivamente accattivanti.

### Domande frequenti

#### D: Posso impostare margini o spaziature diverse per le singole celle di una tabella?

R: Sì, puoi impostare margini o padding diversi per singole celle in una tabella usando Aspose.PDF per .NET. Nell'esempio fornito, abbiamo impostato il padding predefinito per l'intera tabella usando`DefaultCellPadding` proprietà. Per impostare un padding diverso per celle specifiche, puoi accedere a`MarginInfo` di ogni cella individualmente e modificarne i margini.

#### D: Come posso cambiare il colore del bordo o lo stile della tabella?

 A: Per cambiare il colore del bordo o lo stile della tabella, puoi modificare il`Color` E`Width` proprietà del`BorderInfo` oggetto. Nell'esempio dato, impostiamo il colore del bordo su nero e una larghezza di 1F (un punto) utilizzando`tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);`Puoi regolare il colore e la larghezza in base alle tue esigenze.

#### D: È possibile aggiungere intestazioni o piè di pagina alla tabella?

R: Sì, puoi aggiungere intestazioni o piè di pagina alla tabella usando Aspose.PDF per .NET. Intestazioni e piè di pagina sono in genere righe separate che contengono informazioni aggiuntive come etichette di colonna, titoli di tabella o dati di riepilogo. Puoi creare righe aggiuntive, assegnargli uno stile diverso e aggiungerle sopra o sotto il contenuto della tabella.

#### D: Come faccio a regolare l'allineamento del testo all'interno di una cella di una tabella?

 A: Per regolare l'allineamento del testo all'interno di una cella della tabella, puoi utilizzare`HorizontalAlignment` E`VerticalAlignment` proprietà del`TextFragment` oggetto. Ad esempio, per allineare al centro il testo orizzontalmente, puoi impostare`mytext.HorizontalAlignment = HorizontalAlignment.Center;` Allo stesso modo, puoi impostare`mytext.VerticalAlignment` per controllare l'allineamento verticale.

#### D: Posso aggiungere immagini alle celle della tabella al posto del testo?

 A: Sì, puoi aggiungere immagini alle celle della tabella usando Aspose.PDF per .NET. Invece di creare un`TextFragment` oggetto, puoi creare un`Image` oggetto, caricare il file immagine e aggiungerlo alla cella desiderata utilizzando`cell.Paragraphs.Add(image);` metodo. Ciò consente di inserire immagini nella tabella insieme al contenuto di testo.