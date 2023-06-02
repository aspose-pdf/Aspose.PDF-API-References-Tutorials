---
title: Aggiungi tabella
linktitle: Aggiungi tabella
second_title: Aspose.PDF per riferimento API .NET
description: Aggiungi facilmente tabelle ai tuoi documenti PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 40
url: /it/net/programming-with-tables/add-table/
---

Aspose.PDF per .NET è una potente libreria che consente agli sviluppatori di creare, manipolare e trasformare documenti PDF in modo programmatico. In questo tutorial, ti guideremo attraverso il processo di aggiunta di una tabella a un documento PDF utilizzando Aspose.PDF per .NET. Spiegheremo ogni passaggio dello snippet di codice fornito e forniremo una guida completa per aiutarti a comprendere e implementare la funzionalità nei tuoi progetti.

## introduzione

I documenti PDF sono ampiamente utilizzati per condividere e conservare le informazioni in un formato portatile. L'aggiunta di tabelle ai documenti PDF può migliorarne l'aspetto visivo e rendere la presentazione dei dati più organizzata e strutturata. Aspose.PDF per .NET fornisce un modo conveniente per aggiungere tabelle ai documenti PDF esistenti o crearne di nuovi da zero.

## Cos'è Aspose.PDF per .NET?

Aspose.PDF per .NET è una libreria potente e ricca di funzionalità che consente agli sviluppatori .NET di creare, manipolare e convertire documenti PDF in modo programmatico. Fornisce una vasta gamma di funzionalità, tra cui la creazione di file PDF da zero, la modifica di documenti PDF esistenti, l'unione o la divisione di file PDF, l'aggiunta di testo, immagini e tabelle, l'estrazione di dati dai PDF e molto altro. Con Aspose.PDF per .NET, gli sviluppatori possono automatizzare complesse attività relative ai PDF e fornire soluzioni PDF di alta qualità.

## Aggiunta di una tabella a un documento PDF

Per aggiungere una tabella a un documento PDF utilizzando Aspose.PDF per .NET, segui la guida dettagliata di seguito:

## Passaggio 1: caricamento del documento PDF di origine

```csharp
string dataDir = RunExamples.GetDataDir_AsposePdf_Tables();
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "AddTable.pdf");
```

Lo snippet di codice sopra carica il documento PDF di origine a cui vuoi aggiungere la tabella. Assicurati di fornire il percorso corretto al tuo file PDF.

## Passaggio 2: inizializzazione di una nuova istanza della tabella

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

In questo passaggio creiamo una nuova istanza della classe Table, che rappresenta una tabella in un documento PDF.

## Passaggio 3: impostazione del colore del bordo della tabella

```csharp
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

Qui impostiamo il colore del bordo per la tabella usando la classe BorderInfo. Puoi personalizzare lo stile, la larghezza e il colore del bordo in base alle tue esigenze.

## Passaggio 4: impostazione del bordo per le celle della tabella

```csharp
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

Impostiamo anche il bordo per le celle della tabella utilizzando la proprietà DefaultCellBorder dell'oggetto tabella. Ciò garantisce che ogni cella della tabella abbia lo stile, la larghezza e il colore del bordo specificati.

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

In questo passaggio, creiamo un ciclo per aggiungere 10 righe alla tabella. All'interno di ogni riga, aggiungiamo tre celle con dati di esempio. È possibile modificare il codice per aggiungere righe e celle in base alle proprie esigenze specifiche.

## Passaggio 6: aggiunta dell'oggetto tabella al documento

```csharp
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "document_with_table_out.pdf";
// Salva il documento aggiornato contenente l'oggetto tabella
doc.Save(dataDir);
Console.WriteLine("\nText added successfully to an existing pdf file.\nFile saved at " + dataDir);       
```

Infine, aggiungiamo l'oggetto tabella alla prima pagina del documento PDF utilizzando la raccolta Paragrafi della pagina corrispondente.

### Esempio di codice sorgente per aggiungere una tabella utilizzando Aspose.Words per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Carica il documento PDF di origine
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "AddTable.pdf");
// Inizializza una nuova istanza di Table
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Imposta il colore del bordo della tabella come LightGray
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Imposta il bordo per le celle della tabella
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Crea un ciclo per aggiungere 10 righe
for (int row_count = 1; row_count < 10; row_count++)
{
	// Aggiungi riga alla tabella
	Aspose.Pdf.Row row = table.Rows.Add();
	// Aggiungi le celle della tabella
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

In questo tutorial, abbiamo spiegato il processo dettagliato di aggiunta di una tabella a un documento PDF utilizzando Aspose.PDF per .NET. Abbiamo coperto il caricamento del documento PDF di origine, l'inizializzazione di una nuova istanza della classe Table, l'impostazione del colore del bordo della tabella e dei bordi delle celle, l'aggiunta di righe e celle alla tabella e l'aggiunta dell'oggetto tabella al documento. Seguendo questa guida, puoi facilmente incorporare le tabelle nei tuoi documenti PDF in modo programmatico e personalizzarle in base alle tue esigenze specifiche.