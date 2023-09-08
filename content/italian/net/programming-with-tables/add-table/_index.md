---
title: Aggiungi tabella nel file PDF
linktitle: Aggiungi tabella nel file PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Aggiungi facilmente tabelle nel file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 40
url: /it/net/programming-with-tables/add-table/
---
Aspose.PDF per .NET è una potente libreria che consente agli sviluppatori di creare, manipolare e trasformare documenti PDF a livello di codice. In questo tutorial, ti guideremo attraverso il processo di aggiunta di una tabella nel file PDF utilizzando Aspose.PDF per .NET. Spiegheremo ogni passaggio dello snippet di codice fornito e forniremo una guida completa per aiutarti a comprendere e implementare la funzionalità nei tuoi progetti.

## introduzione

I documenti PDF sono ampiamente utilizzati per condividere e conservare informazioni in un formato portatile. L'aggiunta di tabelle ai documenti PDF può migliorarne l'aspetto visivo e rendere la presentazione dei dati più organizzata e strutturata. Aspose.PDF per .NET fornisce un modo conveniente per aggiungere tabelle a documenti PDF esistenti o crearne di nuovi da zero.

## Cos'è Aspose.PDF per .NET?

Aspose.PDF per .NET è una libreria potente e ricca di funzionalità che consente agli sviluppatori .NET di creare, manipolare e convertire documenti PDF a livello di codice. Fornisce un'ampia gamma di funzionalità, tra cui la creazione di file PDF da zero, la modifica di documenti PDF esistenti, l'unione o la divisione di file PDF, l'aggiunta di testo, immagini e tabelle, l'estrazione di dati dai PDF e molto altro. Con Aspose.PDF per .NET, gli sviluppatori possono automatizzare attività complesse relative ai PDF e fornire soluzioni PDF di alta qualità.

## Aggiunta di una tabella a un documento PDF

Per aggiungere una tabella a un documento PDF utilizzando Aspose.PDF per .NET, seguire la guida passo passo di seguito:

## Passaggio 1: caricamento del documento PDF di origine

```csharp
string dataDir = RunExamples.GetDataDir_AsposePdf_Tables();
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "AddTable.pdf");
```

Lo snippet di codice sopra carica il documento PDF di origine a cui desideri aggiungere la tabella. Assicurati di fornire il percorso corretto del tuo file PDF.

## Passaggio 2: inizializzazione di una nuova istanza della tabella

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

In questo passaggio creiamo una nuova istanza della classe Table, che rappresenta una tabella in un documento PDF.

## Passaggio 3: impostazione del colore del bordo della tabella

```csharp
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

Qui impostiamo il colore del bordo della tabella utilizzando la classe BorderInfo. Puoi personalizzare lo stile, la larghezza e il colore del bordo in base alle tue esigenze.

## Passaggio 4: impostazione del bordo per le celle della tabella

```csharp
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

Impostiamo anche il bordo per le celle della tabella utilizzando la proprietà DefaultCellBorder dell'oggetto tabella. Ciò garantisce che ogni cella nella tabella abbia lo stile, la larghezza e il colore del bordo specificati.

## Passaggio 5: aggiunta di righe e celle alla tabella

```csharp
for (int row_count = 1; row_count < 10; row_count++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row. Cells. Add("Column("+row_count+",1)");
   

  row. Cells. Add("Column("+row_count+",2)");
     row. Cells. Add("Column("+row_count+",3)");
}
```

In questo passaggio creiamo un ciclo per aggiungere 10 righe alla tabella. All'interno di ogni riga aggiungiamo tre celle con dati di esempio. Puoi modificare il codice per aggiungere righe e celle in base ai tuoi requisiti specifici.

## Passaggio 6: aggiunta dell'oggetto tabella al documento

```csharp
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "document_with_table_out.pdf";
// Salva il documento aggiornato contenente l'oggetto tabella
doc.Save(dataDir);
Console.WriteLine("\nText added successfully to an existing pdf file.\nFile saved at " + dataDir);       
```

Infine, aggiungiamo l'oggetto tabella alla prima pagina del documento PDF utilizzando la raccolta Paragraphs della pagina corrispondente.

### Codice sorgente di esempio per aggiungere tabella utilizzando Aspose.PDF per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Carica il documento PDF di origine
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "AddTable.pdf");
// Inizializza una nuova istanza della tabella
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Imposta il colore del bordo della tabella come Grigio chiaro
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Imposta il bordo per le celle della tabella
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Crea un ciclo per aggiungere 10 righe
for (int row_count = 1; row_count < 10; row_count++)
{
	// Aggiungi riga alla tabella
	Aspose.Pdf.Row row = table.Rows.Add();
	// Aggiungi celle alla tabella
	row.Cells.Add("Column (" + row_count + ", 1)");
	row.Cells.Add("Column (" + row_count + ", 2)");
	row.Cells.Add("Column (" + row_count + ", 3)");
}
// Aggiungi oggetto tabella alla prima pagina del documento di input
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "document_with_table_out.pdf";
// Salva il documento aggiornato contenente l'oggetto tabella
doc.Save(dataDir);

Console.WriteLine("\nText added successfully to an existing pdf file.\nFile saved at " + dataDir);       
```

## Conclusione

In questo tutorial, abbiamo spiegato il processo passo passo per aggiungere una tabella a un documento PDF utilizzando Aspose.PDF per .NET. Abbiamo trattato il caricamento del documento PDF di origine, l'inizializzazione di una nuova istanza della classe Table, l'impostazione del colore del bordo della tabella e dei bordi delle celle, l'aggiunta di righe e celle alla tabella e l'aggiunta dell'oggetto tabella al documento. Seguendo questa guida, puoi facilmente incorporare tabelle nei tuoi documenti PDF a livello di codice e personalizzarle in base alle tue esigenze specifiche.

### Domande frequenti per aggiungere una tabella nel file PDF

#### D: Posso aggiungere più colonne alla tabella?

R: Sì, puoi aggiungere più colonne alla tabella aumentando il numero di celle aggiunte a ciascuna riga. Nell'esempio fornito, ogni riga ha tre celle che rappresentano tre colonne. Puoi aggiungere più celle a ciascuna riga per aggiungere ulteriori colonne.

#### D: Come posso modificare l'aspetto della tabella, ad esempio la dimensione e lo stile del carattere?

 R: Puoi personalizzare l'aspetto della tabella, inclusa la dimensione e lo stile del carattere, impostando le proprietà sul file`Aspose.Pdf.Table` E`Aspose.Pdf.TextFragment` oggetti. Ad esempio, puoi impostare il file`DefaultCellTextState` proprietà per modificare le proprietà del carattere del testo nelle celle della tabella.

#### D: È possibile unire le celle nella tabella?

 R: Sì, puoi unire le celle nella tabella utilizzando il file`MergeCells` metodo del`Aspose.Pdf.Row` classe. Ciò ti consente di creare celle che si estendono su più righe e colonne.

#### D: Posso aggiungere immagini o altri contenuti alle celle della tabella?

R: Sì, puoi aggiungere vari tipi di contenuto alle celle della tabella, incluse immagini, testo, collegamenti ipertestuali e altro. È possibile utilizzare le classi appropriate da Aspose.PDF per .NET per aggiungere diversi tipi di contenuto alle celle.

#### D: Aspose.PDF per .NET è compatibile con .NET 5.0 o versioni successive?

R: Sì, Aspose.PDF per .NET è compatibile con .NET 5.0 e versioni successive. Supporta varie piattaforme .NET, tra cui .NET Framework, .NET Core e .NET 5.0+.